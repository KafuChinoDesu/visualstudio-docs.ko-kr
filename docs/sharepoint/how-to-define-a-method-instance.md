---
title: '방법: 메서드 인스턴스 정의 | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method
- Business Data Connectivity service [SharePoint development in Visual Studio], method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0e21900e87278ad500ee8497d1dd0c49350695d1
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "72981803"
---
# <a name="how-to-define-a-method-instance"></a>방법: 메서드 인스턴스 정의
  모델의 모든 메서드에 대해 메서드 인스턴스를 하나 이상 정의 해야 합니다.

 **BDC 메서드 세부 정보** 창을 사용 하 여 메서드 인스턴스를 추가 합니다. 메서드 인스턴스를 추가 하면 Visual Studio에서 프로젝트의 모델 파일 XML에 `<MethodInstance>` 요소를 추가 합니다. `<MethodInstance>` 요소의 특성에 대 한 자세한 내용은 [MethodInstance](/previous-versions/office/developer/sharepoint-2010/ee556838(v=office.14))를 참조 하십시오.

### <a name="to-define-a-method-instance"></a>메서드 인스턴스를 정의 하려면

1. **BDC 메서드 세부 정보** 창에서 메서드의 노드를 확장 한 다음 **인스턴스** 노드를 확장 합니다.

2. **메서드 인스턴스 추가** 목록에서 **Finder 인스턴스 만들기**를 선택 합니다.

     새 메서드 인스턴스가 **인스턴스** 노드 아래에 나타납니다.

3. 메뉴 모음에서 **보기** > **속성 창**을 선택 합니다.

4. **속성** 창에서 메서드 인스턴스의 속성을 설정 합니다. 각 속성에 대 한 자세한 내용은 [MethodInstance](/previous-versions/office/developer/sharepoint-2010/ee556838(v=office.14))를 참조 하십시오.

## <a name="see-also"></a>참조
- [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)
- [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)
- [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [방법: 매개 변수의 형식 설명자 정의](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)
