---
title: シングル サインオンと BizTalk Adapter for TIBCO Rendezvous |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52e698bb-38ba-4a12-b15a-d1581061d62f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5e50dbdb6cb673ed3dd125040317e56570cc48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392981"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="24251-102">シングル サインオンと BizTalk Adapter for TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="24251-102">Single Sign-On and BizTalk Adapter for TIBCO Rendezvous</span></span>

## <a name="overview"></a><span data-ttu-id="24251-103">概要</span><span class="sxs-lookup"><span data-stu-id="24251-103">Overview</span></span>
<span data-ttu-id="24251-104">Microsoft BizTalk Adapter for TIBCO Rendezvous シングル サインオン (SSO) を使用すると、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="24251-104">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="24251-105">デザイン時に、アダプターは、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="24251-105">At design time, the adapter obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="24251-106">そのユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="24251-106">That user should be an Application User.</span></span> <span data-ttu-id="24251-107">実行時に、使用、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターが SSO を使用する場合は、パススルーのシナリオで受信場所として。</span><span class="sxs-lookup"><span data-stu-id="24251-107">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when you use SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="24251-108">要求の処理</span><span class="sxs-lookup"><span data-stu-id="24251-108">Processing Requests</span></span>  
 <span data-ttu-id="24251-109">インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="24251-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="24251-110">ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="24251-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="24251-111">このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="24251-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="24251-112">メッセージは、メッセージ ボックス データベースに送られます。</span><span class="sxs-lookup"><span data-stu-id="24251-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="24251-113">BizTalk Adapter for TIBCO Rendezvous がメッセージ ボックス データベースからメッセージを受け取るときに呼び出す`ValidateAndRedeemTicket`ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に暗号化されたチケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24251-113">When BizTalk Adapter for TIBCO Rendezvous receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="24251-114">次に、アダプターは、システムに接続し、要求を処理する外部資格情報を使用してください。</span><span class="sxs-lookup"><span data-stu-id="24251-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24251-115">SSO の構成は、BizTalk Server のセットアップの一部です。</span><span class="sxs-lookup"><span data-stu-id="24251-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="24251-116">SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="24251-116">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="24251-117">ドメイン アカウントでの SSO のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="24251-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24251-118">参照</span><span class="sxs-lookup"><span data-stu-id="24251-118">See Also</span></span>  
 <span data-ttu-id="24251-119">[関連アプリケーションの作成](../core/creating-affiliate-applications1.md) </span><span class="sxs-lookup"><span data-stu-id="24251-119">[Creating Affiliate Applications](../core/creating-affiliate-applications1.md) </span></span>  
[<span data-ttu-id="24251-120">Security</span><span class="sxs-lookup"><span data-stu-id="24251-120">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)