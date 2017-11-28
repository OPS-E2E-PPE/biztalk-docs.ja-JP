---
title: "シングル サインオンと BizTalk Adapter JD Edwards EnterpriseOne for |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182e73ed45a1473286a301cf859e619cc5d21287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="9b8c9-102">シングル サインオンと BizTalk Adapter for JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="9b8c9-102">Single Sign-On and BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="9b8c9-103">Microsoft Adapter for JD Edwards EnterpriseOne でシングル サインオン (SSO) を使用すると、アダプターは SSO 資格情報データベースから資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-103">When you use Single Sign-On (SSO) with Microsoft   Adapter for JD Edwards EnterpriseOne, the adapter obtains the credentials from the SSO Credentials database.</span></span> <span data-ttu-id="9b8c9-104">したがって、する必要はありませんでサーバー システムのログオン資格情報を入力する、**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-104">Therefore, you do not need to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="9b8c9-105">デザイン時には、BizTalk Adapter for JD Edwards OneWorld が、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-105">At design-time, BizTalk Adapter for JD Edwards EnterpriseOne obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="9b8c9-106">このユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-106">That user should be an Application User.</span></span> <span data-ttu-id="9b8c9-107">実行時には、SSO を使用するときにパススルーのシナリオで、受信場所として [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-107">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="9b8c9-108">要求の処理</span><span class="sxs-lookup"><span data-stu-id="9b8c9-108">Processing Requests</span></span>  
 <span data-ttu-id="9b8c9-109">インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="9b8c9-110">ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="9b8c9-111">このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="9b8c9-112">次に、メッセージがメッセージ ボックス データベースに転送されます。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="9b8c9-113">BizTalk Adapter for JD Edwards EnterpriseOne は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して `ValidateAndRedeemTicket` を呼び出し、SSO ストアからログオン資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-113">When BizTalk Adapter for JD Edwards EnterpriseOne receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="9b8c9-114">その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b8c9-115">SSO の構成は BizTalk Server のセットアップの一部として行います。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="9b8c9-116">SSO エラーが発生した場合、アカウントを使用したドメイン BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-116">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="9b8c9-117">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8c9-118">参照</span><span class="sxs-lookup"><span data-stu-id="9b8c9-118">See Also</span></span>  
 <span data-ttu-id="9b8c9-119">[関連アプリケーションの作成](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="9b8c9-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="9b8c9-120">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b8c9-120">Using Single Sign-On</span></span>](../core/using-single-sign-on1.md)