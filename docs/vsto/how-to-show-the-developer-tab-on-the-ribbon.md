---
title: '방법: 리본 메뉴에 개발자 탭 표시'
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
- Developer tab [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7b6641cca4ef2288452b2f6959482b311a5b07a4
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551781"
---
# <a name="how-to-show-the-developer-tab-on-the-ribbon"></a>방법: 리본 메뉴에 개발자 탭 표시
  Office 응용 프로그램의 리본에서 **개발자** 탭에 액세스 하려면 기본적으로 표시 되지 않기 때문에 해당 탭을 표시 하도록 구성 해야 합니다. 예를 표시 Word의 문서 수준 사용자 지정에 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 추가하려면 해당 탭을 표시해야 합니다.

> [!NOTE]
> 이 지침은 Office 2010 또는 이상의 애플리케이션에만 적용됩니다. 2007 Microsoft Office 시스템에서이 탭을 표시 하려면이 항목 [의 다음 버전을 참조 하세요. 리본](https://web.archive.org/web/20140303033431/msdn.microsoft.com/library/bb608625(v=vs.90).aspx
)메뉴에 개발자 탭을 표시 합니다.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

> [!NOTE]
> 액세스에는 **개발자** 탭이 없습니다.

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="to-show-the-developer-tab"></a>개발자 탭을 표시하려면

1. 이 항목에서 지원하는 Office 애플리케이션을 시작합니다. 이 항목의 앞부분에 나오는 **적용 대상: 참고를** 참조 하세요.

2. **파일** 탭에서 **옵션** 단추를 선택 합니다.

     다음 그림에서는 Office 2010의 **파일** 탭 및 **옵션** 단추를 보여 줍니다.

     ![파일 선택, Outlook 2010의 옵션](../vsto/media/vsto-office-file-tab.png "파일 선택, Outlook 2010의 옵션")

     다음 그림에서는 Office 2013의 **파일** 탭을 보여 줍니다.

     ![Outlook 2013의 파일 탭](../vsto/media/vsto-office2013-filetab.png "Outlook 2013의 파일 탭")

     다음 그림에서는 Office 2013의 **옵션** 단추를 보여 줍니다.

     ![Outlook 2013 미리 보기의 옵션 단추](../vsto/media/vsto-office2013-optionsbutton.png "Outlook 2013 미리 보기의 옵션 단추")

3. _ApplicationName_**옵션** 대화 상자에서 **리본 사용자 지정** 단추를 선택 합니다.

     다음 그림에서는 Excel 2010의 **옵션** 대화 상자 및 **리본 사용자 지정** 단추를 보여 줍니다. 이 단추의 위치는 이 항목의 위쪽 “적용 대상&quot; 섹션에 나열된 다른 모든 애플리케이션에서 유사합니다.

     ![리본 사용자 지정 단추](../vsto/media/vsto-office2010-customizeribbonbutton.png "리본 사용자 지정 단추")

4. 주 탭 목록에서 **개발자** 확인란을 선택 합니다.

     다음 그림에서는 Word 2010 및 [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]의 개발자 확인란을 보여 줍니다. 이 확인란의 위치는 이 항목의 위쪽 “적용 대상&quot; 섹션에 나열된 다른 모든 애플리케이션에서 유사합니다.

     ![Word 옵션 대화 상자의 개발자 확인란](../vsto/media/vsto-office2010-developercheckbox.png "Word 옵션 대화 상자의 개발자 확인란")

5. **확인** 단추를 선택 하 여 **옵션** 대화 상자를 닫습니다.

## <a name="see-also"></a>참고자료
- [Office UI 사용자 지정](../vsto/office-ui-customization.md)
