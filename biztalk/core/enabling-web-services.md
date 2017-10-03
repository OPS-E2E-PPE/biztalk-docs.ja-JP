---
title: "Web サービスの有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- hosts, isolated
- Web services, planning
- Web services, enabling
ms.assetid: 2a4681f6-9ded-423d-baa5-5831e6a85c61
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7cd0b1694422caf04285206f0bd7411ff5de20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-web-services"></a><span data-ttu-id="4fbfb-102">Web サービスの有効化</span><span class="sxs-lookup"><span data-stu-id="4fbfb-102">Enabling Web Services</span></span>
<span data-ttu-id="4fbfb-103">Web サービスを公開するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows のユーザー アカウントとグループ アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-103">To publish Web services, you must configure Internet Information Services (IIS), BizTalk Isolated Hosts, and Windows user and group accounts.</span></span> <span data-ttu-id="4fbfb-104">このセクションでは、IIS の Web サービスを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-104">This section discusses how to enable Web services in IIS.</span></span> <span data-ttu-id="4fbfb-105">Web サービスの有効化の詳細については、IIS のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-105">For more information about enabling Web services, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="4fbfb-106">**[インターネット インフォメーション サービス]**</span><span class="sxs-lookup"><span data-stu-id="4fbfb-106">**Internet Information Services**</span></span>  
  
 <span data-ttu-id="4fbfb-107">IIS と ASP.NET が構成されている Windows システムには、Web サービスを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-107">You can publish Web services to Windows systems that have IIS configured with ASP.NET.</span></span> <span data-ttu-id="4fbfb-108">サーバーごとに、すべての Web サービスが ASP.NET ワーカー プロセス内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-108">For each server, all Web services run within the ASP.NET worker process.</span></span>  
  
 <span data-ttu-id="4fbfb-109">既定では、ASP.NET ワーカー プロセスは、ローカルの ASPNET アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-109">The ASP.NET worker process uses the local ASPNET account by default.</span></span> <span data-ttu-id="4fbfb-110">IIS では、Web サービス要求を処理するアプリケーション プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-110">IIS uses application pools for processing Web service requests.</span></span>  
  
 <span data-ttu-id="4fbfb-111">**BizTalk 分離ホスト**</span><span class="sxs-lookup"><span data-stu-id="4fbfb-111">**BizTalk Isolated Hosts**</span></span>  
  
 <span data-ttu-id="4fbfb-112">Web サービスを有効にするには、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-112">To enable Web services, you must create at least one Isolated Host in BizTalk Server.</span></span> <span data-ttu-id="4fbfb-113">分離ホストは、ISAPI 拡張プロセスや ASP.NET プロセスなどの、BizTalk Server で作成、コントロールしない外部プロセスといえます。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-113">Isolated Hosts represent external processes, such as ISAPI extensions and ASP.NET processes that BizTalk Server does not create or control.</span></span> <span data-ttu-id="4fbfb-114">このような種類の外部プロセスは、HTTP/S や SOAP などの特定のアダプタをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-114">These types of external processes must host certain adapters, such as HTTP/S and SOAP.</span></span>  
  
 <span data-ttu-id="4fbfb-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成マネージャにより、BizTalk が既定の分離ホストとして使用する BizTalkServerIsolatedHost が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-115">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Manager creates the BizTalkServerIsolatedHost that BizTalk uses as the default Isolated Host.</span></span> <span data-ttu-id="4fbfb-116">BizTalk 分離ホスト ユーザー グループは、このホストに関連付けられている既定の Windows グループ名です。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-116">The BizTalk Isolated Host Users group is the name of the Windows group associated with this host by default.</span></span> <span data-ttu-id="4fbfb-117">ホストとホスト インスタンスの詳細については、次を参照してください。[を管理する BizTalk ホストとホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-117">For more information about Hosts and Host Instances, see [Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md).</span></span>  
  
 <span data-ttu-id="4fbfb-118">分離ホスト インスタンスは、1 つのアダプターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-118">An isolated host instance can run only one adapter.</span></span> <span data-ttu-id="4fbfb-119">1 つの分離ホストで HTTP アダプタと SOAP アダプタの受信ハンドラを構成する場合、2 つのアプリケーション プール (各アダプタに 1 つのアプリケーション プール) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-119">If you configure the receive handlers of HTTP and SOAP adapters with the one isolated host, you must create two application pools, one application pool for each adapter.</span></span>  
  
 <span data-ttu-id="4fbfb-120">たとえば、次の 2 つの分離ホストを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-120">For example, if you plan to configure two isolated hosts as following:</span></span>  
  
|<span data-ttu-id="4fbfb-121">分離ホスト名</span><span class="sxs-lookup"><span data-stu-id="4fbfb-121">Isolated host name</span></span>|<span data-ttu-id="4fbfb-122">受信場所</span><span class="sxs-lookup"><span data-stu-id="4fbfb-122">Receive locations</span></span>|  
|------------------------|-----------------------|  
|<span data-ttu-id="4fbfb-123">分離ホスト 1</span><span class="sxs-lookup"><span data-stu-id="4fbfb-123">Isolated Host 1</span></span>|<span data-ttu-id="4fbfb-124">HTTP_ReceiveLocation1A</span><span class="sxs-lookup"><span data-stu-id="4fbfb-124">HTTP_ReceiveLocation1A</span></span><br /><br /> <span data-ttu-id="4fbfb-125">HTTP_ReceiveLocation1B</span><span class="sxs-lookup"><span data-stu-id="4fbfb-125">HTTP_ReceiveLocation1B</span></span><br /><br /> <span data-ttu-id="4fbfb-126">SOAP_ReceiveLocation1**注:** 、 **Isolated Host 1**の使用は、SOAP および HTTP アダプターの受信ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-126">SOAP_ReceiveLocation1 **Note:**  The **Isolated Host 1** is used for receive handlers of both SOAP and HTTP adapters.</span></span>|  
|<span data-ttu-id="4fbfb-127">分離ホスト 2</span><span class="sxs-lookup"><span data-stu-id="4fbfb-127">Isolated Host 2</span></span>|<span data-ttu-id="4fbfb-128">HTTP_ReceiveLocation2</span><span class="sxs-lookup"><span data-stu-id="4fbfb-128">HTTP_ReceiveLocation2</span></span>|  
  
 <span data-ttu-id="4fbfb-129">仮想ディレクトリを 4 つ (次の受信場所ごとに 1 つ) 作成するとします。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-129">You may create four virtual directories, one for each receive location as follows:</span></span>  
  
|<span data-ttu-id="4fbfb-130">受信場所</span><span class="sxs-lookup"><span data-stu-id="4fbfb-130">Receive location</span></span>|<span data-ttu-id="4fbfb-131">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="4fbfb-131">Virtual directory</span></span>|  
|----------------------|-----------------------|  
|<span data-ttu-id="4fbfb-132">HTTP_ReceiveLocation1A</span><span class="sxs-lookup"><span data-stu-id="4fbfb-132">HTTP_ReceiveLocation1A</span></span>|<span data-ttu-id="4fbfb-133">IIS_Virtual_Directory1A</span><span class="sxs-lookup"><span data-stu-id="4fbfb-133">IIS_Virtual_Directory1A</span></span>|  
|<span data-ttu-id="4fbfb-134">HTTP_ReceiveLocation1B</span><span class="sxs-lookup"><span data-stu-id="4fbfb-134">HTTP_ReceiveLocation1B</span></span>|<span data-ttu-id="4fbfb-135">IIS_Virtual_Directory1B</span><span class="sxs-lookup"><span data-stu-id="4fbfb-135">IIS_Virtual_Directory1B</span></span>|  
|<span data-ttu-id="4fbfb-136">SOAP_ReceiveLocation1</span><span class="sxs-lookup"><span data-stu-id="4fbfb-136">SOAP_ReceiveLocation1</span></span>|<span data-ttu-id="4fbfb-137">IIS_Virtual_Directory1C</span><span class="sxs-lookup"><span data-stu-id="4fbfb-137">IIS_Virtual_Directory1C</span></span>|  
|<span data-ttu-id="4fbfb-138">HTTP_ReceiveLocation2</span><span class="sxs-lookup"><span data-stu-id="4fbfb-138">HTTP_ReceiveLocation2</span></span>|<span data-ttu-id="4fbfb-139">IIS_Virtual_Directory2</span><span class="sxs-lookup"><span data-stu-id="4fbfb-139">IIS_Virtual_Directory2</span></span>|  
  
 <span data-ttu-id="4fbfb-140">次のように、仮想ディレクトリに、少なくとも 3 つのアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-140">Then, you must create at least three application pools for the virtual directories as follows:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fbfb-141">分離ホストごとに、少なくとも 1 つのアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-141">You must create at least one application pool for each isolated host.</span></span>  
  
|<span data-ttu-id="4fbfb-142">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="4fbfb-142">Virtual directories</span></span>|<span data-ttu-id="4fbfb-143">アプリケーション プール</span><span class="sxs-lookup"><span data-stu-id="4fbfb-143">Application pool</span></span>|<span data-ttu-id="4fbfb-144">Description</span><span class="sxs-lookup"><span data-stu-id="4fbfb-144">Description</span></span>|  
|-------------------------|----------------------|-----------------|  
|<span data-ttu-id="4fbfb-145">IIS_Virtual_Directory1A</span><span class="sxs-lookup"><span data-stu-id="4fbfb-145">IIS_Virtual_Directory1A</span></span><br /><br /> <span data-ttu-id="4fbfb-146">IIS_Virtual_Directory1B</span><span class="sxs-lookup"><span data-stu-id="4fbfb-146">IIS_Virtual_Directory1B</span></span>|<span data-ttu-id="4fbfb-147">AppPool_Host1_HTTP</span><span class="sxs-lookup"><span data-stu-id="4fbfb-147">AppPool_Host1_HTTP</span></span>|<span data-ttu-id="4fbfb-148">すべての受信場所で同じ分離ホスト (分離ホスト 1) と同じプロトコルを使用するため、個別のアプリケーション プールは不要です。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-148">A separate application pool is not required because all of the receive locations have the same isolated host (Isolated Host 1), and the same protocol.</span></span>|  
|<span data-ttu-id="4fbfb-149">IIS_Virtual_Directory1C</span><span class="sxs-lookup"><span data-stu-id="4fbfb-149">IIS_Virtual_Directory1C</span></span>|<span data-ttu-id="4fbfb-150">AppPool_Host1_SOAP</span><span class="sxs-lookup"><span data-stu-id="4fbfb-150">AppPool_Host1_SOAP</span></span>|<span data-ttu-id="4fbfb-151">この受信場所で使用するプロトコル (SOAP) は、同じホスト (Isolated Host 1) の他の受信場所で使用するプロトコルと異なるため、個別のアプリケーション プールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-151">A separate application pool is required because the receive location uses the different protocol (SOAP) from the other receive locations in the same host (Isolated Host 1).</span></span>|  
|<span data-ttu-id="4fbfb-152">IIS_Virtual_Directory2</span><span class="sxs-lookup"><span data-stu-id="4fbfb-152">IIS_Virtual_Directory2</span></span>|<span data-ttu-id="4fbfb-153">AppPool_Host2_HTTP</span><span class="sxs-lookup"><span data-stu-id="4fbfb-153">AppPool_Host2_HTTP</span></span>|<span data-ttu-id="4fbfb-154">この受信場所は、Isolated Host 1 と異なるホストで実行されるため、個別のアプリケーション プールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-154">A separate application pool is required because the receive location runs under the different host from Isolated Host 1.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4fbfb-155">アプリケーション プールのユーザー アカウントを、適切な分離ホストのローカル グループまたはドメイン グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-155">You must add the user account for the application pools to the appropriate local or domain groups of the isolated hosts.</span></span> <span data-ttu-id="4fbfb-156">詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-156">For more information, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fbfb-157">分離ホスト インスタンスと前の表に従って、対応するアプリケーション プールのユーザー アカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-157">You need to match the user account between an isolated host instance and the corresponding application pool according to the previous tables.</span></span> <span data-ttu-id="4fbfb-158">分離ホスト インスタンスとアプリケーション プールのユーザー アカウントの間のリレーションシップの詳細については、次を参照してください。[サービス アカウントの変更をパスワード](../core/how-to-change-service-accounts-and-passwords.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-158">For more information about the relationship between user accounts of isolated host instance and application pools, see [How to Change Service Accounts and Passwords](../core/how-to-change-service-accounts-and-passwords.md).</span></span>  
  
 <span data-ttu-id="4fbfb-159">**単一サーバー インストールのデータベースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="4fbfb-159">**Database access for single server installations**</span></span>  
  
 <span data-ttu-id="4fbfb-160">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および BizTalk 管理データベースが同じサーバーに存在する場合、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを、ローカルの ASPNET ユーザー アカウント、または最小限の権限を持つローカルのユーザー アカウントかドメイン ユーザー アカウントに設定します。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-160">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on the same server, you should set the user context of the ASP.NET worker process or the IIS Application Pool to the local ASPNET user account, or a local or domain user account that has minimal privileges.</span></span>  
  
 <span data-ttu-id="4fbfb-161">**複数のサーバー インストールでのデータベースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="4fbfb-161">**Database access for multiple server installations**</span></span>  
  
 <span data-ttu-id="4fbfb-162">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および BizTalk 管理データベースが異なるサーバーに存在する場合、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストをドメイン ユーザー アカウントに変更します。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-162">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on different servers, you should change the user context of the ASP.NET worker process or the IIS Application Pool to a domain user account.</span></span>  
  
 <span data-ttu-id="4fbfb-163">マルチ サーバー展開を実装するときに、分離ホスト Windows グループが BizTalk データベース サーバーが属するドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-163">When implementing a multi-server deployment, the Isolated Host Windows groups must exist on the domain which the BizTalk database servers belong to.</span></span>  
  
 <span data-ttu-id="4fbfb-164">**アカウントの特権およびユーザー権限を最小限に抑える**</span><span class="sxs-lookup"><span data-stu-id="4fbfb-164">**Minimizing account privileges and user rights**</span></span>  
  
 <span data-ttu-id="4fbfb-165">分離ホストを使用すると、外部プロセスで実行するアダプタに、BizTalk Server との連携に必要な最小限のリソースへのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-165">You use Isolated Hosts to give adapters that run in external processes access to the minimal amount of required resources to interact with BizTalk Server.</span></span> <span data-ttu-id="4fbfb-166">セキュリティで保護された展開を行うために、外部プロセスのユーザー コンテキストに最小限の権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-166">For a secure deployment, you should give the user context for the external processes minimal privileges.</span></span>  
  
 <span data-ttu-id="4fbfb-167">**BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**</span><span class="sxs-lookup"><span data-stu-id="4fbfb-167">**Security recommendations for BizTalk Web Services Publishing Wizard**</span></span>  
  
 <span data-ttu-id="4fbfb-168">BizTalk Web サービス公開ウィザードで作成する仮想ディレクトリは、親仮想ディレクトリまたは Web サイトからアクセス制御リスト (ACL) および認証要件を継承します。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-168">The virtual directory created by the BizTalk Web Services Publishing Wizard will inherit the access control lists (ACL) and authentication requirements from the parent virtual directory or Web site.</span></span> <span data-ttu-id="4fbfb-169">親仮想ディレクトリまたは Web サイトへの匿名アクセスが許可されている場合、仮想ディレクトリを作成するときに、BizTalk Web サービス公開ウィザードによってその機能は削除されます。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-169">If the parent virtual directory or Web site allows anonymous access, the BizTalk Web Services Publishing Wizard will remove that capability when creating the virtual directory.</span></span>  
  
 <span data-ttu-id="4fbfb-170">次のトピックには、[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)] のセキュリティに関する注意事項と推奨事項が記載されています。</span><span class="sxs-lookup"><span data-stu-id="4fbfb-170">The following contains security notes and recommendations for [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="4fbfb-171">Next</span><span class="sxs-lookup"><span data-stu-id="4fbfb-171">Next</span></span>
  
[<span data-ttu-id="4fbfb-172">公開済み Web サービスの ASP.NET を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="4fbfb-172">How to Enable ASP.NET for Published Web Services</span></span>](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)