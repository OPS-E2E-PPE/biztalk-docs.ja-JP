---
title: BizTalk Server で BizTalk RosettaNet アクセラレータ (BTARN) のアンインストール |Microsoft Docs"
description: 成果物を展開解除し、アクセラレータを BizTalk Server から削除する BTARN の構成を解除
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: a8e26119039910f398620efe478d07eeebca6f08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299970"
---
# <a name="uninstall-the-rosettanet-accelerator"></a><span data-ttu-id="75104-103">RosettaNet アクセラレータをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="75104-103">Uninstall the RosettaNet accelerator</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="75104-104">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="75104-104">Before you begin</span></span>
  
* <span data-ttu-id="75104-105">のみを実行する場合**Setup.exe**、アンインストール プロセスでは、ビジネス アクティビティ監視 (BAM) アイテム、BizTalk アイテム、インターネット インフォメーション サービス (IIS) 仮想ディレクトリ、およびアプリケーション プールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="75104-105">If you only run **Setup.exe**, the uninstall process does not remove the Business Activity Monitoring (BAM) artifacts, the BizTalk artifacts, Internet Information Services (IIS) virtual directories, and application pools.</span></span>  
  
* <span data-ttu-id="75104-106">使用した場合、 **Loopback**を 1 台のコンピューター展開用のミラー アグリーメントを作成するためのユーティリティとツールを実行、 **/無効にする <** **ホーム組織** **>** オプションでパートナーを削除する前に、 **BTARN 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="75104-106">If you used the **Loopback** utility to create mirror agreements for a single-computer deployment, then run the tool with the **/disable <** **home organization** **>** option before deleting the partners in the **BTARN Administration Console**.</span></span>  
  
* <span data-ttu-id="75104-107">このサーバーが複数コンピュータ展開の一部である場合は実行しないでください、 **BtarnClean**ユーティリティまたは手動で BTARN アセンブリを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="75104-107">If this server is part of a multi-computer deployment, do not run the **BtarnClean** utility or manually undeploy the BTARN assemblies.</span></span> <span data-ttu-id="75104-108">1 台のコンピューター上のアイテムを削除するには、その他のコンピューターの機能が中断されます。</span><span class="sxs-lookup"><span data-stu-id="75104-108">Removing the artifacts on one computer breaks the functionality of the other computers.</span></span>  <span data-ttu-id="75104-109">すべてのサーバーから BTARN をアンインストールする場合を実行し、 **BtarnClean**ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="75104-109">If you want to uninstall BTARN from all the servers, then run the **BtarnClean** utility.</span></span> 

  
## <a name="undeploy-the-artifacts"></a><span data-ttu-id="75104-110">成果物を展開解除します。</span><span class="sxs-lookup"><span data-stu-id="75104-110">Undeploy the artifacts</span></span>  

<span data-ttu-id="75104-111">展開解除する前に、BAM アイテムをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="75104-111">We recommend backing up your BAM artifacts before undeploying.</span></span> 

1. <span data-ttu-id="75104-112">デプロイしたすべての BAM アイテムの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="75104-112">Undeploy all the BAM artifacts that you deployed:</span></span>  
  
    1.  <span data-ttu-id="75104-113">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="75104-113">At the command prompt, run the following command:</span></span>  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  <span data-ttu-id="75104-114">追跡 UI がインストールされているコマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="75104-114">At the command prompt where the tracking UI was installed, run the following command:</span></span>  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  <span data-ttu-id="75104-115">BAM の詳細については、次を参照してください[ビジネス アクティビティ監視の管理。](../../core/managing-bam.md)</span><span class="sxs-lookup"><span data-stu-id="75104-115">For more information about BAM, see [Managing Business Activity Monitoring](../../core/managing-bam.md)</span></span> 
  
2.  <span data-ttu-id="75104-116">バックアップし、BTARN 管理コンソールからすべての契約、パートナー、およびホーム組織を削除します。</span><span class="sxs-lookup"><span data-stu-id="75104-116">Backup and delete all the agreements, partners, and home organizations from the BTARN Management Console.</span></span> <span data-ttu-id="75104-117">使用方法については、(BTARN ヘルプの操作のノード) で「BTARN 構成の管理」トピックを参照して、 **BtarnConfig**アグリーメントとパートナーをバックアップするユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="75104-117">See the "Administering the BTARN Configuration" topic (in the Operations node of BTARN Help) for information about using the **BtarnConfig** utility to back up the agreements and partners.</span></span>  
  
    > [!NOTE]
    >  * <span data-ttu-id="75104-118">停止しを使用して BTARN によって作成された BizTalk アイテムを展開解除、 [BtarnClean](btarnclean.md)ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="75104-118">Stop and undeploy the BizTalk artifacts created by BTARN by using the [BtarnClean](btarnclean.md) utility.</span></span>
    >  * <span data-ttu-id="75104-119">展開されているその他のアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="75104-119">Remove any additional artifacts that you deployed.</span></span> <span data-ttu-id="75104-120">参照してください[BizTalk アプリケーションを展開解除](../../core/undeploying-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="75104-120">See [Undeploying BizTalk Applications](../../core/undeploying-biztalk-applications.md) .</span></span>
  
3.  <span data-ttu-id="75104-121">BTARN のセットアップ、MSI\Program \microsoft BizTalk Accelerator for rosettanet \sdk フォルダーを探します。</span><span class="sxs-lookup"><span data-stu-id="75104-121">From the BTARN Setup, locate the MSI\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK folder.</span></span> <span data-ttu-id="75104-122">SDK フォルダーで、ダブルクリック**BTARNClean.exe**、し、 **Y**続けるには、または**N**ユーティリティの実行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="75104-122">In the SDK folder, double-click **BTARNClean.exe**, and then select **Y** to continue, or **N** to cancel running the utility.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75104-123">サーバーが複数コンピューター展開シナリオの一部である場合は、手順 3. を省略できます。</span><span class="sxs-lookup"><span data-stu-id="75104-123">If your server is part of a multi-computer deployment scenario, you can skip step 3.</span></span> <span data-ttu-id="75104-124">共有リソースを削除すると、展開内の他のサーバーで、機能が中断されます。</span><span class="sxs-lookup"><span data-stu-id="75104-124">Undeploying any shared resources breaks the functionality on the other servers in the deployment.</span></span>  
  
4.  <span data-ttu-id="75104-125">作成および展開したカスタム アセンブリの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="75104-125">Undeploy any custom assemblies that you created and deployed.</span></span>  
  
5.  <span data-ttu-id="75104-126">コマンド プロンプトで \Program Files\Microsoft BizTalk Server に移動します。 <your version>\Tracking します。</span><span class="sxs-lookup"><span data-stu-id="75104-126">At the command prompt, go to \Program Files\Microsoft BizTalk Server <your version>\Tracking.</span></span> <span data-ttu-id="75104-127">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="75104-127">Run the following command:</span></span> 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a><span data-ttu-id="75104-128">BTARN の構成を解除します。</span><span class="sxs-lookup"><span data-stu-id="75104-128">Unconfigure BTARN</span></span>
  
1.  <span data-ttu-id="75104-129">検索し、BTARN の構成を解除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="75104-129">Locate and run the following to unconfigure BTARN:</span></span>  
  
     <span data-ttu-id="75104-130">***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**</span><span class="sxs-lookup"><span data-stu-id="75104-130">***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**</span></span>  
  
2.  <span data-ttu-id="75104-131">コントロール パネルで、ダブルクリック**プログラム追加と削除**します。</span><span class="sxs-lookup"><span data-stu-id="75104-131">In Control Panel, double-click **Add or Remove Programs**.</span></span>  
  
3.  <span data-ttu-id="75104-132">**現在インストールされているプログラム**一覧で、[ **Microsoft BizTalk Accelerator for RosettaNet**、] をクリックし、**変更/削除**。</span><span class="sxs-lookup"><span data-stu-id="75104-132">In the **Currently installed programs** list, click **Microsoft BizTalk Accelerator for RosettaNet**, and then click **Change/Remove**.</span></span>  
  
4.  <span data-ttu-id="75104-133">**プログラムのメンテナンス**ダイアログ ボックスで、**削除**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="75104-133">In the **Program Maintenance** dialog box, select **Remove**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="75104-134">**概要**ダイアログ ボックスで、をクリックして**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="75104-134">In the **Summary** dialog box, click **Uninstall**.</span></span>  
  
6.  <span data-ttu-id="75104-135">**アンインストール完了**ダイアログ ボックスで、をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="75104-135">In the **Uninstall Completed** dialog box, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75104-136">アンインストール プロセスでは、BTARN のデータベース (BTARNARCHIVE、BTARNCONFIG、および BTARNDATA) は削除されません。</span><span class="sxs-lookup"><span data-stu-id="75104-136">The uninstallation process does not remove the BTARN databases (BTARNARCHIVE, BTARNCONFIG, and BTARNDATA).</span></span> <span data-ttu-id="75104-137">それらを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75104-137">You must manually remove them.</span></span>  
  
7.  <span data-ttu-id="75104-138">**SQL Server Management Studio** を開きます。</span><span class="sxs-lookup"><span data-stu-id="75104-138">Open **SQL Server Management Studio**.</span></span>  
  
8.  <span data-ttu-id="75104-139">**サーバーへの接続**ダイアログ ボックスで、をクリックして**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="75104-139">In the **Connect to Server** dialog box, click **Connect**.</span></span>  
  
9. <span data-ttu-id="75104-140">展開、**データベース**左側のウィンドウでノード。</span><span class="sxs-lookup"><span data-stu-id="75104-140">Expand the **Databases** node in the left pane.</span></span> <span data-ttu-id="75104-141">BTARN データベースの 1 つを右クリックし、をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="75104-141">Right-click one of the BTARN databases, and then click **Delete**.</span></span>  
  
10. <span data-ttu-id="75104-142">**オブジェクトの削除**ダイアログ ボックスで、**既存の接続を閉じる**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="75104-142">In the **Delete Object** dialog box, select **Close Existing Connections**, and then click **OK**.</span></span>  
  
