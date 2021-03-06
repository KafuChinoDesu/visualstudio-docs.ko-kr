---
title: '방법: 워크시트에서 데이터베이스 레코드 스크롤'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f0b3c6a8a9292ceda03c9d0020b78d9518ca49d9
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252039"
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>방법: 워크시트에서 데이터베이스 레코드 스크롤
  다음 절차에서는 디자이너를 사용 하 여 Microsoft Office Excel 워크시트에 데이터베이스 테이블의 단일 필드를 표시 하 고 최종 사용자가 모든 레코드를 스크롤할 수 있는 컨트롤을 표시 하는 방법을 보여 줍니다.

 문서 수준 프로젝트 에서만 디자이너를 사용할 수 있습니다. 그러나 런타임에 컨트롤을 추가 하 고 프로그래밍 방식으로 데이터에 바인딩할 수도 있습니다. 자세한 내용은 [연습: VSTO 추가 기능 프로젝트](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)의 단순 데이터 바인딩

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

## <a name="to-scroll-through-database-records-in-a-worksheet"></a>워크시트의 데이터베이스 레코드를 스크롤하려면

1. Visual Studio에서 Excel 응용 프로그램 프로젝트를 엽니다.

2. **데이터** 원본 창을 열고 데이터베이스에서 데이터 소스를 만듭니다. 자세한 내용은 [새 연결 추가](../data-tools/add-new-connections.md)를 참조 하세요.

3. 표시 하려는 데이터가 포함 된 테이블을 확장 하 고 특정 열을 선택 합니다.

4. 컨트롤 목록을 열고 **NamedRange**를 선택 합니다.

5. 데이터를 <xref:Microsoft.Office.Tools.Excel.NamedRange> 표시할 셀에 컨트롤을 끌어 놓습니다.

6. **도구 상자**의 <xref:System.Windows.Forms.BindingNavigator> **Windows Forms** 탭에서 워크시트에 컨트롤을 추가 하 고 사용 하려는 컨트롤을 설정 합니다. 자세한 내용은 [BindingNavigator 컨트롤 개요 &#40;&#41;Windows Forms](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms)를 참조 하세요.

## <a name="see-also"></a>참고 항목
- [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)
