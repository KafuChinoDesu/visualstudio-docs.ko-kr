---
title: 소스 제어 VSPackage 아키텍처 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, architecture
ms.assetid: 453125fc-23dc-49b1-8476-94581f05e6c7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9484aabd0080b0a44d75a8a5f6d90d9217d74b8e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723359"
---
# <a name="source-control-vspackage-architecture"></a>소스 제어 VSPackage 아키텍처
소스 제어 패키지는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에서 제공 하는 서비스를 사용 하는 VSPackage입니다. 반환 시 소스 제어 패키지는 소스 제어 서비스로 기능을 제공 합니다. 또한 소스 제어 패키지는 소스 제어를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 통합 하기 위한 소스 제어 플러그 인 보다 더 다양 한 방법입니다.

 엄격한 계약이 유럽 연합 원본 제어 플러그 인 API를 구현 하는 소스 제어 플러그 인입니다. 예를 들어 플러그 인은 기본 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] UI (사용자 인터페이스)를 대체할 수 없습니다. 또한 소스 제어 플러그 인 API를 사용 하면 플러그 인에서 자체 소스 제어 모델을 구현할 수 없습니다. 그러나 소스 제어 패키지는 이러한 제한 사항을 모두 극복 합니다. 소스 제어 패키지는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자의 원본 제어 환경을 완벽 하 게 제어 합니다. 또한 소스 제어 패키지는 자체 소스 제어 모델 및 논리를 사용할 수 있으며 모든 소스 제어 관련 사용자 인터페이스를 정의할 수 있습니다.

## <a name="source-control-package-components"></a>소스 제어 패키지 구성 요소
 아키텍처 다이어그램에 표시 된 것 처럼 소스 제어 스텁 이라는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 구성 요소는 소스 제어 패키지를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]와 통합 하는 VSPackage입니다.

 소스 제어 스텁은 다음 작업을 처리 합니다.

- 소스 제어 패키지 등록에 필요한 공통 UI를 제공 합니다.

- 소스 제어 패키지를 로드 합니다.

- 소스 제어 패키지를 활성/비활성으로 설정 합니다.

  소스 제어 스텁은 소스 제어 패키지에 대 한 활성 서비스를 찾고 IDE에서 해당 패키지로 들어오는 모든 서비스 호출을 라우팅합니다.

  원본 제어 어댑터 패키지는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 제공 하는 특수 한 소스 제어 패키지입니다. 이 패키지는 원본 제어 플러그 인 API를 기반으로 소스 제어 플러그 인을 지원 하기 위한 중앙 구성 요소입니다. 소스 제어 플러그 인이 활성 플러그 인 이면 소스 제어 스텁이 소스 제어 어댑터 패키지에 해당 이벤트를 보냅니다. 차례로 원본 제어 어댑터 패키지는 소스 제어 플러그 인 API를 사용 하 여 소스 제어 플러그 인과 통신 하 고 모든 원본 제어 플러그 인에 공통 된 기본 UI를 제공 합니다.

  반면 원본 제어 패키지가 활성 패키지인 경우 소스 제어 스텁은 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 소스 제어 패키지 인터페이스를 사용 하 여 패키지와 직접 통신 합니다. 소스 제어 패키지는 자체 소스 제어 UI를 호스팅해야 합니다.

  ![소스 제어 아키텍처 그래픽](../../extensibility/internals/media/vsipsccarch.gif "VSIPSCCArch")

  소스 제어 패키지의 경우에는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 소스 제어 코드 또는 통합을 위한 API를 제공 하지 않습니다. 이는 소스 제어 플러그 인이 엄격한 함수 및 콜백 집합을 구현 해야 하는 [소스 제어 플러그 인을 만드는](../../extensibility/internals/creating-a-source-control-plug-in.md) 방법에 설명 된 방법과 대조 됩니다.

  VSPackage와 마찬가지로 소스 제어 패키지는 `CoCreateInstance`을 사용 하 여 만들 수 있는 COM 개체입니다. VSPackage는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>를 구현 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에서 사용할 수 있도록 합니다. 인스턴스가 생성 되 면 VSPackage는 IDE에서 사용 가능한 서비스 및 인터페이스에 대 한 VSPackage 액세스를 제공 하는 사이트 포인터 및 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 인터페이스를 수신 합니다.

  VSPackage 기반 소스 제어 패키지를 작성 하려면 소스 제어 플러그 인 API 기반 플러그 인을 작성 하는 것 보다 고급 프로그래밍에 대 한 지식이 필요 합니다.

## <a name="see-also"></a>참조
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>
- [시작](../../extensibility/internals/getting-started-with-source-control-vspackages.md)