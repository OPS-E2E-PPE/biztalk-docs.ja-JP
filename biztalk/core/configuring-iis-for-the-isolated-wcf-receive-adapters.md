---
title: 受信アダプターの IIS 分離 WCF の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- WCF services, receive adapters
- IIS, configuring [WCF receive adapters]
ms.assetid: 1c6f1561-a7ba-4eb0-8878-bf213ebcd6a6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 477afeef37fdf62ecbbd5dc78d11bcf20b5fbd48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390921"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a><span data-ttu-id="9df20-102">構成の IIS 分離 wcf 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="9df20-102">Configuring IIS for the Isolated WCF Receive Adapters</span></span>
<span data-ttu-id="9df20-103">を、BizTalk WCF サービス公開ウィザードを使用して WCF サービスを発行するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows ユーザー グループ アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9df20-103">To publish WCF services by using the BizTalk WCF Service Publishing Wizard, you must configure Internet Information Services (IIS), BizTalk isolated hosts, and Windows user group accounts.</span></span> <span data-ttu-id="9df20-104">このセクションには、Wcf-basichttp 受信アダプターなどの分離 WCF を使用した WCF サービスの公開受信アダプター用の IIS の構成に関連する問題がについて説明します、Wcf-wshttp 受信アダプター、Wcf-customisolated アダプター。</span><span class="sxs-lookup"><span data-stu-id="9df20-104">This section discusses issues related to configuring IIS for publishing WCF services with isolated WCF receive adapters such as the WCF-BasicHttp receive adapter, WCF-WSHttp receive adapter, and WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="9df20-105">IIS で WCF サービスをホストする方法の概要についてで「IIS でホスト」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700)します。</span><span class="sxs-lookup"><span data-stu-id="9df20-105">For general information about hosting WCF services in IIS, see "Hosting in IIS" at [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700).</span></span>  
  
## <a name="considerations-when-configuring-iis"></a><span data-ttu-id="9df20-106">IIS を構成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="9df20-106">Considerations When Configuring IIS</span></span>  
 <span data-ttu-id="9df20-107">**インターネット インフォメーション サービス 7.0 および 7.5**</span><span class="sxs-lookup"><span data-stu-id="9df20-107">**Internet Information Services 7.0 and 7.5**</span></span>  
  
 <span data-ttu-id="9df20-108">受信アダプターの分離 WCF を使用した WCF サービスを公開する ASP.NET 4.0 で構成されている 7.5 および IIS 7.0 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9df20-108">You can use IIS 7.0 and 7.5 configured with ASP.NET 4.0 to publish WCF services with isolated WCF receive adapters.</span></span>  
  
 <span data-ttu-id="9df20-109">(Windows Server 2008 SP2) の IIS 7.0 および IIS 7.5 (Windows Server 2008 R2) は、Web サービス要求を処理するため、IIS アプリケーション プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="9df20-109">IIS 7.0 (for Windows Server 2008 SP2) and IIS 7.5 (for Windows Server 2008 R2) use the IIS application pools for processing Web service requests.</span></span> <span data-ttu-id="9df20-110">IIS 7.0 では、複数のアプリケーション プールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9df20-110">IIS 7.0 supports multiple application pools.</span></span> <span data-ttu-id="9df20-111">各アプリケーション プール プロセスは、別のユーザー コンテキストで実行できます。</span><span class="sxs-lookup"><span data-stu-id="9df20-111">Each application pool process can run under a different user context.</span></span>  
  
 <span data-ttu-id="9df20-112">**BizTalk 分離ホスト**</span><span class="sxs-lookup"><span data-stu-id="9df20-112">**BizTalk isolated hosts**</span></span>  
  
 <span data-ttu-id="9df20-113">WCF をホストするサービスと WCF 分離受信アダプター、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9df20-113">To host the WCF services with isolated WCF receive adapters, you must create at least one isolated host in BizTalk Server.</span></span> <span data-ttu-id="9df20-114">BizTalk 分離ホストを構成する方法の詳細についてを参照してください「BizTalk 分離ホスト」 [Web サービスを有効にする](../core/enabling-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="9df20-114">For more information about how to configure BizTalk isolated hosts, see "BizTalk Isolated Hosts" in [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
 <span data-ttu-id="9df20-115">**複数のサーバー インストールでのデータベースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="9df20-115">**Database access for multiple server installations**</span></span>  
  
 <span data-ttu-id="9df20-116">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と BizTalk 管理データベースが別のサーバーに存在する、ドメイン ユーザー アカウントに、IIS アプリケーション プールのユーザー コンテキストを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9df20-116">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on different servers, you should change the user context of the IIS Application Pool to a domain user account.</span></span>  
  
 <span data-ttu-id="9df20-117">マルチ サーバー展開を実装する場合は、分離ホスト Windows グループが BizTalk データベース サーバーが属するドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9df20-117">When implementing a multi-server deployment, the Isolated Host Windows groups must exist on the domain to which the BizTalk database servers belong.</span></span>  
  
 <span data-ttu-id="9df20-118">**アカウントの特権およびユーザー権限を最小限に抑える**</span><span class="sxs-lookup"><span data-stu-id="9df20-118">**Minimizing account privileges and user rights**</span></span>  
  
 <span data-ttu-id="9df20-119">分離ホストを使用して、BizTalk Server との対話に必要なリソース量が最小限に外部プロセスへのアクセスで実行されるアダプターを与えます。</span><span class="sxs-lookup"><span data-stu-id="9df20-119">You use isolated hosts to give adapters that run in external processes access to the minimal amount of required resources to interact with BizTalk Server.</span></span> <span data-ttu-id="9df20-120">セキュリティで保護された展開は、するようにユーザー コンテキスト、外部プロセスの最小限の特権します。</span><span class="sxs-lookup"><span data-stu-id="9df20-120">For a secure deployment, you should give the user context for the external processes minimal privileges.</span></span>  
  
 <span data-ttu-id="9df20-121">**BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**</span><span class="sxs-lookup"><span data-stu-id="9df20-121">**Security recommendations for the BizTalk Web Services Publishing Wizard**</span></span>  
  
 <span data-ttu-id="9df20-122">BizTalk WCF サービス公開ウィザードによって作成された仮想ディレクトリは、親仮想ディレクトリまたは Web サイトからのアクセス制御リスト (ACL) を継承します。</span><span class="sxs-lookup"><span data-stu-id="9df20-122">The virtual directory created by the BizTalk WCF Service Publishing Wizard inherits the access control lists (ACL) from the parent virtual directory or Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df20-123">参照</span><span class="sxs-lookup"><span data-stu-id="9df20-123">See Also</span></span>  
 [<span data-ttu-id="9df20-124">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="9df20-124">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)