---
title: '테스트 영역 2: 소스 제어에서 가져오기 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, getting items from source control
- source control [Visual Studio SDK], getting items from
ms.assetid: cbd345c5-ca43-4630-b7a4-85564f4e2090
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dca98c927209062d2a1fc67c309d2f32c18d1b5d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722577"
---
# <a name="test-area-2-get-from-source-control"></a>테스트 영역 2: 소스 제어에서 가져오기
이 테스트 영역은 Get 명령을 통해 버전 저장소에서 항목을 검색 하는 테스트 사례를 다룹니다. 이러한 테스트 사례는 로컬 및 웹 프로젝트에 모두 적용할 수 있습니다.

## <a name="command-menu-access"></a>명령 메뉴 액세스
 다음 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합 개발 환경 메뉴 경로가 테스트 사례에 사용 됩니다.

##### <a name="get-latest-version"></a>최신 버전 가져오기:

- **파일**, **소스 제어**, **최신 버전 가져오기**.

- **File**, **최신 버전을 가져옵니다**.

- 바로 가기 메뉴에서 **최신 버전을 가져옵니다**.

- 가져오기: **파일**, **소스 제어**, **가져오기**.

## <a name="expected-behavior"></a>예상 동작

##### <a name="get-latest-version"></a>최신 버전 가져오기:
 버전 저장소에서 항목의 최신 버전에 대 한 자동 (UI 없음) 검색을 수행 합니다.

##### <a name="get"></a>가져오기:
 **가져오기** 대화 상자를 표시 하 고, 사용자가 검색할 파일 집합을 변경 하 고 파일 검색 방법에 영향을 주는 옵션을 수정할 수 있도록 합니다.

## <a name="test-cases"></a>테스트 사례

|작업|테스트 단계|확인 결과가 예상 됩니다.|
|------------|----------------|--------------------------------|
|로컬에 존재 하지 않는 파일의 최신 버전 가져오기|1. 프로젝트를 만듭니다.<br />2. 프로젝트에 항목을 추가 합니다.<br />3. 프로젝트를 소스 제어에 둡니다.<br />4. 항목의 로컬 복사본을 삭제 합니다.<br />5. 항목의 최신 버전을 가져옵니다 (바로 가기 메뉴, **최신 버전 가져오기**).|항목 파일이 로컬로 검색 됩니다.|
|로컬에 존재 하지 않는 파일 가져오기|1. 프로젝트를 만듭니다.<br />2. 프로젝트에 항목을 추가 합니다.<br />3. 프로젝트를 소스 제어에 둡니다.<br />4. 항목의 로컬 복사본을 삭제 합니다.<br />5. 항목 (**파일**, **소스 제어**, **가져오기** \<item >)을 가져옵니다.|항목 파일이 로컬로 검색 됩니다.|
|배타적으로 체크 아웃 되 고 로컬에서 수정 된 파일을 가져옵니다.|1. 프로젝트를 만듭니다.<br />2. 프로젝트에 항목을 추가 합니다.<br />3. 프로젝트를 소스 제어에 둡니다.<br />4. 프로젝트 항목을 단독으로 체크 아웃 합니다.<br />5. 로컬 복사본을 수정 합니다.<br />6. 최신 버전의 항목 (**파일**, **최신 버전의** \<item > 가져오기)을 가져옵니다. 이 단계가 성공 하면 다음 단계를 계속 합니다.<br />7. 경고 대화 상자에서 **바꾸기** 단추를 클릭 합니다.|**6 단계의 ReResult** `:`<br /><br /> 경고 대화 상자는 파일이 체크 아웃 되었음을 나타냅니다.<br /><br /> **7 단계에서 ReResult:**<br /><br /> 수정 된 로컬 파일은 버전 저장소에서 원래 버전으로 대체 됩니다.<br /><br /> 파일이 읽기/쓰기입니다.|
|로컬로 체크 아웃, 공유 및 수정 된 파일 가져오기 및 바꾸기|1. 새 프로젝트를 만듭니다.<br />2. 프로젝트에 항목을 추가 합니다.<br />3. 프로젝트를 소스 제어에 둡니다.<br />4. 프로젝트 항목을 공유로 체크 아웃 합니다.<br />5. 로컬 복사본을 수정 합니다.<br />6. 최신 버전의 항목 (**파일**, **최신 버전의** \<item > 가져오기)을 가져옵니다. 이 단계가 성공 하면 다음 단계를 계속 합니다.<br />7. 경고 대화 상자에서 **바꾸기** 를 클릭 합니다.|**6 단계의 결과:**<br /><br /> 경고 대화 상자는 파일이 체크 아웃 되었음을 나타냅니다.<br /><br /> **7 단계의 결과:**<br /><br /> 수정 된 로컬 파일은 버전 저장소에서 원래 버전으로 대체 됩니다.<br /><br /> 파일이 읽기/쓰기입니다.|
|버전 저장소의 최신 버전과 동일 하 게 로컬에 있는 파일 가져오기|1. 새 프로젝트를 만듭니다.<br />2. 프로젝트에 항목을 추가 합니다.<br />3. 프로젝트를 소스 제어에 둡니다.<br />4. 항목 (**파일**, **소스 제어**, **가져오기** \<item >)을 가져옵니다.|로컬 파일이 변경 되지 않았습니다.|
|하나의 프로젝트를 사용 하 여 솔루션 가져오기|1. 하나의 프로젝트를 사용 하 여 솔루션을 만듭니다.<br />2. 솔루션을 소스 제어에 추가 합니다.<br />3. 모든 프로젝트 파일을 로컬에서 삭제 합니다.<br />4. 솔루션 (**파일**, **소스 제어**, **가져오기**)을 가져옵니다.|삭제 된 모든 파일은 로컬로 복원 됩니다.|

## <a name="see-also"></a>참조
- [소스 제어 플러그 인에 대한 테스트 가이드](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)