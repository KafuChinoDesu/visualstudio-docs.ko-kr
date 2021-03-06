---
title: 상관 관계 초기화 대화 상자 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ab913027a6a992494dad609b98ab11dbc6ae61c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72659046"
---
# <a name="initialize-correlation-dialog-box"></a>상관 관계 초기화 대화 상자
**상관 관계 초기화** 대화 상자는 [!INCLUDE[wfd1](../includes/wfd1-md.md)]에서 <xref:System.ServiceModel.Activities.InitializeCorrelation> 작업의 <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> 속성을 편집 하는 데 사용 됩니다. [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md) 항목을 [!INCLUDE[crdefault](../includes/crdefault-md.md)] 합니다.

 다음 표에서는 **상관 관계 초기화** 대화 상자의 UI (사용자 인터페이스) 요소에 대해 설명 합니다.

|UI 요소|설명|
|----------------|-----------------|
|**상관 관계**|초기화할 상관 관계의 <xref:System.ServiceModel.Activities.CorrelationHandle>입니다.|
|**초기화 설정**|초기화할 데이터가 포함된 키/값 쌍입니다. 이것은 <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> 속성에 해당합니다. 유효한 키/값 쌍의 예로 "OrderID" 키와 OrderID 변수의 쌍이 있습니다.|

## <a name="to-launch-the-initialize-correlation-dialog-box"></a>상관 관계 초기화 대화 상자를 시작하려면

- **InitializeCorrelation** 활동 디자이너에서 **보기** 를 클릭 하거나 [!INCLUDE[wfd2](../includes/wfd2-md.md)]에서 <xref:System.ServiceModel.Activities.InitializeCorrelation> 활동을 선택한 다음 속성 표에서 <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> 속성 옆에 있는 줄임표 단추를 클릭 합니다.

## <a name="see-also"></a>관련 항목:
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)