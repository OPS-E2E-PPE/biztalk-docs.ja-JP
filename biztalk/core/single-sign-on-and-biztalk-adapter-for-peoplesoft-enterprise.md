---
title: PeopleSoft Enterprise の単一のサインオンと BizTalk Adapter |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing HTTP requests
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: d8ad75f1-a83f-4722-a43f-50dc95df2f9d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb898906bfd3087ef909e59990a16ce16c2822c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015601"
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="3fd25-102">シングル サインオンと BizTalk Adapter for PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="3fd25-102">Single Sign-On and BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="3fd25-103">シングル サインオン (SSO) を Microsoft BizTalk Adapter for PeopleSoft Enterprise を使用するときに、アダプターが SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ**] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3fd25-103">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="3fd25-104">デザイン時には、BizTalk Adapter for PeopleSoft Enterprise が、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3fd25-104">At design-time, BizTalk Adapter for PeopleSoft Enterprise obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the BizTalk Server project.</span></span> <span data-ttu-id="3fd25-105">このユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fd25-105">That user should be an Application User.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="3fd25-106">要求の処理</span><span class="sxs-lookup"><span data-stu-id="3fd25-106">Processing Requests</span></span>  
 <span data-ttu-id="3fd25-107">インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="3fd25-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="3fd25-108">ISAPI 拡張が Windows ユーザーの権限を借用し、SSO 資格情報ストアを呼び出して、暗号化されたチケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="3fd25-108">The ISAPI extension impersonates the Windows user and then calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="3fd25-109">このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3fd25-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="3fd25-110">次に、メッセージがメッセージ ボックス データベースに転送されます。</span><span class="sxs-lookup"><span data-stu-id="3fd25-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="3fd25-111">BizTalk Adapter for PeopleSoft Enterprises は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得します。</span><span class="sxs-lookup"><span data-stu-id="3fd25-111">When BizTalk Adapter for PeopleSoft Enterprises receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="3fd25-112">その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="3fd25-112">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fd25-113">SSO の構成は BizTalk Server のセットアップの一部として行います。</span><span class="sxs-lookup"><span data-stu-id="3fd25-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="3fd25-114">SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成したように、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="3fd25-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="3fd25-115">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3fd25-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd25-116">参照</span><span class="sxs-lookup"><span data-stu-id="3fd25-116">See Also</span></span>  
 <span data-ttu-id="3fd25-117">[関連アプリケーションの作成](../core/creating-affiliate-applications2.md) </span><span class="sxs-lookup"><span data-stu-id="3fd25-117">[Creating Affiliate Applications](../core/creating-affiliate-applications2.md) </span></span>  
 [<span data-ttu-id="3fd25-118">アダプターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="3fd25-118">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)