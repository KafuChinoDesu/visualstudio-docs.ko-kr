---
title: '방법: 도구 상자에 활동 추가 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: b3a8a785-5928-457a-8a50-30267e29503d
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8fc2af704ab587480913c51cdbc593e6cc0f483a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663463"
---
# <a name="how-to-add-activities-to-the-toolbox"></a>방법: 도구 상자에 활동 추가
작업은 여러 가지 방법으로 솔루션의 **도구 상자** 에 추가할 수 있습니다. 현재 프로젝트에서 활동을 추가하거나, 다른 프로젝트의 활동을 참조하거나, 다른 어셈블리의 활동을 참조할 수 있습니다.

### <a name="to-add-an-activity-from-within-your-current-project"></a>현재 프로젝트에서 활동을 추가하려면

1. 현재 워크플로 프로젝트에 새 사용자 지정 활동을 추가합니다. 프로젝트에 새 사용자 지정 활동을 추가 하는 [!INCLUDE[crabout](../includes/crabout-md.md)] [방법: 워크플로 프로젝트에 새 항목 추가](../workflow-designer/how-to-add-a-new-item-to-a-workflow-project.md)를 참조 하세요.

2. 활동에 사용자 지정 논리를 추가합니다.

3. 프로젝트를 빌드합니다. 빌드가 성공적으로 완료 되 면 "\<*project name*>" 이라는 **도구 상자** 에 해당 범주에 포함 된 사용자 지정 활동과 함께 새 범주가 표시 됩니다.

    > [!NOTE]
    > 도구 상자를 다시 설정하는 경우 솔루션을 다시 빌드하더라도 사용자 지정 활동은 제거됩니다. 다시 설정한 후에 도구 상자를 사용자 지정 활동으로 다시 채우려면 [!INCLUDE[vs2010](../includes/vs2010-md.md)]을 다시 시작합니다.

    > [!NOTE]
    > 도구 상자는 주어진 이름의 활동을 하나만 표시할 수 있습니다. 다른 어셈블리의 두 활동의 클래스 이름이 같은 경우 하나만 표시됩니다.

    > [!NOTE]
    > 애플리케이션 도메인은 편집기 인스턴스 간에 공유되며 정적 변수를 사용하는 경우에도 편집기 인스턴스 간에 공유됩니다. 원하는 동작이 아닌 경우 인스턴스를 추적하는 데 서비스를 사용해야 합니다. 디자이너 내에서 서비스를 사용 하는 방법에 대 한 자세한 내용은 [ModelItem 편집 컨텍스트 사용](https://msdn.microsoft.com/library/7f9f1ea5-0147-4079-8eca-be94f00d3aa1) 을 참조 하세요.

### <a name="to-add-an-activity-from-within-a-different-project"></a>다른 프로젝트에서 활동을 추가하려면

1. 하나 이상의 워크플로 프로젝트와 사용자 지정 활동 라이브러리 프로젝트 또는 사용자 지정 활동을 정의하는 다른 워크플로 프로젝트가 포함된 솔루션을 엽니다.

2. 프로젝트를 모두 빌드합니다. 빌드가 성공적으로 완료 되 면 "\<*project name*>" 이라는 **도구 상자** 에 해당 범주에 포함 된 사용자 지정 활동과 함께 새 범주가 표시 됩니다.

### <a name="to-add-an-activity-to-the-toolbox-from-an-assembly"></a>어셈블리에서 도구 상자에 활동을 추가하려면

1. 워크플로 솔루션을 엽니다.

2. **도구** 메뉴에서 **도구 상자 항목 선택**...을 선택 합니다.

3. **도구 상자 항목 선택** 대화 상자에서 **시스템-작업 구성 요소** 탭을 선택한 다음 **찾아보기 ...** 를 클릭 합니다. 추가 하려는 사용자 지정 활동이 포함 된 어셈블리로 이동 합니다.

4. 어셈블리를 선택 하 고 **확인을**클릭 합니다. 사용자 지정 활동 구성 요소가 구성 요소 목록에 추가되고 자동으로 선택됩니다.

    1. **확인** 을 클릭 하 여 대화 상자를 닫습니다.

5. 도구 상자를 표시 하려면 **보기** 메뉴에서 **도구 상자** 를 선택 합니다.

6. 사용자 지정 작업은 **도구 상자** 에서 항목이 추가 되기 전에 포커스가 있던 범주 아래에 나타납니다. 예를 들어 도구 상자 항목을 추가 하기 전에 **도구 상자** 에서 **일반** 범주를 선택 하면 활동이 **일반** 범주 아래에 나타납니다.

## <a name="see-also"></a>관련 항목:
 [워크플로 디자이너 사용](../workflow-designer/using-the-workflow-designer.md)