---
title: 소스 목록 표시 명령
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6c211773f20ab4643b62c8c71fc6ae6581a91987
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747897"
---
# <a name="list-source-command"></a>소스 목록 표시 명령
소스 코드의 지정된 줄을 표시합니다.

## <a name="syntax"></a>구문

```
Debug.ListSource [/Count:number] [/Current] [/File:filename]
[/Line:number] [/ShowLineNumbers:yes|no]
```

## <a name="switches"></a>스위치
/Count:`number`

선택 사항입니다. 표시할 줄 수를 지정합니다.

/Current

선택 사항입니다. 현재 줄을 표시합니다.

/File:`filename`

선택 사항입니다. 표시할 파일의 경로입니다. 파일 이름이 지정되지 않은 경우 이 명령은 현재 문의 줄에 대한 소스 코드를 표시합니다.

/Line:`number`

선택 사항입니다. 특정 줄 번호를 표시합니다.

/ShowLineNumbers:`yes|no`

선택 사항입니다. 줄 번호를 표시할지 여부를 지정합니다.

## <a name="example"></a>예
이 예제에서는 줄 번호를 표시하여 Form1.vb 파일의 줄 4 소스 코드를 나열합니다.

```
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes
```

## <a name="see-also"></a>참고 항목

- [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)
- [명령 창](../../ide/reference/command-window.md)