---
title: "シングル サインオンと BizTalk Adapter TIBCO Rendezvous for |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, using with the adapter
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: 52e698bb-38ba-4a12-b15a-d1581061d62f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54529d8eefb351471ea1c2bd7278c744737b66f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="f8aca-102">シングル サインオンと BizTalk Adapter for TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="f8aca-102">Single Sign-On and BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="f8aca-103">シングル サインオン (SSO) を Microsoft BizTalk Adapter for TIBCO Rendezvous を使用するときに、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="f8aca-103">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="f8aca-104">デザイン時には、アダプターが、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="f8aca-104">At design time, the adapter obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="f8aca-105">このユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8aca-105">That user should be an Application User.</span></span> <span data-ttu-id="f8aca-106">実行時には、SSO を使用するときにパススルーのシナリオで受信場所として [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="f8aca-106">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when you use SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="f8aca-107">要求の処理</span><span class="sxs-lookup"><span data-stu-id="f8aca-107">Processing Requests</span></span>  
 <span data-ttu-id="f8aca-108">インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="f8aca-108">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="f8aca-109">ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="f8aca-109">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="f8aca-110">このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f8aca-110">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="f8aca-111">次に、メッセージがメッセージ ボックス データベースに転送されます。</span><span class="sxs-lookup"><span data-stu-id="f8aca-111">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="f8aca-112">BizTalk Adapter for TIBCO Rendezvous は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して `ValidateAndRedeemTicket` を呼び出し、ログオン資格情報を SSO ストアから取得します。</span><span class="sxs-lookup"><span data-stu-id="f8aca-112">When BizTalk Adapter for TIBCO Rendezvous receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="f8aca-113">その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="f8aca-113">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8aca-114">SSO の構成は BizTalk Server のセットアップの一部として行います。</span><span class="sxs-lookup"><span data-stu-id="f8aca-114">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="f8aca-115">SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成したように、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="f8aca-115">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="f8aca-116">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f8aca-116">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8aca-117">参照</span><span class="sxs-lookup"><span data-stu-id="f8aca-117">See Also</span></span>  
 <span data-ttu-id="f8aca-118">[関連アプリケーションの作成](../core/creating-affiliate-applications1.md) </span><span class="sxs-lookup"><span data-stu-id="f8aca-118">[Creating Affiliate Applications](../core/creating-affiliate-applications1.md) </span></span>  
 [<span data-ttu-id="f8aca-119">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8aca-119">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)