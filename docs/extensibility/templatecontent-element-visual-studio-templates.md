---
title: TemplateContent 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateContent
helpviewer_keywords:
- TemplateContent element [Visual Studio project templates]
ms.assetid: 90ae401c-b294-49ac-98da-e0d274f5bebb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9a4ddbdeeaecdb832b2601992272de9d76f4bdcb
ms.sourcegitcommit: d4920babfc3d24a3fe1d4bf446ed3fe73b344467
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "67160005"
---
# <a name="templatecontent-element-visual-studio-templates"></a>TemplateContent 요소(Visual Studio 템플릿)

서식 파일의 내용을 지정합니다.

요소 계층:

```xml
<VSTemplate>
  <TemplateContent>
```

## <a name="syntax"></a>구문

```xml
<TemplateContent>
    ...
</TemplateContent>
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|[BuildOnLoad](../extensibility/buildonload-visual-studio-templates.md)|프로젝트를 템플릿에서 만들면 솔루션을 빌드할 것인지 지정 합니다.|

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 다중 프로젝트 템플릿의 구성과 내용을 지정합니다.|
|[프로젝트](../extensibility/project-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 파일 또는 프로젝트에 추가할 디렉터리를 지정 합니다.|
|[참조](../extensibility/references-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 항목 템플릿에 대해 필요한 어셈블리 참조를 지정 합니다.|
|[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)|선택적 요소입니다.<br /><br /> 템플릿에 포함 된 파일을 지정 합니다.|
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 템플릿에서 프로젝트 또는 항목을 만들 때 사용할 수 있는 사용자 지정 매개 변수를 지정 합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 프로젝트 템플릿, 항목 템플릿 또는 시작 키트에 대 한 모든 메타 데이터를 포함합니다.|

## <a name="remarks"></a>설명
 `TemplateContent` 필수 요소가입니다.

## <a name="example"></a>예제
 다음 예제에서는 프로젝트 템플릿에 대 한 메타 데이터는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 응용 프로그램입니다.

```xml
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic starter kit</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
    </TemplateData>
    <TemplateContent>
        <Project File="MyStarterKit.csproj">
            <ProjectItem>Form1.cs</ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>참고자료

- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)
