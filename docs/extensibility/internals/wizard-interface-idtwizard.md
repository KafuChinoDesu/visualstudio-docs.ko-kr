---
title: 마법사 인터페이스 (IDTWizard) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f571fbd0a68ddbf56b637071ac250159461f61d1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721537"
---
# <a name="wizard-interface-idtwizard"></a>마법사 인터페이스(IDTWizard)
IDE (통합 개발 환경)는 <xref:EnvDTE.IDTWizard> 인터페이스를 사용 하 여 마법사와 통신 합니다. 마법사는 IDE에 설치 하기 위해이 인터페이스를 구현 해야 합니다.

 @No__t_0 메서드는 <xref:EnvDTE.IDTWizard> 인터페이스와 연결 된 유일한 메서드입니다. 마법사는이 메서드를 구현 하 고 IDE는 인터페이스에서 메서드를 호출 합니다. 다음 예제에서는 메서드의 서명을 보여 줍니다.

```
/* IDTWizard Method */
STDMETHOD(Execute)(THIS_
   /* [in] */ IDispatch *Application,
   /* [in] */ long hwndOwner,
   /* [in] */ SAFEARRAY * *ContextParams,
   /* [in] */ SAFEARRAY * *CustomParams,
   /* [out] [in] */ wizardResult *RetVal
   );
```

 시작 메커니즘은 **새 프로젝트** 및 **새 항목 추가** 마법사와 유사 합니다. 시작 하려면 다음을 실행 합니다. <xref:EnvDTE.IDTWizard> 인터페이스를 호출 합니다. 유일한 차이점은 인터페이스가 호출 될 때 인터페이스에 전달 되는 컨텍스트 및 사용자 지정 매개 변수 집합입니다.

 다음 정보는 마법사가 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에서 작업 하기 위해 구현 해야 하는 <xref:EnvDTE.IDTWizard> 인터페이스에 대해 설명 합니다. IDE는 마법사에서 <xref:EnvDTE.IDTWizard.Execute%2A> 메서드를 호출 하 여 다음을 전달 합니다.

- DTE 개체입니다.

     DTE 개체는 자동화 모델의 루트입니다.

- @No__t_0 코드 세그먼트에 표시 된 창 대화 상자에 대 한 핸들입니다.

     마법사는이 `hwndOwner`를 마법사 대화 상자의 부모로 사용 합니다.

- 코드 세그먼트에 표시 된 것 처럼 인터페이스에 SAFEARRAY에 대 한 variant로 전달 된 컨텍스트 매개 변수 `[in] SAFEARRAY (VARIANT)* ContextParams`입니다.

     컨텍스트 매개 변수에는 시작 되는 마법사의 종류 및 프로젝트의 현재 상태와 관련 된 값의 배열이 포함 됩니다. IDE는 컨텍스트 매개 변수를 마법사에 전달 합니다. 자세한 내용은 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)를 참조 하세요.

- 코드 세그먼트에 표시 된 것 처럼 인터페이스에 SAFEARRAY에 대 한 variant로 전달 된 사용자 지정 매개 변수 `[in] SAFEARRAY (VARIANT)* CustomParams`입니다.

     사용자 지정 매개 변수는 사용자 정의 매개 변수의 배열을 포함 합니다. .Vsz 파일은 사용자 지정 매개 변수를 IDE에 전달 합니다. 값은 `Param=` 문에 의해 결정 됩니다. 자세한 내용은 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)를 참조 하세요.

- 인터페이스에 대 한 반환 값은

    ```
    wizardResultSuccess = -1,
    wizardResultFailure = 0
    wizardResultCancel = 1
    wizardResultBackout = 2
    ```

## <a name="see-also"></a>참조
- [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)
- [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)
- [마법사](../../extensibility/internals/wizards.md)
- [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)