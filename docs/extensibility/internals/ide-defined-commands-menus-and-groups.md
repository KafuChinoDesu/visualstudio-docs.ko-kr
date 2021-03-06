---
title: IDE 정의 명령, 메뉴 및 그룹 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: af6d3e180e2b3d5eb2e0f6c85b7488761e160c69
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72727290"
---
# <a name="ide-defined-commands-menus-and-groups"></a>IDE 정의 명령, 메뉴 및 그룹
대부분의 메뉴, 명령 및 명령 그룹은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에서 사용할 수 있도록 이미 정의 되어 있습니다. 이러한 명령은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 확장 하는 경우에도 사용할 수 있습니다.

## <a name="finding-environment-defined-commands"></a>환경에서 정의 된 명령 찾기
 환경 명령은 다음과 같은 4 개의 vsct 파일 집합에 정의 되어 있습니다.

- SharedCmdDef vsct

- SharedCmdPlace vsct

- ShellCmdDef vsct

- ShellCmdPlace vsct

  이러한 파일은 *\<Visual STUDIO SDK 설치 경로 >* \VisualStudioIntegration\Common\Inc \\에 있습니다. 이러한 파일은 메뉴 및 그룹의 정의와 Guid를 제공 합니다 .이 파일은 VSPackage의 명령 테이블 구성 파일 (vsct)에서 사용자 고유의 메뉴, 그룹 및 명령에 대 한 컨테이너로 사용할 수 있습니다.

## <a name="in-this-section"></a>단원 내용
- [Visual Studio 메뉴의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)

 Visual Studio 메뉴 모음 및 여기에 포함 된 그룹의 메뉴에 GUID 및 ID 값을 제공 합니다.

- [Visual Studio 도구 모음의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)

 Visual Studio IDE 및 도구 모음의 GUID 및 ID 값에 포함 된 그룹을 제공 합니다.

- [Visual Studio 명령의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)

 Visual Studio IDE에서 정의한 명령의 GUID 및 ID 값을 제공 합니다.

## <a name="see-also"></a>참조
- [Visual Studio 명령 테이블(.Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [프로젝트 시스템 확장을 위한 IDE 정의 명령](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)
- [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)