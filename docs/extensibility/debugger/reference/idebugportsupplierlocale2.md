---
title: IDebugPortSupplierLocale2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierLocale2 interface
ms.assetid: 910e7220-da2a-4339-9fff-9fb1bad3c28c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1f691bba978243e75511996caee38df09baa3c3e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353295"
---
# <a name="idebugportsupplierlocale2"></a>IDebugPortSupplierLocale2
포트 공급자에 대 한 로캘 지원을 제공합니다.

## <a name="syntax"></a>구문

```
IDebugPortSupplierLocale2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 사용자 지정 포트 공급자 로캘을 설정 하려면이 인터페이스를 구현 합니다.

## <a name="methods"></a>메서드
 다음 표에서의 메서드를 보여 줍니다 **IDebugPortSupplierLocale2**합니다.

|메서드|설명|
|------------|-----------------|
|[SetLocale](../../../extensibility/debugger/reference/idebugportsupplierlocale2-setlocale.md)|포트 공급자에 대 한 로캘을 설정합니다.|

## <a name="requirements"></a>요구 사항
 헤더: Portpriv.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고자료
- [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)