---
title: "BizTalk Server で BizTalk RosettaNet Accelerator (BTARN) をアンインストール |Microsoft ドキュメント\""
description: "成果物を展開解除して、アクセラレータを BizTalk Server から削除する BTARN の構成を解除"
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
ms.author: mandia
ms.openlocfilehash: 8d289a3705eb0c127dc4d2637c2d6ffd3c122b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="uninstall-the-rosettanet-accelerator"></a><span data-ttu-id="b31c4-103">RosettaNet accelerator をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b31c4-103">Uninstall the RosettaNet accelerator</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b31c4-104">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="b31c4-104">Before you begin</span></span>
  
* <span data-ttu-id="b31c4-105">のみを実行する場合**Setup.exe**、アンインストール プロセスでは、ビジネス アクティビティ監視 (BAM) アイテム、BizTalk アイテム、インターネット インフォメーション サービス (IIS) 仮想ディレクトリ、およびアプリケーション プールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b31c4-105">If you only run **Setup.exe**, the uninstall process does not remove the Business Activity Monitoring (BAM) artifacts, the BizTalk artifacts, Internet Information Services (IIS) virtual directories, and application pools.</span></span>  
  
* <span data-ttu-id="b31c4-106">使用した場合、**ループバック**、1 台のコンピューターの展開用のミラー アグリーメントを作成するユーティリティとツールを実行、**を無効にする/<** **ホーム組織** **>** でパートナーを削除する前にオプション、 **BTARN 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-106">If you used the **Loopback** utility to create mirror agreements for a single-computer deployment, then run the tool with the **/disable <** **home organization** **>** option before deleting the partners in the **BTARN Administration Console**.</span></span>  
  
* <span data-ttu-id="b31c4-107">このサーバーが複数コンピュータ展開の一部である場合は実行しないで、 **BtarnClean**ユーティリティまたは手動で BTARN アセンブリを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-107">If this server is part of a multi-computer deployment, do not run the **BtarnClean** utility or manually undeploy the BTARN assemblies.</span></span> <span data-ttu-id="b31c4-108">1 台のコンピューター上のアイテムを削除すると、他のコンピューターの機能が中断されます。</span><span class="sxs-lookup"><span data-stu-id="b31c4-108">Removing the artifacts on one computer breaks the functionality of the other computers.</span></span>  <span data-ttu-id="b31c4-109">すべてのサーバーから BTARN をアンインストールする場合を実行し、 **BtarnClean**ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="b31c4-109">If you want to uninstall BTARN from all the servers, then run the **BtarnClean** utility.</span></span> 

  
## <a name="undeploy-the-artifacts"></a><span data-ttu-id="b31c4-110">成果物を展開解除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-110">Undeploy the artifacts</span></span>  

<span data-ttu-id="b31c4-111">展開解除する前に、BAM アイテムをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b31c4-111">We recommend backing up your BAM artifacts before undeploying.</span></span> 

1. <span data-ttu-id="b31c4-112">展開したすべての BAM アイテムの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-112">Undeploy all the BAM artifacts that you deployed:</span></span>  
  
    1.  <span data-ttu-id="b31c4-113">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-113">At the command prompt, run the following command:</span></span>  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  <span data-ttu-id="b31c4-114">追跡 UI のインストール完了を示すコマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-114">At the command prompt where the tracking UI was installed, run the following command:</span></span>  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  <span data-ttu-id="b31c4-115">BAM の詳細については、次を参照してください[ビジネス アクティビティ監視の管理。](../../core/managing-bam.md)</span><span class="sxs-lookup"><span data-stu-id="b31c4-115">For more information about BAM, see [Managing Business Activity Monitoring](../../core/managing-bam.md)</span></span> 
  
2.  <span data-ttu-id="b31c4-116">バックアップし、BTARN 管理コンソールからすべてのアグリーメント、パートナー、およびホーム組織を削除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-116">Backup and delete all the agreements, partners, and home organizations from the BTARN Management Console.</span></span> <span data-ttu-id="b31c4-117">参照してください「BTARN 構成の管理」(BTARN ヘルプの操作ノード) を使用する方法について、 **BtarnConfig**アグリーメントとパートナーのバックアップを作成するユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="b31c4-117">See the "Administering the BTARN Configuration" topic (in the Operations node of BTARN Help) for information about using the **BtarnConfig** utility to back up the agreements and partners.</span></span>  
  
    > [!NOTE]
    >  * <span data-ttu-id="b31c4-118">停止しを使用して BTARN によって作成された BizTalk アイテムを展開解除、 [BtarnClean](btarnclean.md)ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="b31c4-118">Stop and undeploy the BizTalk artifacts created by BTARN by using the [BtarnClean](btarnclean.md) utility.</span></span>
    >  * <span data-ttu-id="b31c4-119">展開したその他のアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-119">Remove any additional artifacts that you deployed.</span></span> <span data-ttu-id="b31c4-120">参照してください[BizTalk アプリケーションを展開解除](../../core/undeploying-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-120">See [Undeploying BizTalk Applications](../../core/undeploying-biztalk-applications.md) .</span></span>
  
3.  <span data-ttu-id="b31c4-121">BTARN セットアップ、MSI\Program \microsoft BizTalk Accelerator for rosettanet \sdk フォルダーを探します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-121">From the BTARN Setup, locate the MSI\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK folder.</span></span> <span data-ttu-id="b31c4-122">SDK のフォルダーをダブルクリックして**BTARNClean.exe**、し、 **Y**続けるには、または**N**ユーティリティの実行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="b31c4-122">In the SDK folder, double-click **BTARNClean.exe**, and then select **Y** to continue, or **N** to cancel running the utility.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b31c4-123">サーバーが複数コンピューター展開シナリオで使用されている場合は、手順 3. を省略できます。</span><span class="sxs-lookup"><span data-stu-id="b31c4-123">If your server is part of a multi-computer deployment scenario, you can skip step 3.</span></span> <span data-ttu-id="b31c4-124">共有リソースを削除すると、展開内の他のサーバーが機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="b31c4-124">Undeploying any shared resources breaks the functionality on the other servers in the deployment.</span></span>  
  
4.  <span data-ttu-id="b31c4-125">作成および展開したすべてのカスタム アセンブリの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-125">Undeploy any custom assemblies that you created and deployed.</span></span>  
  
5.  <span data-ttu-id="b31c4-126">コマンド プロンプトで \Program Files\Microsoft BizTalk Server に移動<your version>\Tracking です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-126">At the command prompt, go to \Program Files\Microsoft BizTalk Server <your version>\Tracking.</span></span> <span data-ttu-id="b31c4-127">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-127">Run the following command:</span></span> 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a><span data-ttu-id="b31c4-128">BTARN の構成を解除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-128">Unconfigure BTARN</span></span>
  
1.  <span data-ttu-id="b31c4-129">次のファイルを探して実行し、BTARN の構成を解除します。</span><span class="sxs-lookup"><span data-stu-id="b31c4-129">Locate and run the following to unconfigure BTARN:</span></span>  
  
     <span data-ttu-id="b31c4-130">***< ドライブ\>*****: \Program Files\\< インストール ディレクトリ\>\Configuration.exe/u** </span><span class="sxs-lookup"><span data-stu-id="b31c4-130">***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**</span></span>  
  
2.  <span data-ttu-id="b31c4-131">コントロール パネルで、ダブルクリック**プログラム追加と削除**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-131">In Control Panel, double-click **Add or Remove Programs**.</span></span>  
  
3.  <span data-ttu-id="b31c4-132">**現在インストールされているプログラム**一覧で、をクリックして**Microsoft BizTalk Accelerator for RosettaNet**、クリックして**変更/削除**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-132">In the **Currently installed programs** list, click **Microsoft BizTalk Accelerator for RosettaNet**, and then click **Change/Remove**.</span></span>  
  
4.  <span data-ttu-id="b31c4-133">**プログラムのメンテナンス**ダイアログ ボックスで、**削除**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-133">In the **Program Maintenance** dialog box, select **Remove**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="b31c4-134">**概要**ダイアログ ボックスで、をクリックして**アンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-134">In the **Summary** dialog box, click **Uninstall**.</span></span>  
  
6.  <span data-ttu-id="b31c4-135">**アンインストール完了**ダイアログ ボックスで、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-135">In the **Uninstall Completed** dialog box, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b31c4-136">アンインストール プロセスでは、BTARN データベース (BTARNARCHIVE、BTARNCONFIG、および BTARNDATA) は削除されません。</span><span class="sxs-lookup"><span data-stu-id="b31c4-136">The uninstallation process does not remove the BTARN databases (BTARNARCHIVE, BTARNCONFIG, and BTARNDATA).</span></span> <span data-ttu-id="b31c4-137">それらを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31c4-137">You must manually remove them.</span></span>  
  
7.  <span data-ttu-id="b31c4-138">開いている**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-138">Open **SQL Server Management Studio**.</span></span>  
  
8.  <span data-ttu-id="b31c4-139">**サーバーへの接続**ダイアログ ボックスで、をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-139">In the **Connect to Server** dialog box, click **Connect**.</span></span>  
  
9. <span data-ttu-id="b31c4-140">展開して、**データベース**左側のウィンドウ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="b31c4-140">Expand the **Databases** node in the left pane.</span></span> <span data-ttu-id="b31c4-141">BTARN データベースの 1 つを右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-141">Right-click one of the BTARN databases, and then click **Delete**.</span></span>  
  
10. <span data-ttu-id="b31c4-142">**オブジェクトの削除**ダイアログ ボックスで、**既存の接続を閉じる**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b31c4-142">In the **Delete Object** dialog box, select **Close Existing Connections**, and then click **OK**.</span></span>  
  
