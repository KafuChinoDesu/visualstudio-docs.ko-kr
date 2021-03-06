---
title: 콘솔 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 6ec56665b546f962e8b3f4fd35460715390aee30
ms.sourcegitcommit: 00b71889bd72b6a566586885bdb982cfe807cf54
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74777818"
---
# <a name="console"></a>Console
VSPerfCmd.exe **콘솔** 옵션은 새 명령 프롬프트 창에서 지정된 애플리케이션을 시작합니다. **콘솔**은 VSPerfCmd **Launch** 옵션에만 사용할 수 있습니다. 애플리케이션이 명령줄 애플리케이션이 아닌 경우 **콘솔**에 영향을 주지 않습니다.

## <a name="syntax"></a>구문

```cmd
VSPerfCmd.exe /Launch:AppName /Console
```

#### <a name="parameters"></a>매개 변수
 없음

## <a name="required-options"></a>필수 옵션
 **콘솔**은 **Launch** 옵션도 포함하는 명령줄에서만 지정할 수 있습니다.

 **시작:** `AppName` 프로파일러 및 `AppName`에서 지정한 애플리케이션을 시작합니다.

## <a name="see-also"></a>참고 항목
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [독립 실행형 애플리케이션 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [ASP.NET 웹 애플리케이션 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)
