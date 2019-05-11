---
title: Web サービスの有効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- hosts, isolated
- Web services, planning
- Web services, enabling
ms.assetid: 2a4681f6-9ded-423d-baa5-5831e6a85c61
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a811fe61a6a5b17e8c5cbf803b35d630836d05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349697"
---
# <a name="enabling-web-services"></a><span data-ttu-id="d9452-102">Web サービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d9452-102">Enabling Web Services</span></span>
<span data-ttu-id="d9452-103">Web サービスを発行するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows ユーザーおよびグループ アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-103">To publish Web services, you must configure Internet Information Services (IIS), BizTalk Isolated Hosts, and Windows user and group accounts.</span></span> <span data-ttu-id="d9452-104">このセクションでは、IIS の Web サービスを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9452-104">This section discusses how to enable Web services in IIS.</span></span> <span data-ttu-id="d9452-105">Web サービスを有効にする方法の詳細については、IIS のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9452-105">For more information about enabling Web services, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="d9452-106">**[インターネット インフォメーション サービス]**</span><span class="sxs-lookup"><span data-stu-id="d9452-106">**Internet Information Services**</span></span>  
  
 <span data-ttu-id="d9452-107">ASP.NET で構成された IIS を搭載する Windows システムに Web サービスを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="d9452-107">You can publish Web services to Windows systems that have IIS configured with ASP.NET.</span></span> <span data-ttu-id="d9452-108">各サーバーでは、すべての Web サービスは、ASP.NET ワーカー プロセス内で実行します。</span><span class="sxs-lookup"><span data-stu-id="d9452-108">For each server, all Web services run within the ASP.NET worker process.</span></span>  
  
 <span data-ttu-id="d9452-109">ASP.NET ワーカー プロセスは、既定では、ローカルの ASPNET アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9452-109">The ASP.NET worker process uses the local ASPNET account by default.</span></span> <span data-ttu-id="d9452-110">IIS は、Web サービス要求を処理するためのアプリケーション プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9452-110">IIS uses application pools for processing Web service requests.</span></span>  
  
 <span data-ttu-id="d9452-111">**BizTalk 分離ホスト**</span><span class="sxs-lookup"><span data-stu-id="d9452-111">**BizTalk Isolated Hosts**</span></span>  
  
 <span data-ttu-id="d9452-112">Web サービスを有効には、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-112">To enable Web services, you must create at least one Isolated Host in BizTalk Server.</span></span> <span data-ttu-id="d9452-113">分離ホストは、ISAPI 拡張機能と BizTalk Server は作成または制御する ASP.NET プロセスなどの外部プロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="d9452-113">Isolated Hosts represent external processes, such as ISAPI extensions and ASP.NET processes that BizTalk Server does not create or control.</span></span> <span data-ttu-id="d9452-114">これらの種類の外部プロセスでは、HTTP/S や SOAP などの特定のアダプターをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-114">These types of external processes must host certain adapters, such as HTTP/S and SOAP.</span></span>  
  
 <span data-ttu-id="d9452-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Manager は、BizTalk が既定値として使用する BizTalkServerIsolatedHost を作成します。 分離ホスト。</span><span class="sxs-lookup"><span data-stu-id="d9452-115">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Manager creates the BizTalkServerIsolatedHost that BizTalk uses as the default Isolated Host.</span></span> <span data-ttu-id="d9452-116">BizTalk 分離ホスト ユーザー グループは、既定では、このホストに関連付けられている Windows グループの名前です。</span><span class="sxs-lookup"><span data-stu-id="d9452-116">The BizTalk Isolated Host Users group is the name of the Windows group associated with this host by default.</span></span> <span data-ttu-id="d9452-117">ホストとホスト インスタンスの詳細については、次を参照してください。 [BizTalk ホストの管理およびホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9452-117">For more information about Hosts and Host Instances, see [Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md).</span></span>  
  
 <span data-ttu-id="d9452-118">分離ホスト インスタンスは、1 つのアダプターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="d9452-118">An isolated host instance can run only one adapter.</span></span> <span data-ttu-id="d9452-119">1 つの分離ホストで HTTP および SOAP アダプターの受信ハンドラーを構成する場合は、2 つのアプリケーション プール、アダプターごとに 1 つのアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-119">If you configure the receive handlers of HTTP and SOAP adapters with the one isolated host, you must create two application pools, one application pool for each adapter.</span></span>  
  
 <span data-ttu-id="d9452-120">たとえば、次の 2 つの分離ホストを構成する予定の場合。</span><span class="sxs-lookup"><span data-stu-id="d9452-120">For example, if you plan to configure two isolated hosts as following:</span></span>  
  
|<span data-ttu-id="d9452-121">分離ホスト名</span><span class="sxs-lookup"><span data-stu-id="d9452-121">Isolated host name</span></span>|<span data-ttu-id="d9452-122">受信場所</span><span class="sxs-lookup"><span data-stu-id="d9452-122">Receive locations</span></span>|  
|------------------------|-----------------------|  
|<span data-ttu-id="d9452-123">分離ホスト 1</span><span class="sxs-lookup"><span data-stu-id="d9452-123">Isolated Host 1</span></span>|<span data-ttu-id="d9452-124">HTTP_ReceiveLocation1A</span><span class="sxs-lookup"><span data-stu-id="d9452-124">HTTP_ReceiveLocation1A</span></span><br /><br /> <span data-ttu-id="d9452-125">HTTP_ReceiveLocation1B</span><span class="sxs-lookup"><span data-stu-id="d9452-125">HTTP_ReceiveLocation1B</span></span><br /><br /> <span data-ttu-id="d9452-126">SOAP_ReceiveLocation1**に注意してください。\*\*\*\*Isolated Host 1**の使用は、SOAP および HTTP アダプターの受信ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="d9452-126">SOAP_ReceiveLocation1 **Note:**  The **Isolated Host 1** is used for receive handlers of both SOAP and HTTP adapters.</span></span>|  
|<span data-ttu-id="d9452-127">分離ホスト 2</span><span class="sxs-lookup"><span data-stu-id="d9452-127">Isolated Host 2</span></span>|<span data-ttu-id="d9452-128">HTTP_ReceiveLocation2</span><span class="sxs-lookup"><span data-stu-id="d9452-128">HTTP_ReceiveLocation2</span></span>|  
  
 <span data-ttu-id="d9452-129">ごとに 1 つの受信場所を次のように、4 つの仮想ディレクトリを作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="d9452-129">You may create four virtual directories, one for each receive location as follows:</span></span>  
  
|<span data-ttu-id="d9452-130">受信場所</span><span class="sxs-lookup"><span data-stu-id="d9452-130">Receive location</span></span>|<span data-ttu-id="d9452-131">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="d9452-131">Virtual directory</span></span>|  
|----------------------|-----------------------|  
|<span data-ttu-id="d9452-132">HTTP_ReceiveLocation1A</span><span class="sxs-lookup"><span data-stu-id="d9452-132">HTTP_ReceiveLocation1A</span></span>|<span data-ttu-id="d9452-133">IIS_Virtual_Directory1A</span><span class="sxs-lookup"><span data-stu-id="d9452-133">IIS_Virtual_Directory1A</span></span>|  
|<span data-ttu-id="d9452-134">HTTP_ReceiveLocation1B</span><span class="sxs-lookup"><span data-stu-id="d9452-134">HTTP_ReceiveLocation1B</span></span>|<span data-ttu-id="d9452-135">IIS_Virtual_Directory1B</span><span class="sxs-lookup"><span data-stu-id="d9452-135">IIS_Virtual_Directory1B</span></span>|  
|<span data-ttu-id="d9452-136">SOAP_ReceiveLocation1</span><span class="sxs-lookup"><span data-stu-id="d9452-136">SOAP_ReceiveLocation1</span></span>|<span data-ttu-id="d9452-137">IIS_Virtual_Directory1C</span><span class="sxs-lookup"><span data-stu-id="d9452-137">IIS_Virtual_Directory1C</span></span>|  
|<span data-ttu-id="d9452-138">HTTP_ReceiveLocation2</span><span class="sxs-lookup"><span data-stu-id="d9452-138">HTTP_ReceiveLocation2</span></span>|<span data-ttu-id="d9452-139">IIS_Virtual_Directory2</span><span class="sxs-lookup"><span data-stu-id="d9452-139">IIS_Virtual_Directory2</span></span>|  
  
 <span data-ttu-id="d9452-140">次に、よう、仮想ディレクトリの少なくとも 3 つのアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-140">Then, you must create at least three application pools for the virtual directories as follows:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9452-141">分離ホストごとに少なくとも 1 つのアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-141">You must create at least one application pool for each isolated host.</span></span>  
  
|<span data-ttu-id="d9452-142">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="d9452-142">Virtual directories</span></span>|<span data-ttu-id="d9452-143">アプリケーション プール</span><span class="sxs-lookup"><span data-stu-id="d9452-143">Application pool</span></span>|<span data-ttu-id="d9452-144">説明</span><span class="sxs-lookup"><span data-stu-id="d9452-144">Description</span></span>|  
|-------------------------|----------------------|-----------------|  
|<span data-ttu-id="d9452-145">IIS_Virtual_Directory1A</span><span class="sxs-lookup"><span data-stu-id="d9452-145">IIS_Virtual_Directory1A</span></span><br /><br /> <span data-ttu-id="d9452-146">IIS_Virtual_Directory1B</span><span class="sxs-lookup"><span data-stu-id="d9452-146">IIS_Virtual_Directory1B</span></span>|<span data-ttu-id="d9452-147">AppPool_Host1_HTTP</span><span class="sxs-lookup"><span data-stu-id="d9452-147">AppPool_Host1_HTTP</span></span>|<span data-ttu-id="d9452-148">同じ分離ホスト (Isolated Host 1) と同じプロトコルのすべての受信場所があるために、個別のアプリケーション プールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d9452-148">A separate application pool is not required because all of the receive locations have the same isolated host (Isolated Host 1), and the same protocol.</span></span>|  
|<span data-ttu-id="d9452-149">IIS_Virtual_Directory1C</span><span class="sxs-lookup"><span data-stu-id="d9452-149">IIS_Virtual_Directory1C</span></span>|<span data-ttu-id="d9452-150">AppPool_Host1_SOAP</span><span class="sxs-lookup"><span data-stu-id="d9452-150">AppPool_Host1_SOAP</span></span>|<span data-ttu-id="d9452-151">受信場所は、同じホスト (Isolated Host 1) で他の受信場所から別のプロトコル (SOAP) を使用するため、個別のアプリケーション プールが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9452-151">A separate application pool is required because the receive location uses the different protocol (SOAP) from the other receive locations in the same host (Isolated Host 1).</span></span>|  
|<span data-ttu-id="d9452-152">IIS_Virtual_Directory2</span><span class="sxs-lookup"><span data-stu-id="d9452-152">IIS_Virtual_Directory2</span></span>|<span data-ttu-id="d9452-153">AppPool_Host2_HTTP</span><span class="sxs-lookup"><span data-stu-id="d9452-153">AppPool_Host2_HTTP</span></span>|<span data-ttu-id="d9452-154">受信場所は、分離ホスト 1 から別のホストで実行されるので、個別のアプリケーション プールが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9452-154">A separate application pool is required because the receive location runs under the different host from Isolated Host 1.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d9452-155">分離ホストの適切なローカルまたはドメイン グループには、アプリケーション プールのユーザー アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-155">You must add the user account for the application pools to the appropriate local or domain groups of the isolated hosts.</span></span> <span data-ttu-id="d9452-156">詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9452-156">For more information, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9452-157">分離ホスト インスタンスと前の表に従って、対応するアプリケーション プールのユーザー アカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-157">You need to match the user account between an isolated host instance and the corresponding application pool according to the previous tables.</span></span> <span data-ttu-id="d9452-158">分離ホスト インスタンスとアプリケーション プールのユーザー アカウントの間のリレーションシップの詳細については、次を参照してください。[変更サービス アカウントおよびパスワード方法](../core/how-to-change-service-accounts-and-passwords.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9452-158">For more information about the relationship between user accounts of isolated host instance and application pools, see [How to Change Service Accounts and Passwords](../core/how-to-change-service-accounts-and-passwords.md).</span></span>  
  
 <span data-ttu-id="d9452-159">**単一サーバー インストールのデータベースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="d9452-159">**Database access for single server installations**</span></span>  
  
 <span data-ttu-id="d9452-160">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と BizTalk 管理データベースが同じサーバー上に、ローカルの ASPNET ユーザー アカウント、または最小限の特権を持つローカルまたはドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-160">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on the same server, you should set the user context of the ASP.NET worker process or the IIS Application Pool to the local ASPNET user account, or a local or domain user account that has minimal privileges.</span></span>  
  
 <span data-ttu-id="d9452-161">**複数のサーバー インストールでのデータベースへのアクセス**</span><span class="sxs-lookup"><span data-stu-id="d9452-161">**Database access for multiple server installations**</span></span>  
  
 <span data-ttu-id="d9452-162">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と BizTalk 管理データベースが別のサーバーに存在する、ドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-162">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on different servers, you should change the user context of the ASP.NET worker process or the IIS Application Pool to a domain user account.</span></span>  
  
 <span data-ttu-id="d9452-163">マルチ サーバー展開を実装する場合は、分離ホスト Windows グループが BizTalk データベース サーバーが属するドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9452-163">When implementing a multi-server deployment, the Isolated Host Windows groups must exist on the domain which the BizTalk database servers belong to.</span></span>  
  
 <span data-ttu-id="d9452-164">**アカウントの特権およびユーザー権限を最小限に抑える**</span><span class="sxs-lookup"><span data-stu-id="d9452-164">**Minimizing account privileges and user rights**</span></span>  
  
 <span data-ttu-id="d9452-165">分離ホストを使用して、BizTalk Server との対話に必要なリソース量が最小限に外部プロセスへのアクセスで実行されるアダプターを与えます。</span><span class="sxs-lookup"><span data-stu-id="d9452-165">You use Isolated Hosts to give adapters that run in external processes access to the minimal amount of required resources to interact with BizTalk Server.</span></span> <span data-ttu-id="d9452-166">セキュリティで保護された展開は、するようにユーザー コンテキスト、外部プロセスの最小限の特権します。</span><span class="sxs-lookup"><span data-stu-id="d9452-166">For a secure deployment, you should give the user context for the external processes minimal privileges.</span></span>  
  
 <span data-ttu-id="d9452-167">**BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**</span><span class="sxs-lookup"><span data-stu-id="d9452-167">**Security recommendations for BizTalk Web Services Publishing Wizard**</span></span>  
  
 <span data-ttu-id="d9452-168">BizTalk Web サービス公開ウィザードによって作成された仮想ディレクトリでは、アクセス制御リスト (ACL) と認証の要件を親仮想ディレクトリまたは Web サイトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="d9452-168">The virtual directory created by the BizTalk Web Services Publishing Wizard will inherit the access control lists (ACL) and authentication requirements from the parent virtual directory or Web site.</span></span> <span data-ttu-id="d9452-169">親仮想ディレクトリまたは Web サイトへの匿名アクセスを許可している場合、BizTalk Web サービス公開ウィザードは、仮想ディレクトリを作成するときにその機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="d9452-169">If the parent virtual directory or Web site allows anonymous access, the BizTalk Web Services Publishing Wizard will remove that capability when creating the virtual directory.</span></span>  
  
 <span data-ttu-id="d9452-170">次には、セキュリティに関する注意事項と推奨事項が含まれます。[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d9452-170">The following contains security notes and recommendations for [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="d9452-171">Next</span><span class="sxs-lookup"><span data-stu-id="d9452-171">Next</span></span>
  
[<span data-ttu-id="d9452-172">公開済み Web サービスの ASP.NET を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="d9452-172">How to Enable ASP.NET for Published Web Services</span></span>](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)