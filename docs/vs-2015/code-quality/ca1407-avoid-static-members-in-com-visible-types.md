---
title: 'CA1407: COM 노출 형식에 정적 멤버를 사용 하지 마십시오. Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
caps.latest.revision: 25
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6996d210417a56dd83532c481aaa0dc80b9f23ea
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72655241"
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidStaticMembersInComVisibleTypes|
|CheckId|CA1407|
|범주|Microsoft.Interoperability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 COM (구성 요소 개체 모델)에 표시 되도록 특별히 표시 된 형식에 `public``static` 메서드가 포함 되어 있습니다.

## <a name="rule-description"></a>규칙 설명
 COM은 `static` 메서드를 지원 하지 않습니다.

 이 규칙은 속성 및 이벤트 접근자, 연산자 오버 로드 메서드 또는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 특성 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성을 사용 하 여 표시 된 메서드를 무시 합니다.

 기본적으로 다음은 COM에 표시 됩니다. 어셈블리, public 형식, public 형식의 공용 인스턴스 멤버 및 public 값 형식의 모든 멤버입니다.

 이 규칙이 발생 하려면 다음 코드에 나와 있는 것 처럼 어셈블리 수준 <xref:System.Runtime.InteropServices.ComVisibleAttribute>를 `false`로 설정 하 고 클래스 <xref:System.Runtime.InteropServices.ComVisibleAttribute>를 `true`로 설정 해야 합니다.

```csharp
using System;
using System.Runtime.InteropServices;

[assembly: ComVisible(false)]
namespace Samples
{
    [ComVisible(true)]
    public class MyClass
    {
        public static void DoSomething()
        {
        }
    }
}
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 `static` 메서드와 동일한 기능을 제공 하는 인스턴스 메서드를 사용 하도록 디자인을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 COM 클라이언트가 `static` 메서드에서 제공 하는 기능에 액세스할 필요가 없는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example-violation"></a>위반 예

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 `static` 메서드를 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComVisibleStaticMembersViolation/cs/FxCop.Interoperability.ComVisibleStaticMembersViolation.cs#1)]

### <a name="comments"></a>주석
 이 예제에서는 COM에서 **Book. FromPages** 메서드를 호출할 수 없습니다.

## <a name="example-fix"></a>예제 수정

### <a name="description"></a>설명
 이전 예제에서 위반 문제를 해결 하기 위해 메서드를 인스턴스 메서드로 변경할 수 있지만이 경우이 인스턴스에서는 의미가 없습니다. 더 나은 솔루션은 메서드에 명시적으로 `ComVisible(false)`를 적용 하 여 다른 개발자가 COM에서 메서드를 볼 수 없도록 하는 것입니다.

 다음 예제에서는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>을 메서드에 적용 합니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComVisibleStaticMembersFixed/cs/FxCop.Interoperability.ComVisibleStaticMembersFixed.cs#1)]

## <a name="related-rules"></a>관련 규칙
 [CA1017: 어셈블리를 ComVisibleAttribute로 표시하십시오.](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

 [CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용하지 않습니다.](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)

 [CA1413: Com 노출 값 형식에 public이 아닌 필드를 사용하지 마십시오.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

## <a name="see-also"></a>관련 항목:
 [비관리 코드와의 상호 운용](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
