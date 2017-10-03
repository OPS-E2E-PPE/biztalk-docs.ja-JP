---
title: "ライブ データ ブックを再生成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fcabebb1429fae8531753a8a3aede5595bb148f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-regenerate-the-live-data-workbook"></a><span data-ttu-id="19e2e-102">ライブ データ ブックを再生成する方法</span><span class="sxs-lookup"><span data-stu-id="19e2e-102">How to Regenerate the Live Data Workbook</span></span>
<span data-ttu-id="19e2e-103">BAM ライブ データ ブックが失われるか破損した場合、BAM 管理ユーティリティを使用してブックを再生成できます。</span><span class="sxs-lookup"><span data-stu-id="19e2e-103">In cases where the BAM live data workbook has been lost or corrupted, you can regenerate the workbook using the BAM Management utiprolity.</span></span> <span data-ttu-id="19e2e-104">[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] のライブ データ ブックは [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] と互換性がないため、このプロセスは [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] から [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にアップグレードする場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19e2e-104">This process is also useful when you are upgrading from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], since live data workbooks for [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] are not compatible with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
 <span data-ttu-id="19e2e-105">一般的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19e2e-105">The general steps are as follows:</span></span>  
  
-   <span data-ttu-id="19e2e-106">BAM 管理ユーティリティを使用して BAM データベースから BAM 定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-106">Retrieve the BAM definition from the BAM database using the BAM Management utility.</span></span>  
  
-   <span data-ttu-id="19e2e-107">PivotTable レポートを再作成します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-107">Re-create the PivotTable reports.</span></span> <span data-ttu-id="19e2e-108">get-defxml コマンドを使用して取得した XML にはアクティビティとビューしか含まれていないため、Excel 用の BAM アドインを使用して PivotTable レポートを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e2e-108">Since the XML retrieval by the get-defxml command contains only the activities and views, you must re-create the PivotTable reports using the BAM Add-in for Excel.</span></span>  
  
-   <span data-ttu-id="19e2e-109">PivotTable レポートの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-109">Rename the PivotTable reports.</span></span> <span data-ttu-id="19e2e-110">この手順は、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] から [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にアップグレードする場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-110">This step is necessary if you are upgrading from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="19e2e-111">これは、必要な[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]、BAM によって BAM ブックの名前の 2 つのセット。 表示名と内部名です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-111">This is necessary since in [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)], BAM stores two sets of names for BAM workbooks: a display name and an internal name.</span></span> <span data-ttu-id="19e2e-112">BAM 定義を取得すると、XML にはブックの内部名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="19e2e-112">When you retrieve the BAM definition, the XML contains the internal name for the workbook.</span></span> <span data-ttu-id="19e2e-113">PivotTable レポートの名前を変更して、ライブ データ ブックがデータベースに適切に接続できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e2e-113">You must rename the PivotTable reports to ensure that the live data workbook has the correct connection to the database.</span></span>  
  
-   <span data-ttu-id="19e2e-114">BAM 管理ユーティリティを使用してライブ データ ブックを再生成します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-114">Regenerate the live data workbook using the BAM Management utility.</span></span>  
  
### <a name="to-retrieve-the-bam-definition"></a><span data-ttu-id="19e2e-115">BAM 定義を取得するには</span><span class="sxs-lookup"><span data-stu-id="19e2e-115">To retrieve the BAM definition</span></span>  
  
1.  <span data-ttu-id="19e2e-116">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-116">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="19e2e-117">コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-117">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="19e2e-118">型: **bm.exe get defxml-FileName:abc.xml**</span><span class="sxs-lookup"><span data-stu-id="19e2e-118">Type: **bm.exe get-defxml -FileName:abc.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="19e2e-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="19e2e-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-re-create-the-pivottable-reports"></a><span data-ttu-id="19e2e-120">PivotTable レポートを再作成するには</span><span class="sxs-lookup"><span data-stu-id="19e2e-120">To re-create the PivotTable reports</span></span>  
  
1.  <span data-ttu-id="19e2e-121">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリック**Microsoft Office Excel**です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-121">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="19e2e-122">クリックして、**アドイン**、タブをクリックし**XML のインポート**から、 **BAM**のドロップ ダウン リスト、**メニュー コマンド**グループ。</span><span class="sxs-lookup"><span data-stu-id="19e2e-122">Click the **Add-Ins** tab, and then select **Import XML** from the **BAM** drop-down list in the **Menu Commands** group.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="19e2e-123">場合、**アドイン** タブが存在しない、指示に従って[手順 1: Microsoft Office Excel に BAM アドインを追加](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)BAM アドインを追加します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-123">If the **Add-Ins** tab is not present, follow the instructions in [Step 1: Add the BAM Add-In to Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448) to add the BAM add-in.</span></span>  
  
3.  <span data-ttu-id="19e2e-124">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking フォルダーに移動し、abc.xml ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-124">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking folder and select the abc.xml file.</span></span>  
  
4.  <span data-ttu-id="19e2e-125">使用している定義に基づいて PivotTable レポートを再作成します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-125">Re-create your PivotTable reports based on your definition.</span></span>  
  
5.  <span data-ttu-id="19e2e-126">ブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-126">Save the workbook.</span></span> <span data-ttu-id="19e2e-127">これを行うには、をクリックして、**ファイル** メニューをクリックして**名前を付けて保存**とファイル名の入力を求め mynewbook.xls を入力します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-127">To do this, click the **File** menu, and then click **Save As** and type mynewbook.xls when prompted for a file name.</span></span>  
  
### <a name="to-rename-the-pivottable-reports-optional"></a><span data-ttu-id="19e2e-128">PivotTable レポートの名前を変更するには (省略可)</span><span class="sxs-lookup"><span data-stu-id="19e2e-128">To rename the PivotTable reports (optional)</span></span>  
  
1.  <span data-ttu-id="19e2e-129">クリックしてメモ帳を使用して BAM 定義を取得するときに作成した abc.xml ファイルを開く**開始**をクリックすると、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\abc.xml をクリックし、 **[Ok]**です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-129">Open the abc.xml file that you created when you retrieved the BAM definitions using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\abc.xml, and then clicking **OK**.</span></span>  
  
2.  <span data-ttu-id="19e2e-130">検索、\<キャプション > の下にタグ付け\<BAMDefinition >\\< 拡張子\>\\< OWC\>\\< PivotTableView\>\\<ピボット テーブル\>\\< PivotView\>\\< ラベル\>です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-130">Locate the \<Caption> tag under \<BAMDefinition>\\<Extension\>\\<OWC\>\\<PivotTableView\>\\<PivotTable\>\\<PivotView\>\\<Label\>.</span></span> <span data-ttu-id="19e2e-131">このタグの内容は、いずれかの PivotTable レポートの内部名です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-131">The content of this tag is the internal name for one of your PivotTable reports.</span></span> <span data-ttu-id="19e2e-132">次を配置することにより、他のピボット テーブル レポートの内部名を見つけることができます\<Caption > タグです。</span><span class="sxs-lookup"><span data-stu-id="19e2e-132">You can find the internal name for the other PivotTable reports by locating the next \<Caption> tag.</span></span> <span data-ttu-id="19e2e-133">開いている**mynewbook.xls**し、ピボット テーブル レポートの名前を変更する配置名を使用します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-133">Open **mynewbook.xls** and use the names you located to rename your PivotTable reports.</span></span>  
  
3.  <span data-ttu-id="19e2e-134">更新したブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-134">Save the updated workbook.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="19e2e-135">この手順を実行する必要があるのは、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] から [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にアップグレードしている場合だけです。</span><span class="sxs-lookup"><span data-stu-id="19e2e-135">You must follow this procedure only if you are upgrading from [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
### <a name="to-regenerate-the-bam-live-data-workbook"></a><span data-ttu-id="19e2e-136">BAM ライブ データ ブックを再生成するには</span><span class="sxs-lookup"><span data-stu-id="19e2e-136">To regenerate the BAM live data workbook</span></span>  
  
1.  <span data-ttu-id="19e2e-137">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="19e2e-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="19e2e-138">コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-138">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="19e2e-139">型: **bm.exe regenerate livedataworkbook-WorkbookName:mynewbook.xls**</span><span class="sxs-lookup"><span data-stu-id="19e2e-139">Type: **bm.exe regenerate-livedataworkbook -WorkbookName:mynewbook.xls**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="19e2e-140">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="19e2e-140">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e2e-141">参照</span><span class="sxs-lookup"><span data-stu-id="19e2e-141">See Also</span></span>  
 <span data-ttu-id="19e2e-142">[BAM の管理](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="19e2e-142">[Managing BAM](../core/managing-bam.md) </span></span>  
 <span data-ttu-id="19e2e-143">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="19e2e-143">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="19e2e-144">[Excel 用 BAM アドインを使用するための要件](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="19e2e-144">[Requirements for Using the BAM Add-In for Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="19e2e-145">手順 1: が Microsoft Office Excel に BAM アドインを追加します。</span><span class="sxs-lookup"><span data-stu-id="19e2e-145">Step 1: Add the BAM Add-In to Microsoft Office Excel</span></span>](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)