---
title: 'CA2145: 투명 한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅 해서는 안 됩니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6bffa680fa39014ffa96feec997b5eca63ee08ff
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72610216"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145: 투명한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅해서는 안 됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|
|CheckId|CA2145|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 투명 한 메서드, <xref:System.Security.SecuritySafeCriticalAttribute> 메서드로 표시 된 메서드 또는 메서드를 포함 하는 형식이 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 표시 됩니다.

## <a name="rule-description"></a>규칙 설명
 @No__t_0 특성을 사용 하 여 데코레이팅된 메서드에는 호출 하는 메서드에 대 한 암시적 LinkDemand가 배치 됩니다. 이 LinkDemand는 호출 코드가 보안을 중요시 하도록 요구합니다. SuppressUnmanagedCodeSecurity를 사용 하는 메서드를 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 하면이 요구 사항이 메서드 호출자에 게 더 명확 하 게 표시 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드 또는 형식을 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2145.transparentmethodsshouldnotusesuppressunmanagedcodesecurity/cs/ca2145.cs#1)]

### <a name="comments"></a>주석
