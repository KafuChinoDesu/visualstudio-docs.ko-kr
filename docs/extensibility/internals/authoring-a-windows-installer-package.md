---
title: Windows Installer 패키지 작성 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .msi files, VSPackages
- msi files, VSPackages
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aa967b5f23ff9f4e5afa67b9b1cb4e83707616c6
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "72982237"
---
# <a name="author-a-windows-installer-package"></a>Windows Installer 패키지 작성
데이터는 Windows Installer 모델을 구동 합니다. 예를 들어 파일을 복사 하 고 레지스트리 항목을 작성 하는 프로시저 스크립트를 작성 하는 대신 파일 및 레지스트리 데이터를 포함 하는 데이터베이스 테이블에서 행과 열을 작성 합니다.

## <a name="database-entries"></a>데이터베이스 항목
VSPackage를 설치 하려면 Windows Installer 패키지에 다음 태스크를 수행 하는 데이터베이스 항목이 포함 되어 있어야 합니다.

- 시스템을 검색 하 여 VSPackage에서 지 원하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 버전을 찾습니다 (AppSearch, CompLocator, RegLocator, DrLocator 및 서명이 포함 된 Windows Installer 테이블 사용).

- 지원 되는 버전의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설치 되지 않았거나 VSPackage의 다른 시스템 요구 사항이 충족 되지 않는 경우 (LaunchCondition 테이블 사용) 설치를 취소 합니다.

- 디렉터리, 구성 요소 및 파일 테이블을 사용 하 여 VSPackage 및 종속 파일을 설치 합니다.

- 레지스트리 테이블을 사용 하 여 VSPackage에 대 한 적절 한 정보를 레지스트리에 추가 합니다.

- CustomAction 테이블을 사용 하 여 VSPackage **를 호출 하** 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 있는를 통합 합니다.

자세한 내용은 [Windows Installer](/windows/desktop/Msi/windows-installer-portal)를 참조 하세요.

## <a name="setup-tools"></a>설치 도구
다양 한 타사 설치 도구는 Windows Installer 패키지에 대 한 개발 환경을 제공 합니다. 사용할 수 있는 무료 도구는 다음과 같습니다.

- InstallShield 제한 된 버전

   Visual Studio **새 프로젝트** 대화 상자를 통해 InstallShield의 제한 된 버전을 가져올 수 있습니다. **기타 프로젝트 형식** 을 확장 한 다음 **설치 및 배포**를 선택 합니다. InstallShield 템플릿을 선택 합니다.

- Windows Installer XML 도구 집합

   WiX (Windows Installer XML) 도구 집합은 XML 원본 파일에서 패키지 Windows Installer를 빌드합니다. WiX 도구 집합은 Microsoft 오픈 소스 프로젝트입니다. [Wix 도구 집합](https://sourceforge.net/projects/wix/)에서 소스 코드 및 실행 파일을 다운로드할 수 있습니다.

   [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]를 사용 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 통합 되는 상용 제품은 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)를 참조 하세요.

## <a name="see-also"></a>참조
- [Windows Installer를 사용 하 여 Vspackage 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)