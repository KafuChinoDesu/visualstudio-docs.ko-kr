---
title: 옵션 및 옵션 페이지 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], managed package framework support
- managed package framework, Tools Options pages support
- support, Tools Options pages
- Tools Options pages [Visual Studio SDK], layouts
- Tools Options pages [Visual Studio SDK], attributes
ms.assetid: e6c0e636-5ec3-450e-b395-fc4bb9d75918
caps.latest.revision: 35
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1e30be26c40834d3122d491f8d150f02b6f3b776
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74300692"
---
# <a name="options-and-options-pages"></a>옵션 및 옵션 페이지
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**도구** 메뉴에서 **옵션** 을 클릭 하 여 **옵션** 대화 상자를 엽니다. 이 대화 상자의 옵션을 옵션 페이지 라고 통칭 합니다. 탐색 창에 있는 트리 컨트롤에는 옵션 범주가 있으며 모든 범주에는 옵션 페이지가 있습니다. 페이지를 선택 하면 오른쪽 창에 해당 옵션이 표시 됩니다. 이러한 페이지를 사용 하 여 VSPackage 상태를 결정 하는 옵션의 값을 변경할 수 있습니다.  
  
## <a name="support-for-options-pages"></a>옵션 페이지에 대 한 지원  
 <xref:Microsoft.VisualStudio.Shell.Package> 클래스는 옵션 페이지 및 옵션 범주 만들기에 대 한 지원을 제공 합니다. <xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스는 옵션 페이지를 구현 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.DialogPage>의 기본 구현에서는 속성의 일반 표에 있는 사용자에 게 공용 속성을 제공 합니다. 페이지의 다양 한 메서드를 재정의 하 여 고유한 UI (사용자 인터페이스)가 있는 사용자 지정 옵션 페이지를 만들면이 동작을 사용자 지정할 수 있습니다. 자세한 내용은 [옵션 페이지 만들기](../../extensibility/creating-an-options-page.md)를 참조 하세요.  
  
 <xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스는 옵션 페이지와 사용자 설정에 대 한 지 속성을 제공 하는 <xref:Microsoft.VisualStudio.Shell.IProfileManager>을 구현 합니다. <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 및 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> 메서드의 기본 구현에서는 속성을 문자열로 변환 하거나 문자열로 변환할 수 있는 경우 레지스트리의 사용자 섹션에 속성 변경 내용을 유지 합니다.  
  
## <a name="options-page-registry-path"></a>옵션 페이지 레지스트리 경로  
 기본적으로 옵션 페이지에서 관리 하는 속성의 레지스트리 경로는 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, word DialogPage 및 옵션 페이지 클래스의 형식 이름을 결합 하 여 결정 됩니다. 예를 들어 옵션 페이지 클래스는 다음과 같이 정의할 수 있습니다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#1](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#1)]
 [!code-vb[VSSDKSupportForOptionsPages#1](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#1)]  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A> HKEY_CURRENT_USER \Software\Microsoft\VisualStudio\8.0Exp 경우 속성 이름 및 값 쌍은 HKEY_CURRENT_USER의 하위 키입니다.  
  
 옵션 페이지 자체의 레지스트리 경로는 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, 단어, ToolsOptionsPages 및 옵션 페이지 범주와 이름을 결합 하 여 결정 됩니다. 예를 들어 사용자 지정 옵션 페이지의 범주, 내 옵션 페이지 및 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\VisualStudio\8.0Exp 경우 옵션 페이지에 레지스트리 키 HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\VisualStudio\8.0Exp\ToolsOptionsPages\My Option Pages\Custom.가 있습니다.  
  
## <a name="toolsoptions-page-attributes-and-layout"></a>도구/옵션 페이지 특성 및 레이아웃  
 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성은 옵션 대화 상자의 탐색 트리에서 사용자 지정 옵션 페이지를 범주로 그룹화 하는 **방법을** 결정 합니다. <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성은 옵션 페이지를 인터페이스를 제공 하는 VSPackage 연결 합니다. 다음과 같은 코드 조각을 생각해 봅시다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#2](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#2)]
 [!code-vb[VSSDKSupportForOptionsPages#2](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#2)]  
  
 이를 통해 MyPackage는 옵션 Spagegeneral 및 OptionsPageCustom의 두 가지 옵션 페이지를 제공 합니다. **옵션** 대화 상자에서 두 옵션 페이지가 모두 **내 옵션** 페이지 범주에 **일반** 및 **사용자 지정**으로 나타납니다.  
  
## <a name="option-attributes-and-layout"></a>옵션 특성 및 레이아웃  
 페이지에서 제공 하는 UI (사용자 인터페이스)는 사용자 지정 옵션 페이지의 옵션 모양을 결정 합니다. 일반 옵션 페이지의 레이아웃, 레이블 지정 및 옵션에 대 한 설명은 다음 특성에 따라 결정 됩니다.  
  
- <xref:System.ComponentModel.CategoryAttribute>는 옵션의 범주를 결정 합니다.  
  
- <xref:System.ComponentModel.DisplayNameAttribute>는 옵션의 표시 이름을 결정 합니다.  
  
- <xref:System.ComponentModel.DescriptionAttribute>은 옵션에 대 한 설명을 결정 합니다.  
  
  > [!NOTE]
  > 동일한 특성, SRCategory, LocDisplayName 및 Srcategory은 지역화에 문자열 리소스를 사용 하 고 [관리 되는 프로젝트 샘플](https://go.microsoft.com/fwlink/?LinkId=122774)에 정의 되어 있습니다.  
  
  다음과 같은 코드 조각을 생각해 봅시다.  
  
  [!code-csharp[VSSDKSupportForOptionsPages#3](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/optionspagecustom.cs#3)]
  [!code-vb[VSSDKSupportForOptionsPages#3](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/optionspagegeneral.vb#3)]  
  
  옵션 페이지의 옵션 페이지에 **는 옵션** **페이지에 표시** 되는 옵션입니다. 이 옵션을 선택 하면 설명 상자에 설명, **내 정수 옵션이**표시 됩니다.  
  
## <a name="accessing-options-pages-from-another-vspackage"></a>다른 VSPackage에서 옵션 페이지 액세스  
 옵션 페이지를 호스트 하 고 관리 하는 VSPackage는 자동화 모델을 사용 하 여 다른 VSPackage에서 프로그래밍 방식으로 액세스할 수 있습니다. 예를 들어 다음 코드에서 VSPackage는 옵션 페이지를 호스트 하는 것으로 등록 됩니다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#4](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#4)]
 [!code-vb[VSSDKSupportForOptionsPages#4](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#4)]  
  
 다음 코드 조각에서는 My: 페이지에서:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#5](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#5)]
 [!code-vb[VSSDKSupportForOptionsPages#5](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#5)]  
  
 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성이 옵션 페이지를 등록 하면 특성의 `SupportsAutomation` 인수가 `true`되 면 해당 페이지가 AutomationProperties 키 아래에 등록 됩니다. Automation은이 레지스트리 항목을 검토 하 여 연결 된 VSPackage을 찾은 다음,이 경우에는 호스팅된 옵션 페이지 (이 경우 내 그리드 페이지)를 통해 속성에 액세스 합니다.  
  
 Automation 속성의 레지스트리 경로는 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, word, AutomationProperties 및 options 페이지 범주와 이름을 결합 하 여 결정 됩니다. 예를 들어 옵션 페이지의 내 범주 범주, 내 그리드 페이지 이름 및 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\VisualStudio\8.0Exp 경우 automation 속성에는 레지스트리 키 HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\VisualStudio\8.0Exp\AutomationProperties\My Category\My Grid 페이지가 있습니다.  
  
> [!NOTE]
> 정식 이름인 내 Category.My 그리드 페이지는이 키의 Name 하위 키 값입니다.
