---
title: 저장 하기 전에 데이터 바인딩된 컨트롤에 대 한 in-process 편집 내용 커밋
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- committing edited records
- data-bound controls, in-process edits
- DataBinding class, committing edited records
- hierarchical update, committing edited records
- BindingSource class, committing edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 129f8e03ca982dc1e028dc23a9e342b5793e39cf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648683"
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>데이터 바인딩된 컨트롤에서 데이터를 저장하기 전에 In-Process 편집 커밋

데이터 바인딩된 컨트롤에서 값을 편집할 때 사용자는 현재 레코드를 탐색 하 여 컨트롤이 바인딩되는 기본 데이터 소스에 업데이트 된 값을 커밋해야 합니다. [데이터 소스 창](add-new-data-sources.md) 에서 폼으로 항목을 끌어 놓으면 첫 번째 항목은 <xref:System.Windows.Forms.BindingNavigator>의 **저장** 단추 클릭 이벤트에 코드를 생성 합니다. 이 코드는 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드를 호출 합니다. 따라서 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드에 대 한 호출은 폼에 추가 된 첫 번째 <xref:System.Windows.Forms.BindingSource>에 대해서만 생성 됩니다.

<xref:System.Windows.Forms.BindingSource.EndEdit%2A> 호출에서는 현재 편집 중인 데이터 바인딩된 컨트롤의 프로세스에 포함된 모든 변경 내용을 커밋합니다. 따라서 데이터 바인딩된 컨트롤에 계속 포커스가 있는 상태에서 **저장** 단추를 클릭하면 실제 저장 전에 해당 컨트롤에서 보류 중인 모든 편집 내용이 커밋됩니다(`TableAdapterManager.UpdateAll` 메서드).

사용자가 변경 내용을 커밋하지 않고 저장 프로세스의 일부로 데이터를 저장 하려고 하는 경우에도 자동으로 변경 내용을 커밋하는 응용 프로그램을 구성할 수 있습니다.

> [!NOTE]
> 디자이너는 폼에 끌어 놓은 첫 번째 항목에 대해서만 `BindingSource.EndEdit` 코드를 추가 합니다. 따라서 폼의 각 <xref:System.Windows.Forms.BindingSource>에 대 한 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드를 호출 하는 코드 줄을 추가 해야 합니다. 각 <xref:System.Windows.Forms.BindingSource>에 대 한 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드를 호출 하는 코드 줄을 수동으로 추가할 수 있습니다. 또는 폼에 `EndEditOnAllBindingSources` 메서드를 추가 하 고 저장을 수행 하기 전에 호출할 수 있습니다.

다음 코드는 [LINQ (통합 언어 쿼리)](/dotnet/csharp/linq/) 쿼리를 사용 하 여 모든 <xref:System.Windows.Forms.BindingSource> 구성 요소를 반복 하 고 폼의 각 <xref:System.Windows.Forms.BindingSource>에 대해 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드를 호출 합니다.

## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>폼의 모든 BindingSource 구성 요소에 대해 EndEdit를 호출 하려면

1. @No__t_0 구성 요소를 포함 하는 폼에 다음 코드를 추가 합니다.

     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.vb)]

2. 폼의 데이터를 저장 하기 위한 호출 바로 앞에 다음 코드 줄을 추가 합니다 (`TableAdapterManager.UpdateAll()` 메서드).

     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.vb)]

## <a name="see-also"></a>참고 항목

- [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [계층적 업데이트](../data-tools/hierarchical-update.md)