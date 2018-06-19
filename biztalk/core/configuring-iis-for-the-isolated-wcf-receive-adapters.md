---
title: 構成の IIS 分離 wcf 受信アダプター |Microsoft ドキュメント
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
ms.openlocfilehash: 1515a69ab6a9150668db4f3415f0483dd1ce4e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233370"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a><span data-ttu-id="a27a9-102">分離 WCF 受信アダプターのための IIS の構成</span><span class="sxs-lookup"><span data-stu-id="a27a9-102">Configuring IIS for the Isolated WCF Receive Adapters</span></span>
<span data-ttu-id="a27a9-103">BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows のユーザー グループ アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a27a9-103">To publish WCF services by using the BizTalk WCF Service Publishing Wizard, you must configure Internet Information Services (IIS), BizTalk isolated hosts, and Windows user group accounts.</span></span> <span data-ttu-id="a27a9-104">ここでは、WCF-BasicHttp 受信アダプター、WCF-WSHttp 受信アダプター、WCF-CustomIsolated アダプターなどの分離 WCF 受信アダプターを使用して WCF サービスを公開するための IIS の構成に関連する問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="a27a9-104">This section discusses issues related to configuring IIS for publishing WCF services with isolated WCF receive adapters such as the WCF-BasicHttp receive adapter, WCF-WSHttp receive adapter, and WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="a27a9-105">詳細については、IIS で WCF サービスをホストしているを参照してください「IIS でホストしている」 [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700)です。</span><span class="sxs-lookup"><span data-stu-id="a27a9-105">For general information about hosting WCF services in IIS, see "Hosting in IIS" at [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700).</span></span>  
  
## <a name="considerations-when-configuring-iis"></a><span data-ttu-id="a27a9-106">IIS を構成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="a27a9-106">Considerations When Configuring IIS</span></span>  
 <span data-ttu-id="a27a9-107">**インターネット インフォメーション サービス 7.0 および 7.5**</span><span class="sxs-lookup"><span data-stu-id="a27a9-107">**Internet Information Services 7.0 and 7.5**</span></span>  
  
 <span data-ttu-id="a27a9-108">分離 WCF 受信アダプターを使用して WCF サービスを公開するには、ASP.NET 4.0 を使用するように構成された IIS 7.0 または 7.5 を使用します。</span><span class="sxs-lookup"><span data-stu-id="a27a9-108">You can use IIS 7.0 and 7.5 configured with ASP.NET 4.0 to publish WCF services with isolated WCF receive adapters.</span></span>  
  
 <span data-ttu-id="a27a9-109">IIS 7.0 (Windows Server 2008 SP2 の場合) および IIS 7.5 (Windows Server 2008 R2 の場合) は、IIS アプリケーション プールを使用して Web サービス要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="a27a9-109">IIS 7.0 (for Windows Server 2008 SP2) and IIS 7.5 (for Windows Server 2008 R2) use the IIS application pools for processing Web service requests.</span></span> <span data-ttu-id="a27a9-110">IIS 7.0 は、複数のアプリケーション プールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a27a9-110">IIS 7.0 supports multiple application pools.</span></span> <span data-ttu-id="a27a9-111">それぞれのアプリケーション プールは、異なるユーザー コンテキストで実行できます。</span><span class="sxs-lookup"><span data-stu-id="a27a9-111">Each application pool process can run under a different user context.</span></span>  
  
 <span data-ttu-id="a27a9-112">**BizTalk 分離ホスト**</span><span class="sxs-lookup"><span data-stu-id="a27a9-112">**BizTalk isolated hosts**</span></span>  
  
 <span data-ttu-id="a27a9-113">分離 WCF 受信アダプターを使用して WFC サービスをホストするには、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a27a9-113">To host the WCF services with isolated WCF receive adapters, you must create at least one isolated host in BizTalk Server.</span></span> <span data-ttu-id="a27a9-114">BizTalk 分離ホストを構成する方法の詳細についてを参照してください「BizTalk 分離ホスト」 [Web サービスを有効にすると](../core/enabling-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="a27a9-114">For more information about how to configure BizTalk isolated hosts, see "BizTalk Isolated Hosts" in [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
 <span data-ttu-id="a27a9-115">**複数のサーバー インストールでのデータベースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="a27a9-115">**Database access for multiple server installations**</span></span>  
  
 <span data-ttu-id="a27a9-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および BizTalk 管理データベースが異なるサーバーに存在する場合、IIS アプリケーション プールのユーザー コンテキストをドメイン ユーザー アカウントに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a27a9-116">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on different servers, you should change the user context of the IIS Application Pool to a domain user account.</span></span>  
  
 <span data-ttu-id="a27a9-117">マルチサーバー展開を実装する場合、分離ホスト Windows グループは BizTalk データベース サーバーが属するドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a27a9-117">When implementing a multi-server deployment, the Isolated Host Windows groups must exist on the domain to which the BizTalk database servers belong.</span></span>  
  
 <span data-ttu-id="a27a9-118">**アカウントの特権およびユーザー権限を最小限に抑える**</span><span class="sxs-lookup"><span data-stu-id="a27a9-118">**Minimizing account privileges and user rights**</span></span>  
  
 <span data-ttu-id="a27a9-119">分離ホストを使用すると、外部プロセスで実行するアダプターに、BizTalk Server との連携に必要な最小限のリソースへのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="a27a9-119">You use isolated hosts to give adapters that run in external processes access to the minimal amount of required resources to interact with BizTalk Server.</span></span> <span data-ttu-id="a27a9-120">セキュリティで保護された展開を行うために、外部プロセスのユーザー コンテキストに最小限の権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="a27a9-120">For a secure deployment, you should give the user context for the external processes minimal privileges.</span></span>  
  
 <span data-ttu-id="a27a9-121">**BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**</span><span class="sxs-lookup"><span data-stu-id="a27a9-121">**Security recommendations for the BizTalk Web Services Publishing Wizard**</span></span>  
  
 <span data-ttu-id="a27a9-122">BizTalk WCF サービス公開ウィザードで作成される仮想ディレクトリは、親仮想ディレクトリまたは Web サイトからアクセス制御リスト (ACL) を継承します。</span><span class="sxs-lookup"><span data-stu-id="a27a9-122">The virtual directory created by the BizTalk WCF Service Publishing Wizard inherits the access control lists (ACL) from the parent virtual directory or Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a27a9-123">参照</span><span class="sxs-lookup"><span data-stu-id="a27a9-123">See Also</span></span>  
 [<span data-ttu-id="a27a9-124">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="a27a9-124">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)