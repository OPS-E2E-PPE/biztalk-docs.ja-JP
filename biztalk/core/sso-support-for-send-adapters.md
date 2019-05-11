---
title: 送信アダプターの SSO のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efe1b6eac59478dea5e7ba56351c543c04f8c223
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398960"
---
# <a name="sso-support-for-send-adapters"></a><span data-ttu-id="63e71-102">送信アダプター用の SSO サポート</span><span class="sxs-lookup"><span data-stu-id="63e71-102">SSO Support for Send Adapters</span></span>
<span data-ttu-id="63e71-103">エンタープライズ シングル サインオン (SSO) では、暗号化されたユーザー資格情報をローカル、ネットワーク、およびドメインの境界を格納および転送するサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="63e71-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="63e71-104">トランスポート アダプターを作成する場合は、トランスポート アダプターがバックエンド アプリケーションへのアクセスに使用するユーザーの資格情報を処理するために SSO Api を利用できます。</span><span class="sxs-lookup"><span data-stu-id="63e71-104">When you create a transport adapter, you can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="63e71-105">SSO をサポートしないトランスポート アダプターは、通常、バックエンド アプリケーションにアクセスするために使用する資格情報の 1 つのセットで構成される必要です。</span><span class="sxs-lookup"><span data-stu-id="63e71-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="63e71-106">多くのバックエンド システムでは、1 つのアカウントの認証がすべてのセキュリティの実施を満たしていません。</span><span class="sxs-lookup"><span data-stu-id="63e71-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="63e71-107">多くのアプリケーションでは、それらにアクセスしているユーザーに応じて異なるアクセス権を提供します。</span><span class="sxs-lookup"><span data-stu-id="63e71-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="63e71-108">SSO により、アダプターを動的にアクセスしようとしたユーザーに基づくエンドポイントに使用する資格情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="63e71-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-send-adapters-work-with-sso"></a><span data-ttu-id="63e71-109">アダプターと SSO の連携を送信する方法</span><span class="sxs-lookup"><span data-stu-id="63e71-109">How Send Adapters Work with SSO</span></span>  
 <span data-ttu-id="63e71-110">送信の SSO をサポートするアダプターを検証し、チケットを引き換えるし、を使用して、SSO システムからユーザーの資格情報を取得、 **ISSOTicket.ValidateAndRedeemTicket** API。</span><span class="sxs-lookup"><span data-stu-id="63e71-110">Send adapters that support SSO validate and redeem the ticket and obtain the user credentials from the SSO system by using the **ISSOTicket.ValidateAndRedeemTicket** API.</span></span> <span data-ttu-id="63e71-111">アダプターは、送信先エンドポイントに対する認証を取得した資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="63e71-111">The adapter uses the obtained credentials to authenticate with the destination endpoint.</span></span>  
  
 <span data-ttu-id="63e71-112">次のコード フラグメントでは、送信アダプターが SSO システムからユーザーの資格情報を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63e71-112">The following code fragment demonstrates how a send adapter obtains the user credentials from the SSO system:</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                        IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_UserName = null;  
     private string m_UserPassword = null;  
  
 // Get user credentials from SSO  
 // AffiliateAppVal is the name of SSO affiliate   
 // application for the specific destination endpoint  
     private void GetUserCredentials(  
 IBaseMessage message,   
 string AffiliateAppVal )  
     {  
 string creds[] = null;  
 string externalUserName = null;  
  
 ISSOTicket ssoTicket = new ISSOTicket();  
 creds = ssoTicket.ValidateAndRedeemTicket(  
 message,   
 AffiliateAppVal,   
 0,   
 out externalUserName);  
  
 m_UserName = externalUserName;  
 m_UserPassword = creds[0];  
     }  
...  
}  
```  
  
## <a name="party-resolution"></a><span data-ttu-id="63e71-113">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="63e71-113">Party Resolution</span></span>  
 <span data-ttu-id="63e71-114">パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ識別子 (SID) を対応する構成済みの BizTalk Server パーティにマップします。</span><span class="sxs-lookup"><span data-stu-id="63e71-114">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="63e71-115">この情報が使用できるようにするアダプター設定の 2 つのシステム メッセージ コンテキスト プロパティでは、必要があります**WindowsUser**と**SignatureCertificate**、下流のパーティの解決で使用するにはコンポーネントは構成されている場合。</span><span class="sxs-lookup"><span data-stu-id="63e71-115">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="63e71-116">**WindowsUser** redmond\myBtsUser など、送信者のドメイン ユーザーとプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="63e71-116">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="63e71-117">**SignatureCertificate**クライアント認証証明書の拇印を持つプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="63e71-117">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="63e71-118">パスワードの管理</span><span class="sxs-lookup"><span data-stu-id="63e71-118">Managing passwords</span></span>  
 <span data-ttu-id="63e71-119">エンドポイントのプロパティに直接資格情報を配置する場合、パスワード フィールドが空になります、バインド ファイルをエクスポートする必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="63e71-119">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="63e71-120">管理者としてパスワードを再入力をユーザーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="63e71-120">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="63e71-121">SSO 資格情報を使用すると、この問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="63e71-121">You can avoid this difficulty by using SSO for credentials.</span></span>