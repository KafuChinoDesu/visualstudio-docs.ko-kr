---
title: 'IEnumDebugExpressionContexts:: Clone | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExpressionContexts.Clone
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugExpressionContexts::Clone
ms.assetid: c8070ae1-120c-4b5d-bd3d-ae8fca6f9277
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70e11ec9af8859b0e1d4ecd10bd52c8c573de930
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577164"
---
# <a name="ienumdebugexpressioncontextsclone"></a>IEnumDebugExpressionContexts::Clone
현재 열거자와 같은 상태를 포함 하는 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Clone(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppedec`  
 제한이 열거자 복제본의 `IEnumDebugExpressionContexts` 인터페이스를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 `HRESULT`를 반환 합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
 이 메서드는 현재 열거자와 같은 상태를 포함 하는 열거자를 만듭니다.  
  
## <a name="see-also"></a>참조  
 [IEnumDebugExpressionContexts 인터페이스](../../winscript/reference/ienumdebugexpressioncontexts-interface.md)