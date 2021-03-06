---
title: SccUninitialize 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 321f50173e3c1517cc6a431ff74933e1a02ef1d0
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72720124"
---
# <a name="sccuninitialize-function"></a>SccUninitialize 함수
이 함수는 소스 제어 플러그 인을 종료 하기 위해 [Sccinitialize](../extensibility/sccinitialize-function.md) 에 대 한 이전 호출로 생성 된 모든 할당 또는 열린 연결을 정리 합니다.

## <a name="syntax"></a>구문

```cpp
SCCRTN SccUninitialize (
   LPVOID pvContext
);
```

#### <a name="parameters"></a>매개 변수
 pvContext

진행 [Sccinitialize](../extensibility/sccinitialize-function.md)에서 만든 소스 제어 플러그 인 컨텍스트 구조에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값
 이 함수의 소스 제어 플러그 인 구현은 다음 값 중 하나를 반환 해야 합니다.

|값|설명|
|-----------|-----------------|
|SCC_OK|정리를 완료 했습니다.|

## <a name="remarks"></a>주의
 원본 제어 플러그 인은 종료 하 고 플러그 인이 컨텍스트 구조에 할당 한 메모리를 확보 하기 위한 준비를 담당 합니다. 함수는 플러그 인의 지정 된 각 인스턴스에 대해 한 번씩 호출 됩니다. [Sccinitialize](../extensibility/sccinitialize-function.md) 에 대 한 호출은이 호출 앞에 나옵니다. @No__t_0를 호출 하는 시점에는 프로젝트가 열려 있지 않습니다.

## <a name="see-also"></a>참조
- [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)
- [SccInitialize](../extensibility/sccinitialize-function.md)