---
title: 'IRemoteDebugApplicationThread:: Resume | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.Resume
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::Resume
ms.assetid: ac290861-515d-4f06-b452-3b96f54e538c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc9ccb28604d3a185a1919eb8dc288df711630b6
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571966"
---
# <a name="iremotedebugapplicationthreadresume"></a>IRemoteDebugApplicationThread::Resume
스레드를 다시 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Resume(  
   DWORD*  pdwCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwCount`  
 제한이 스레드의 일시 중단 횟수입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 `HRESULT`를 반환 합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>주의  
 이 메서드는 스레드를 다시 시작할 때 일시 중단 횟수를 감소 시킵니다.  
  
## <a name="see-also"></a>참조  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)