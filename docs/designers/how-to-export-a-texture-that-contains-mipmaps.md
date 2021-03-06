---
title: '방법: 밉 맵을 포함하는 질감 내보내기'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d3aa73f24a8fc7c3a5fceb9094acec2f9c6b80f9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72635500"
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>방법: 밉 맵을 포함하는 질감 내보내기

이미지 콘텐츠 파이프라인은 프로젝트의 빌드 단계 중에 소스 이미지에서 MIP 맵을 생성할 수 있습니다. 특정 효과를 구현하기 위해 경우에 따라 각 MIP 수준의 이미지 콘텐츠를 수동으로 지정해야 합니다. 각 MIP 수준의 이미지 콘텐츠를 수동으로 지정할 필요가 없는 경우 빌드 시 MIP 맵을 생성하면 MIP 맵 콘텐츠가 항상 동기화됩니다. 또한 런타임 시 MIP 맵 생성의 성능 비용을 없애줍니다.

이 문에서는 다음과 같은 내용을 설명합니다.

- 이미지 콘텐츠 파이프라인에서 처리할 소스 이미지 구성.

- MIP 맵을 생성하도록 이미지 콘텐츠 파이프라인 구성.

## <a name="export-mipmaps"></a>밉 맵 내보내기

MIP 매핑은 3차원 게임이나 앱에서 질감이 적용된 표면에 대한 자동 화면 공간 수준 세부 정보를 제공합니다. 질감의 다운 샘플링 버전을 미리 계산하여 게임이나 앱의 렌더링 성능을 향상시킵니다. 다운 샘플링 버전을 미리 계산하면 샘플링할 때마다 전체 질감을 다운 샘플링할 필요가 없습니다.

### <a name="to-export-a-texture-that-has-mipmaps"></a>MIP 맵이 있는 질감을 내보내려면

1. 기본 질감으로 시작합니다. 기존 이미지 파일을 로드하거나 [방법: 기본 질감 만들기](../designers/how-to-create-a-basic-texture.md)에서 설명된 대로 새 질감을 만듭니다. MIP 맵을 지원하려면 너비 및 높이가 둘 다 동일한 2의 거듭제곱인 크기(예: 64x64, 256x256 또는 512x512)의 질감을 지정합니다.

2. 방금 만든 질감 파일이 이미지 콘텐츠 파이프라인에서 처리되도록 구성합니다. **솔루션 탐색기**에서 만들어 놓은 질감 파일에 대한 바로 가기 메뉴를 열고 **속성**을 선택합니다. **구성 속성** > **일반** 페이지에서 **항목 종류** 속성을 **이미지 콘텐츠 파이프라인**으로 설정합니다. **콘텐츠** 속성이 **예**로 설정되고 **빌드에서 제외**가 **아니요**로 설정되어야 합니다. **적용**을 선택합니다.

   **이미지 콘텐츠 파이프라인** 구성 속성 페이지가 표시됩니다.

3. MIP 맵을 생성하도록 이미지 콘텐츠 파이프라인을 구성합니다. **구성 속성** > **이미지 콘텐츠 파이프라인** > **일반** 페이지에서 **MIP 생성** 속성을 **예(/generatemips)** 로 설정합니다.

4. **확인**을 선택합니다.

프로젝트를 빌드할 때 이미지 콘텐츠 파이프라인은 소스 이미지를 작업 형식에서 지정한 출력 형식으로 변환합니다(MIP 수준 포함). 결과는 프로젝트의 출력 디렉터리로 복사됩니다.