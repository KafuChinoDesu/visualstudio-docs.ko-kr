---
title: SccGetUserOption 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetUserOption
helpviewer_keywords:
- SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cd024aa12b263eab7fea4bd80a0e77a3bbad5f1c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721447"
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption 함수
이 함수는 다양 한 사용자별 옵션을 검색 합니다.

## <a name="syntax"></a>구문

```cpp
SCCRTN SccGetUserOption(
   LPVOID pContext,
   LONG nOption,
   LPLONG lpVal
);
```

#### <a name="parameters"></a>매개 변수
 pContext

진행 소스 제어 플러그 인 컨텍스트 포인터입니다.

 nOption

진행 검색할 옵션입니다 (가능한 옵션에 대 한 설명 참조).

 lpVal

제한이 옵션과 관련 된 값입니다.

## <a name="return-value"></a>반환 값
 이 함수의 소스 제어 플러그 인 구현은 다음 값 중 하나를 반환 해야 합니다.

|값|설명|
|-----------|-----------------|
|SCC_OK|옵션을 검색 했습니다.|
|SCC_E_OPNOTSUPPORTED|옵션은 지원 되지 않습니다.|
|SCC_E_NONSPECIFICERROR|지정되지 않은 오류가 발생했습니다.|

## <a name="remarks"></a>주의
 다음 옵션은이 명령에서 지원 됩니다.

|사용자 옵션|설명|
|-----------------|-----------------|
|`SCC_USEROPT_CHECKOUT_LOCALVER`|사용자가 파일의 로컬 버전을 체크 아웃 하려고 할지 여부를 결정 합니다. `lpVal` `SCC_USEROPT_COLV_YES` 할당 됩니다 (사용자가 로컬 파일을 체크 아웃 하려고 합니다) 또는 `SCC_USEROPT_COLV_NO`.|

## <a name="see-also"></a>참조
- [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)
- [오류 코드](../extensibility/error-codes.md)