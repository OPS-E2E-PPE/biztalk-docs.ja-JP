---
title: JD Edwards EnterpriseOne の 1 つのシングル サインオンと BizTalk Adapter |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83fefe6ae447a5f68c9516e6fb92ab6e1c0b0614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393029"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="067e3-102">JD Edwards EnterpriseOne の 1 つのシングル サインオンと BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="067e3-102">Single Sign-On and BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="067e3-103">シングル サインオン (SSO) を Microsoft Adapter for JD Edwards EnterpriseOne を使用する場合、アダプターは SSO 資格情報データベースから資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="067e3-103">When you use Single Sign-On (SSO) with Microsoft   Adapter for JD Edwards EnterpriseOne, the adapter obtains the credentials from the SSO Credentials database.</span></span> <span data-ttu-id="067e3-104">そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="067e3-104">Therefore, you do not need to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="067e3-105">デザイン時に、BizTalk Adapter for JD Edwards EnterpriseOne が開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="067e3-105">At design-time, BizTalk Adapter for JD Edwards EnterpriseOne obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="067e3-106">そのユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="067e3-106">That user should be an Application User.</span></span> <span data-ttu-id="067e3-107">実行時に、使用、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターが SSO を使用する場合は、パススルーのシナリオで受信場所として。</span><span class="sxs-lookup"><span data-stu-id="067e3-107">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="067e3-108">要求の処理</span><span class="sxs-lookup"><span data-stu-id="067e3-108">Processing Requests</span></span>  
 <span data-ttu-id="067e3-109">インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="067e3-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="067e3-110">ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="067e3-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="067e3-111">このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="067e3-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="067e3-112">メッセージは、メッセージ ボックス データベースに送られます。</span><span class="sxs-lookup"><span data-stu-id="067e3-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="067e3-113">BizTalk Adapter for JD Edwards EnterpriseOne では、メッセージ ボックス データベースからメッセージを受け取るときに呼び出す`ValidateAndRedeemTicket`ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に暗号化されたチケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="067e3-113">When BizTalk Adapter for JD Edwards EnterpriseOne receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="067e3-114">次に、アダプターは、システムに接続し、要求を処理する外部資格情報を使用してください。</span><span class="sxs-lookup"><span data-stu-id="067e3-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="067e3-115">SSO の構成は、BizTalk Server のセットアップの一部です。</span><span class="sxs-lookup"><span data-stu-id="067e3-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="067e3-116">SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="067e3-116">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="067e3-117">ドメイン アカウントでの SSO のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="067e3-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067e3-118">参照</span><span class="sxs-lookup"><span data-stu-id="067e3-118">See Also</span></span>  
 <span data-ttu-id="067e3-119">[関連アプリケーションの作成](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="067e3-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="067e3-120">BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="067e3-120">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)