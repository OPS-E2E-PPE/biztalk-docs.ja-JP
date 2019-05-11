---
title: ホスト インスタンスの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35a06480-0962-4bdc-add2-56f979a2f1c9
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 472dac5fe3f4cf71431ad670b87aa3a1958abf9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338787"
---
# <a name="delete-a-host-instance"></a><span data-ttu-id="87383-102">ホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="87383-102">Delete a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="87383-103">概要</span><span class="sxs-lookup"><span data-stu-id="87383-103">Overview</span></span>
<span data-ttu-id="87383-104">使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは Windows Management Instrumentation (WMI) ホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="87383-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to delete host instances.</span></span> <span data-ttu-id="87383-105">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="87383-105">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="87383-106">WMI を使用して、ホスト インスタンスを削除する方法の詳細については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="87383-106">For information about using WMI to delete a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="87383-107">ホスト インスタンスを削除すると、BizTalk Server ランタイムのインスタンスが、関連付けられたサーバーから削除されます。また、BizTalk 管理データベースが、ホストからそのインスタンスを削除するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="87383-107">When you delete a host instance, the instance of the BizTalk Server runtime is removed from the associated server and the BizTalk Management database is updated to remove that instance from the host.</span></span>  
  
 <span data-ttu-id="87383-108">ホスト インスタンスを削除したときにメッセージが失われることのないように、BizTalk Server では、インスタンスが実際に削除される前にすべての処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="87383-108">To avoid losing messages when you delete a host instance, BizTalk Server completes all processing before the instance is actually removed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87383-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="87383-109">Prerequisites</span></span>  
 <span data-ttu-id="87383-110">ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87383-110">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="87383-111">また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="87383-111">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="87383-112">BAM プライマリ インポート (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="87383-112">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="87383-113">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="87383-113">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="87383-114">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)</span><span class="sxs-lookup"><span data-stu-id="87383-114">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="87383-115">BizTalk 追跡 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="87383-115">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="87383-116">ルール エンジン (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="87383-116">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="87383-117">ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="87383-117">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="87383-118">これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="87383-118">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="87383-119">手順</span><span class="sxs-lookup"><span data-stu-id="87383-119">Steps</span></span>
  
1. <span data-ttu-id="87383-120">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="87383-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="87383-121">コンソール ツリーで、展開**BizTalk Server 管理**BizTalk グループ、をクリックして**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="87383-121">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="87383-122">詳細ペインで、削除、およびクリックするホスト インスタンスを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="87383-122">In the details pane, right-click the host instance you want to delete, and then click **Delete**.</span></span>  
  
4. <span data-ttu-id="87383-123">**ホスト インスタンスの削除確認**ダイアログ ボックスで、をクリックして **[はい]** します。</span><span class="sxs-lookup"><span data-stu-id="87383-123">In the **Confirm delete host instance** dialog box, click **Yes**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="87383-124">BizTalk Server でホスト インスタンスを削除できない場合は、別のダイアログ ボックスが表示され、ホスト インスタンスを強制的に削除できます。</span><span class="sxs-lookup"><span data-stu-id="87383-124">If BizTalk Server cannot delete the host instance, a dialog box appears in which you can force the deletion of the host instance.</span></span> <span data-ttu-id="87383-125">提供される情報を読むには、次のようにクリックします。**はい**ホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="87383-125">After reading the information provided, click **Yes** to delete the host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87383-126">参照</span><span class="sxs-lookup"><span data-stu-id="87383-126">See Also</span></span>  
 <span data-ttu-id="87383-127">[BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="87383-127">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="87383-128">[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="87383-128">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="87383-129">[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="87383-129">[How to Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="87383-130">[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="87383-130">[How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 [<span data-ttu-id="87383-131">ホスト インスタンスのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="87383-131">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)