---
title: 디버그 및 릴리스 구성 설정 | Microsoft Docs
ms.date: 10/05/2018
ms.topic: reference
f1_keywords:
- vs.debug.builds
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- configurations, release
- build configurations, release
- projects [Visual Studio], release configurations
- debugging [Visual Studio], release configurations
- release builds, changing settings
- debug builds
- debug builds, switching to release build
- debug builds, changing configuration settings
- debugging [Visual Studio], debug configurations
- projects [Visual Studio], debug configurations
- build configurations, debug
- debug configurations
- release builds, switching to debug build
- Visual Basic projects, debug and release builds
ms.assetid: 57b6bbb7-f2af-48f7-8773-127d75034ed2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 75acf0a3a821b4d2561ea14e583e71761b8b476e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925463"
---
# <a name="set-debug-and-release-configurations-in-visual-studio"></a>Visual Studio에서 디버그 및 릴리스 구성 설정

Visual Studio 프로젝트에는 사용하는 프로그램에 대한 별도의 릴리스 및 디버그 구성이 있습니다. 디버그 버전은 디버깅용으로 빌드하고 릴리스 버전은 최종 릴리스 배포용으로 빌드합니다.

디버그 구성에서 프로그램은 전체 기호화 된 디버그 정보를 사용 하 여 컴파일되며 최적화 되지 않습니다. 최적화하면 소스 코드와 생성된 명령 간의 관계가 복잡해지므로 디버깅이 복잡해집니다.

프로그램의 릴리스 구성은 기호화 된 디버그 정보를 포함 하지 않으며 완전히 최적화 되었습니다. 관리 코드와 C++ 코드의 경우 사용 되는 [컴파일러 옵션에 따라](#BKMK_symbols_release) .pdb 파일에서 디버그 정보를 생성할 수 있습니다. 나중에 릴리스 버전을 디버깅 해야 하는 경우 .pdb 파일을 만드는 것이 유용할 수 있습니다.

빌드 구성에 대한 자세한 내용은 [빌드 구성 이해](../ide/understanding-build-configurations.md)를 참조하세요.

도구 모음의 **빌드** 메뉴나 프로젝트의 속성 페이지에서 빌드 구성을 변경할 수 있습니다. 프로젝트 속성 페이지는 언어마다 다릅니다. 다음 절차는 메뉴 및 도구 모음에서 빌드 구성을 변경하는 방법을 보여 줍니다. 다른 언어로 된 프로젝트의 빌드 구성을 변경 하는 방법에 대 한 자세한 내용은 아래의 [참고](#see-also) 항목 섹션을 참조 하세요.

## <a name="change-the-build-configuration"></a>빌드 구성 변경

빌드 구성을 변경 하려면 다음 중 하나를 수행 합니다.

* **빌드** 메뉴에서 **Configuration Manager**를 선택한 다음 **디버그** 또는 **릴리스**를 선택 합니다.

로 구분하거나 여러

* 도구 모음의 **솔루션 구성** 목록 상자에서 **디버그** 또는 **릴리스**를 선택합니다.

  ![도구 모음 빌드 구성](../debugger/media/toolbarbuildconfiguration.png "환경 buildconfiguration")

## <a name="BKMK_symbols_release"></a>빌드에 대 한 기호 (.pdb) 파일 생성 (C#, C++, Visual Basic, F#)

기호 (.pdb) 파일 및 포함할 디버그 정보를 생성 하도록 선택할 수 있습니다. 대부분의 프로젝트 형식에 대해 컴파일러는 기본적으로 디버그 및 릴리스 빌드에 대 한 기호 파일을 생성 하 고, 다른 기본 설정은 프로젝트 형식 및 Visual Studio 버전에 따라 다릅니다.

> [!IMPORTANT]
> 디버거는 실행 파일을 빌드할 때 만든 .pdb 파일과 정확히 일치하는 실행 파일의 .pdb 파일만 로드합니다. 즉, .pdb는 원본이거나 원본 .pdb 파일의 복사본이어야 합니다. 자세한 내용은 [Visual Studio에서 빌드된 이진 파일과 정확히 일치 하는 디버거 기호 파일이 필요한 이유](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)(영문)를 참조 하세요.

각 프로젝트 형식에는 이러한 옵션을 설정 하는 다른 방법이 있을 수 있습니다.

### <a name="generate-symbol-files-for-a-c-aspnet-or-visual-basic-project"></a>C#, ASP.NET 또는 Visual Basic 프로젝트에 대 한 기호 파일 생성

또는 Visual Basic 디버그 구성에 대 한 프로젝트 설정에 대 한 자세한 내용은 [ C# ](../debugger/project-settings-for-csharp-debug-configurations.md) 디버그 구성에 대 한 프로젝트 설정 또는 [Visual Basic 디버그 구성에 대 한 프로젝트](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)설정을 참조 하세요. C#

1. 솔루션 탐색기에서 프로젝트를 선택합니다.

2. **속성** 아이콘을 선택 하거나 **alt + enter**를 누릅니다.

3. 측면 창에서 **빌드** (또는 Visual Basic에서 **컴파일** )를 선택 합니다.

4. **구성** 목록에서 **디버그** 또는 **릴리스**를 선택 합니다.

5. **고급** 단추 (또는 Visual Basic의 **고급 컴파일 옵션** 단추)를 선택 합니다.

6. **디버깅 정보** 목록 (또는 Visual Basic의 **디버그 정보 생성** 목록)에서 **전체**, **Pdb 전용**또는 **이식 가능**을 선택 합니다.

   이식 가능한 형식은 .NET Core에 대 한 최신 플랫폼 간 형식입니다. 옵션에 대 한 자세한 내용은 [고급 빌드 설정 대화 상자 (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md)를 참조 하세요.

   ![빌드 C# 에 대 한 pdb 생성](../debugger/media/dbg_project_properties_pdb_csharp.png "GeneratePDBsForCSharp")

7. 프로젝트를 빌드합니다.

   컴파일러는 실행 파일이 나 주 출력 파일과 동일한 폴더에 기호 파일을 만듭니다.

### <a name="generate-symbol-files-for-a-c-project"></a>C++ 프로젝트에 대 한 기호 파일 생성

1. 솔루션 탐색기에서 프로젝트를 선택합니다.

2. **속성** 아이콘을 선택 하거나 **alt + enter**를 누릅니다.

3. **구성** 목록에서 **디버그** 또는 **릴리스**를 선택 합니다.

4. 측면 창에서 **링커 > 디버깅**을 선택한 다음 **디버그 정보 생성**옵션을 선택 합니다.

   의 C++디버그 구성에 대 한 프로젝트 설정에 대 한 자세한 내용은 [ C++ 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)을 참조 하세요.

5. **프로그램 데이터베이스 파일 생성**옵션을 구성 합니다.

   대부분 C++ 의 프로젝트에서 기본값은입니다. `$(OutDir)$(TargetName).pdb`이 값은 출력 폴더에 .pdb 파일을 생성 합니다.

   ![빌드 C++ 에 대 한 pdb 생성](../debugger/media/dbg_project_properties_pdb_cplusplus.png "GeneratePDBsforCPlusPlus")

6. 프로젝트를 빌드합니다.

   컴파일러는 실행 파일이 나 주 출력 파일과 동일한 폴더에 기호 파일을 만듭니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio 디버거에서 기호 파일 (.pdb) 및 소스 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)<br/>
- [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)<br/>
- [C++ 디버그 구성에 대한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)<br/>
- [C# 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-csharp-debug-configurations.md)<br/>
- [Visual Basic 디버그 구성에 대한 프로젝트 설정](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)<br/>
- [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)
