---
title: 'CA2136: 멤버는 충돌 하는 투명도 주석을 포함 하지 않아야 합니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f2fbb856ff53552ab99dabd4f650e9fd7f62a088
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72602976"
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: 멤버는 충돌하는 투명도 주석을 가져서는 안 됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 이 규칙은 형식 멤버가 멤버 컨테이너의 보안 특성과 투명도가 다른 <xref:System.Security> 보안 특성으로 표시 될 때 발생 합니다.

## <a name="rule-description"></a>규칙 설명
 투명성 특성은 큰 범위의 코드 요소에서 작은 범위의 요소에 적용됩니다. 범위가 큰 코드 요소의 투명성 특성은 첫 번째 요소에 포함된 코드 요소의 투명성 특성보다 우선합니다. 예를 들어 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 된 클래스에는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 된 메서드가 포함 될 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 위반 문제를 해결 하려면 범위가 낮은 코드 요소에서 보안 특성을 제거 하거나 해당 특성을 포함 하는 코드 요소와 동일 하 게 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 표시 하지 않습니다.

## <a name="example"></a>예제
 다음 예제에서 메서드는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 되며 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 된 클래스의 멤버입니다. 보안 안전 특성을 제거 해야 합니다.

 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2136.transparencyannotationsshouldnotconflict/cs/ca2136 - transparencyannotationsshouldnotconflict.cs#1)]
