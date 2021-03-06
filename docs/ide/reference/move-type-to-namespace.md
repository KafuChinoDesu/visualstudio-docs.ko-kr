---
title: 형식을 네임스페이스로 이동
ms.date: 06/17/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 821e915a0b66f25c5b89a83b31e93b01aea6f400
ms.sourcegitcommit: b593bb889f049fcbdff502c30b73178ed17dbdf0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67292701"
---
# <a name="move-type-to-namespace"></a>형식을 네임스페이스로 이동

이 리팩터링은 다음에 적용됩니다.

- C#

**내용:** 형식을 네임스페이스로 이동

**시기:** 형식을 다른 네임스페이스 또는 폴더로 이동하려는 경우 

**이유:** 솔루션의 일부를 리팩터링하고, 형식을 다른 네임스페이스 또는 폴더로 빠르게 이동하려고 합니다. 

## <a name="how-to"></a>방법

1. 커서를 클래스 이름에 놓습니다.
2. 줄의 임의 위치에서 **Ctrl**+ **.** 를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.
3. **네임스페이스로 이동**을 선택합니다.

   ![네임스페이스로 이동 리팩터링](media/move-to-namespace.png)

4. 열리는 대화 상자에서, 형식을 이동하려는 대상 네임스페이스를 선택합니다. 

   ![네임스페이스 선택 대화 상자](media/select-target-namespace.png)

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
