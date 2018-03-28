---
title: 受信アダプターの SSO サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4767387c-f24b-4986-aaed-6724c5d6b347
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3c992f47ad46b4a9d5ee095ad650f6cc492179
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="sso-support-for-receive-adapters"></a><span data-ttu-id="5eeb0-102">受信アダプターの SSO のサポート</span><span class="sxs-lookup"><span data-stu-id="5eeb0-102">SSO Support for Receive Adapters</span></span>
<span data-ttu-id="5eeb0-103">エンタープライズ シングル サインオン (SSO) には、ローカル、ネットワーク、およびドメインの境界間で暗号化されたユーザーの資格情報を格納および転送するサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="5eeb0-104">トランスポート アダプター ライターは SSO API を利用して、トランスポート アダプターがバックエンドのアプリケーションにアクセスするために使用するユーザー資格情報を処理できます。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-104">Transport adapter writers can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="5eeb0-105">SSO をサポートしないトランスポート アダプターでは、一連のバックエンド アプリケーションにアクセスするために使用する資格情報で構成されている通常必要です。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="5eeb0-106">多くのバックエンド システムの場合、単一のアカウント認証ではすべてのセキュリティの実施に対応できません。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="5eeb0-107">多くのアプリケーションは、それらのアプリケーションにアクセスしているユーザーに応じて異なるアクセス権を提供します。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="5eeb0-108">アダプターは、SSO を使用して、アクセスしようとしているユーザーに基づいてエンドポイントに使用する資格情報を動的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-receive-adapters-work-with-sso"></a><span data-ttu-id="5eeb0-109">受信アダプターと SSO の連携</span><span class="sxs-lookup"><span data-stu-id="5eeb0-109">How Receive Adapters Work with SSO</span></span>  
 <span data-ttu-id="5eeb0-110">SSO をサポートする受信アダプターは、メッセージを受け取った後、および BizTalk Server にそのメッセージを公開する前に次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-110">Receive adapters that support SSO perform the following steps after receiving a message and before publishing it to BizTalk Server:</span></span>  
  
1.  <span data-ttu-id="5eeb0-111">アダプターが送信元を偽装しを使用して、送信者の代わりに SSO チケットを取得、 **ISSOTicket.IssueTicket** API です。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-111">The adapter impersonates the sender and obtains the SSO ticket on behalf of the sender by using the **ISSOTicket.IssueTicket** API.</span></span>  
  
2.  <span data-ttu-id="5eeb0-112">SSO チケットが取得できたら、アダプターはシステム名前空間の下のメッセージ コンテキスト プロパティ "SSOTicket" にその SSO チケットを保存します。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-112">After successfully obtaining an SSO ticket the adapter stores it on the message context property “SSOTicket” under the system namespace.</span></span>  
  
 <span data-ttu-id="5eeb0-113">次のコードは、チケットの取得方法と、メッセージ コンテキストへのチケットの保存方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-113">The following code fragment demonstrates how the ticket is obtained and how it is stored on the message context.</span></span>  
  
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
  
## <a name="party-resolution"></a><span data-ttu-id="5eeb0-114">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="5eeb0-114">Party Resolution</span></span>  
 <span data-ttu-id="5eeb0-115">パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ ID (SID) を、対応する構成済み BizTalk Server パーティにマップします。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-115">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="5eeb0-116">この情報が使用できるようにするアダプターでも、2 つのシステム メッセージをコンテキスト プロパティ設定する必要があります **WindowsUser** と **SignatureCertificate**, 、構成されている場合は、下流のパーティの解決コンポーネントが消費できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-116">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="5eeb0-117">**WindowsUser** redmond\myBtsUser たとえば、送信者のドメイン ユーザーを伴うプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-117">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="5eeb0-118">**SignatureCertificate** クライアント認証証明書の拇印を持つプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-118">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="5eeb0-119">パスワードの管理</span><span class="sxs-lookup"><span data-stu-id="5eeb0-119">Managing Passwords</span></span>  
 <span data-ttu-id="5eeb0-120">エンドポイントのプロパティに直接資格情報を設定する場合、バインド ファイルをエクスポートする必要があるときはパスワード フィールドが空になります。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-120">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="5eeb0-121">この場合、ユーザーはパスワードを管理者として再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-121">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="5eeb0-122">この問題を回避するには、資格情報に SSO を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-122">You can avoid this difficulty by using SSO for credentials.</span></span>  
  
 <span data-ttu-id="5eeb0-123">アダプターのエンドポイントがある場合、 **パスワード** プロパティには、実際の値をクリア テキストで SSO 構成ストア データベースに保存することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-123">If the adapter endpoint has a **Password** property, be aware that the actual value is stored in clear text in the SSO Configure Store database.</span></span> <span data-ttu-id="5eeb0-124">実際には、パスワードはユーザー インターフェイスに "\*" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-124">This is despite the fact that it is displayed in the user interface as "\*".</span></span> <span data-ttu-id="5eeb0-125">また、このプロパティはネットワークを介して転送され、BizTalk Server のサンプルの ExplorerOM を使用する単純なスクリプトでこのプロパティを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5eeb0-125">This property is also transferred through the network and a simple script using the BizTalk Server sample ExplorerOM will be able to read it.</span></span>