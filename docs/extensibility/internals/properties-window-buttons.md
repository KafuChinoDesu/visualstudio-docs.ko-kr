---
title: 속성 창 단추 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3f2a41917a58a6fc5780b62c2c9e3db8aa52d407
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725267"
---
# <a name="properties-window-buttons"></a>속성 창 단추
개발 언어와 제품 유형에 따라 **속성** 창의 도구 모음에는 기본적으로 특정 단추가 표시 됩니다. 모든 경우에는 **항목별**, **사전순**, **속성**및 **속성 페이지** 단추가 표시 됩니다. 시각적 개체 C# 와 Visual Basic에도 **이벤트** 단추가 표시 됩니다. 특정 Visual C++ 프로젝트에서 **Vc + + 메시지** 와 **vc 재정의** 단추가 표시 됩니다. 다른 프로젝트 형식에 대 한 추가 단추가 표시 될 수 있습니다. **속성** 창에 있는 단추에 대 한 자세한 내용은 [속성 창](../../ide/reference/properties-window.md)을 참조 하세요.

## <a name="implementation-of-properties-window-buttons"></a>속성 창 단추 구현
 **항목별** 단추를 클릭 하면 Visual Studio에서 포커스가 있는 개체의 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> 인터페이스를 호출 하 여 해당 속성을 범주별로 정렬 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>은 **속성** 창에 표시 되는 `IDispatch` 개체에서 구현 됩니다.

 음수 값을 포함 하는 미리 정의 된 속성 범주가 11 개 있습니다. 사용자 지정 범주를 정의할 수 있지만 미리 정의 된 범주와 구분 하기 위해 양수 값을 할당 하는 것이 좋습니다.

 @No__t_0 메서드는 지정 된 속성에 대 한 적절 한 속성 범주 값을 반환 합니다. @No__t_0 메서드는 범주 이름을 포함 하는 문자열을 반환 합니다. Visual Studio에서 표준 속성 범주 값을 알고 있으므로 사용자 지정 범주 값에 대 한 지원도 제공 해야 합니다.

 **사전순** 단추를 클릭 하면 속성은 이름별로 사전순으로 표시 됩니다. 이름은 지역화 된 정렬 알고리즘에 따라 `IDispatch`에 의해 검색 됩니다.

 **속성** 창이 열려 있으면 **속성** 단추가 자동으로 선택 된 것으로 표시 됩니다. 환경의 다른 부분에는 동일한 단추가 표시 되 고 클릭 하 여 **속성** 창을 표시할 수 있습니다.

 선택한 개체에 대해 `ISpecifyPropertyPages`을 구현 하지 않으면 **속성 페이지** 단추를 사용할 수 없습니다. 속성 페이지는 일반적으로 솔루션 및 프로젝트와 연결 되는 구성 종속 속성을 표시 하지만, 프로젝트 항목 (예: 시각적 개체 C++)에도 연결 될 수 있습니다.

> [!NOTE]
> 비관리 코드를 사용 하 여 **속성** 창에 도구 모음 단추를 추가할 수는 없습니다. 도구 모음 단추를 추가 하려면 <xref:System.Windows.Forms.Design.PropertyTab>에서 파생 되는 관리 되는 개체를 만들어야 합니다.

## <a name="see-also"></a>참조
- [속성 확장](../../extensibility/internals/extending-properties.md)