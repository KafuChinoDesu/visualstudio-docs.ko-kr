---
title: 워크플로 디자이너-CorrelatesOn 정의 대화 상자
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 401f72f55f23779f7c6257437034a4ebc294d219
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650593"
---
# <a name="correlateson-definition-dialog-box"></a>CorrelatesOn 정의 대화 상자

**CorrelatesOn** 대화 상자는 워크플로 디자이너에서 <xref:System.ServiceModel.Activities.Receive> 작업의 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> 속성을 편집 하는 데 사용 됩니다. 자세한 내용은 [Receive Activity Designer](../workflow-designer/receive-activity-designer.md)를 참조 하세요.

<xref:System.ServiceModel.Activities.Receive> 활동 간의 상관 관계는 워크플로에서 서비스 작업 간의 다양한 상호 연결 방식을 지정합니다.

다음 표에서는 **CorrelatesOn** 대화 상자의 UI (사용자 인터페이스) 요소에 대해 설명 합니다.

|UI 요소|설명|
|-|-----------------|
|**CorrelatesWith**|메시지를 적절한 워크플로 인스턴스로 라우팅하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>입니다.|
|**XPath 쿼리**|받은 메시지에서 상관 관계 데이터를 추출하는 데 사용되는 쿼리가 포함된 키/값 쌍입니다. 이 값은 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> 속성에 해당 합니다. XPath 쿼리는 <xref:System.ServiceModel.MessageQuerySet> 개체에 포함되어 있습니다.|

## <a name="to-launch-the-correlateson-dialog-box"></a>CorrelatesOn 대화 상자를 시작하려면

활동은 일반적으로 활동을 배치 **하는 위치** 에 관계 없이 **도구 상자** 에서 끌어서 워크플로 디자이너 화면에 놓을 수 있습니다. 활동 디자이너를 삭제 하면 기본 <xref:System.Activities.Activity.DisplayName%2A> Receive를 사용 하는 <xref:System.ServiceModel.Activities.Receive> 활동이 만들어집니다. **CorrelatesOn 정의** 대화 상자를 열려면 **Receive** 활동 디자이너를 선택한 다음 속성 표에서 **CorrelatesOn** 속성에 대 한 컬렉션 텍스트 옆에 있는 줄임표 단추를 선택 합니다.

## <a name="see-also"></a>참조

- <xref:System.ServiceModel.Activities.Receive>
- [상관 관계 이니셜라이저 추가 대화 상자](../workflow-designer/add-correlationinitializers-dialog-box.md)
- [상관 관계 초기화 대화 상자](../workflow-designer/initialize-correlation-dialog-box.md)