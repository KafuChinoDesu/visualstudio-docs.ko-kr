---
title: IDiaEnumDebugStreams | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams interface
ms.assetid: 611caf4f-7a5f-4aa4-b909-52feeb3cc752
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 70e14e594b385a2fa93f51eed4dec36d74db347e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744686"
---
# <a name="idiaenumdebugstreams"></a>IDiaEnumDebugStreams
데이터 소스에 포함 된 다양 한 디버그 스트림을 열거 합니다.

## <a name="syntax"></a>구문

```
IDiaEnumDebugStreams : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
다음 표에서는 `IDiaEnumDebugStreams`의 메서드를 보여 줍니다.

|메서드|설명|
|------------|-----------------|
|[IDiaEnumDebugStreams::get__NewEnum](../../debugger/debug-interface-access/idiaenumdebugstreams-get-newenum.md)|이 열거자의 `IEnumVARIANT` 버전을 검색 합니다.|
|[IDiaEnumDebugStreams::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreams-get-count.md)|디버그 스트림 수를 검색 합니다.|
|[IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)|인덱스를 사용 하 여 디버그 스트림을 검색 합니다.|
|[IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)|열거형 시퀀스에서 지정 된 수의 디버그 스트림을 검색 합니다.|
|[IDiaEnumDebugStreams::Skip](../../debugger/debug-interface-access/idiaenumdebugstreams-skip.md)|열거형 시퀀스에서 지정 된 수의 디버그 스트림을 건너뜁니다.|
|[IDiaEnumDebugStreams::Reset](../../debugger/debug-interface-access/idiaenumdebugstreams-reset.md)|열거형 시퀀스를 시작 부분으로 다시 설정 합니다.|
|[IDiaEnumDebugStreams::Clone](../../debugger/debug-interface-access/idiaenumdebugstreams-clone.md)|현재 열거자와 동일한 열거 상태를 포함 하는 열거자를 만듭니다.|

## <a name="remarks"></a>주의
디버그 스트림의 콘텐츠는 구현에 따라 다르며 데이터 형식은 문서화 되지 않습니다.

## <a name="notes-for-callers"></a>호출자 참고 사항
[IDiaSession:: getEnumDebugStreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md) 메서드를 호출 하 여 `IDiaEnumDebugStreams` 개체를 가져옵니다.

## <a name="example"></a>예제
이 예제에서는이 인터페이스에서 사용할 수 있는 데이터 스트림에 액세스 하는 방법을 보여 줍니다. @No__t_1 함수의 구현에 대 한 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) 인터페이스를 참조 하세요.

```C++
void DumpAllDebugStreams( IDiaSession* pSession)
{
    IDiaEnumDebugStreams* pEnumStreams;

    wprintf(L"\n\n*** DEBUG STREAMS\n\n");
    // Retrieve an enumerated sequence of debug data streams
    if(pSession->getEnumDebugStreams(&pEnumStreams) == S_OK)
    {
        IDiaEnumDebugStreamData* pStream;
        ULONG celt = 0;

        for(; pEnumStreams->Next(1, &pStream, &celt) == S_OK; pStream = NULL)
        {
            PrintStreamData(pStream);
            pStream->Release();
        }
        pEnumStreams->Release();
    }
    else
    {
        wprintf(L"Failed to get any debug streams!\n");
    }
    wprintf(L"\n");
}
```

## <a name="requirements"></a>요구 사항
헤더: Dia2

라이브러리: diaguids

DLL: msdia80

## <a name="see-also"></a>참조
- [인터페이스(디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaSession::getEnumDebugStreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md)
