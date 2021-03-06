---
title: 'CA2004: GC에 대 한 호출을 제거 합니다. KeepAlive | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e34a8e7d4860a599155554410e13df5a6eb3bfe1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672488"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: GC.KeepAlive에 대한 호출을 제거하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|범주|Microsoft.Reliability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 클래스가 `SafeHandle`를 사용 하지만 `GC.KeepAlive`에 대 한 호출을 계속 포함 합니다.

## <a name="rule-description"></a>규칙 설명
 @No__t_0 사용으로 변환 하는 경우 `GC.KeepAlive` (개체)에 대 한 모든 호출을 제거 합니다. 이 경우 클래스는 종료 자가 없지만 `SafeHandle`를 사용 하 여이에 대 한 OS 핸들을 완료 한다고 가정 하 고 `GC.KeepAlive`를 호출할 필요가 없습니다.  @No__t_0에 대 한 호출을 종료 하는 비용은 성능으로 측정 되는 것 보다 무시할 수 있지만, `GC.KeepAlive`에 대 한 호출이 더 이상 존재 하지 않는 수명 문제를 해결 하는 데 필요 하거나 코드를 유지 관리 하기가 더 어려워질 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 @No__t_0에 대 한 호출을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 클래스에서 `SafeHandle` 사용으로 변환 하기 위해 기술적으로 정확 하지 않은 경우에만이 경고를 표시 하지 않을 수 있습니다.
