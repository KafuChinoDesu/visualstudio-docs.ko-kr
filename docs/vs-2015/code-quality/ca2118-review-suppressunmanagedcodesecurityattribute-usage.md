---
title: 'CA2118: SuppressUnmanagedCodeSecurityAttribute 사용법 검토 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2118
- ReviewSuppressUnmanagedCodeSecurityUsage
helpviewer_keywords:
- ReviewSuppressUnmanagedCodeSecurityUsage
- CA2118
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: bb7404d9add159f182ae44b22444dded1aafca20
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658648"
---
# <a name="ca2118-review-suppressunmanagedcodesecurityattribute-usage"></a>CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|
|CheckId|CA2118|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 공용 또는 보호 된 형식 또는 멤버에 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 특성이 있습니다.

## <a name="rule-description"></a>규칙 설명
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>은 COM interop 또는 플랫폼 호출을 사용 하 여 비관리 코드를 실행 하는 멤버에 대 한 기본 보안 시스템 동작을 변경 합니다. 일반적으로 시스템은 데이터를 [만들고](https://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6) 비관리 코드 사용 권한을 모델링 합니다. 이 요청은 멤버를 호출할 때마다 런타임에 발생 하며, 호출 스택의 모든 호출자에 게 사용 권한이 있는지 확인 합니다. 특성이 있으면 시스템은 권한 부여에 대 한 [링크를 요청](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) 합니다. 호출자가 JIT 컴파일될 때 직접 실행 호출자의 권한이 확인 됩니다.

 이 특성은 기본적으로 성능 향상을 위해 사용되지만 성능이 향상되는 대신 중대한 보안 위험이 발생합니다. 네이티브 메서드를 호출 하는 public 멤버에 특성을 저장 하는 경우 호출 스택의 호출자에 게 비관리 코드를 실행할 수 있는 비관리 코드 권한이 필요 하지 않습니다. 공용 멤버의 작업 및 입력 처리에 따라 신뢰할 수 없는 호출자가 일반적으로 신뢰할 수 있는 코드로 제한 된 기능에 액세스할 수 있습니다.

 @No__t_0는 호출자가 현재 프로세스의 주소 공간에 직접 액세스할 수 없도록 보안 검사에 의존 합니다. 이 특성은 일반적인 보안을 우회 하므로 프로세스의 메모리를 읽거나 쓰는 데 사용할 수 있는 경우 코드는 심각한 위협을 발생 합니다. 프로세스 메모리에 대 한 액세스를 의도적으로 제공 하는 방법으로는 위험이 제한 되지 않습니다. 예를 들어 놀라운 형식이 나 잘못 된 입력을 제공 하는 등의 방법으로 악의적인 코드가 액세스를 달성할 수 있는 모든 시나리오에도 제공 됩니다.

 기본 보안 정책은 로컬 컴퓨터에서 실행 되 고 있지 않거나 다음 그룹 중 하나의 멤버인 경우에만 어셈블리에 비관리 코드 권한을 부여 하지 않습니다.

- 내 컴퓨터 영역 코드 그룹

- Microsoft 강력한 이름 코드 그룹

- ECMA 강력한 이름 코드 그룹

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 코드를 신중 하 게 검토 하 여이 특성이 반드시 필요한 지 확인 합니다. 관리 코드 보안에 익숙하지 않거나이 특성을 사용 하는 보안의 영향을 이해 하지 못하는 경우 코드에서 제거 합니다. 특성이 필요한 경우 호출자가 코드를 악의적으로 사용할 수 없도록 해야 합니다. 코드에 비관리 코드를 실행할 수 있는 권한이 없는 경우이 특성은 효과가 없으며 제거 되어야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 안전 하 게 표시 하지 않으려면 코드가 안전 하지 않은 방식으로 사용할 수 있는 네이티브 작업 또는 리소스에 대 한 액세스 권한을 호출자에 게 제공 하지 않도록 해야 합니다.

## <a name="example"></a>예제
 다음 예에서는 규칙을 위반 합니다.

 [!code-csharp[FxCop.Security.TypesDoNotSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesDoNotSuppress/cs/FxCop.Security.TypesDoNotSuppress.cs#1)]

## <a name="example"></a>예제
 다음 예제에서 `DoWork` 메서드는 `FormatHardDisk` 플랫폼 호출 메서드에 공개적으로 액세스할 수 있는 코드 경로를 제공 합니다.

 [!code-csharp[FxCop.Security.PInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PInvokeAndSuppress/cs/FxCop.Security.PInvokeAndSuppress.cs#1)]

## <a name="example"></a>예제
 다음 예제에서는 공용 메서드 `DoDangerousThing` 위반을 발생 시킵니다. 위반 문제를 해결 하려면 `DoDangerousThing`를 비공개로 설정 해야 하며,이에 대 한 액세스는 `DoWork` 메서드에 설명 된 대로 보안 요청으로 보호 되는 공용 메서드를 통해 수행 해야 합니다.

 [!code-csharp[FxCop.Security.TypeInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypeInvokeAndSuppress/cs/FxCop.Security.TypeInvokeAndSuppress.cs#1)]

## <a name="see-also"></a>관련 항목:
 보안 [코딩 지침](https://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> [보안 최적화](https://msdn.microsoft.com/cf255069-d85d-4de3-914a-e4625215a7c0) [데이터 및 모델링](https://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6) [링크 요구](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)
