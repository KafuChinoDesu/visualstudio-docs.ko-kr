---
title: SccProperties 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccProperties
helpviewer_keywords:
- SccProperties function
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e269727441eebc93cd78b70f11fdb571f111ee8b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72720842"
---
# <a name="sccproperties-function"></a>SccProperties 함수
이 함수는 파일 또는 프로젝트에 대 한 소스 제어 속성을 표시 합니다.

## <a name="syntax"></a>구문

```cpp
SCCRTN SccProperties (
   LPVOID pvContext,
   HWND   hWnd,
   LPCSTR lpFileName
);
```

#### <a name="parameters"></a>매개 변수
 pvContext

진행 소스 제어 플러그 인 컨텍스트 구조입니다.

 hWnd

진행 소스 제어 플러그 인이 제공 하는 대화 상자의 부모로 사용할 수 있는 IDE 창에 대 한 핸들입니다.

 lpFileName

진행 파일 또는 프로젝트의 정규화 된 경로 이름입니다.

## <a name="return-value"></a>반환 값
 이 함수의 소스 제어 플러그 인 구현은 다음 값 중 하나를 반환 해야 합니다.

|값|설명|
|-----------|-----------------|
|SCC_OK|속성이 표시 되었습니다.|
|SCC_I_RELOADFILE|버전 제어 시스템에서 파일 속성을 수정 하 여 IDE에서이 파일을 다시 로드 해야 합니다.|
|SCC_E_PROJNOTOPEN|지정한 프로젝트가 소스 제어에서 열려 있지 않습니다.|
|SCC_E_NOTAUTHORIZED|사용자에 게이 파일 또는 프로젝트의 속성을 볼 수 있는 권한이 없습니다.|
|SCC_E_FILENOTCONTROLLED|지정 된 파일 또는 프로젝트가 소스 제어에 있지 않습니다.|
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|알 수 없거나 일반 오류가 발생 했습니다.|

## <a name="remarks"></a>주의
 소스 제어 플러그 인은 속성을 자체 대화 상자에 표시 합니다.

 속성은 원본 제어 플러그 인에서 정의 되며 플러그 인과 플러그 인에 따라 다를 수 있습니다. 플러그 인을 사용 하 여 사용자가 파일의 소스 제어 속성을 변경할 수 있는 경우이 파일 또는 프로젝트를 다시 로드 해야 함을 IDE에 알리기 위해 `SCC_I_RELOAD`를 반환 해야 합니다.

## <a name="see-also"></a>참조
- [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)