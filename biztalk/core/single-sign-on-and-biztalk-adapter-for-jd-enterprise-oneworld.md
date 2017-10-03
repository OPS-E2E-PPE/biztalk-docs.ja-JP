---
title: "シングル サインオンと BizTalk Adapter JD Enterprise OneWorld for |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9d3d102c3ab79ea719587fdb3632612e75faa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a><span data-ttu-id="c6c93-102">シングル サインオンと BizTalk Adapter for JD Enterprise OneWorld</span><span class="sxs-lookup"><span data-stu-id="c6c93-102">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>
<span data-ttu-id="c6c93-103">シングル サインオン (SSO) 資格情報がデータベースから取得した、SSO 資格情報です。したがって、する必要はありませんでサーバー システムのログオン資格情報を入力する、**トランスポートのプロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-103">Single Sign-On (SSO) credentials are obtained from the SSO credentials database; therefore, you do not need to enter the server system's logon credentials in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="c6c93-104">デザイン時には、Microsoft BizTalk Adapter for JD Edwards OneWorld が、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-104">At design-time, Microsoft BizTalk Adapter for JD Edwards OneWorld obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="c6c93-105">このユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c93-105">That user should be an Application User.</span></span>  
  
 <span data-ttu-id="c6c93-106">実行時には、SSO を使用するときにパススルーのシナリオで受信場所として BizTalk Adapter for JD Edwards OneWorld を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c6c93-106">At run time, use the BizTalk Adapter for JD Edwards OneWorld as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
 <span data-ttu-id="c6c93-107">インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="c6c93-108">ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-108">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="c6c93-109">このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="c6c93-110">次に、メッセージがメッセージ ボックス データベースに転送されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="c6c93-111">アダプタは、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して IBTSTicket.ValidateAndRedeemTicket メソッドを呼び出し、ログオン資格情報を SSO ストアから取得します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-111">When the adapter receives the message from the Message Box database, it calls the IBTSTicket.ValidateAndRedeemTicket method with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="c6c93-112">その後、BizTalk Adapter for JD Edwards OneWorld は外部の資格情報を使用してシステムに接続し、要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-112">BizTalk Adapter for JD Edwards OneWorld then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6c93-113">SSO の構成は BizTalk Server のセットアップの一部として行います。</span><span class="sxs-lookup"><span data-stu-id="c6c93-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="c6c93-114">SSO エラーが発生した場合は、あるアカウントを使用したドメイン BizTalk Server を構成したときに、エンタープライズ SSO サービスの機能に影響するためことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="c6c93-115">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c93-116">参照</span><span class="sxs-lookup"><span data-stu-id="c6c93-116">See Also</span></span>  
 <span data-ttu-id="c6c93-117">[関連アプリケーションの作成](../core/creating-affiliate-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="c6c93-117">[Creating Affiliate Applications](../core/creating-affiliate-applications3.md) </span></span>  
 [<span data-ttu-id="c6c93-118">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-118">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)