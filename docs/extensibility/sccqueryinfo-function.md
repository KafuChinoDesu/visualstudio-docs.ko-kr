---
title: SccQueryInfo 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccQueryInfo
helpviewer_keywords:
- SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5807eb6b695e140350696436a8bba351687f4a24
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72720825"
---
# <a name="sccqueryinfo-function"></a>SccQueryInfo 함수
이 함수는 소스 제어에서 선택한 파일 집합에 대 한 상태 정보를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
SCCRTN SccQueryInfo(
   LPVOID  pvContext,
   LONG    nFiles,
   LPCSTR* lpFileNames,
   LPLONG  lpStatus
);
```

#### <a name="parameters"></a>매개 변수
 pvContext

진행 소스 제어 플러그 인 컨텍스트 구조입니다.

 n

진행 @No__t_0 배열에 지정 된 파일 수와 `lpStatus` 배열의 길이입니다.

 lpFileNames 이름

진행 쿼리할 파일의 이름 배열입니다.

 lpStatus

[in, out] 소스 제어 플러그 인에서 각 파일에 대 한 상태 플래그를 반환 하는 배열입니다. 자세한 내용은 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)를 참조 하세요.

## <a name="return-value"></a>반환 값
 이 함수의 소스 제어 플러그 인 구현은 다음 값 중 하나를 반환 해야 합니다.

|값|설명|
|-----------|-----------------|
|SCC_OK|쿼리가 성공 했습니다.|
|SCC_E_ACCESSFAILURE|원본 제어 시스템에 액세스 하는 데 문제가 발생 했습니다. 네트워크 또는 경합 문제로 인해 발생 했을 수 있습니다. 다시 시도 하는 것이 좋습니다.|
|SCC_E_PROJNOTOPEN|프로젝트가 소스 제어에서 열려 있지 않습니다.|
|SCC_E_NONSPECIFICERROR|일반 오류입니다.|

## <a name="remarks"></a>주의
 @No__t_0 빈 문자열인 경우 현재 업데이트할 상태 정보가 없습니다. 그렇지 않으면 상태 정보가 변경 되었을 수 있는 파일의 전체 경로 이름입니다.

 반환 배열은 `SCC_STATUS_xxxx` 비트의 비트 마스크 일 수 있습니다. 자세한 내용은 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)를 참조 하세요. 소스 제어 시스템은 일부 비트 형식을 지원 하지 않을 수 있습니다. 예를 들어 `SCC_STATUS_OUTOFDATE` 제공 되지 않으면 비트가 설정 되지 않습니다.

 이 함수를 사용 하 여 파일을 체크 아웃 하는 경우 다음 `MSSCCI` 상태 요구 사항을 참고 하십시오.

- 현재 사용자가 파일을 체크 아웃 하면 `SCC_STATUS_OUTBYUSER` 설정 됩니다.

- `SCC_STATUS_OUTBYUSER` 설정 하지 않으면 `SCC_STATUS_CHECKEDOUT`를 설정할 수 없습니다.

- 지정 된 작업 디렉터리로 파일이 체크 아웃 된 경우에만 `SCC_STATUS_CHECKEDOUT` 설정 됩니다.

- 현재 사용자가 파일을 작업 디렉터리가 아닌 다른 디렉터리에 체크 아웃 하면 `SCC_STATUS_OUTBYUSER` 설정 되지만 `SCC_STATUS_CHECKEDOUT`는 설정 되지 않습니다.

## <a name="see-also"></a>참조
- [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)
- [파일 상태 코드](../extensibility/file-status-code-enumerator.md)