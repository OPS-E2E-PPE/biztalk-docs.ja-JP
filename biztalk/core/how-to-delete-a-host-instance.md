---
title: ホスト インスタンスを削除する |Microsoft ドキュメント
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
ms.openlocfilehash: 798ea341ef61b15729dd15742eef7701641e7547
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249202"
---
# <a name="delete-a-host-instance"></a><span data-ttu-id="96c5f-102">ホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="96c5f-102">Delete a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="96c5f-103">概要</span><span class="sxs-lookup"><span data-stu-id="96c5f-103">Overview</span></span>
<span data-ttu-id="96c5f-104">使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは Windows Management Instrumentation (WMI) をホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="96c5f-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to delete host instances.</span></span> <span data-ttu-id="96c5f-105">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="96c5f-105">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="96c5f-106">WMI を使用してホスト インスタンスを削除する方法については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="96c5f-106">For information about using WMI to delete a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="96c5f-107">ホスト インスタンスを削除すると、BizTalk Server ランタイムのインスタンスが、関連付けられたサーバーから削除されます。また、BizTalk 管理データベースが、ホストからそのインスタンスを削除するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="96c5f-107">When you delete a host instance, the instance of the BizTalk Server runtime is removed from the associated server and the BizTalk Management database is updated to remove that instance from the host.</span></span>  
  
 <span data-ttu-id="96c5f-108">ホスト インスタンスを削除したときにメッセージが失われることのないように、BizTalk Server では、インスタンスが実際に削除される前にすべての処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="96c5f-108">To avoid losing messages when you delete a host instance, BizTalk Server completes all processing before the instance is actually removed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96c5f-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="96c5f-109">Prerequisites</span></span>  
 <span data-ttu-id="96c5f-110">ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c5f-110">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="96c5f-111">また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="96c5f-111">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="96c5f-112">BAM プライマリ インポート (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="96c5f-112">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="96c5f-113">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="96c5f-113">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="96c5f-114">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)</span><span class="sxs-lookup"><span data-stu-id="96c5f-114">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="96c5f-115">BizTalk 追跡 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="96c5f-115">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="96c5f-116">ルール エンジン (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="96c5f-116">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="96c5f-117">ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96c5f-117">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="96c5f-118">これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="96c5f-118">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="96c5f-119">手順</span><span class="sxs-lookup"><span data-stu-id="96c5f-119">Steps</span></span>
  
1.  <span data-ttu-id="96c5f-120">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="96c5f-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="96c5f-121">コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループ、をクリックして**プラットフォームの設定**、順にクリック**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="96c5f-121">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="96c5f-122">詳細ウィンドウで、削除、およびをクリックするホスト インスタンスを右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="96c5f-122">In the details pane, right-click the host instance you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="96c5f-123">**確認ホスト インスタンスの削除**ダイアログ ボックスで、をクリックして**はい**です。</span><span class="sxs-lookup"><span data-stu-id="96c5f-123">In the **Confirm delete host instance** dialog box, click **Yes**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96c5f-124">BizTalk Server でホスト インスタンスを削除できない場合は、別のダイアログ ボックスが表示され、ホスト インスタンスを強制的に削除できます。</span><span class="sxs-lookup"><span data-stu-id="96c5f-124">If BizTalk Server cannot delete the host instance, a dialog box appears in which you can force the deletion of the host instance.</span></span> <span data-ttu-id="96c5f-125">提供される内容を読み、をクリックして**はい**ホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="96c5f-125">After reading the information provided, click **Yes** to delete the host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c5f-126">参照</span><span class="sxs-lookup"><span data-stu-id="96c5f-126">See Also</span></span>  
 <span data-ttu-id="96c5f-127">[BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="96c5f-127">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="96c5f-128">[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="96c5f-128">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="96c5f-129">[ホスト インスタンスを起動する方法](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="96c5f-129">[How to Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="96c5f-130">[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="96c5f-130">[How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 [<span data-ttu-id="96c5f-131">ホスト インスタンスのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="96c5f-131">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)