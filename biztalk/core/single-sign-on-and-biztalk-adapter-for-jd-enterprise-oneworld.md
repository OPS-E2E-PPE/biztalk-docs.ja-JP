---
title: シングル サインオンと BizTalk Adapter JD Enterprise OneWorld 単一 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec5be842305bbad1fb6e6963b4fcdd770a989224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393040"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a><span data-ttu-id="b88e6-102">単一でサインオンと BizTalk Adapter JD Enterprise OneWorld</span><span class="sxs-lookup"><span data-stu-id="b88e6-102">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>
<span data-ttu-id="b88e6-103">シングル サインオン (SSO) 資格情報は、SSO 資格情報データベースから取得されます。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b88e6-103">Single Sign-On (SSO) credentials are obtained from the SSO credentials database; therefore, you do not need to enter the server system's logon credentials in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="b88e6-104">デザイン時に、Microsoft BizTalk Adapter for JD Edwards OneWorld は、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b88e6-104">At design-time, Microsoft BizTalk Adapter for JD Edwards OneWorld obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="b88e6-105">そのユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b88e6-105">That user should be an Application User.</span></span>  
  
 <span data-ttu-id="b88e6-106">実行時にを使用して、BizTalk Adapter for JD Edwards OneWorld パススルーのシナリオで受信場所としての SSO を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="b88e6-106">At run time, use the BizTalk Adapter for JD Edwards OneWorld as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
 <span data-ttu-id="b88e6-107">インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="b88e6-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="b88e6-108">ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b88e6-108">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="b88e6-109">このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="b88e6-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="b88e6-110">メッセージは、メッセージ ボックス データベースに送られます。</span><span class="sxs-lookup"><span data-stu-id="b88e6-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="b88e6-111">アダプターはメッセージを受信、メッセージ ボックス データベースから、ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に、暗号化されたチケットを指定して IBTSTicket.ValidateAndRedeemTicket メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b88e6-111">When the adapter receives the message from the Message Box database, it calls the IBTSTicket.ValidateAndRedeemTicket method with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="b88e6-112">BizTalk Adapter for JD Edwards OneWorld には、外部の資格情報がシステムに接続し、要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="b88e6-112">BizTalk Adapter for JD Edwards OneWorld then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b88e6-113">SSO の構成は、BizTalk Server のセットアップの一部です。</span><span class="sxs-lookup"><span data-stu-id="b88e6-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="b88e6-114">SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、エンタープライズ SSO サービスの機能に影響するためことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b88e6-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="b88e6-115">ドメイン アカウントでの SSO のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="b88e6-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88e6-116">参照</span><span class="sxs-lookup"><span data-stu-id="b88e6-116">See Also</span></span>  
 <span data-ttu-id="b88e6-117">[関連アプリケーションの作成](../core/creating-affiliate-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="b88e6-117">[Creating Affiliate Applications](../core/creating-affiliate-applications3.md) </span></span>  
 [<span data-ttu-id="b88e6-118">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="b88e6-118">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)