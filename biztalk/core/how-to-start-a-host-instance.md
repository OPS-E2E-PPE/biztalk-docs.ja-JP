---
title: ホスト インスタンスを起動 |Microsoft ドキュメント
description: BizTalk 管理コンソールを使用して、BizTalk Server でホスト インスタンスを開始するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96a4362-2147-4b8e-a270-bf9a17477ba3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd5cccc48b33dda4b6458f8dfa8f56a84ad3cd62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255818"
---
# <a name="start-a-host-instance"></a><span data-ttu-id="446d0-103">ホスト インスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="446d0-103">Start a Host Instance</span></span>
<span data-ttu-id="446d0-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、ホスト インスタンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="446d0-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to start host instances.</span></span> <span data-ttu-id="446d0-105">ホスト インスタンスを追加または停止したら、インスタンスを開始し、実行して、メッセージがメッセージ ボックス データベースにルーティングされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="446d0-105">After you add or stop a host instance, you must start it so that it is running and routing messages to the MessageBox databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="446d0-106">ホスト インスタンスに指定するサービス アカウントは、関連するホストの Windows グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="446d0-106">The service account that you specify for a host instance should be a member of the Windows group for the associated host.</span></span> <span data-ttu-id="446d0-107">それ以外の場合、ホスト インスタンスには、実行時に適切なアクセス許可または認証がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="446d0-107">Otherwise, the host instance may not have the appropriate permissions or authentication at run time.</span></span> <span data-ttu-id="446d0-108">また、セキュリティ上の理由により、ホスト インスタンスでホストされているオーケストレーションが悪意のあるカスタム コードを実行する可能性があるため、アカウントには、最小限の特権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446d0-108">In addition, for security reasons, the account should have minimum privileges because orchestrations hosted by the host instance might execute potentially malicious custom code.</span></span>  
  
 <span data-ttu-id="446d0-109">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="446d0-109">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="446d0-110">WMI を使用してホスト インスタンスを起動する方法については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="446d0-110">For information about using WMI to start a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="446d0-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="446d0-111">Prerequisites</span></span>  
 <span data-ttu-id="446d0-112">ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="446d0-112">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="446d0-113">また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="446d0-113">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="446d0-114">BAM プライマリ インポート (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="446d0-114">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="446d0-115">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="446d0-115">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="446d0-116">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)</span><span class="sxs-lookup"><span data-stu-id="446d0-116">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="446d0-117">BizTalk 追跡 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="446d0-117">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="446d0-118">ルール エンジン (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="446d0-118">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="446d0-119">ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="446d0-119">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="446d0-120">これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="446d0-120">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="446d0-121">手順</span><span class="sxs-lookup"><span data-stu-id="446d0-121">Steps</span></span>
  
1.  <span data-ttu-id="446d0-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="446d0-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="446d0-123">コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループ、をクリックして**プラットフォームの設定**、順にクリック**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="446d0-123">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="446d0-124">開始して、をクリックするホスト インスタンスを右クリックし、詳細ウィンドウで、**開始**です。</span><span class="sxs-lookup"><span data-stu-id="446d0-124">In the details pane, right-click the host instance you want to start, and then click **Start**.</span></span>  
  
     <span data-ttu-id="446d0-125">ホスト インスタンスの状態に変わる**開始待ち**です。</span><span class="sxs-lookup"><span data-stu-id="446d0-125">The status of the host instance changes to **Start pending**.</span></span> <span data-ttu-id="446d0-126">ホスト インスタンスが開始すると、状態に変わります**を実行している**です。</span><span class="sxs-lookup"><span data-stu-id="446d0-126">After the host instance initiates, the status changes to **Running**.</span></span>  
  
 <span data-ttu-id="446d0-127">ホスト インスタンスを開始後、インスタンスを停止して、メッセージがメッセージ ボックス データベースにルーティングされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="446d0-127">After you start a host instance, you can stop it to prevent it from routing messages to the MessageBox database.</span></span> <span data-ttu-id="446d0-128">特定のコンピューターから BizTalk Server を削除する前に、ホスト インスタンスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446d0-128">You must stop a host instance before you can remove BizTalk Server from a given computer.</span></span> <span data-ttu-id="446d0-129">ホスト インスタンスを停止する方法については、次を参照してください。[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)です。</span><span class="sxs-lookup"><span data-stu-id="446d0-129">For information about stopping a host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446d0-130">参照</span><span class="sxs-lookup"><span data-stu-id="446d0-130">See Also</span></span>  
 <span data-ttu-id="446d0-131">[BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="446d0-131">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="446d0-132">[ホスト インスタンスを追加します。](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="446d0-132">[Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="446d0-133">[ホスト インスタンスを停止します。](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="446d0-133">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 <span data-ttu-id="446d0-134">[ホスト インスタンスを削除します。](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="446d0-134">[Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="446d0-135">ホスト インスタンスのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="446d0-135">Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)