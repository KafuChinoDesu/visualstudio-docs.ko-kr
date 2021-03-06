---
title: GetScheduledTasksForDebugger 메서드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 49a63462eece9bef09579c7284f72790a3914bc2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353724"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger 메서드
모든 예약 된 작업의 배열을 검색합니다.

 **네임스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **어셈블리:** mscorlib (에서 *mscorlib.dll*)

 .NET Framework에서이 내부 멤버에 액세스할 수 없는 때문에 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.

## <a name="syntax"></a>구문

```csharp
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed
```

## <a name="return-value"></a>반환 값
 모든 예약 된 작업의 배열입니다. 각 작업 실행 되거나 실행이 완료 합니다.

## <a name="remarks"></a>설명
 이 메서드는 스레드로부터 안전 하지 및 다른 인스턴스의 동시 사용 하면 안 <xref:System.Threading.Tasks.TaskScheduler>합니다. 디버거가 다른 모든 스레드가 일시 중단 하는 경우에 디버거에서이 메서드를 호출 합니다.

## <a name="see-also"></a>참고자료
- [TaskScheduler 클래스](../../extensibility/debugger/taskscheduler-class-internal-members.md)