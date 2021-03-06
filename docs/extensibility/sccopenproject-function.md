---
title: SccOpenProject 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccOpenProject
helpviewer_keywords:
- SccOpenProject function
ms.assetid: d609510b-660a-46d7-b93d-2406df20434d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a6aa4a715f8d1b87aa831f6a315f07a19e5d4f46
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721049"
---
# <a name="sccopenproject-function"></a>SccOpenProject 함수
이 함수는 기존 소스 제어 프로젝트를 열거나 새 프로젝트를 만듭니다.

## <a name="syntax"></a>구문

```cpp
SCCRTN SccOpenProject (
   LPVOID        pvContext,
   HWND          hWnd,
   LPSTR         lpUser,
   LPCSTR        lpProjName,
   LPCSTR        lpLocalProjPath,
   LPSTR         lpAuxProjPath,
   LPCSTR        lpComment,
   LPTEXTOUTPROC lpTextOutProc,
   LONG          dwFlags
);
```

#### <a name="parameters"></a>매개 변수
 pvContext

진행 소스 제어 플러그 인 컨텍스트 구조입니다.

 hWnd

진행 소스 제어 플러그 인이 제공 하는 대화 상자의 부모로 사용할 수 있는 IDE 창에 대 한 핸들입니다.

 lpUser

[in, out] NULL 종결자를 포함 하 여 SCC_USER_SIZE를 초과 하지 않는 사용자의 이름입니다.

 lpProjName

진행 프로젝트의 이름을 식별 하는 문자열입니다.

 lpLocalProjPath

진행 프로젝트에 대 한 작업 폴더의 경로입니다.

 lpAuxProjPath

[in, out] 프로젝트를 식별 하는 선택적 보조 문자열입니다 (NULL 종결자를 포함 하 여 SCC_AUXPATH_SIZE를 초과 하지 않음).

 lpComment

진행 만들려는 새 프로젝트에 주석을 추가 합니다.

 lpTextOutProc

진행 소스 제어 플러그 인의 텍스트 출력을 표시 하는 선택적 콜백 함수입니다.

 dwFlags

진행 소스 제어 플러그 인에서 프로젝트를 알 수 없는 경우 새 프로젝트를 만들어야 하는지 여부를 나타냅니다. 값은 `SCC_OP_CREATEIFNEW` 및의 조합일 수 있습니다 `SCC_OP_SILENTOPEN.`

## <a name="return-value"></a>반환 값
 이 함수의 소스 제어 플러그 인 구현은 다음 값 중 하나를 반환 해야 합니다.

|값|설명|
|-----------|-----------------|
|SCC_OK|프로젝트를 여는 동안 성공 했습니다.|
|SCC_E_INITIALIZEFAILED|프로젝트를 초기화할 수 없습니다.|
|SCC_E_INVALIDUSER|사용자가 원본 제어 시스템에 로그인 할 수 없습니다.|
|SCC_E_COULDNOTCREATEPROJECT|호출 전에 프로젝트가 존재 하지 않습니다.  `SCC_OPT_CREATEIFNEW` 플래그가 설정 되었지만 프로젝트를 만들 수 없습니다.|
|SCC_E_PROJSYNTAXERR|프로젝트 구문이 잘못 되었습니다.|
|SCC_E_UNKNOWNPROJECT|소스 제어 플러그 인에서 프로젝트를 알 수 없으며 `SCC_OPT_CREATEIFNEW` 플래그가 설정 되지 않았습니다.|
|SCC_E_INVALIDFILEPATH|파일 경로가 잘못 되었거나 사용할 수 없습니다.|
|SCC_E_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|
|SCC_E_ACCESSFAILURE|네트워크 또는 경합 문제로 인해 원본 제어 시스템에 액세스 하는 동안 문제가 발생 했습니다. 다시 시도 하는 것이 좋습니다.|
|SCC_E_NONSPECFICERROR|일반 오류입니다. 소스 제어 시스템이 초기화 되지 않았습니다.|

## <a name="remarks"></a>주의
 IDE는 사용자 이름 (`lpUser`)을 전달 하거나, 빈 문자열에 대 한 포인터를 전달 하는 것일 수 있습니다. 사용자 이름이 있으면 원본 제어 플러그 인에서이를 기본값으로 사용 해야 합니다. 그러나 이름이 전달 되지 않았거나 지정 된 이름으로 로그인이 실패 한 경우 플러그 인은 사용자에 게 로그인 하 라는 메시지를 표시 해야 하며, 플러그 인이 사용자 이름 문자열을 변경할 수 있기 때문에 올바른 `.` 로그인을 수신 하는 경우 `lpUser`에서 유효한 이름을 반환 합니다. 에서 IDE는 항상 크기 (null 종결자를 위한 공간을 포함 하는 `SCC_USER_LEN` + 1 또는 SCC_USER_SIZE)의 버퍼를 할당 합니다.

> [!NOTE]
> IDE에서 수행 해야 하는 첫 번째 작업은 `SccOpenProject` 함수 또는 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)에 대 한 호출이 될 수 있습니다. 이러한 이유로 두 항목 모두 동일한 `lpUser` 매개 변수를 가집니다.

 `lpAuxProjPath` 및 `lpProjName` 솔루션 파일에서 읽거나 `SccGetProjPath` 함수 호출에서 반환 됩니다. 이러한 매개 변수에는 소스 제어 플러그 인이 프로젝트와 연결 하 고 플러그 인에만 의미가 있는 문자열이 포함 됩니다. 이러한 문자열이 솔루션 파일에 없고 사용자에 게 찾아보기를 요청 하지 않은 경우 (`SccGetProjPath` 함수를 통해 문자열을 반환 함) IDE는 `lpAuxProjPath` 및 `lpProjName`에 대해 빈 문자열을 전달 하 고이 값이 다음에 플러그 인에 의해 업데이트 될 것으로 예상 합니다. is 함수는를 반환 합니다.

 `lpTextOutProc`는 IDE에서 소스 제어 플러그 인에 제공 하는 콜백 함수에 대 한 포인터로, 명령 결과 출력을 표시 하기 위한 것입니다. 이 콜백 함수는 [Lptextoutproc](../extensibility/lptextoutproc.md)에 자세히 설명 되어 있습니다.

> [!NOTE]
> 소스 제어 플러그 인이이를 활용 하려면 [Sccinitialize](../extensibility/sccinitialize-function.md)에서 `SCC_CAP_TEXTOUT` 플래그를 설정 해야 합니다. 해당 플래그가 설정 되지 않았거나 IDE에서이 기능을 지원 하지 않는 경우 `lpTextOutProc` `NULL` 됩니다.

 @No__t_0 매개 변수는 열리는 프로젝트가 현재 존재 하지 않는 경우의 결과를 제어 합니다. @No__t_0 및 `SCC_OP_SILENTOPEN`의 두 bitflags로 구성 됩니다. 열려는 프로젝트가 이미 있는 경우 함수는 단순히 프로젝트를 열고 `SCC_OK` 반환 합니다. 프로젝트가 존재 하지 않고 `SCC_OP_CREATEIFNEW` 플래그가 설정 된 경우 소스 제어 플러그 인이 소스 제어 시스템에서 프로젝트를 만든 다음 열고 `SCC_OK`를 반환할 수 있습니다. 프로젝트가 존재 하지 않는 경우 `SCC_OP_CREATEIFNEW` 플래그가 해제 되어 있으면 플러그 인에서 `SCC_OP_SILENTOPEN` 플래그를 확인 해야 합니다. 이 플래그가 설정 되어 있지 않으면 플러그 인에서 사용자에 게 프로젝트 이름을 묻는 메시지를 표시할 수 있습니다. 이 플래그가 설정 되어 있으면 플러그 인은 단순히 `SCC_E_UNKNOWNPROJECT`을 반환 해야 합니다.

## <a name="calling-order"></a>호출 순서
 일반적인 이벤트 과정에서 [Sccinitialize](../extensibility/sccinitialize-function.md) 를 먼저 호출 하 여 소스 제어 세션을 엽니다. 세션은 `SccOpenProject` 호출로 구성 될 수 있으며, 그 다음에 다른 소스 제어 플러그 인 API 함수 호출로 구성 되며 [Scccloseproject](../extensibility/scccloseproject-function.md)를 호출 하 여 종료 됩니다. 이러한 세션은 [SccUninitialize](../extensibility/sccuninitialize-function.md) 를 호출 하기 전에 여러 번 반복 될 수 있습니다.

 소스 제어 플러그 인이 `SccInitialize`에서 `SCC_CAP_REENTRANT` 비트를 설정 하는 경우 위의 세션 시퀀스가 병렬로 여러 번 반복 될 수 있습니다. @No__t_0 구조는 서로 다른 세션을 추적 하 고 각 `pvContext`는 한 번에 하나의 열린 프로젝트와 연결 됩니다. @No__t_0 매개 변수를 기반으로 플러그 인은 특정 호출에서 참조 되는 프로젝트를 확인할 수 있습니다. @No__t_0 기능 비트를 설정 하지 않은 경우에는 여러 프로젝트에 대 한 작업을 수행 하는 기능에서 재진입이 아닌 소스 제어 플러그 인이 제한 됩니다.

> [!NOTE]
> @No__t_0 비트는 소스 제어 플러그 인 API 버전 1.1에서 도입 되었습니다. 이 파일은 설정 되지 않았거나 버전 1.0에서 무시 되며, 모든 버전 1.0 원본 제어 플러그 인은 재진입이 아닌 것으로 간주 됩니다.

## <a name="see-also"></a>참조
- [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)
- [SccCloseProject](../extensibility/scccloseproject-function.md)
- [SccGetProjPath](../extensibility/sccgetprojpath-function.md)
- [SccInitialize](../extensibility/sccinitialize-function.md)
- [SccUninitialize](../extensibility/sccuninitialize-function.md)
- [문자열 길이에 대한 제한](../extensibility/restrictions-on-string-lengths.md)
- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)