---
title: CustomDataSignature 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- <CustomDataSignature> Element (Visual Studio Templates)
- CustomDataSignature Element (Visual Studio Templates)
ms.assetid: 8c3db51d-7014-4484-802a-15aa1353dbdb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: db2b4d089495245d1a37469df1dc43a19be31866
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351971"
---
# <a name="customdatasignature-element-visual-studio-templates"></a>CustomDataSignature 요소 (Visual Studio 템플릿)
사용자 지정 데이터를 찾을 텍스트 서명을 지정 합니다.

 \<VSTemplate > \<TemplateData > \<CustomDataSignature >

## <a name="syntax"></a>구문

```
<CustomDataSignature>"string"</CustomDataSignature>
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성
 없음

### <a name="child-elements"></a>자식 요소
 없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류 하 고에서 표시 되는 방식을 정의 합니다 **새 프로젝트** 또는 **새 항목 추가** 대화 상자.|

## <a name="text-value"></a>텍스트 값
 텍스트 값은 필수입니다.

 텍스트는 사용자 지정 데이터를 배치 하는 데 필요한 텍스트 서명이 포함 된 문자열.

## <a name="remarks"></a>설명
 `CustomDataSignature`는 선택적 요소입니다.

## <a name="see-also"></a>참고자료
- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [프로젝트 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)