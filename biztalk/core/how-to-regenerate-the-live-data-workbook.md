---
title: ライブ データ ブックを再生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eda4dcb210f3d0272cdb0f04da8ae7d7ef2942d
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753146"
---
# <a name="regenerate-the-live-data-workbook"></a><span data-ttu-id="fe73c-102">ライブ データ ブックを再生成します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-102">Regenerate the Live Data Workbook</span></span>
<span data-ttu-id="fe73c-103">BAM ライブ データ ブックが失われるか破損した場合、BAM 管理ユーティリティを使用してブックを再生成できます。</span><span class="sxs-lookup"><span data-stu-id="fe73c-103">In cases where the BAM live data workbook has been lost or corrupted, you can regenerate the workbook using the BAM Management utiprolity.</span></span> <span data-ttu-id="fe73c-104">このプロセスは、BizTalk Server の以前のバージョンからアップグレードする場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe73c-104">This process is also useful when you are upgrading from previous BizTalk Server versions.</span></span>
  
 <span data-ttu-id="fe73c-105">一般的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe73c-105">The general steps are as follows:</span></span>  
  
-   <span data-ttu-id="fe73c-106">BAM 管理ユーティリティを使用して BAM データベースから BAM 定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-106">Retrieve the BAM definition from the BAM database using the BAM Management utility.</span></span>  
  
-   <span data-ttu-id="fe73c-107">PivotTable レポートを再作成します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-107">Re-create the PivotTable reports.</span></span> <span data-ttu-id="fe73c-108">get-defxml コマンドを使用して取得した XML にはアクティビティとビューしか含まれていないため、Excel 用の BAM アドインを使用して PivotTable レポートを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe73c-108">Since the XML retrieval by the get-defxml command contains only the activities and views, you must re-create the PivotTable reports using the BAM Add-in for Excel.</span></span>  
  
-   <span data-ttu-id="fe73c-109">PivotTable レポートの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-109">Rename the PivotTable reports.</span></span> <span data-ttu-id="fe73c-110">この手順は必要なは、BizTalk Server の以前のバージョンからアップグレードする場合にあります。</span><span class="sxs-lookup"><span data-stu-id="fe73c-110">This step may be necessary if you are upgrading from a previous BizTalk Server version.</span></span> <span data-ttu-id="fe73c-111">BAM によって BAM ブック名の 2 つのセットをいくつかのバージョンでは、: 表示名と内部名。</span><span class="sxs-lookup"><span data-stu-id="fe73c-111">With some versions, BAM stores two sets of names for BAM workbooks: a display name and an internal name.</span></span> <span data-ttu-id="fe73c-112">BAM 定義を取得すると、XML にはブックの内部名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe73c-112">When you retrieve the BAM definition, the XML contains the internal name for the workbook.</span></span> <span data-ttu-id="fe73c-113">PivotTable レポートの名前を変更して、ライブ データ ブックがデータベースに適切に接続できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe73c-113">You must rename the PivotTable reports to ensure that the live data workbook has the correct connection to the database.</span></span>  
  
-   <span data-ttu-id="fe73c-114">BAM 管理ユーティリティを使用してライブ データ ブックを再生成します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-114">Regenerate the live data workbook using the BAM Management utility.</span></span>  
  
## <a name="retrieve-the-bam-definition"></a><span data-ttu-id="fe73c-115">BAM 定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-115">Retrieve the BAM definition</span></span>  
  
1. <span data-ttu-id="fe73c-116">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="fe73c-116">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="fe73c-117">コマンド プロンプトで次のディレクトリに移動します: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-117">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span></span>  
  
3. <span data-ttu-id="fe73c-118">型: **bm.exe の get defxml-FileName:abc.xml**</span><span class="sxs-lookup"><span data-stu-id="fe73c-118">Type: **bm.exe get-defxml -FileName:abc.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fe73c-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe73c-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="recreate-the-pivottable-reports"></a><span data-ttu-id="fe73c-120">ピボット テーブル レポートを再作成します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-120">Recreate the PivotTable reports</span></span>  
  
1. <span data-ttu-id="fe73c-121">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリックします**Microsoft Office Excel**します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-121">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2. <span data-ttu-id="fe73c-122">をクリックして、**アドイン**、タブを選び**XML のインポート**から、 **BAM**ドロップダウン リストで、**メニュー コマンド**グループ。</span><span class="sxs-lookup"><span data-stu-id="fe73c-122">Click the **Add-Ins** tab, and then select **Import XML** from the **BAM** drop-down list in the **Menu Commands** group.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fe73c-123">場合、**アドイン**タブが存在しない、指示に従って[手順 1: Microsoft Office Excel に BAM アドインを追加](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)BAM アドインを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-123">If the **Add-Ins** tab is not present, follow the instructions in [Step 1: Add the BAM Add-In to Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448) to add the BAM add-in.</span></span>  
  
3. <span data-ttu-id="fe73c-124">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking フォルダーに移動し、abc.xml ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-124">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking folder and select the abc.xml file.</span></span>  
  
4. <span data-ttu-id="fe73c-125">使用している定義に基づいて PivotTable レポートを再作成します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-125">Re-create your PivotTable reports based on your definition.</span></span>  
  
5. <span data-ttu-id="fe73c-126">ブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-126">Save the workbook.</span></span> <span data-ttu-id="fe73c-127">これを行うには、をクリックして、**ファイル** メニューをクリック**付けて**ファイル名の入力を求められたら、mynewbook.xls」と入力します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-127">To do this, click the **File** menu, and then click **Save As** and type mynewbook.xls when prompted for a file name.</span></span>  
  
## <a name="rename-the-pivottable-reports-optional"></a><span data-ttu-id="fe73c-128">(省略可能) のピボット テーブル レポートを名前します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-128">Rename the PivotTable reports (optional)</span></span>  

> [!NOTE]
> <span data-ttu-id="fe73c-129">この手順は、BizTalk Server の以前のバージョンからアップグレードする場合に必要なります。</span><span class="sxs-lookup"><span data-stu-id="fe73c-129">This step may only be required if you are upgrading from an older version of BizTalk Server.</span></span> 

1. <span data-ttu-id="fe73c-130">クリックしてメモ帳を使用して BAM 定義を取得したときに作成した abc.xml ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking\abc.xml、 をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-130">Open the abc.xml file that you created when you retrieved the BAM definitions using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking\abc.xml, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="fe73c-131">検索、\<キャプション\>でタグ付け\<BAMDefinition\>\\< 拡張\>\\< OWC\>\\< PivotTableView\> \\< PivotTable\>\\< PivotView\>\\< ラベル\>します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-131">Locate the \<Caption\> tag under \<BAMDefinition\>\\<Extension\>\\<OWC\>\\<PivotTableView\>\\<PivotTable\>\\<PivotView\>\\<Label\>.</span></span> <span data-ttu-id="fe73c-132">このタグの内容は、いずれかの PivotTable レポートの内部名です。</span><span class="sxs-lookup"><span data-stu-id="fe73c-132">The content of this tag is the internal name for one of your PivotTable reports.</span></span> <span data-ttu-id="fe73c-133">次を配置することにより、他のピボット テーブル レポートの内部名を検索できます\<キャプション\>タグ。</span><span class="sxs-lookup"><span data-stu-id="fe73c-133">You can find the internal name for the other PivotTable reports by locating the next \<Caption\> tag.</span></span> <span data-ttu-id="fe73c-134">開いている**mynewbook.xls**し、ピボット テーブル レポートの名前を変更するにある名を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-134">Open **mynewbook.xls** and use the names you located to rename your PivotTable reports.</span></span>  
  
3. <span data-ttu-id="fe73c-135">更新したブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-135">Save the updated workbook.</span></span>    
 
  
## <a name="regenerate-the-bam-live-data-workbook"></a><span data-ttu-id="fe73c-136">BAM ライブ データ ブックを再生成します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-136">Regenerate the BAM live data workbook</span></span>  

> [!NOTE]
>  <span data-ttu-id="fe73c-137">このツールは、管理者特権で実行します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-137">Run this tool with Administrative privileges.</span></span>  


1. <span data-ttu-id="fe73c-138">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="fe73c-138">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="fe73c-139">コマンド プロンプトで次のディレクトリに移動します: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking します。</span><span class="sxs-lookup"><span data-stu-id="fe73c-139">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span></span>  
  
3. <span data-ttu-id="fe73c-140">型: **bm.exe の再生成 livedataworkbook-WorkbookName:mynewbook.xls**</span><span class="sxs-lookup"><span data-stu-id="fe73c-140">Type: **bm.exe regenerate-livedataworkbook -WorkbookName:mynewbook.xls**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe73c-141">参照</span><span class="sxs-lookup"><span data-stu-id="fe73c-141">See Also</span></span>  
 <span data-ttu-id="fe73c-142">[BAM の管理](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="fe73c-142">[Managing BAM](../core/managing-bam.md) </span></span>  
 <span data-ttu-id="fe73c-143">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fe73c-143">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="fe73c-144">[Excel 用 BAM アドインを使用するための要件](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="fe73c-144">[Requirements for Using the BAM Add-In for Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="fe73c-145">Microsoft Office Excel に BAM アドインを追加する手順 1。</span><span class="sxs-lookup"><span data-stu-id="fe73c-145">Step 1: Add the BAM Add-In to Microsoft Office Excel</span></span>](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)
