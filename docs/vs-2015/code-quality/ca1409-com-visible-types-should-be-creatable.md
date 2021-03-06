---
title: 'CA1409: Com 노출 형식을 만들 수 있어야 합니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: feb50f576fbff656acaa10b70bb4d8adbca1d6c3
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72602385"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: COM 노출 형식을 만들 수 있어야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ComVisibleTypesShouldBeCreatable|
|CheckId|CA1409|
|범주|Microsoft.Interoperability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 COM (구성 요소 개체 모델)에 표시 되는 것으로 특별히 표시 된 참조 형식에 매개 변수가 있는 공용 생성자가 포함 되어 있지만 매개 변수가 없는 공용 생성자가 포함 되어 있지 않습니다.

## <a name="rule-description"></a>규칙 설명
 COM 클라이언트는 공용 기본 생성자가 없는 형식을 만들 수 없습니다. 그러나 형식을 만들어 클라이언트에 전달 (예: 메서드 호출의 반환 값을 통해) 할 수 있는 다른 방법이 있으면 COM 클라이언트에서 해당 형식을 계속 액세스할 수 있습니다.

 규칙은 <xref:System.Delegate?displayProperty=fullName>에서 파생 된 형식을 무시 합니다.

 기본적으로 다음은 COM에 표시 됩니다. 어셈블리, public 형식, public 형식의 공용 인스턴스 멤버 및 public 값 형식의 모든 멤버입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 공용 기본 생성자를 추가 하거나 형식에서 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 개체를 만들어 COM 클라이언트에 전달 하는 다른 방법이 제공 되는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="related-rules"></a>관련 규칙
 [CA1017: 어셈블리를 ComVisibleAttribute로 표시하십시오.](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>관련 항목:
 [비관리 코드와](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258) [상호 운용 하기 위해 .net 형식의 정규화](https://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)
