---
title: WizardExtension 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardExtension
helpviewer_keywords:
- WizardExtension element [Visual Studio Templates]
- <WizardExtension> element [Visual Studio Templates]
ms.assetid: d54b01c1-50f5-4b65-828c-686e2321cc8c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cfd46573f70b31559f9d6c4749c142d763537764
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72748944"
---
# <a name="wizardextension-element-visual-studio-templates"></a>WizardExtension 요소(Visual Studio 템플릿)
템플릿 마법사를 사용자 지정 하기 위한 등록 요소를 포함 합니다.

 > \<VSTemplate \<WizardExtension >

## <a name="syntax"></a>구문

```
<WizardExtension>
    <Assembly>... </Assembly>
    <FullClassName>... </FullClassName>
</WizardExtension>
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성
 없음.

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[어셈블리](../extensibility/assembly-element-visual-studio-template-wizard-extension.md)|필수적 요소입니다.<br /><br /> 전역 어셈블리 캐시에 표시 되는 어셈블리의 이름 또는 강력한 이름을 지정 합니다. @No__t_1 요소에 `Assembly` 요소가 하나 이상 있어야 합니다.|
|[FullClassName](../extensibility/fullclassname-element-visual-studio-template-wizard-extension.md)|필수적 요소입니다.<br /><br /> @No__t_0 인터페이스를 구현 하는 클래스의 정규화 된 이름입니다. @No__t_1 요소에 `FullClassName` 요소가 하나 이상 있어야 합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[템플릿의](../extensibility/vstemplate-element-visual-studio-templates.md)|프로젝트 템플릿, 항목 템플릿 또는 시작 키트에 대 한 모든 메타 데이터를 포함 합니다.|

## <a name="remarks"></a>주의
 `WizardExtension`은 `VSTemplate`의 선택적 자식 요소입니다.

## <a name="example"></a>예제
 다음 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows 응용 프로그램에 대 한 표준 프로젝트 템플릿에 대 한 메타 데이터를 보여 줍니다.

```
<VSTemplate Version="3.0.0" Type="Item"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyTemplate</Name>
        <Description>Template using IWizard extension</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
    <WizardExtension>
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom=null</Assembly>
        <FullClassName>MyWizard.CustomWizard</FullClassName>
    </WizardExtension>
</VSTemplate>
```

## <a name="see-also"></a>참조
- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)
- [방법: 프로젝트 템플릿에 마법사 사용](../extensibility/how-to-use-wizards-with-project-templates.md)