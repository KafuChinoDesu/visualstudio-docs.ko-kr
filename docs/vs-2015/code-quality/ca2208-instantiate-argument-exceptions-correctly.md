---
title: 'CA2208: 인수 예외를 올바르게 인스턴스화 하십시오. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2208
- InstantiateArgumentExceptionsCorrectly
helpviewer_keywords:
- InstantiateArgumentExceptionsCorrectly
- CA2208
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 5b5e1525d1ee706f9cd46a58c022763d2ed234bf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662691"
---
# <a name="ca2208-instantiate-argument-exceptions-correctly"></a>CA2208: 인수 예외를 올바르게 인스턴스화하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|InstantiateArgumentExceptionsCorrectly|
|CheckId|CA2208|
|범주|Microsoft 사용|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 가능한 원인은 다음과 같습니다.

- 예외 형식의 기본 (매개 변수가 없는) 생성자를 호출 하거나 [ArgumentException] (<!-- TODO: review code entity reference <xref:assetId:///System.ArgumentException?qualifyHint=True&amp;autoUpgrade=True>  -->)를 사용하여 저장하는 값에 액세스할 수 있습니다.

- 잘못 된 문자열 인수가 이거나 [ArgumentException]에서 파생 된 예외 형식의 매개 변수가 있는 생성자에 전달 되었습니다. (<!-- TODO: review code entity reference <xref:assetId:///System.ArgumentException.?qualifyHint=True&amp;autoUpgrade=True>  -->)

## <a name="rule-description"></a>규칙 설명
 기본 생성자를 호출 하는 대신 보다 의미 있는 예외 메시지를 제공할 수 있도록 하는 생성자 오버 로드 중 하나를 호출 합니다. 예외 메시지는 개발자를 대상으로 하며 오류 조건 및 예외를 해결 하거나 방지 하는 방법을 명확 하 게 설명 해야 합니다.

 @No__t_0의 한 문자열 생성자와 해당 파생 형식의 시그니처는 `message` 및 `paramName` 매개 변수와 일치 하지 않습니다. 올바른 문자열 인수를 사용 하 여 이러한 생성자가 호출 되었는지 확인 합니다. 시그니처는 다음과 같습니다.

 <xref:System.ArgumentException> (문자열 `message`)

 <xref:System.ArgumentException> (문자열 `message`, 문자열 `paramName`)

 <xref:System.ArgumentNullException> (문자열 `paramName`)

 <xref:System.ArgumentNullException> (문자열 `paramName`, 문자열 `message`)

 <xref:System.ArgumentOutOfRangeException> (문자열 `paramName`)

 <xref:System.ArgumentOutOfRangeException> (문자열 `paramName`, 문자열 `message`)

 <xref:System.DuplicateWaitObjectException> (문자열 `parameterName`)

 <xref:System.DuplicateWaitObjectException> (문자열 `parameterName`, 문자열 `message`)

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메시지, 매개 변수 이름 또는 두 가지를 모두 사용 하는 생성자를 호출 하 고 호출 되는 <xref:System.ArgumentException> 형식에 대해 인수가 적절 한지 확인 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 올바른 문자열 인수를 사용 하 여 매개 변수가 있는 생성자를 호출 하는 경우에만이 규칙에서 경고를 표시 하는 것이 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 ArgumentNullException 형식의 인스턴스를 잘못 인스턴스화하는 생성자를 보여 줍니다.

 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cpp/FxCop.Usage.InheritedPublic.cpp#1)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cs/FxCop.Usage.InheritedPublic.cs#1)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/vb/FxCop.Usage.InstantiateArgumentExceptionsCorrectly.vb#1)]

## <a name="example"></a>예제
 다음 예제에서는 생성자 인수를 전환 하 여 위의 위반을 수정 합니다.

 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cpp/FxCop.Usage.InheritedPublic.cpp#2)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cs/FxCop.Usage.InheritedPublic.cs#2)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/vb/FxCop.Usage.InstantiateArgumentExceptionsCorrectly.vb#2)]
