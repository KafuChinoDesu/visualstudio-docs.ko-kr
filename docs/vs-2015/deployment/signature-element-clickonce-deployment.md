---
title: '&lt;Signature&gt; 요소 (ClickOnce 배포) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: db696546fdd64199753054b38fa2ac554f6a774f
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74295073"
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;Signature&gt; 요소 (ClickOnce 배포)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 배포 매니페스트에 디지털 방식으로 서명하는 데 필요한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      <Signature>   
   XML signature information   
</Signature>  
```  
  
## <a name="remarks"></a>주의  
 봉투 (envelope) 서명을 사용 하 여 배포 매니페스트에 서명 하는 것은 선택 사항 이지만 권장 됩니다. XML 파일에 서명 하는 방법에 대 한 자세한 내용은 [http://www.w3.org/TR/xmldsig-core/](https://www.w3.org/TR/xmldsig-core/)에 설명 된 World Wide Web 컨소시엄 권장 사항 "XML 서명 구문 및 처리"를 참조 하십시오.  
  
 매니페스트에 서명 하려면 모든 파일에 대해 해시를 제공 해야 합니다. 사용자는 해시 되지 않은 파일의 콘텐츠를 확인할 수 없으므로 해시 되지 않은 파일이 있는 매니페스트는 서명할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 배포에 사용 되는 배포 매니페스트의 `Signature` 요소를 보여 줍니다.  
  
```  
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
  <SignedInfo>  
    <CanonicalizationMethod Algorithm=  
           "http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />  
    <SignatureMethod Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#rsa-sha1" />  
    <Reference URI="">  
      <Transforms>  
        <Transform Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#enveloped-signature" />  
      </Transforms>  
      <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <DigestValue>d2z5AE...</DigestValue>  
    </Reference>  
  </SignedInfo>  
  <SignatureValue>  
4PHj6SaopoLp...  
  </SignatureValue>  
  <KeyInfo>  
    <X509Data>  
      <X509Certificate>  
MIIHnTCCBoWgAwIBAgIKJY9+nwAHAAB...  
      </X509Certificate>  
    </X509Data>  
  </KeyInfo>  
</Signature>  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)
