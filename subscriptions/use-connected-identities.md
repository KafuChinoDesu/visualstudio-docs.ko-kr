---
title: 연결된 Microsoft 계정 및 Azure Active Directory ID를 사용하는 방법 | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 09/27/2019
ms.topic: conceptual
robots: noindex, nofollow
description: 연결된 Microsoft 계정 및 Azure Active Directory ID를 사용하는 방법 알아보기
ms.openlocfilehash: 1a862caa1f984f5d22f041a6f0cbff6534d8cc1c
ms.sourcegitcommit: bcdab788085bd9931d73883fe70cd5831317dca2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72816583"
---
# <a name="how-to-use-connected-identities-in-visual-studio-subscriptions"></a>Visual Studio 구독에서 연결된 ID를 사용하는 방법
사용자가 회사 또는 학교를 통해 Visual Studio 구독을 받고 Microsoft 계정(MSA)을 사용하여 로그인하는 경우, 구독 관리자는 조직의 Azure Active Directory(Azure AD)에서 사용자의 ID에 MSA를 연결할 수 있습니다.  이렇게 하면 구독에 포함된 일부 혜택에 액세스하는 방법이 변경됩니다. 

## <a name="overview-of-connected-ids"></a>연결된 ID 개요
조직은 Azure AD 기반 ID로 점점 이동하여 향상된 보안을 제공하고 구독의 자동화된 관리를 지원합니다.  구독에서 @outlook.com 또는 다른 개인 이메일 주소와 같은 MSA를 사용하는 경우 관리자가 로그인 이메일을 Azure AD ID로 변경할 수 있습니다.  그러면 https://my.visualstudio.com 에서 구독자 포털에 로그인하는 방법이 변경되지만 모든 혜택에 액세스하는 방법은 변경되지 않을 수 있습니다.  

관리자가 MSA와 Azure AD ID를 연결하는 경우 MSA 대신 Azure AD ID를 사용하여 Visual Studio 구독에 액세스를 시작하는 것을 알리는 이메일을 받게 됩니다. 

## <a name="how-to-access-benefits-using-azure-ad-identities"></a>Azure AD ID를 사용하여 혜택에 액세스하는 방법
관리자가 MSA를 Azure AD ID에 연결한 후 Azure AD를 사용하는 혜택에 액세스하려면 Azure AD ID를 사용하여 https://my.visualstudio.com 에서 구독자 포털에 로그인해야 합니다.  여기에는 다음이 포함됩니다.
- Visual Studio IDE
- Azure DevOps
- Azure DevTest 개별 크레딧

## <a name="how-to-access-benefits-using-your-msa"></a>MSA를 사용하여 혜택에 액세스하는 방법
Pluralsight, LinkedIn, CloudPilot 등의 Visual Studio 구독에서 제공되는 많은 혜택을 위해 실제로 파트너의 웹 사이트에 사용자 계정을 만듭니다.  이러한 계정의 경우 계정을 만들 때 사용한 ID를 계속 사용해야 합니다.  예를 들어 MSA를 사용하여 Pluralsight 혜택을 활성화한 경우 구독자 포털에 로그인하는 데 사용하는 ID와 관계없이 Pluralsight 학습을 가져올 때 MSA를 계속 사용해야 합니다.  

## <a name="use-an-alternate-identity-to-access-your-subscription"></a>대체 ID를 사용하여 구독 액세스
대체 계정을 Visual Studio 구독에 추가하면 구독이 할당된 ID 외에 다른 ID로 Azure DevOps 및 Azure 같은 구독 혜택에 액세스할 수 있습니다. 이전에 이 기능은 VS(Visual Studio) 구독이 MSA(Microsoft 계정)에 할당된 경우에만 사용할 수 있었습니다. Azure AD(Azure Active Directory)에서 회사 또는 학교 계정에 대해 이 기능을 확장했습니다.  대체 계정을 사용하는 방법에 대한 자세한 내용은 [대체 ID](vs-alternate-identity.md) 문서를 확인하세요. 

## <a name="frequently-asked-questions"></a>질문과 대답
### <a name="q-how-can-i-contact-my-admin-about-this"></a>Q: 이에 대해 관리자에게 문의하려면 어떻게 해야 하나요?
A:  관리자에게 연락하는 방법에 대한 자세한 내용은 [구독 관리자에게 문의](contact-my-admin.md)를 참조하세요.  

## <a name="next-steps"></a>다음 단계
관리자가 Azure AD 및 MSA 계정을 연결한 후 [구독 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs)에 성공적으로 로그인할 수 있는지 확인하고 Azure DevOps, Visual Studio 및 Azure DevTest 개별 크레딧과 같은 혜택에 액세스할 수 있는지 확인하는 것이 좋습니다. 