---
title: GetOutputFileName 작업 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.getoutputfilename
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (C++), GetOutputFileName task
- GetOutputFileName task (MSBuild (C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 9733aae5e53948cdf07d62f62cd7ca5f930d08a3
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747296"
---
# <a name="getoutputfilename-task"></a>GetOutputFileName 작업

출력 디렉터리 또는 전체 파일 이름만 지정하거나 아무것도 지정하지 않는 cl 및 기타 도구에 대한 출력 파일 이름을 가져오는 도우미 작업입니다.

## <a name="parameters"></a>매개 변수

다음 표에서는 **GetOutputFileName** 작업의 매개 변수에 대해 설명합니다.

|매개 변수|설명|
|---------------|-----------------|
|**OutputExtension**|필수 **문자열** 매개 변수입니다.|
|**OutputFile**|선택적 **string** 출력 매개 변수입니다.|
|**OutputPath**|선택적 **string** 매개 변수입니다.|
|**SourceFile**|필수 **문자열** 매개 변수입니다.|

## <a name="see-also"></a>참고 항목

[작업 참조](../msbuild/msbuild-task-reference.md)