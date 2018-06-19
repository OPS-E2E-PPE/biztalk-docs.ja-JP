---
title: Windows アカウントをセキュリティで保護された分散型 BizTalk Server 展開の |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, Windows groups
- user accounts, naming conventions
- user accounts
- access control, Windows groups
- security, access control
- architecture, security
- security, Windows accounts
- administrator accounts
- user accounts, administrators
- architecture, large distributions
ms.assetid: 2a0893ef-8bfb-481b-b024-7f7d6e2a6f09
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04c7e6e28cc0deb83eaa7868c6c4ee17da8bc563
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974960"
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="d4062-102">セキュリティで保護された分散型 BizTalk Server 展開向けの Windows アカウント</span><span class="sxs-lookup"><span data-stu-id="d4062-102">Windows Accounts for a Secure Distributed BizTalk Server Deployment</span></span>
<span data-ttu-id="d4062-103">BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4062-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="d4062-104">このセクションでは、分散型 BizTalk Server 環境の Windows グループとアカウントを作成するための推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4062-104">This section provides recommendations for creating Windows groups and accounts in a distributed BizTalk Server environment.</span></span> <span data-ttu-id="d4062-105">グループ名とアカウント名は、グループとアカウントの機能に基づいた提案です。</span><span class="sxs-lookup"><span data-stu-id="d4062-105">The group and account names are suggestions based on the function of the groups and accounts.</span></span> <span data-ttu-id="d4062-106">これらのグループとアカウントの名前は自由に選択できます。</span><span class="sxs-lookup"><span data-stu-id="d4062-106">You can choose the name of these groups and accounts.</span></span> <span data-ttu-id="d4062-107">分散型 BizTalk Server アーキテクチャの詳細については、次を参照してください。[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4062-107">For more information about distributed BizTalk Server architectures, see [Large Distributed Architecture](../core/large-distributed-architecture.md).</span></span>  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="d4062-108">セキュリティで保護された分散型 BizTalk Server 展開向けの Windows グループ</span><span class="sxs-lookup"><span data-stu-id="d4062-108">Windows Groups for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="d4062-109">次の表は、ドメイン管理者によりデータ層内のドメイン コントローラーに作成することが推奨される Windows グループを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4062-109">The following list describes the recommended Windows groups for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
-   <span data-ttu-id="d4062-110">SSO 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-110">SSO Administrators</span></span>  
  
-   <span data-ttu-id="d4062-111">SSO 関連管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-111">SSO Affiliate Administrators</span></span>  
  
-   <span data-ttu-id="d4062-112">BizTalk Server 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-112">BizTalk Server Administrators</span></span>  
  
-   <span data-ttu-id="d4062-113">BizTalk Server オペレータ</span><span class="sxs-lookup"><span data-stu-id="d4062-113">BizTalk Server Operators</span></span>  
  
 <span data-ttu-id="d4062-114">BizTalk Server で使用する Windows グループに関する詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4062-114">For complete information about the Windows groups that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="d4062-115">次の表は、上記のドメイン グループ以外に、ドメイン管理者がデータ層内のドメイン コントローラーに作成する、セキュリティで保護された展開専用の追加グループを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4062-115">In addition to the previous domain groups, the following table lists additional groups specific to secure deployment for the domain administrator to create in the domain controller in the data tier.</span></span>  
  
|<span data-ttu-id="d4062-116">グループ名 (推奨)</span><span class="sxs-lookup"><span data-stu-id="d4062-116">Group name (suggested)</span></span>|<span data-ttu-id="d4062-117">用途</span><span class="sxs-lookup"><span data-stu-id="d4062-117">Purpose</span></span>|  
|------------------------------|-------------|  
|<span data-ttu-id="d4062-118">BizTalk 処理ホスト ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="d4062-118">BizTalk Processing Host Users 1</span></span>|<span data-ttu-id="d4062-119">メッセージの処理に使用する特定のインプロセス ホストのホスト インスタンス用グループ。</span><span class="sxs-lookup"><span data-stu-id="d4062-119">Group for the host instances of a specific in-process host that you use for processing messages.</span></span> <span data-ttu-id="d4062-120">BizTalk Server 環境でメッセージの処理に使用する各インプロセス ホスト用のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4062-120">Create a group for each in-process host that you use for processing messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="d4062-121">BizTalk 送信ホスト ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="d4062-121">BizTalk Send Host Users 1</span></span>|<span data-ttu-id="d4062-122">メッセージの送信に使用する特定のインプロセス ホストのホスト インスタンス用グループ。</span><span class="sxs-lookup"><span data-stu-id="d4062-122">Group for the host instance of a specific in-process host that you use for sending messages.</span></span> <span data-ttu-id="d4062-123">BizTalk Server 環境でメッセージの送信に使用する各インプロセス ホスト用のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4062-123">Create a group for each in-process host that you use for sending messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="d4062-124">BizTalk 受信ホスト ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="d4062-124">BizTalk Receive Host Users 1</span></span>|<span data-ttu-id="d4062-125">メッセージの受信に使用する特定のインプロセス ホストのホスト インスタンス用グループ。</span><span class="sxs-lookup"><span data-stu-id="d4062-125">Group for the host instance of a specific in-process host that you use for receiving messages.</span></span> <span data-ttu-id="d4062-126">BizTalk Server 環境でメッセージの受信に使用する各インプロセス ホスト用のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4062-126">Create a group for each in-process host that you use for receiving messages in your BizTalk Server environment.</span></span>|  
|<span data-ttu-id="d4062-127">BizTalk 追跡ホスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-127">BizTalk Tracking Host Users</span></span>|<span data-ttu-id="d4062-128">追跡専用に使用する BizTalk ホスト用グループ。</span><span class="sxs-lookup"><span data-stu-id="d4062-128">Group for the BizTalk host that you dedicate for tracking.</span></span>|  
|<span data-ttu-id="d4062-129">BizTalk SOAP ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-129">BizTalk SOAP Users</span></span>|<span data-ttu-id="d4062-130">SOAP アダプターに使用する分離ホストのホスト インスタンス用グループ。</span><span class="sxs-lookup"><span data-stu-id="d4062-130">Group for the host instances of the isolated host you use for the SOAP adapter.</span></span>|  
|<span data-ttu-id="d4062-131">BizTalk HTTP ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-131">BizTalk HTTP Users</span></span>|<span data-ttu-id="d4062-132">HTTP アダプターに使用する分離ホストのホスト インスタンス用グループ。</span><span class="sxs-lookup"><span data-stu-id="d4062-132">Group for the host instances of the isolated hosts you use for the HTTP adapter.</span></span>|  
  
 <span data-ttu-id="d4062-133">ドメイン管理者は、企業ドメインのドメイン コントローラーに次のグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4062-133">The domain administrator must create the following groups in the domain controller of the service interfaces domain:</span></span>  
  
-   <span data-ttu-id="d4062-134">BizTalk BAM Portal ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-134">BizTalk BAM Portal Users</span></span>  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a><span data-ttu-id="d4062-135">セキュリティで保護された分散型 BizTalk Server 展開向けの Windows ユーザーまたはサービス アカウント</span><span class="sxs-lookup"><span data-stu-id="d4062-135">Windows User or Service Accounts for a Secure Distributed BizTalk Server Deployment</span></span>  
 <span data-ttu-id="d4062-136">次の表は、ドメイン管理者によりデータ ドメインのドメイン コントローラーに作成することが推奨されるアカウントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4062-136">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the data domain.</span></span> <span data-ttu-id="d4062-137">ドメイン管理者は、アカウントが対象グループのメンバーであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4062-137">The domain administrator must ensure the accounts are members of the groups indicated.</span></span>  
  
 <span data-ttu-id="d4062-138">BizTalk Server で使用するユーザー アカウントに関する詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4062-138">For complete information about the user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
|<span data-ttu-id="d4062-139">アカウント名 (例)</span><span class="sxs-lookup"><span data-stu-id="d4062-139">Account name (example)</span></span>|<span data-ttu-id="d4062-140">型</span><span class="sxs-lookup"><span data-stu-id="d4062-140">Type</span></span>|<span data-ttu-id="d4062-141">グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="d4062-141">Member of group</span></span>|  
|------------------------------|----------|---------------------|  
|<span data-ttu-id="d4062-142">SSO 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-142">SSO administrator</span></span>|<span data-ttu-id="d4062-143">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-143">User</span></span>|<span data-ttu-id="d4062-144">SSO 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-144">SSO Administrators</span></span>|  
|<span data-ttu-id="d4062-145">SSO サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-145">SSO service</span></span>|<span data-ttu-id="d4062-146">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-146">Service</span></span>|<span data-ttu-id="d4062-147">SSO 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-147">SSO Administrators</span></span>|  
|<span data-ttu-id="d4062-148">SSO マスター シークレット</span><span class="sxs-lookup"><span data-stu-id="d4062-148">SSO master secret</span></span>|<span data-ttu-id="d4062-149">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-149">Service</span></span>|<span data-ttu-id="d4062-150">SSO 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-150">SSO Administrators</span></span>|  
|<span data-ttu-id="d4062-151">BizTalk 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-151">BizTalk administrator</span></span>|<span data-ttu-id="d4062-152">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-152">User</span></span>|<span data-ttu-id="d4062-153">BizTalk 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-153">BizTalk Administrators</span></span><br /><br /> <span data-ttu-id="d4062-154">SSO 関連管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-154">SSO Affiliate Administrators</span></span>|  
|<span data-ttu-id="d4062-155">BizTalk オペレーター</span><span class="sxs-lookup"><span data-stu-id="d4062-155">BizTalk operator</span></span>|<span data-ttu-id="d4062-156">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-156">User</span></span>|<span data-ttu-id="d4062-157">BizTalk Operators</span><span class="sxs-lookup"><span data-stu-id="d4062-157">BizTalk Operators</span></span>|  
|<span data-ttu-id="d4062-158">BizTalk 処理 1</span><span class="sxs-lookup"><span data-stu-id="d4062-158">BizTalk Processing 1</span></span>|<span data-ttu-id="d4062-159">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-159">Service</span></span>|<span data-ttu-id="d4062-160">BizTalk 処理ホスト ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="d4062-160">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="d4062-161">BizTalk 処理 2**注:** 環境内で各処理ホストの複数のアカウントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d4062-161">BizTalk Processing 2 **Note:**  You can create multiple accounts for each processing host in your environment.</span></span>|<span data-ttu-id="d4062-162">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-162">Service</span></span>|<span data-ttu-id="d4062-163">BizTalk 処理ホスト ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="d4062-163">BizTalk Processing Host Users 1</span></span>|  
|<span data-ttu-id="d4062-164">BizTalk 追跡</span><span class="sxs-lookup"><span data-stu-id="d4062-164">BizTalk Tracking</span></span>|<span data-ttu-id="d4062-165">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-165">Service</span></span>|<span data-ttu-id="d4062-166">BizTalk 追跡ホスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-166">BizTalk Tracking Host Users</span></span>|  
|<span data-ttu-id="d4062-167">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="d4062-167">SOAP adapter</span></span>|<span data-ttu-id="d4062-168">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-168">Service</span></span>|<span data-ttu-id="d4062-169">BizTalk SOAP ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-169">BizTalk SOAP Users</span></span>|  
|<span data-ttu-id="d4062-170">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="d4062-170">HTTP adapter</span></span>|<span data-ttu-id="d4062-171">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-171">Service</span></span>|<span data-ttu-id="d4062-172">BizTalk HTTP ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-172">BizTalk HTTP Users</span></span>|  
|<span data-ttu-id="d4062-173">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-173">Rule Engine Update Service</span></span>|<span data-ttu-id="d4062-174">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-174">Service</span></span>||  
|<span data-ttu-id="d4062-175">インストール</span><span class="sxs-lookup"><span data-stu-id="d4062-175">Installation</span></span>|<span data-ttu-id="d4062-176">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-176">User</span></span>|<span data-ttu-id="d4062-177">SSO 管理者 (の場合のみ、マスタ シークレット サーバーを構成する)</span><span class="sxs-lookup"><span data-stu-id="d4062-177">SSO Administrators (only for configuring the master secret server)</span></span><br /><br /> <span data-ttu-id="d4062-178">ローカル管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-178">local Administrators</span></span><br /><br /> <span data-ttu-id="d4062-179">sysadmin SQL Server ロール</span><span class="sxs-lookup"><span data-stu-id="d4062-179">sysadmin SQL Server Role</span></span><br /><br /> <span data-ttu-id="d4062-180">OLAP 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-180">OLAP Administrator</span></span>|  
|<span data-ttu-id="d4062-181">BAM アプリケーション プール</span><span class="sxs-lookup"><span data-stu-id="d4062-181">BAM Application pool</span></span>|<span data-ttu-id="d4062-182">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-182">Service</span></span>|<span data-ttu-id="d4062-183">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="d4062-183">IIS_WPG</span></span>|  
|<span data-ttu-id="d4062-184">BAM 管理</span><span class="sxs-lookup"><span data-stu-id="d4062-184">BAM Management</span></span>|<span data-ttu-id="d4062-185">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-185">Service</span></span>|<span data-ttu-id="d4062-186">IIS_WPG</span><span class="sxs-lookup"><span data-stu-id="d4062-186">IIS_WPG</span></span>|  
|<span data-ttu-id="d4062-187">BAM 通知</span><span class="sxs-lookup"><span data-stu-id="d4062-187">BAM Notification</span></span>|<span data-ttu-id="d4062-188">サービス</span><span class="sxs-lookup"><span data-stu-id="d4062-188">Service</span></span>|<span data-ttu-id="d4062-189">SQLServer2005NotificationServicesUser$\<**ComputerName**\></span><span class="sxs-lookup"><span data-stu-id="d4062-189">SQLServer2005NotificationServicesUser$\<**ComputerName**\></span></span>|  
  
 <span data-ttu-id="d4062-190">次の表は、ドメイン管理者により企業ドメインのドメイン コントローラーに作成することが推奨されるアカウントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4062-190">The following table lists the recommended accounts for the domain administrator to create in the domain controller of the corporate domain.</span></span>  
  
|<span data-ttu-id="d4062-191">アカウント名</span><span class="sxs-lookup"><span data-stu-id="d4062-191">Account name</span></span>|<span data-ttu-id="d4062-192">型</span><span class="sxs-lookup"><span data-stu-id="d4062-192">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="d4062-193">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="d4062-193">SharePoint administrator</span></span>|<span data-ttu-id="d4062-194">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-194">User</span></span>|  
|<span data-ttu-id="d4062-195">SharePoint サイト適格者</span><span class="sxs-lookup"><span data-stu-id="d4062-195">SharePoint Site credential</span></span>|<span data-ttu-id="d4062-196">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4062-196">User</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4062-197">参照</span><span class="sxs-lookup"><span data-stu-id="d4062-197">See Also</span></span>  
 <span data-ttu-id="d4062-198">[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d4062-198">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="d4062-199">[セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="d4062-199">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="d4062-200">[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="d4062-200">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="d4062-201">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d4062-201">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)