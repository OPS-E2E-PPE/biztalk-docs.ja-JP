---
title: 受信アダプターの SSO サポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4767387c-f24b-4986-aaed-6724c5d6b347
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edfd57afb1eba520c6ae0211cbb6bc0e90922d59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398975"
---
# <a name="sso-support-for-receive-adapters"></a><span data-ttu-id="69beb-102">受信アダプターの SSO のサポート</span><span class="sxs-lookup"><span data-stu-id="69beb-102">SSO Support for Receive Adapters</span></span>
<span data-ttu-id="69beb-103">エンタープライズ シングル サインオン (SSO) では、暗号化されたユーザー資格情報をローカル、ネットワーク、およびドメインの境界を格納および転送するサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="69beb-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="69beb-104">トランスポート アダプター ライターは、トランスポート アダプターがバックエンド アプリケーションへのアクセスに使用するユーザーの資格情報を処理するために SSO Api を活用できます。</span><span class="sxs-lookup"><span data-stu-id="69beb-104">Transport adapter writers can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="69beb-105">SSO をサポートしないトランスポート アダプターは、通常、バックエンド アプリケーションにアクセスするために使用する資格情報の 1 つのセットで構成される必要です。</span><span class="sxs-lookup"><span data-stu-id="69beb-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="69beb-106">多くのバックエンド システムでは、1 つのアカウントの認証がすべてのセキュリティの実施を満たしていません。</span><span class="sxs-lookup"><span data-stu-id="69beb-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="69beb-107">多くのアプリケーションでは、それらにアクセスしているユーザーに応じて異なるアクセス権を提供します。</span><span class="sxs-lookup"><span data-stu-id="69beb-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="69beb-108">SSO により、アダプターを動的にアクセスしようとしたユーザーに基づくエンドポイントに使用する資格情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="69beb-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-receive-adapters-work-with-sso"></a><span data-ttu-id="69beb-109">アダプターと SSO の連携を受け取る方法</span><span class="sxs-lookup"><span data-stu-id="69beb-109">How Receive Adapters Work with SSO</span></span>  
 <span data-ttu-id="69beb-110">受信アダプターがメッセージを受け取った後、BizTalk Server に発行する前に、SSO のサポートが次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="69beb-110">Receive adapters that support SSO perform the following steps after receiving a message and before publishing it to BizTalk Server:</span></span>  
  
1. <span data-ttu-id="69beb-111">アダプターが、送信側を偽装しを使用して送信者の代わりに SSO チケットを取得、 **ISSOTicket.IssueTicket** API。</span><span class="sxs-lookup"><span data-stu-id="69beb-111">The adapter impersonates the sender and obtains the SSO ticket on behalf of the sender by using the **ISSOTicket.IssueTicket** API.</span></span>  
  
2. <span data-ttu-id="69beb-112">SSO チケットを正常に取得した後、アダプターは、それをメッセージ コンテキスト プロパティ"SSOTicket"システム名前空間の下で格納します。</span><span class="sxs-lookup"><span data-stu-id="69beb-112">After successfully obtaining an SSO ticket the adapter stores it on the message context property “SSOTicket” under the system namespace.</span></span>  
  
   <span data-ttu-id="69beb-113">次のコード フラグメントは、チケットを取得する方法と、メッセージ コンテキストに格納する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="69beb-113">The following code fragment demonstrates how the ticket is obtained and how it is stored on the message context.</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                         IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_SSOToken = null;  
  
 // Get a ticket for the sender  
     private void GetSSOTicket(IntPtr token)  
     {  
       bool impersonated = false;  
      WindowsImpersonationContext wic = null;  
  
 if (token != (IntPtr)0)   
 {  
     try   
 {  
         // Impersonate the user using his security  
 // token  
            WindowsIdentity wi =   
 new WindowsIdentity(token);  
            wic = wi.Impersonate();  
            impersonated = true;  
  
         // Get an SSO ticket for the impersonated  
 // user  
            ISSOTicket ssoTicket = new ISSOTicket();  
            m_SSOToken = ssoTicket.IssueTicket(0);  
         }  
         finally   
 {  
           if (impersonated)  
            // Revert the impersonation  
            wic.Undo();  
          }  
}  
}  
...  
  
     private void WriteSSOTicketToContext(  
 IBaseMessage message )  
     {  
         if (m_SSOTicket != null)   
 {  
 // Write the SSO ticket to the message context  
          message.Context.Write(  
 “SSOTicket”,  
 http://schemas.microsoft.com/BizTalk/2003/system-properties,   
 m_SSOToken);  
        }  
      }  
}  
```  
  
## <a name="party-resolution"></a><span data-ttu-id="69beb-114">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="69beb-114">Party Resolution</span></span>  
 <span data-ttu-id="69beb-115">パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ識別子 (SID) を対応する構成済みの BizTalk Server パーティにマップします。</span><span class="sxs-lookup"><span data-stu-id="69beb-115">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="69beb-116">この情報が使用できるようにするアダプター設定の 2 つのシステム メッセージ コンテキスト プロパティでは、必要があります**WindowsUser**と**SignatureCertificate**、下流のパーティの解決で使用するにはコンポーネントは構成されている場合。</span><span class="sxs-lookup"><span data-stu-id="69beb-116">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="69beb-117">**WindowsUser** redmond\myBtsUser など、送信者のドメイン ユーザーとプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="69beb-117">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="69beb-118">**SignatureCertificate**クライアント認証証明書の拇印を持つプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="69beb-118">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="69beb-119">パスワードの管理</span><span class="sxs-lookup"><span data-stu-id="69beb-119">Managing Passwords</span></span>  
 <span data-ttu-id="69beb-120">エンドポイントのプロパティに直接資格情報を配置する場合、パスワード フィールドが空になります、バインド ファイルをエクスポートする必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="69beb-120">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="69beb-121">管理者としてパスワードを再入力をユーザーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="69beb-121">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="69beb-122">SSO 資格情報を使用すると、この問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="69beb-122">You can avoid this difficulty by using SSO for credentials.</span></span>  
  
 <span data-ttu-id="69beb-123">アダプターのエンドポイントがある場合、**パスワード**プロパティ、実際の値がクリア テキストで、SSO 構成ストア データベースに格納されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="69beb-123">If the adapter endpoint has a **Password** property, be aware that the actual value is stored in clear text in the SSO Configure Store database.</span></span> <span data-ttu-id="69beb-124">これは、ファクトとしてユーザー インターフェイスに表示されることに関係なく、"\*"。</span><span class="sxs-lookup"><span data-stu-id="69beb-124">This is despite the fact that it is displayed in the user interface as "\*".</span></span> <span data-ttu-id="69beb-125">このプロパティはネットワークを介して転送もと、BizTalk Server サンプルの ExplorerOM を使用して単純なスクリプトが読み取ることになります。</span><span class="sxs-lookup"><span data-stu-id="69beb-125">This property is also transferred through the network and a simple script using the BizTalk Server sample ExplorerOM will be able to read it.</span></span>