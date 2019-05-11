---
title: シングル サインオンと BizTalk Adapter for PeopleSoft Enterprise |Microsoft Docs
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
ms.openlocfilehash: 6819b89f7c09fdf347f362f89038e732f6f24396
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393014"
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="64c2f-102">シングル サインオンと BizTalk Adapter for PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="64c2f-102">Single Sign-On and BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="64c2f-103">Microsoft BizTalk adapter for PeopleSoft Enterprise のシングル サインオン (SSO) を使用するときに、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="64c2f-103">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="64c2f-104">デザイン時に、BizTalk Adapter for PeopleSoft Enterprise は、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="64c2f-104">At design-time, BizTalk Adapter for PeopleSoft Enterprise obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the BizTalk Server project.</span></span> <span data-ttu-id="64c2f-105">そのユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c2f-105">That user should be an Application User.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="64c2f-106">要求の処理</span><span class="sxs-lookup"><span data-stu-id="64c2f-106">Processing Requests</span></span>  
 <span data-ttu-id="64c2f-107">インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="64c2f-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="64c2f-108">ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="64c2f-108">The ISAPI extension impersonates the Windows user and then calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="64c2f-109">このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="64c2f-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="64c2f-110">メッセージは、メッセージ ボックス データベースに送られます。</span><span class="sxs-lookup"><span data-stu-id="64c2f-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="64c2f-111">BizTalk Adapter for PeopleSoft Enterprises は、メッセージ ボックス データベースからメッセージを受信、ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に暗号化されたチケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="64c2f-111">When BizTalk Adapter for PeopleSoft Enterprises receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="64c2f-112">次に、アダプターは、システムに接続し、要求を処理する外部資格情報を使用してください。</span><span class="sxs-lookup"><span data-stu-id="64c2f-112">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64c2f-113">SSO の構成は、BizTalk Server のセットアップの一部です。</span><span class="sxs-lookup"><span data-stu-id="64c2f-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="64c2f-114">SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="64c2f-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="64c2f-115">ドメイン アカウントでの SSO のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="64c2f-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64c2f-116">参照</span><span class="sxs-lookup"><span data-stu-id="64c2f-116">See Also</span></span>  
 <span data-ttu-id="64c2f-117">[関連アプリケーションの作成](../core/creating-affiliate-applications2.md) </span><span class="sxs-lookup"><span data-stu-id="64c2f-117">[Creating Affiliate Applications](../core/creating-affiliate-applications2.md) </span></span>  
 [<span data-ttu-id="64c2f-118">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="64c2f-118">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)