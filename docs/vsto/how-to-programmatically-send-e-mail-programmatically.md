---
title: '방법: 프로그래밍 방식으로 전자 메일 보내기'
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 72d033add2ba8320b14eebd5af700ab225d34410
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551761"
---
# <a name="how-to-programmatically-send-email"></a>방법: 프로그래밍 방식으로 전자 메일 보내기
  이 예에서는 전자 메일 주소에서 도메인 이름이 **example.com** 인 연락처에 전자 메일 메시지를 보냅니다.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="example"></a>예제
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]

## <a name="compile-the-code"></a>코드 컴파일
 이 예제에는 다음 사항이 필요합니다.

- 도메인 이름이 있는 연락처는 전자 메일 주소로 **example.com** .

## <a name="robust-programming"></a>강력한 프로그래밍
 도메인 이름 **example.com**를 검색 하는 필터 코드는 제거 하지 마십시오. 필터를 제거 하면 솔루션에서 모든 연락처에 전자 메일 메시지를 보냅니다.

## <a name="see-also"></a>참고자료
- [메일 항목 작업](../vsto/working-with-mail-items.md)
- [방법: 프로그래밍 방식으로 전자 메일 항목 만들기](../vsto/how-to-programmatically-create-an-e-mail-item.md)
- [방법: 프로그래밍 방식으로 Outlook 연락처 액세스](../vsto/how-to-programmatically-access-outlook-contacts.md)
- [방법: 전자 메일 메시지를 받을 때 프로그래밍 방식으로 작업 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
