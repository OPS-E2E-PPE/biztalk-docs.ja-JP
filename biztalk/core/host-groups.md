---
title: ホスト グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e56411a55fefd4c54c1a0583b619e68b868e2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344273"
---
# <a name="host-groups"></a><span data-ttu-id="12ea9-102">ホスト グループ</span><span class="sxs-lookup"><span data-stu-id="12ea9-102">Host Groups</span></span>

## <a name="overview"></a><span data-ttu-id="12ea9-103">概要</span><span class="sxs-lookup"><span data-stu-id="12ea9-103">Overview</span></span>
<span data-ttu-id="12ea9-104">ホスト グループ (既定では、BizTalk Application Users グループをという名前)、Windows グループでは、インプロセス BizTalk ホスト (BizTalk Server ホスト プロセス) へのアクセス権を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="12ea9-104">The host group is the Windows group (named the BizTalk Application Users group by default) that you use for accounts with access to the in-process BizTalk hosts (host processes in BizTalk Server).</span></span> <span data-ttu-id="12ea9-105">環境内で、インプロセス ホストごとに 1 つのホスト グループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12ea9-105">It is recommended that you use one host group for each in-process host in your environment.</span></span>  
  
 <span data-ttu-id="12ea9-106">1 つの Windows グループにのみ、ホストを関連付けることができます (と呼ばれる、*ホスト グループ*)。</span><span class="sxs-lookup"><span data-stu-id="12ea9-106">You can only associate a host with one Windows group (called a *host group*).</span></span> <span data-ttu-id="12ea9-107">ホスト グループは、関連するすべての BizTalk Server データベースで SQL Server ログインと特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="12ea9-107">The host group must have a SQL Server login and privileges in all relevant BizTalk Server databases.</span></span> <span data-ttu-id="12ea9-108">ホストをホスト グループに関連付けると、ホストにホスト グループの権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="12ea9-108">When you associate a host with the host group, you grant the host the privileges of the host group.</span></span>  
  
 <span data-ttu-id="12ea9-109">ホストを作成、構成ウィザードを使用するホストに使用するローカル Windows グループを指定する場合は、構成ウィザードは自動的に 2 つの Windows グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="12ea9-109">If you use the Configuration Wizard to create hosts, and you specify a local Windows group to use for hosts, the Configuration Wizard automatically creates two Windows groups.</span></span> <span data-ttu-id="12ea9-110">これらのグループの既定の名前は、BizTalk Application Users グループと BizTalk 分離ホスト ユーザー グループです。</span><span class="sxs-lookup"><span data-stu-id="12ea9-110">The default names of these groups are the BizTalk Application Users group and the BizTalk Isolated Host Users group.</span></span>  
  
 <span data-ttu-id="12ea9-111">ホスト グループに関連付けられているホストのホスト インスタンスを作成するときに、ホスト インスタンスは、ホスト グループのデータベースの権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="12ea9-111">When you create a host instance of a host associated with the host group, the host instance inherits the database privileges of the host group.</span></span>  
  
 <span data-ttu-id="12ea9-112">ホスト グループは、ホストの Windows Management Instrumentation (WMI) オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="12ea9-112">The host group is a property of the host Windows Management Instrumentation (WMI) object.</span></span> <span data-ttu-id="12ea9-113">ホストのホスト インスタンスがない場合に、ホストが属する Windows グループを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="12ea9-113">You can change the Windows group that a host belongs to if there are no host instances of the host.</span></span>  
  
 <span data-ttu-id="12ea9-114">ホストが属するホストを作成するときに、ホスト グループを指定するとします。</span><span class="sxs-lookup"><span data-stu-id="12ea9-114">You specify the host group a host belongs to when you create the host.</span></span> <span data-ttu-id="12ea9-115">BizTalk WMI プロバイダーは、ホスト グループをホストに (たとえば、SQL Server ログインとデータベース ユーザーへのアクセスなど、ランタイム機能に必要な BizTalk Server の特権など) には、特権を付与します。</span><span class="sxs-lookup"><span data-stu-id="12ea9-115">The BizTalk WMI provider grants the privileges that the host group has (for example, the BizTalk Server privileges required for runtime functionality, including SQL Server logins and database user access) to the host.</span></span> <span data-ttu-id="12ea9-116">指定してください、正しいサービス アカウント (ホスト)、ホスト インスタンスを作成するときに、BizTalk Server WMI プロバイダーがホスト グループの権限を付与するため、ホスト インスタンスに。</span><span class="sxs-lookup"><span data-stu-id="12ea9-116">You must specify the correct service account (host) when you create a host instance, so that the BizTalk Server WMI provider grants the privileges of the host group to the host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12ea9-117">ローカルのホスト グループを作成する場合は、ローカル Windows グループを作成し、グループのメンバーとしてドメイン ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="12ea9-117">If you want to create a local host group, you can create a local Windows group and assign a domain user as a member of the group.</span></span> <span data-ttu-id="12ea9-118">ホストのローカル Windows グループを指定する場合、Windows グループのメンバーでドメインまたはローカルのユーザーがいるかどうか使用できますホスト インスタンスのログオン ユーザーとして。</span><span class="sxs-lookup"><span data-stu-id="12ea9-118">If you specify a local Windows group for the Host, the Windows group member, whether it is a domain or local user, can be used as the host instance log-on user.</span></span>  

## <a name="required-permissions"></a><span data-ttu-id="12ea9-119">必要な権限</span><span class="sxs-lookup"><span data-stu-id="12ea9-119">Required permissions</span></span>  
 <span data-ttu-id="12ea9-120">ホスト グループには、次の特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="12ea9-120">The host group requires the following privileges:</span></span>  
  
-   <span data-ttu-id="12ea9-121">次のデータベースの BTS_HOST_USERS SQL Server ロールのメンバーの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12ea9-121">It must be a member of the BTS_HOST_USERS SQL Server role in the following databases:</span></span>  
  
    -   <span data-ttu-id="12ea9-122">BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="12ea9-122">BizTalk Management</span></span> 
  
    -   <span data-ttu-id="12ea9-123">メッセージ ボックス</span><span class="sxs-lookup"><span data-stu-id="12ea9-123">MessageBox</span></span>  
  
    -   <span data-ttu-id="12ea9-124">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="12ea9-124">Rule Engine</span></span>  
  
    -   <span data-ttu-id="12ea9-125">Tracking</span><span class="sxs-lookup"><span data-stu-id="12ea9-125">Tracking</span></span>  
  
    -   <span data-ttu-id="12ea9-126">BAM プライマリ インポート</span><span class="sxs-lookup"><span data-stu-id="12ea9-126">BAM Primary Import</span></span>  
  
-   <span data-ttu-id="12ea9-127">Bts _ のメンバーである必要があります、\<インプロセス ホスト名\>メッセージ ボックス データベースの SQL Server ロールを (_u)</span><span class="sxs-lookup"><span data-stu-id="12ea9-127">It must be a member of the BTS_\<in-process host name\>_USERS SQL Server role for the MessageBox database</span></span>  
  
-   <span data-ttu-id="12ea9-128">BAM プライマリ インポート データベースの BAM_EVENT_WRITER SQL Server ロールのメンバーであるする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ea9-128">It must be a member of the BAM_EVENT_WRITER SQL Server role in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12ea9-129">追跡ホストとしてホストを指定すると、追跡データベースの SQL Server ロールから BizTalk ホスト グループは、BizTalk Server 管理コンソールによって自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="12ea9-129">If you designate a host as a tracking host, BizTalk Server Administration automatically removes the BizTalk Host group from the SQL Server roles for the Tracking database.</span></span> <span data-ttu-id="12ea9-130">BizTalk 管理データベースとメッセージ ボックス データベースの SQL Server ロールから BizTalk ホスト グループを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ea9-130">You must manually remove the BizTalk Host group from the SQL Server roles for the BizTalk Management database and the MessageBox database.</span></span> <span data-ttu-id="12ea9-131">追跡ホストとしてホストを指定する方法の詳細については、次を参照してください。[ホスト プロパティの変更](../core/how-to-modify-host-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="12ea9-131">For information about designating a host as a tracking host, see [Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ea9-132">参照</span><span class="sxs-lookup"><span data-stu-id="12ea9-132">See Also</span></span>  
 [<span data-ttu-id="12ea9-133">エンティティ</span><span class="sxs-lookup"><span data-stu-id="12ea9-133">Entities</span></span>](../core/entities.md)