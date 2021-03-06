---
title: '방법: 프로그래밍 방식으로 문서 저장'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], saving
- Word [Office development in Visual Studio], saving documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b4fbf8e4cb67d5216dc17c325911bb243fae6e1c
ms.sourcegitcommit: 5b34052a1c7d86179d7898ed532babb2d9dad4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490615"
---
# <a name="how-to-programmatically-save-documents"></a>방법: 프로그래밍 방식으로 문서 저장

Word 문서 Microsoft Office 저장 하는 방법에는 여러 가지가 있습니다. 문서 이름을 변경 하지 않고 문서를 저장 하거나 새 이름으로 문서를 저장할 수 있습니다.

[!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="save-a-document-without-changing-the-name"></a>이름을 변경 하지 않고 문서를 저장 합니다.

### <a name="to-save-the-document-associated-with-a-document-level-customization"></a>문서 수준 사용자 지정과 연결 된 문서를 저장 하려면

1. <xref:Microsoft.Office.Tools.Word.Document> 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Save%2A> 메서드를 호출합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#7)]

### <a name="to-save-the-active-document"></a>활성 문서를 저장 하려면

1. 활성 문서 <xref:Microsoft.Office.Interop.Word._Document.Save%2A> 에 대해 메서드를 호출 합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

    [!code-vb[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#8)]
    [!code-csharp[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#8)]

   저장 하려는 문서가 활성 문서 인지 확실 하지 않은 경우 해당 문서를 이름으로 참조할 수 있습니다.

### <a name="to-save-a-document-specified-by-name"></a>이름으로 지정 된 문서를 저장 하려면

1. 문서 이름을 <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션에 대 한 인수로 사용 합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#9)]
     [!code-csharp[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#9)]

## <a name="save-a-document-with-a-new-name"></a>새 이름으로 문서 저장

새 이름 `SaveAs` 으로 문서를 저장 하려면 메서드를 사용 합니다. 문서 수준 word 프로젝트의 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목 또는 word 프로젝트의 네이티브 <xref:Microsoft.Office.Interop.Word.Document> 개체에 대해이 메서드를 사용할 수 있습니다. 이 메서드를 사용 하려면 새 파일 이름을 지정 해야 하지만 다른 인수는 선택 사항입니다.

> [!NOTE]
> <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave>의 이벤트처리기내에다른이름으로저장대화상자를표시하고Cancel매개변수를false로설정하면응용프로그램이예기치않게종료될수`ThisDocument` 있습니다. *Cancel* 매개 변수를 **true**로 설정 하면 자동 저장이 사용 하지 않도록 설정 되었음을 나타내는 오류 메시지가 나타납니다.

### <a name="to-save-the-document-associated-with-a-document-level-customization-with-a-new-name"></a>문서 수준 사용자 지정과 연결 된 문서를 새 이름으로 저장 하려면

1. 정규화 된 `SaveAs` 경로와 파일 `ThisDocument` 이름을 사용 하 여 프로젝트에서 클래스의 메서드를 호출 합니다. 해당 이름의 파일이 폴더에 이미 있으면 자동으로 덮어씁니다. 이 코드 예제를 사용하려면 `ThisDocument` 클래스에서 실행합니다.

    > [!NOTE]
    > 대상 `SaveAs` 디렉터리가 없거나 파일을 저장 하는 다른 문제가 있는 경우 메서드는 예외를 throw 합니다. 메서드 주위 또는 호출 하는 메서드 내부`try...catch` 에서 블록을 사용 하는 것이 좋습니다. `SaveAs`

     [!code-vb[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#10)]

### <a name="to-save-a-native-document-with-a-new-name"></a>네이티브 문서를 새 이름으로 저장 하려면

1. 정규화 된 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 경로와 파일 <xref:Microsoft.Office.Interop.Word.Document> 이름을 사용 하 여 저장 하려는의 메서드를 호출 합니다. 해당 이름의 파일이 폴더에 이미 있으면 자동으로 덮어씁니다.

     다음 코드 예제에서는 활성 문서를 새 이름으로 저장 합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

    > [!NOTE]
    > 대상 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 디렉터리가 없거나 파일을 저장 하는 다른 문제가 있는 경우 메서드는 예외를 throw 합니다. Try ...를 사용 하는 것이 좋습니다.메서드 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 주위 또는 호출 하는 메서드 내부에서 블록을 catch 합니다.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#10)]

## <a name="compile-the-code"></a>코드 컴파일

이 코드 예제에는 다음이 필요합니다.

- 이름을 기준으로 문서를 저장 하려면 C 드라이브에 *Test* 라는 디렉터리가 있어야 합니다 *.*

- 새 이름으로 문서를 저장 하려면 C 드라이브에 *Test* 라는 디렉터리가 있어야 합니다.

## <a name="see-also"></a>참고자료

- [방법: 프로그래밍 방식으로 문서 닫기](../vsto/how-to-programmatically-close-documents.md)
- [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)
- [문서 호스트 항목](../vsto/document-host-item.md)
- [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)
