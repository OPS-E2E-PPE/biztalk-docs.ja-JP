---
title: "シングル サインオンと BizTalk Adapter TIBCO Enterprise Message Service for |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, processing requests
- Single Sign-On, using with adapter
- processing requests
- HTTP requests, processing
ms.assetid: 68e85ceb-bf4c-489a-a2c2-1558e718ceed
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181e54426d568857a9116aa47022adbc7788edaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="3b515-102">シングル サインオンおよび BizTalk Adapter for TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="3b515-102">Single Sign-On and BizTalk Adapter for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="3b515-103">TIBCO Enterprise Message Service (EMS) 用 Microsoft BizTalk Adapter のシングル サインオン (SSO) を使用する場合、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3b515-103">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS), the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="3b515-104">デザイン時には、アダプターが、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b515-104">At design time, the adapter obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="3b515-105">このユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b515-105">That user should be an Application User.</span></span> <span data-ttu-id="3b515-106">実行時には、SSO を使用するときにパススルーのシナリオで受信場所として Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="3b515-106">At run time, use the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when you use SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="3b515-107">要求の処理</span><span class="sxs-lookup"><span data-stu-id="3b515-107">Processing Requests</span></span>  
 <span data-ttu-id="3b515-108">インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="3b515-108">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="3b515-109">ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b515-109">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="3b515-110">このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3b515-110">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="3b515-111">次に、メッセージがメッセージ ボックス データベースに転送されます。</span><span class="sxs-lookup"><span data-stu-id="3b515-111">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="3b515-112">BizTalk Adapter for TIBCO EMS は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得します。</span><span class="sxs-lookup"><span data-stu-id="3b515-112">When BizTalk Adapter for TIBCO EMS receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="3b515-113">その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="3b515-113">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b515-114">SSO の構成は BizTalk Server のセットアップの一部として行います。</span><span class="sxs-lookup"><span data-stu-id="3b515-114">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="3b515-115">SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成したように、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="3b515-115">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="3b515-116">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3b515-116">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b515-117">参照</span><span class="sxs-lookup"><span data-stu-id="3b515-117">See Also</span></span>  
 <span data-ttu-id="3b515-118">[関連アプリケーションの作成](../core/creating-affiliate-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="3b515-118">[Creating Affiliate Applications](../core/creating-affiliate-applications5.md) </span></span>  
 [<span data-ttu-id="3b515-119">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b515-119">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)