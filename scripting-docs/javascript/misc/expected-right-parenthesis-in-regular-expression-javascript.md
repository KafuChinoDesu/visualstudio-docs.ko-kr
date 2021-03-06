---
title: 정규식에 ') '가 필요 합니다. (JavaScript) | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5020
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2087ba1d-9783-4d40-b609-e8542f579f7f
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c10449df9ef3331949695b7423da3eb08b65433
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577532"
---
# <a name="expected--in-regular-expression-javascript"></a>정규식에 ')'가 필요합니다.(JavaScript)
정규식 캡처, 어설션 또는 그룹을 만들려고 했지만 닫는 괄호는 포함 되지 않았습니다. 괄호는 정규식에서 여러 가지 용도로 사용 됩니다. 주로 이러한 항목은 하위 식을 캡처하고, 어설션을 지정 하거나, *, +,? 등을 기준으로 항목을 단일 단위로 처리할 수 있도록 패턴을 그룹화 하는 데 사용 됩니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 오른쪽에 닫는 괄호를 추가 합니다.  
  
    > [!NOTE]
    > 단일 괄호를 일치 시키려면를 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]하 여 특수 문자로 해석 되지 않도록 백슬래시 \\(-)를 사용 하 여 이스케이프 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](https://msdn.microsoft.com/library/1400241x)