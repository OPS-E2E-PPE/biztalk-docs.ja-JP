---
title: SSO と BizTalk Adapter for TIBCO Enterprise メッセージ サービス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68e85ceb-bf4c-489a-a2c2-1558e718ceed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 577fa596fadee68c94dfa510de101d01b0ab06e4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013417"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="fa12b-102">シングル サインオンおよび BizTalk Adapter for TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="fa12b-102">Single Sign-On and BizTalk Adapter for TIBCO Enterprise Message Service</span></span>

## <a name="overview"></a><span data-ttu-id="fa12b-103">概要</span><span class="sxs-lookup"><span data-stu-id="fa12b-103">Overview</span></span>
<span data-ttu-id="fa12b-104">TIBCO Enterprise Message Service (EMS) 用 Microsoft BizTalk Adapter のシングル サインオン (SSO) を使用する場合、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="fa12b-104">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS), the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="fa12b-105">デザイン時には、アダプターが、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa12b-105">At design time, the adapter obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="fa12b-106">このユーザーは、アプリケーション ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa12b-106">That user should be an Application User.</span></span> <span data-ttu-id="fa12b-107">実行時には、SSO を使用するときにパススルーのシナリオで受信場所として Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fa12b-107">At run time, use the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when you use SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="fa12b-108">要求の処理</span><span class="sxs-lookup"><span data-stu-id="fa12b-108">Processing Requests</span></span>  
 <span data-ttu-id="fa12b-109">インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="fa12b-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="fa12b-110">ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="fa12b-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="fa12b-111">このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="fa12b-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="fa12b-112">次に、メッセージがメッセージ ボックス データベースに転送されます。</span><span class="sxs-lookup"><span data-stu-id="fa12b-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="fa12b-113">BizTalk Adapter for TIBCO EMS は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得します。</span><span class="sxs-lookup"><span data-stu-id="fa12b-113">When BizTalk Adapter for TIBCO EMS receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="fa12b-114">その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="fa12b-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa12b-115">SSO の構成は BizTalk Server のセットアップの一部として行います。</span><span class="sxs-lookup"><span data-stu-id="fa12b-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="fa12b-116">SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成したように、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="fa12b-116">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="fa12b-117">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fa12b-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa12b-118">参照</span><span class="sxs-lookup"><span data-stu-id="fa12b-118">See Also</span></span>  
 <span data-ttu-id="fa12b-119">[関連アプリケーションの作成](../core/creating-affiliate-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="fa12b-119">[Creating Affiliate Applications](../core/creating-affiliate-applications5.md) </span></span>  
 [<span data-ttu-id="fa12b-120">アダプターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="fa12b-120">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)