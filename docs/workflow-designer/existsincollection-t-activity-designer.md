---
title: 워크플로 디자이너-ExistsInCollection &lt;T &gt; Activity Designer
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ExistsInCollection`1.UI
ms.assetid: 0acf9a13-caf5-4bb4-ba22-ec37d2b7267a
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a9dc1f6a3694b6164fe4f2187fa4c6e2b42751e7
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650482"
---
# <a name="existsincollectiont-activity-designer"></a>ExistsInCollection \<T > Activity Designer

**ExistsInCollection \<T >** activity designer는 <xref:System.Activities.Statements.ExistsInCollection%601> 작업을 만들고 구성 하는 데 사용 됩니다.

## <a name="the-existsincollectiont-activity"></a>ExistsInCollection \<T > 활동

<xref:System.Activities.Statements.ExistsInCollection%601> 활동은 지정된 항목이 특정 컬렉션에 있는지 여부를 결정합니다.

### <a name="using-the-existsincollectiont-activity-designer"></a>ExistsInCollection \<T > 활동 디자이너 사용

**ExistsInCollection \<T >** 활동 디자이너는 **도구 상자**의 **컬렉션** 범주에 있습니다 .이 범주에 액세스 하려면 워크플로 디자이너의 **도구 상자** 탭을 클릭 합니다. 또는 **보기** 메뉴에서 **도구 상자** 를 선택 하거나 **ctrl** +**alt** +**X**를 누릅니다.

**ExistsInCollection \<T >** 활동 디자이너를 **도구 상자** 에서 끌어다 <xref:System.Activities.Statements.Sequence> 내 등 일반적으로 활동을 배치 하는 워크플로 디자이너 화면에 놓을 수 있습니다. 이렇게 하면 기본 <xref:System.Activities.Activity.DisplayName%2A> ExistsInCollection < Int32 \>의 <xref:System.Activities.Statements.ExistsInCollection%601> 활동이 만들어집니다. 기본적으로 *Typeargument* 는 **Int32**입니다. 속성 표에서이를 변경할 수 있습니다.  **ExistsInCollection < t \>** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 값을 편집할 수 있습니다. 다른 속성은 속성 표에서 편집해야 합니다.

### <a name="the-existsincollectiont-properties"></a>ExistsInCollection \<T > 속성

다음 표에서는 <xref:System.Activities.Statements.ExistsInCollection%601> 속성을 보여 주고 디자이너에서 이러한 속성을 사용 하는 방법을 설명 합니다.

|속성 이름|필요한 공간|사용 현황|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ExistsInCollection%601> 활동의 이름입니다. 기본값은 ExistsInCollection < Int32 \>입니다. <xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.ExistsInCollection%601.Item%2A>|True|컬렉션에서 찾을 항목 \<T >입니다. 이 항목은 유형 *T*이며 *typeargument*유형입니다. 이 항목을 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|
|<xref:System.Activities.Statements.ExistsInCollection%601.Collection%2A>|True|항목이 있는지 확인할 컬렉션입니다. 이 컬렉션은 **ICollection < TypeArgument 형식 \>입니다.** 컬렉션을 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601>에 포함된 항목의 형식 T입니다. 기본적으로이 형식 *인수* 형식은 **Int32**로 설정 됩니다. 형식을 변경 하려면 속성 표의 콤보 상자에서 *Typeargument* 의 값을 변경 합니다.|
|<xref:System.Activities.Activity%601.Result%2A>|False|지정된 항목이 컬렉션에 있는지 여부를 나타내는 값입니다. 결과에 바인딩할 변수를 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|

## <a name="see-also"></a>참조

- [수집](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)