---
title: '테스트 영역 8: 플러그 인 전환 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], switching plug-ins
- source control plug-ins, switching
ms.assetid: 01370792-b5da-4e46-9ce2-7dd326587141
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fb815a773351c1bb6212962a639e2758114a0e2c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722426"
---
# <a name="test-area-8-plug-in-switching"></a>테스트 영역 8: 플러그 인 전환
@No__t_0 IDE (통합 개발 환경)에는 현재 소스 제어 플러그 인을 변경 하는 UI (사용자 인터페이스)가 있습니다. 이 테스트 영역에서는 솔루션 소스 제어에 사용할 플러그 인을 선택 하는 프로세스에 대 한 테스트 사례를 제공 합니다.

## <a name="command-menu-access"></a>명령 메뉴 액세스
 다음 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합 개발 환경 메뉴 경로가 테스트 사례에 사용 됩니다.

- 현재 소스 제어 플러그 인: **도구**  -> **옵션**  -> **소스 제어**  ->  플러그 인**선택**.

- 소스 제어 바인딩 변경 **: 소스 제어  ->  소스** 제어를**변경**하는 **파일**  ->  ...

## <a name="common-expected-behavior"></a>일반적인 예상 동작
 솔루션에 대 한 소스 제어 플러그 인을 변경 하는 것은 Visual Studio를 종료 하거나 솔루션을 다시 로드 하지 않고도 가능 합니다. 또한 현재 소스 제어 플러그 인은 솔루션이 로드 될 때 솔루션에서 사용 하는 플러그 인으로 자동 변경 됩니다.

## <a name="test-cases"></a>테스트 사례
 다음은 플러그 인 전환 테스트 영역에 대 한 특정 테스트 사례입니다.

### <a name="case-8a-automatic-change"></a>Case 8a: 자동 변경

#### <a name="expected-behavior"></a>예상 동작
 사용자가 소스 제어에서 사용 하는 솔루션을 로드 하면 솔루션이 자동으로 로드 되 고 적절 한 소스 제어 플러그 인이 현재 상태로 선택 됩니다.

| 작업 | 테스트 단계 | 확인 결과가 예상 됩니다. |
| - | - | - |
| 자동 소스 제어 플러그 인 변경 | 1. 현재 상태로 테스트에서 플러그 인을 선택 합니다 (**도구**  -> **옵션**  -> **소스 제어**  -> **플러그 인 선택**).<br />2. 새 프로젝트를 만듭니다.<br />3. 솔루션을 소스 제어에 추가 합니다.<br />4. 다른 플러그 인을 선택 합니다 (예: [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />5. 솔루션 언로드 프롬프트를 수락 합니다.<br />6. 디스크에서 솔루션을 다시 엽니다. | 솔루션이 열립니다.<br /><br /> 테스트 중인 플러그 인은 현재 소스 제어 플러그 인입니다. |

### <a name="case-8b-solution-based-change"></a>Case 8b: 솔루션 기반 변경

#### <a name="expected-behavior"></a>예상 동작
 솔루션은 연결 된 소스 제어 플러그 인을 변경할 수 있습니다.

| 작업 | 테스트 단계 | 확인 결과가 예상 됩니다. |
|----------------------------------| - | - |
| 솔루션에 대 한 플러그 인 변경 | 1. 현재 상태로 테스트에서 플러그 인을 선택 합니다 (**도구**  -> **옵션**  -> **소스 제어**  -> **플러그 인 선택**).<br />2. 새 프로젝트 및 솔루션을 만듭니다.<br />3. 솔루션을 소스 제어에 추가 합니다.<br />4. 소스 제어 **변경** 대화 상자를 사용 하 여 소스 제어에서 솔루션의 바인딩을 해제 합니다.<br />5. 다른 플러그 인을 선택 합니다 (예: [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />6. 언로드된 경우 디스크에서 솔루션을 다시 로드 합니다.<br />7. 솔루션을 소스 제어에 추가 합니다.<br />8. 소스 제어에서 솔루션 바인딩 해제 ( **소스 제어 변경** 대화 상자 사용)<br />9. 테스트에서 플러그 인을 다시 선택 합니다.<br />10. 언로드된 경우 디스크에서 솔루션을 다시 로드 합니다.<br />11. **소스 제어 변경** 대화 상자를 사용 하 여 솔루션을 원래 위치에 바인딩합니다. | 선택한 플러그 인을 사용 하 여 솔루션을 소스 제어에 추가 합니다. |

## <a name="see-also"></a>참조
- [소스 제어 플러그 인에 대한 테스트 가이드](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)