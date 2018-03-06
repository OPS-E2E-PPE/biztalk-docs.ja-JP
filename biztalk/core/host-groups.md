---
title: "ホスト グループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3132b4084ed0d153895e252c5c64419ce0ac72
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="host-groups"></a><span data-ttu-id="906b3-102">ホスト グループ</span><span class="sxs-lookup"><span data-stu-id="906b3-102">Host Groups</span></span>

## <a name="overview"></a><span data-ttu-id="906b3-103">概要</span><span class="sxs-lookup"><span data-stu-id="906b3-103">Overview</span></span>
<span data-ttu-id="906b3-104">ホスト グループは、インプロセスの BizTalk ホスト (BizTalk Server のホスト プロセス) に対するアクセスに使用するアカウントの Windows グループ (既定で BizTalk アプリケーション ユーザー グループという名前) です。</span><span class="sxs-lookup"><span data-stu-id="906b3-104">The host group is the Windows group (named the BizTalk Application Users group by default) that you use for accounts with access to the in-process BizTalk hosts (host processes in BizTalk Server).</span></span> <span data-ttu-id="906b3-105">使用している環境のインプロセス ホストごとに 1 つのホスト グループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="906b3-105">It is recommended that you use one host group for each in-process host in your environment.</span></span>  
  
 <span data-ttu-id="906b3-106">ホストは 1 つの Windows グループにのみ関連付けることができます (と呼ばれる、 *ホスト グループ*)。</span><span class="sxs-lookup"><span data-stu-id="906b3-106">You can only associate a host with one Windows group (called a *host group*).</span></span> <span data-ttu-id="906b3-107">ホスト グループには、すべての関連する BizTalk Server データベースの SQL Server ログインと権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="906b3-107">The host group must have a SQL Server login and privileges in all relevant BizTalk Server databases.</span></span> <span data-ttu-id="906b3-108">ホストをホスト グループに関連付けると、ホストにホスト グループの権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="906b3-108">When you associate a host with the host group, you grant the host the privileges of the host group.</span></span>  
  
 <span data-ttu-id="906b3-109">構成ウィザードでホストを作成し、ホストに対してローカル Windows グループを指定すると、構成ウィザードは、自動的に 2 つの Windows グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="906b3-109">If you use the Configuration Wizard to create hosts, and you specify a local Windows group to use for hosts, the Configuration Wizard automatically creates two Windows groups.</span></span> <span data-ttu-id="906b3-110">これらのグループの既定の名前は、BizTalk アプリケーション ユーザー グループと BizTalk 分離ホスト ユーザー グループです。</span><span class="sxs-lookup"><span data-stu-id="906b3-110">The default names of these groups are the BizTalk Application Users group and the BizTalk Isolated Host Users group.</span></span>  
  
 <span data-ttu-id="906b3-111">ホスト グループに関連付けられているホストのホスト インスタンスを作成すると、ホスト インスタンスは、ホスト グループのデータベース権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="906b3-111">When you create a host instance of a host associated with the host group, the host instance inherits the database privileges of the host group.</span></span>  
  
 <span data-ttu-id="906b3-112">ホスト グループは、ホストの WMI (Windows Management Instrumentation) オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="906b3-112">The host group is a property of the host Windows Management Instrumentation (WMI) object.</span></span> <span data-ttu-id="906b3-113">ホストにホスト インスタンスがない場合は、ホストが属する Windows グループを変更できます。</span><span class="sxs-lookup"><span data-stu-id="906b3-113">You can change the Windows group that a host belongs to if there are no host instances of the host.</span></span>  
  
 <span data-ttu-id="906b3-114">ホストを作成する際、ホストが属するホスト グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="906b3-114">You specify the host group a host belongs to when you create the host.</span></span> <span data-ttu-id="906b3-115">BizTalk WMI プロバイダーは、ホスト グループが持つ権限 (たとえば、SQL Server ログインとデータベース ユーザー アクセスを含むランタイム機能に必要な BizTalk Server 権限) をホストに付与します。</span><span class="sxs-lookup"><span data-stu-id="906b3-115">The BizTalk WMI provider grants the privileges that the host group has (for example, the BizTalk Server privileges required for runtime functionality, including SQL Server logins and database user access) to the host.</span></span> <span data-ttu-id="906b3-116">BizTalk Server WMI プロバイダーがホスト グループの権限をホスト インスタンスに付与するため、ホスト インスタンスを作成する際には、正しいサービス アカウント (ホスト) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="906b3-116">You must specify the correct service account (host) when you create a host instance, so that the BizTalk Server WMI provider grants the privileges of the host group to the host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="906b3-117">ローカルのホスト グループを作成する場合、ローカル Windows グループを作成し、グループのメンバーとしてドメイン ユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="906b3-117">If you want to create a local host group, you can create a local Windows group and assign a domain user as a member of the group.</span></span> <span data-ttu-id="906b3-118">ホストに対してローカル Windows グループを指定すると、ドメイン ユーザーおよびローカル ユーザーのどちらであるかに関係なく、ホスト インスタンスのログオン ユーザーとして Windows グループのメンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="906b3-118">If you specify a local Windows group for the Host, the Windows group member, whether it is a domain or local user, can be used as the host instance log-on user.</span></span>  

## <a name="required-permissions"></a><span data-ttu-id="906b3-119">必要な権限</span><span class="sxs-lookup"><span data-stu-id="906b3-119">Required permissions</span></span>  
 <span data-ttu-id="906b3-120">ホスト グループには、次の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="906b3-120">The host group requires the following privileges:</span></span>  
  
-   <span data-ttu-id="906b3-121">ホスト グループは、次のデータベースの BTS_HOST_USERS SQL Server ロールのメンバーである必要がある。</span><span class="sxs-lookup"><span data-stu-id="906b3-121">It must be a member of the BTS_HOST_USERS SQL Server role in the following databases:</span></span>  
  
    -   <span data-ttu-id="906b3-122">BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="906b3-122">BizTalk Management</span></span> 
  
    -   <span data-ttu-id="906b3-123">メッセージ ボックス</span><span class="sxs-lookup"><span data-stu-id="906b3-123">MessageBox</span></span>  
  
    -   <span data-ttu-id="906b3-124">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="906b3-124">Rule Engine</span></span>  
  
    -   <span data-ttu-id="906b3-125">Tracking</span><span class="sxs-lookup"><span data-stu-id="906b3-125">Tracking</span></span>  
  
    -   <span data-ttu-id="906b3-126">BAM プライマリ インポート</span><span class="sxs-lookup"><span data-stu-id="906b3-126">BAM Primary Import</span></span>  
  
-   <span data-ttu-id="906b3-127">Bts _ のメンバーである必要があります、\<インプロセス ホスト名\>メッセージ ボックス データベースの SQL Server ロールを (_u)</span><span class="sxs-lookup"><span data-stu-id="906b3-127">It must be a member of the BTS_\<in-process host name\>_USERS SQL Server role for the MessageBox database</span></span>  
  
-   <span data-ttu-id="906b3-128">BAM プライマリ インポート データベースの BAM_EVENT_WRITER SQL Server ロールのメンバーである必要がある。</span><span class="sxs-lookup"><span data-stu-id="906b3-128">It must be a member of the BAM_EVENT_WRITER SQL Server role in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="906b3-129">追跡ホストとしてホストを指定すると、BizTalk Server 管理コンソールは、追跡データベースの SQL Server ロールから BizTalk ホスト グループを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="906b3-129">If you designate a host as a tracking host, BizTalk Server Administration automatically removes the BizTalk Host group from the SQL Server roles for the Tracking database.</span></span> <span data-ttu-id="906b3-130">BizTalk ホスト グループは、BizTalk 管理データベースとメッセージ ボックス データベースの SQL Server ロールから手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="906b3-130">You must manually remove the BizTalk Host group from the SQL Server roles for the BizTalk Management database and the MessageBox database.</span></span> <span data-ttu-id="906b3-131">追跡ホストとしてホストを指定する方法については、次を参照してください。[ホスト プロパティの変更](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="906b3-131">For information about designating a host as a tracking host, see [Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906b3-132">参照</span><span class="sxs-lookup"><span data-stu-id="906b3-132">See Also</span></span>  
 [<span data-ttu-id="906b3-133">エンティティ</span><span class="sxs-lookup"><span data-stu-id="906b3-133">Entities</span></span>](../core/entities.md)