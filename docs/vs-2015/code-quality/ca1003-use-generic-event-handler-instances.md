---
title: 'CA1003: 제네릭 이벤트 처리기 인스턴스 사용 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 34318d3fb01f3f8dee50da2bc534908cecbdaf32
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72646293"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하세요.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|범주|Microsoft 디자인|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식에는 void를 반환 하는 대리자가 포함 됩니다. 해당 시그니처에는 두 개의 매개 변수 (첫 번째 개체와 EventArgs에 할당할 수 있는 두 번째 형식)와 포함 하는 어셈블리 대상 [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] 포함 됩니다.

## <a name="rule-description"></a>규칙 설명
 @No__t_0 하기 전에 이벤트 처리기에 사용자 지정 정보를 전달 하기 위해 <xref:System.EventArgs?displayProperty=fullName> 클래스에서 파생 된 클래스를 지정 하는 새 대리자를 선언 해야 했습니다. 이는 <xref:System.EventHandler%601?displayProperty=fullName> 대리자를 도입 하는 [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)]에 더 이상 적용 되지 않습니다. 이 제네릭 대리자를 사용 하면 <xref:System.EventArgs>에서 파생 된 모든 클래스를 이벤트 처리기와 함께 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 대리자를 제거 하 고 <xref:System.EventHandler%601?displayProperty=fullName> 대리자를 사용 하 여 사용을 바꿉니다. 대리자가 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 컴파일러에 의해 자동으로 생성 되는 경우 <xref:System.EventHandler%601?displayProperty=fullName> 대리자를 사용 하도록 이벤트 선언 구문을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 대리자를 보여 줍니다. @No__t_0 예제에서 주석은 규칙을 충족 하도록 예제를 수정 하는 방법을 설명 합니다. C# 예제에서 수정 된 코드를 보여 주는 예제는 다음과 같습니다.

 [!code-csharp[FxCop.Design.CustomEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/cs/FxCop.Design.CustomEventHandler.cs#1)]
 [!code-vb[FxCop.Design.CustomEventHandler#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/vb/FxCop.Design.CustomEventHandler.vb#1)]

## <a name="example"></a>예제
 다음 예제에서는 규칙을 충족 하는 이전 예제에서 대리자 선언을 제거 하 고 <xref:System.EventHandler%601?displayProperty=fullName> 대리자를 사용 하 여 `ClassThatRaisesEvent` 및 `ClassThatHandlesEvent` 메서드의 사용을 대체 합니다.

 [!code-csharp[FxCop.Design.GenericEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.GenericEventHandler/cs/FxCop.Design.GenericEventHandler.cs#1)]

## <a name="related-rules"></a>관련 규칙
 [CA1005: 제네릭 형식의 매개 변수를 과도 하 게 사용 하지 않습니다 ](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: 컬렉션은 제네릭 인터페이스를 구현 해야 ](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: 정적 멤버를 제네릭 형식으로 선언 하지 마세요 ](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: 제네릭 목록을 노출 하지 않습니다 ](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마세요 ](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공 해야 ](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1007: 적절 한 ](../code-quality/ca1007-use-generics-where-appropriate.md) 제네릭을 사용 합니다.

## <a name="see-also"></a>관련 항목:
 [제네릭](https://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)
