---
title: usings 생성
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
helpviewer_keywords:
- add missing usings
ms.openlocfilehash: 78786e6e6e7a8e5d8a8766138cb1a54a49416f9a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72610885"
---
# <a name="add-missing-usings-in-visual-studio"></a>Visual Studio에서 누락 usings 추가

이 코드 생성은 다음에 적용됩니다.

- C#

**내용:** 필요한 가져오기 또는 복사하여 붙여넣은 코드의 [using 지시문](/dotnet/csharp/language-reference/keywords/using-directive)을 즉시 추가할 수 있습니다.

**시기:** 프로젝트 또는 다른 소스의 서로 다른 위치에서 코드를 복사하여 새 코드에 붙여넣는 것이 일반적입니다. 이 빠른 작업은 복사하여 붙여넣은 코드의 누락된 imports 지시문을 찾은 다음, 추가하라는 메시지를 표시합니다.

**이유:** 빠른 작업은 필요한 imports를 자동으로 추가하므로, 코드에 필요한 `using` 지시문을 수동으로 복사할 필요가 없습니다.

## <a name="add-missing-usings-refactoring"></a>누락 usings 리팩터링 추가

1. 필요한 `using` 지시문을 포함하지 않고 한 파일의 코드를 복사해 새 파일에 붙여넣습니다. 결과로 나타나는 오류는 누락된 `using` 지시문을 추가하는 코드 수정이 수반됩니다.

    > [!NOTE]
    > 이 제안은 **도구 > 옵션 > 텍스트 편집기 > C# > 고급 > Using 지시문**에서 사용 설정해야 합니다.

2. Ctrl+.를 선택하여 **빠른 작업 및 리팩터링** 메뉴를 엽니다.

    ![usings 생성](media/generate-using-codefix.png)

3. **using \<your reference\>;** 를 선택하여 누락된 참조를 추가합니다.

    ![usings 결과 생성](media/generate-using-result.png)

## <a name="see-also"></a>참고 항목

- [코드 생성](../code-generation-in-visual-studio.md)
- [변경 내용 미리 보기](../../ide/preview-changes.md)
- [.NET 개발자를 위한 팁](../csharp-developer-productivity.md)
