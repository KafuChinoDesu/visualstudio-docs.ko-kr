---
title: RemoveFromCollection &lt;T &gt; Activity Designer | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ac088c6e5710fcd1b7c401402ad473488f89524
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672570"
---
# <a name="removefromcollectionlttgt-activity-designer"></a>RemoveFromCollection &lt;T &gt; Activity Designer
**RemoveFromCollection \<T >** activity designer는 <xref:System.Activities.Statements.RemoveFromCollection%601> 작업을 만들고 구성 하는 데 사용 됩니다.

## <a name="the-removefromcollectiont-activity"></a>RemoveFromCollection \<T > 활동
 <xref:System.Activities.Statements.RemoveFromCollection%601> 활동은 지정한 항목을 특정 컬렉션에서 제거합니다.

### <a name="using-the-removefromcollectiont-activity-designer"></a>RemoveFromCollection \<T > 활동 디자이너 사용
 **RemoveFromCollection \<T >** 활동 디자이너는 **도구 상자**의 **컬렉션** 범주에 있습니다 .이 범주에 액세스 하려면 [!INCLUDE[wfd2](../includes/wfd2-md.md)]에서 도구 **상자** 탭을 클릭 하거나에서 **도구 모음** 을 선택 합니다. **보기** 메뉴 또는 CTRL + ALT + X.)

 **RemoveFromCollection \<T >** 활동 디자이너를 **도구 상자** 에서 끌어다 <xref:System.Activities.Statements.Sequence> 내 등 일반적으로 활동을 배치 하는 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 화면에 놓을 수 있습니다. 그러면 기본 <xref:System.Activities.Activity.DisplayName%2A> RemoveFromCollection \<Int32 > <xref:System.Activities.Statements.RemoveFromCollection%601> 활동이 만들어집니다. @No__t_0 값은 **RemoveFromCollection \<T >** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 편집할 수 있습니다. 다른 속성은 속성 표에서 편집해야 합니다.

### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection \<T > 속성
 다음 표에서는 <xref:System.Activities.Statements.RemoveFromCollection%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|사용법|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.RemoveFromCollection%601> 활동의 선택적 이름입니다. 기본값은 RemoveFromCollection \<Int32 >입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|True|컬렉션에 추가할 항목 **\<T >** 입니다. 이 항목은 유형 *T*이며 *typeargument*유형입니다. 이 항목을 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|True|항목이 추가될 컬렉션입니다. 이 컬렉션은 **ICollection \<TypeArgument >** 형식입니다. 컬렉션을 지정 하려면 속성 표에 Visual Basic 식을 입력 합니다.|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601>에 포함된 항목의 형식 T입니다. 기본적으로이 형식 *인수* 형식은 **Int32**로 설정 됩니다. 형식을 변경 하려면 속성 표의 콤보 상자에서 *Typeargument* 의 값을 변경 합니다.|
|<xref:System.Activities.Activity%601.Result%2A>|False|지정된 항목이 컬렉션에서 제거되었는지 여부를 나타내는 값입니다. 결과에 바인딩할 변수를 지정하려면 속성 표에 변수를 입력합니다.|

## <a name="see-also"></a>관련 항목:
 [컬렉션](../workflow-designer/collection-activity-designers.md) [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md) [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md) [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)