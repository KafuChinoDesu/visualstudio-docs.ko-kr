---
title: 'IDebugDocumentTextEvents:: onDestroy | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentTextEvents.onDestroy
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentTextEvents::onDestroy
ms.assetid: 1b7eb341-6bad-403f-9821-19112f8732f3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd8162a33e61af0aab23d7414a2283ec60480960
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572927"
---
# <a name="idebugdocumenttexteventsondestroy"></a>IDebugDocumentTextEvents::onDestroy
기본 문서가 소멸 되었으며 더 이상 유효 하지 않음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT onDestroy();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수를 사용 하지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 `HRESULT`를 반환 합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
 이 메서드는 기본 문서가 소멸 되었으며 더 이상 유효 하지 않음을 나타냅니다.  
  
## <a name="see-also"></a>참조  
 [IDebugDocumentTextEvents 인터페이스](../../winscript/reference/idebugdocumenttextevents-interface.md)