---
title: "ホスト グループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host groups, privileges
- Windows groups, host groups
- host groups, Windows groups
- host groups, about host groups
- host groups
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98e3798e42442e1a6533e4f286d194c8e2474be6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="host-groups"></a><span data-ttu-id="53b70-102">ホスト グループ</span><span class="sxs-lookup"><span data-stu-id="53b70-102">Host Groups</span></span>
<span data-ttu-id="53b70-103">ホスト グループは、インプロセスの BizTalk ホスト (BizTalk Server のホスト プロセス) に対するアクセスに使用するアカウントの Windows グループ (既定で BizTalk アプリケーション ユーザー グループという名前) です。</span><span class="sxs-lookup"><span data-stu-id="53b70-103">The host group is the Windows group (named the BizTalk Application Users group by default) that you use for accounts with access to the in-process BizTalk hosts (host processes in BizTalk Server).</span></span> <span data-ttu-id="53b70-104">使用している環境のインプロセス ホストごとに 1 つのホスト グループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53b70-104">It is recommended that you use one host group for each in-process host in your environment.</span></span>  
  
 <span data-ttu-id="53b70-105">ホストは 1 つの Windows グループとのみ関連付けることができます (と呼ばれる、*ホスト グループ*)。</span><span class="sxs-lookup"><span data-stu-id="53b70-105">You can only associate a host with one Windows group (called a *host group*).</span></span> <span data-ttu-id="53b70-106">ホスト グループには、すべての関連する BizTalk Server データベースの SQL Server ログインと権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="53b70-106">The host group must have a SQL Server login and privileges in all relevant BizTalk Server databases.</span></span> <span data-ttu-id="53b70-107">ホストをホスト グループに関連付けると、ホストにホスト グループの権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="53b70-107">When you associate a host with the host group, you grant the host the privileges of the host group.</span></span>  
  
 <span data-ttu-id="53b70-108">構成ウィザードでホストを作成し、ホストに対してローカル Windows グループを指定すると、構成ウィザードは、自動的に 2 つの Windows グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="53b70-108">If you use the Configuration Wizard to create hosts, and you specify a local Windows group to use for hosts, the Configuration Wizard automatically creates two Windows groups.</span></span> <span data-ttu-id="53b70-109">これらのグループの既定の名前は、BizTalk アプリケーション ユーザー グループと BizTalk 分離ホスト ユーザー グループです。</span><span class="sxs-lookup"><span data-stu-id="53b70-109">The default names of these groups are the BizTalk Application Users group and the BizTalk Isolated Host Users group.</span></span>  
  
 <span data-ttu-id="53b70-110">ホスト グループに関連付けられているホストのホスト インスタンスを作成すると、ホスト インスタンスは、ホスト グループのデータベース権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="53b70-110">When you create a host instance of a host associated with the host group, the host instance inherits the database privileges of the host group.</span></span>  
  
 <span data-ttu-id="53b70-111">ホスト グループは、ホストの WMI (Windows Management Instrumentation) オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="53b70-111">The host group is a property of the host Windows Management Instrumentation (WMI) object.</span></span> <span data-ttu-id="53b70-112">ホストにホスト インスタンスがない場合は、ホストが属する Windows グループを変更できます。</span><span class="sxs-lookup"><span data-stu-id="53b70-112">You can change the Windows group that a host belongs to if there are no host instances of the host.</span></span>  
  
 <span data-ttu-id="53b70-113">ホストを作成する際、ホストが属するホスト グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="53b70-113">You specify the host group a host belongs to when you create the host.</span></span> <span data-ttu-id="53b70-114">BizTalk WMI プロバイダーは、ホスト グループが持つ権限 (たとえば、SQL Server ログインとデータベース ユーザー アクセスを含むランタイム機能に必要な BizTalk Server 権限) をホストに付与します。</span><span class="sxs-lookup"><span data-stu-id="53b70-114">The BizTalk WMI provider grants the privileges that the host group has (for example, the BizTalk Server privileges required for runtime functionality, including SQL Server logins and database user access) to the host.</span></span> <span data-ttu-id="53b70-115">BizTalk Server WMI プロバイダーがホスト グループの権限をホスト インスタンスに付与するため、ホスト インスタンスを作成する際には、正しいサービス アカウント (ホスト) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53b70-115">You must specify the correct service account (host) when you create a host instance, so that the BizTalk Server WMI provider grants the privileges of the host group to the host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53b70-116">ローカルのホスト グループを作成する場合、ローカル Windows グループを作成し、グループのメンバーとしてドメイン ユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="53b70-116">If you want to create a local host group, you can create a local Windows group and assign a domain user as a member of the group.</span></span> <span data-ttu-id="53b70-117">ホストに対してローカル Windows グループを指定すると、ドメイン ユーザーおよびローカル ユーザーのどちらであるかに関係なく、ホスト インスタンスのログオン ユーザーとして Windows グループのメンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="53b70-117">If you specify a local Windows group for the Host, the Windows group member, whether it is a domain or local user, can be used as the host instance log-on user.</span></span>  
  
 <span data-ttu-id="53b70-118">ホスト グループには、次の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="53b70-118">The host group requires the following privileges:</span></span>  
  
-   <span data-ttu-id="53b70-119">ホスト グループは、次のデータベースの BTS_HOST_USERS SQL Server ロールのメンバーである必要がある。</span><span class="sxs-lookup"><span data-stu-id="53b70-119">It must be a member of the BTS_HOST_USERS SQL Server role in the following databases:</span></span>  
  
    -   <span data-ttu-id="53b70-120">BizTalk 管理 ([!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] では構成データベースと呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="53b70-120">BizTalk Management (known as the Configuration database in [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)])</span></span>  
  
    -   <span data-ttu-id="53b70-121">メッセージ ボックス</span><span class="sxs-lookup"><span data-stu-id="53b70-121">MessageBox</span></span>  
  
    -   <span data-ttu-id="53b70-122">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="53b70-122">Rule Engine</span></span>  
  
    -   <span data-ttu-id="53b70-123">Tracking</span><span class="sxs-lookup"><span data-stu-id="53b70-123">Tracking</span></span>  
  
    -   <span data-ttu-id="53b70-124">BAM プライマリ インポート</span><span class="sxs-lookup"><span data-stu-id="53b70-124">BAM Primary Import</span></span>  
  
-   <span data-ttu-id="53b70-125">Bts _ のメンバーである必要があります、\<インプロセス ホスト名\>メッセージ ボックス データベースの SQL Server ロールを (_u)</span><span class="sxs-lookup"><span data-stu-id="53b70-125">It must be a member of the BTS_\<in-process host name\>_USERS SQL Server role for the MessageBox database</span></span>  
  
-   <span data-ttu-id="53b70-126">BAM プライマリ インポート データベースの BAM_EVENT_WRITER SQL Server ロールのメンバーである必要がある。</span><span class="sxs-lookup"><span data-stu-id="53b70-126">It must be a member of the BAM_EVENT_WRITER SQL Server role in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53b70-127">追跡ホストとしてホストを指定すると、BizTalk Server 管理コンソールは、追跡データベースの SQL Server ロールから BizTalk ホスト グループを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="53b70-127">If you designate a host as a tracking host, BizTalk Server Administration automatically removes the BizTalk Host group from the SQL Server roles for the Tracking database.</span></span> <span data-ttu-id="53b70-128">BizTalk ホスト グループは、BizTalk 管理データベースとメッセージ ボックス データベースの SQL Server ロールから手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53b70-128">You must manually remove the BizTalk Host group from the SQL Server roles for the BizTalk Management database and the MessageBox database.</span></span> <span data-ttu-id="53b70-129">追跡ホストとしてホストを指定する方法については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="53b70-129">For information about designating a host as a tracking host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b70-130">参照</span><span class="sxs-lookup"><span data-stu-id="53b70-130">See Also</span></span>  
 [<span data-ttu-id="53b70-131">エンティティ</span><span class="sxs-lookup"><span data-stu-id="53b70-131">Entities</span></span>](../core/entities.md)