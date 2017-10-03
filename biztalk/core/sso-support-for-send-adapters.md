---
title: "送信アダプターの SSO のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d590ada6b8ee80c942714a698d0001c207ac6751
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-support-for-send-adapters"></a><span data-ttu-id="997ac-102">送信アダプター用の SSO サポート</span><span class="sxs-lookup"><span data-stu-id="997ac-102">SSO Support for Send Adapters</span></span>
<span data-ttu-id="997ac-103">エンタープライズ シングル サインオン (SSO) には、ローカル、ネットワーク、およびドメインの境界間で暗号化されたユーザーの資格情報を格納および転送するサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="997ac-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="997ac-104">トランスポート アダプターを作成する場合は、SSO API を利用して、トランスポート アダプターがバックエンドのアプリケーションにアクセスするために使用するユーザーの資格情報を処理できます。</span><span class="sxs-lookup"><span data-stu-id="997ac-104">When you create a transport adapter, you can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="997ac-105">SSO をサポートしないトランスポート アダプターは、通常、1 セットのバックエンド アプリケーションにアクセスするために使用する資格情報を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="997ac-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="997ac-106">多くのバックエンド システムの場合、単一のアカウント認証ではすべてのセキュリティの実施に対応できません。</span><span class="sxs-lookup"><span data-stu-id="997ac-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="997ac-107">多くのアプリケーションは、それらのアプリケーションにアクセスしているユーザーに応じて異なるアクセス権を提供します。</span><span class="sxs-lookup"><span data-stu-id="997ac-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="997ac-108">アダプターは、SSO を使用して、アクセスしようとしているユーザーに基づいてエンドポイントに使用する資格情報を動的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="997ac-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-send-adapters-work-with-sso"></a><span data-ttu-id="997ac-109">送信アダプターと SSO の連携</span><span class="sxs-lookup"><span data-stu-id="997ac-109">How Send Adapters Work with SSO</span></span>  
 <span data-ttu-id="997ac-110">SSO をサポートするアダプターを検証し、チケットを引き換えるし、を使用して、SSO システムからユーザーの資格情報を取得送信、 **ISSOTicket.ValidateAndRedeemTicket** API です。</span><span class="sxs-lookup"><span data-stu-id="997ac-110">Send adapters that support SSO validate and redeem the ticket and obtain the user credentials from the SSO system by using the **ISSOTicket.ValidateAndRedeemTicket** API.</span></span> <span data-ttu-id="997ac-111">アダプターは、取得した資格情報を使用して送信先エンドポイントを認証します。</span><span class="sxs-lookup"><span data-stu-id="997ac-111">The adapter uses the obtained credentials to authenticate with the destination endpoint.</span></span>  
  
 <span data-ttu-id="997ac-112">次のコードは、送信アダプターが SSO システムからユーザーの資格情報を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="997ac-112">The following code fragment demonstrates how a send adapter obtains the user credentials from the SSO system:</span></span>  
  
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
  
## <a name="party-resolution"></a><span data-ttu-id="997ac-113">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="997ac-113">Party Resolution</span></span>  
 <span data-ttu-id="997ac-114">パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ ID (SID) を、対応する構成済み BizTalk Server パーティにマップします。</span><span class="sxs-lookup"><span data-stu-id="997ac-114">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="997ac-115">この情報が使用できるようにするアダプターがコンテキスト プロパティには、2 つのシステム メッセージの設定する必要があります**WindowsUser**と**SignatureCertificate**、下流のパーティの解決が使用します。構成されている場合のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="997ac-115">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="997ac-116">**WindowsUser**プロパティには、たとえば redmond\myBtsUser、送信者のドメイン ユーザーが設定されます。</span><span class="sxs-lookup"><span data-stu-id="997ac-116">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="997ac-117">**SignatureCertificate**プロパティには、クライアント認証証明書の拇印が設定されます。</span><span class="sxs-lookup"><span data-stu-id="997ac-117">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="997ac-118">パスワードを管理します。</span><span class="sxs-lookup"><span data-stu-id="997ac-118">Managing passwords</span></span>  
 <span data-ttu-id="997ac-119">エンドポイントのプロパティに直接資格情報を設定する場合、バインド ファイルをエクスポートする必要があるときはパスワード フィールドが空になります。</span><span class="sxs-lookup"><span data-stu-id="997ac-119">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="997ac-120">この場合、ユーザーはパスワードを管理者として再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="997ac-120">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="997ac-121">この問題を回避するには、資格情報に SSO を使用します。</span><span class="sxs-lookup"><span data-stu-id="997ac-121">You can avoid this difficulty by using SSO for credentials.</span></span>