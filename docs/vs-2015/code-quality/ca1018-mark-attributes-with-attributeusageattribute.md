---
title: 'CA1018: AttributeUsageAttribute를 사용 하 여 특성 표시 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 404ef250726d12300e2b72150ff42b4f0b7bfb24
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662045"
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018: 특성을 AttributeUsageAttribute로 표시하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAttributesWithAttributeUsage|
|CheckId|CA1018|
|범주|Microsoft 디자인|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 @No__t_0 특성이 사용자 지정 특성에 없습니다.

## <a name="rule-description"></a>규칙 설명
 사용자 지정 특성을 정의 하는 경우 사용자 지정 특성을 적용할 수 있는 소스 코드의 위치를 나타내기 위해 <xref:System.AttributeUsageAttribute>를 사용 하 여 표시 합니다. 특성의 의미 및 용도에 따라 코드에서의 유효한 위치가 결정됩니다. 예를 들어 라이브러리에서 각 형식을 유지 관리 하 고 개선할 책임이 있는 사용자를 식별 하는 특성을 정의할 수 있으며 해당 책임은 항상 형식 수준에서 할당 됩니다. 이 경우 컴파일러는 클래스, 열거형 및 인터페이스에서 특성을 사용 하도록 설정 해야 하지만 메서드, 이벤트 또는 속성에 대해 사용 하도록 설정 하면 안 됩니다. 조직 정책 및 절차에서는 어셈블리에 대 한 특성을 사용할지 여부를 결정 합니다.

 @No__t_0 열거형은 사용자 지정 특성에 대해 지정할 수 있는 대상을 정의 합니다. @No__t_0를 생략 하는 경우 <xref:System.AttributeTargets> 열거의 `All` 값에 정의 된 대로 모든 대상에 대해 사용자 지정 특성을 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 <xref:System.AttributeUsageAttribute>를 사용 하 여 특성의 대상을 지정 합니다. 다음 예제를 참조하세요.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 메시지를 제외 하는 대신이 규칙 위반 문제를 해결 해야 합니다. 특성이 <xref:System.AttributeUsageAttribute> 상속 하는 경우에도 특성을 제공 하 여 코드 유지 관리를 간소화 해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 두 개의 특성을 정의 합니다. `BadCodeMaintainerAttribute`에서 <xref:System.AttributeUsageAttribute> 문을 잘못 생략 하 고 `GoodCodeMaintainerAttribute`이 섹션의 앞부분에서 설명한 특성을 올바르게 구현 합니다. 속성 `DeveloperName`는 [특성 인수에 대 한 디자인 규칙 CA1019: Define 접근자](../code-quality/ca1019-define-accessors-for-attribute-arguments.md) 에 필요 하며 완전성을 위해 포함 되었습니다.

 [!code-csharp[FxCop.Design.AttributeUsage#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeUsage/cs/FxCop.Design.AttributeUsage.cs#1)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeUsage/vb/FxCop.Design.AttributeUsage.vb#1)]

## <a name="related-rules"></a>관련 규칙
 [CA1019: 특성 인수의 접근자를 정의하십시오.](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1813: 봉인되지 않은 특성을 사용하지 마십시오.](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>관련 항목:
 [특성](https://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b)
