---
title: '방법: 프로그래밍 방식으로 숨겨진 모드에서 Word 대화 상자 사용'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e32c97069e3400b447f8756f9638c9d88d38d99a
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255843"
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>방법: 프로그래밍 방식으로 숨겨진 모드에서 Word 대화 상자 사용
  사용자에 게 표시 하지 않고 Microsoft Office Word에서 기본 제공 대화 상자를 호출 하 여 하나의 메서드 호출로 복잡 한 작업을 수행할 수 있습니다. 메서드를 호출 <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> <xref:Microsoft.Office.Interop.Word.Dialog> 하지 않고 개체의 메서드를 사용 하 여이 작업을 수행할 수 있습니다. <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A>

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="examples"></a>예
 다음 코드 예제에서는 숨김 모드에서 **페이지 설정** 대화 상자를 사용 하 여 사용자 입력 없이 여러 페이지 설정 속성을 설정 하는 방법을 보여 줍니다. 이 예제에서는 개체 <xref:Microsoft.Office.Interop.Word.Dialog> 를 사용 하 여 사용자 지정 페이지 크기를 구성 합니다. 위쪽 여백, 아래쪽 여백 등의 페이지 설정에 대 한 특정 설정은 <xref:Microsoft.Office.Interop.Word.Dialog> 개체의 런타임에 바인딩된 속성으로 사용할 수 있습니다. 이러한 속성은 런타임에 Word에 의해 동적으로 만들어집니다.

 다음 예제에서는 **Option Strict** 가 off 인 Visual Basic 프로젝트에서이 작업을 수행 하는 방법과를 C# [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]대상으로 하는 Visual 프로젝트에서이 작업을 수행 하는 방법을 보여 줍니다. 이러한 프로젝트에서는 Visual Basic 및 Visual C# 컴파일러에서 런타임에 바인딩 기능을 사용할 수 있습니다. 이 예제를 사용 하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행 합니다.

 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]

 다음 예에서는 **Option Strict** 가 on 인 Visual Basic 프로젝트에서이 작업을 수행 하는 방법을 보여 줍니다. 이러한 프로젝트에서는 리플렉션을 사용 하 여 런타임에 바인딩된 속성에 액세스 해야 합니다. 이 예제를 사용 하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행 합니다.

 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]

## <a name="see-also"></a>참고 항목
- [방법: Word에서 프로그래밍 방식으로 기본 제공 대화 상자 사용](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)
- [Word 개체 모델 개요](../vsto/word-object-model-overview.md)
- [Office 솔루션의 런타임에 바인딩](../vsto/late-binding-in-office-solutions.md)
- [리플렉션(C#)](/dotnet/csharp/programming-guide/concepts/reflection)
- [리플렉션(Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)
