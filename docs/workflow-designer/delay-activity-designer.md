---
title: 워크플로 디자이너-Delay 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5190807bba08f05e176acc15ac8daf42ac028c50
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650542"
---
# <a name="delay-activity-designer"></a>Delay 활동 디자이너

**Delay** 활동 디자이너는 <xref:System.Activities.Statements.Delay> 활동을 만들고 구성 하는 데 사용 됩니다.

## <a name="the-delay-activity"></a>Delay 작업

<xref:System.Activities.Statements.Delay> 활동은 지정된 시간 동안 워크플로 실행을 지연시킵니다.

### <a name="use-the-delay-activity-designer"></a>Delay 활동 디자이너 사용

**Delay** 활동 디자이너는 **도구**상자의 **기본 형식** 범주에서 찾을 수 있습니다 .이 범주에 액세스 하려면 워크플로 디자이너의 **도구 상자** 탭을 클릭 합니다. 또는 **보기** 메뉴에서 **도구 상자** 를 선택 하거나 **ctrl** +**alt** +**X**를 누릅니다.

**Delay** 활동 디자이너를 **도구 상자** 에서 끌어와 같이 일반적으로 활동을 <xref:System.Activities.Statements.Sequence> 배치 하는 워크플로 디자이너 화면에 놓을 수 있습니다. 활동 디자이너를 삭제 하면 기본 <xref:System.Activities.Activity.DisplayName%2A> 지연 시간을 사용 하 여 <xref:System.Activities.Statements.Delay> 활동이 만들어집니다. **지연** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 편집할 수 있습니다.

### <a name="the-delay-properties"></a>Delay 속성

다음 표에서는 <xref:System.Activities.Statements.Delay> 속성을 보여 주고 디자이너에서 이러한 속성을 사용 하는 방법을 설명 합니다. 이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 워크플로 디자이너 화면에서 편집할 수 있습니다.

|속성 이름|필요한 공간|사용 현황|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Delay> 활동의 이름입니다. 기본값은 Delay입니다. @No__t_0 값이 반드시 필요한 것은 아니지만 사용 하는 것이 좋습니다.|
|<xref:System.Activities.Statements.Delay.Duration%2A>|True|워크플로를 지연할 시간입니다. 이 속성은 속성 표에서 설정합니다. 리터럴 <xref:System.TimeSpan>을 00:00:00 형식으로 입력하거나 Visual Basic 식을 입력하여 시간을 지정합니다.|

## <a name="see-also"></a>참조

- [Primitives](../workflow-designer/primitives-activity-designers.md)
- [Assign](../workflow-designer/assign-activity-designer.md)
- [Delay 활동 디자이너](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)