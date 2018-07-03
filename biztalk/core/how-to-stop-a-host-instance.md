---
title: ホスト インスタンスの停止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1f2e0c1-a387-4182-82ef-e25f49ac509b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b66c89ccafa72c56de00aebd24091915643f44e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972675"
---
# <a name="stop-a-host-instance"></a><span data-ttu-id="4be25-102">ホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="4be25-102">Stop a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="4be25-103">概要</span><span class="sxs-lookup"><span data-stu-id="4be25-103">Overview</span></span>
<span data-ttu-id="4be25-104">使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは Windows Management Instrumentation (WMI) をホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="4be25-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to stop host instances.</span></span> <span data-ttu-id="4be25-105">コンピューターからホスト インスタンスまたは BizTalk Server を削除する前に、ホスト インスタンスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be25-105">You must stop a host instance before you can delete it or remove BizTalk Server from a computer.</span></span> <span data-ttu-id="4be25-106">インストールされ、開始しているホスト インスタンスを停止できます。</span><span class="sxs-lookup"><span data-stu-id="4be25-106">You can stop a host instance that is installed and started.</span></span> <span data-ttu-id="4be25-107">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="4be25-107">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="4be25-108">WMI を使用して、ホスト インスタンスを停止する方法の詳細については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4be25-108">For information about using WMI to stop a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="4be25-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="4be25-109">Prerequisites</span></span>  
 <span data-ttu-id="4be25-110">ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be25-110">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="4be25-111">また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="4be25-111">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="4be25-112">BAM プライマリ インポート (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="4be25-112">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="4be25-113">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="4be25-113">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="4be25-114">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)</span><span class="sxs-lookup"><span data-stu-id="4be25-114">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="4be25-115">BizTalk 追跡 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="4be25-115">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="4be25-116">ルール エンジン (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="4be25-116">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4be25-117">ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4be25-117">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="4be25-118">これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="4be25-118">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="4be25-119">手順</span><span class="sxs-lookup"><span data-stu-id="4be25-119">Steps</span></span>
  
1. <span data-ttu-id="4be25-120">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4be25-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4be25-121">コンソール ツリーで、展開**BizTalk Server 管理**BizTalk グループ、をクリックして**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="4be25-121">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="4be25-122">詳細ペインで、停止、およびクリックするホスト インスタンスを右クリックして**停止**します。</span><span class="sxs-lookup"><span data-stu-id="4be25-122">In the details pane, right-click the host instance you want to stop, and then click **Stop**.</span></span>  
  
    <span data-ttu-id="4be25-123">ホスト インスタンスの状態に変わる**Stopped**します。</span><span class="sxs-lookup"><span data-stu-id="4be25-123">The status of the host instance changes to **Stopped**.</span></span>  
  
   <span data-ttu-id="4be25-124">ホスト インスタンスを開始または削除するか、コンピューターから BizTalk Server を削除する場合、まず、ホスト インスタンスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be25-124">After you stop a host instance, you can start it, delete it, or remove BizTalk Server from the computer.</span></span> <span data-ttu-id="4be25-125">ホスト インスタンスの開始方法の詳細については、次を参照してください。[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="4be25-125">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span> <span data-ttu-id="4be25-126">ホスト インスタンスの削除方法の詳細については、次を参照してください。[ホスト インスタンスを削除する方法](../core/how-to-delete-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="4be25-126">For information about deleting a host instance, see [How to Delete a Host Instance](../core/how-to-delete-a-host-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be25-127">参照</span><span class="sxs-lookup"><span data-stu-id="4be25-127">See Also</span></span>  
 <span data-ttu-id="4be25-128">[BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="4be25-128">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="4be25-129">[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="4be25-129">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="4be25-130">[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="4be25-130">[How to Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="4be25-131">[ホスト インスタンスを削除する方法](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="4be25-131">[How to Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="4be25-132">ホスト インスタンスのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="4be25-132">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)