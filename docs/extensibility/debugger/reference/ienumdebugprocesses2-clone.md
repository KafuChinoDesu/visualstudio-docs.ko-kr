---
title: IEnumDebugProcesses2::Clone | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2::Clone
helpviewer_keywords:
- IEnumDebugProcesses2::Clone
ms.assetid: 3d4196d3-5a80-4f76-b8b2-f72e80c8d406
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 005044e6fee9db30e5317636f86099e73bd0d890
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66326305"
---
# <a name="ienumdebugprocesses2clone"></a>IEnumDebugProcesses2::Clone
별도 개체와 현재 열거형의 복사본을 반환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Clone(
   IEnumDebugProcesses2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugProcesses2 ppEnum
);
```

## <a name="parameters"></a>매개 변수
`ppEnum`\
[out] 이 열거형은 개별 개체로 복사본을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 열거형의 복사본을이 메서드는 시간에 원본과 동일한 상태를 있습니다. 그러나 복사본의 및는 원래 상태는 각각 별도 이며 개별적으로 변경할 수 있습니다.

## <a name="see-also"></a>참고자료
- [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)