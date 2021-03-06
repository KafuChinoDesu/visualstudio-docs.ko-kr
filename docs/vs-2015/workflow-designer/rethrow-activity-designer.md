---
title: 다시 throw 활동 디자이너 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c65469242a60c64d6f31bfaea4fdbbf2d5251a34
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663364"
---
# <a name="rethrow-activity-designer"></a>Rethrow 활동 디자이너
다시 **throw** 활동 디자이너는 <xref:System.Activities.Statements.Rethrow> 활동을 만들고 구성 하는 데 사용 됩니다.

## <a name="the-rethrow-activity"></a>Rethrow 활동
 <xref:System.Activities.Statements.Rethrow> 활동은 이전에 throw된 예외를 throw합니다. 이 활동은 <xref:System.Activities.Statements.Catch> 활동의 <xref:System.Activities.Statements.TryCatch> 처리기에서만 사용할 수 있습니다.

### <a name="using-the-rethrow-activity-designer"></a>ReThrow 활동 디자이너 사용
 다시 **throw** 활동 디자이너는 **도구 상자**의 **오류 처리** 범주에 있습니다 .이 범주에 액세스 하려면 **[!INCLUDE[wfd2](../includes/wfd2-md.md)]의 왼쪽** 에 있는 **도구 상자** 탭을 클릭 하거나,  **보기** 메뉴 또는 CTRL + ALT + X.)

 다시 **throw** 활동 디자이너를 **도구 상자** 에서 끌어와 같이 일반적으로 활동을 <xref:System.Activities.Statements.Sequence> 배치 하는 아무 곳에 나 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 화면에 놓을 수 있습니다. 그러면 기본 **DisplayName** 인 Throw를 사용 하 여 <xref:System.Activities.Statements.Rethrow> 활동이 만들어집니다. 다시 **throw** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 값을 편집할 수 있습니다.

### <a name="the-rethrow-properties"></a>Rethrow 속성
 다음 표에서는 <xref:System.Activities.Statements.Rethrow> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.

|속성 이름|필요한 공간|사용 현황|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Rethrow> 활동의 선택적 이름을 지정합니다. 기본값은 Rethrow입니다.|

## <a name="see-also"></a>관련 항목:
 [컬렉션](../workflow-designer/collection-activity-designers.md) [Throw](../workflow-designer/throw-activity-designer.md) [TryCatch](../workflow-designer/trycatch-activity-designer.md)