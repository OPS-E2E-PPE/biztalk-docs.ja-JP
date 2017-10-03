---
title: "メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67404919-33a6-40ac-b1c4-09841db12fcf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2999ce9a188b2d9b94df11328485e8b7440ecec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="98838-102">メモリ リークが発生したプロセスのメモリ ダンプを取得する方法</span><span class="sxs-lookup"><span data-stu-id="98838-102">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>
<span data-ttu-id="98838-103">不要になったメモリを BizTalk プロセス BTSNTSvc.exe が解放できず、時間の経過と共に使用可能なメモリ量が減少している場合、このプロセスにメモリ リークが発生していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="98838-103">The BizTalk process BTSNTSvc.exe is defined as having a memory leak when it fails to release memory that it no longer needs, thereby reducing the amount of available memory over time.</span></span> <span data-ttu-id="98838-104">下の値を表示することによって、プロセスのメモリ使用量を決定できます、**メモリ使用量**の列、**プロセス** タブで使用できる**タスク マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="98838-104">The memory usage of the process can be determined by viewing the value under the **Mem Usage** column of the **Processes** tab available in **Task Manager**.</span></span> <span data-ttu-id="98838-105">プロセスが長時間にわたってメモリを解放せずに消費し続けると、全体のシステム パフォーマンスに悪影響が生じます。</span><span class="sxs-lookup"><span data-stu-id="98838-105">If the process continues to consume memory over time without releasing memory then overall system performance will be adversely impacted.</span></span>  
  
 <span data-ttu-id="98838-106">ここでは、ルールの使用か、メモリ ダンプの手動取得によって、メモリ リークの発生が疑われる BizTalk プロセスのメモリ ダンプを取得する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="98838-106">This topic contains instructions for capturing a memory dump of a BizTalk process that is suspected of leaking memory by using a Rule or by manually capturing the memory dump.</span></span> <span data-ttu-id="98838-107">メモリ リークの発生が予測不可能な場合、メモリ ダンプを手動で取得する方法を使用してください。</span><span class="sxs-lookup"><span data-stu-id="98838-107">Use the manual method of capturing a memory dump if the occurrence of the memory leak is not predictable.</span></span>  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a><span data-ttu-id="98838-108">メモリ リークが発生したプロセスのメモリ ダンプを、ルールを使用して取得するには</span><span class="sxs-lookup"><span data-stu-id="98838-108">To capture a memory dump of a process that is leaking memory by using a rule</span></span>  
  
1.  <span data-ttu-id="98838-109">デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="98838-109">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="98838-110">場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合をクリックして、**ツール** メニューの 選択**ルール アクション**、 をクリック**ルールの追加**を規則の追加ウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="98838-110">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="98838-111">選択、 **Memory and Handle Leak**オプション、 **Select Rule Type**ダイアログとクリック**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="98838-111">Select the **Memory and Handle Leak** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="98838-112">メモリおよびクリックをリークの発生が疑われる BTSNTSvc.exe プロセスを選択**次**です。</span><span class="sxs-lookup"><span data-stu-id="98838-112">Select the BTSNTSvc.exe process that is suspected of leaking memory and click **Next**.</span></span>  
  
5.  <span data-ttu-id="98838-113">**Configure Tracking Duration**ダイアログに次の手順します。</span><span class="sxs-lookup"><span data-stu-id="98838-113">In the **Configure Tracking Duration** dialog follow these steps:</span></span>  
  
    1.  <span data-ttu-id="98838-114">観察対象のプロセス メモリの増加が直ちに発生した場合にオプションをオンに**Start ルールがアクティブにするとすぐに追跡 memory**です。</span><span class="sxs-lookup"><span data-stu-id="98838-114">If the observed process memory growth occurs immediately, check the option to **Start memory tracking immediately when rule is activated**.</span></span> <span data-ttu-id="98838-115">観察対象のプロセス メモリの増加が直ちに発生しない場合は、適切な数の分を指定します。、 **Warm-up time**メモリ追跡を開始するまでのテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="98838-115">If the observed process memory growth doesn't occur immediately, specify an appropriate number of minutes in the **Warm-up time** text box after which memory tracking will start.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="98838-116">BizTalk オーケストレーションによる外部のコンポーネントの参照時など、特定のコンポーネントがメモリに読み込まれたときにメモリ リークが発生する場合、観察対象のプロセス メモリの増加が直ちに発生しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98838-116">The observed process memory growth may not occur immediately if the memory leak is caused when loading a particular component into memory, for example when a BizTalk orchestration references an external component.</span></span>  
  
    2.  <span data-ttu-id="98838-117">適切な数の分の指定、 **Tracking time**メモリ追跡を停止するまでのテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="98838-117">Specify an appropriate number of minutes in the **Tracking time** text box after which memory tracking will stop.</span></span> <span data-ttu-id="98838-118">この分数は、メモリ リークの再現に十分な長さにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98838-118">This should be a number of minutes long enough to reproduce the memory leak.</span></span> <span data-ttu-id="98838-119">この期間が経過した後、プロセスのメモリ ダンプが取得されます。</span><span class="sxs-lookup"><span data-stu-id="98838-119">A memory dump of the process will be captured after this time period has elapsed.</span></span>  
  
    3.  <span data-ttu-id="98838-120">チェック ボックスをオン**userdump を予期しないプロセスの終了時に取得するルールのクラッシュを自動作成**です。</span><span class="sxs-lookup"><span data-stu-id="98838-120">Check the option to **Auto-create a crash rule to get userdump on unexpected process exit**.</span></span>  
  
    4.  <span data-ttu-id="98838-121">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98838-121">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="98838-122">**選択 Dump Location And Rule Name**ダイアログ**[次へ]**既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="98838-122">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="98838-123">**Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**です。</span><span class="sxs-lookup"><span data-stu-id="98838-123">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
8.  <span data-ttu-id="98838-124">\Program Files\IIS Resources\DebugDiag\Logs に既定では、プロセスのメモリ ダンプが保存される\\<*クラッシュ ルールの名前*> で指定された時間間隔後に、ローカル コンピューターのディレクトリ**Configure Tracking Duration**ダイアログが経過しました。</span><span class="sxs-lookup"><span data-stu-id="98838-124">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*> directory of the local computer after the time intervals specified in the **Configure Tracking Duration** dialog has elapsed.</span></span>  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="98838-125">メモリ リークが発生したプロセスのメモリ ダンプを手動で取得するには</span><span class="sxs-lookup"><span data-stu-id="98838-125">To manually capture a memory dump of a process that is leaking memory</span></span>  
  
1.  <span data-ttu-id="98838-126">デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="98838-126">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="98838-127">場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されたら、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="98838-127">If the **Select Rule Type** dialog of the Add Rule Wizard is displayed, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="98838-128">クリックして選択、**プロセス**デバッグ診断ツールのタブです。</span><span class="sxs-lookup"><span data-stu-id="98838-128">Click to select the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="98838-129">メモリおよびクリックをリークの発生が疑われる BTSNTSvc.exe プロセスを右クリックして**リークを監視**です。</span><span class="sxs-lookup"><span data-stu-id="98838-129">Right-click the BTSNTSvc.exe process that is suspected of leaking memory and click **Monitor For Leaks**.</span></span>  
  
5.  <span data-ttu-id="98838-130">プロセスのメモリ使用量を監視**タスク マネージャー**を右クリックして、プロセスのメモリ ダンプを手動でキャプチャ プロセスのメモリ使用量、BizTalk コンピューター上で利用できるメモリの 60 ~ 80% に近づくと、プロセスにオプションを選択して**Create Full Userdump**です。</span><span class="sxs-lookup"><span data-stu-id="98838-130">Monitor the memory usage of the process in **Task Manager** and when the memory usage of the process approaches 60-80% of the memory available on the BizTalk computer; manually capture a memory dump of the process by right-clicking the process and selecting the option to **Create Full Userdump**.</span></span>  
  
6.  <span data-ttu-id="98838-131">既定では、プロセスのメモリ ダンプは、ローカル コンピューターの \Program Files\IIS Resources\DebugDiag\Logs\Misc\ ディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="98838-131">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc\ directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98838-132">参照</span><span class="sxs-lookup"><span data-stu-id="98838-132">See Also</span></span>  
 [<span data-ttu-id="98838-133">デバッグ診断ツールを使用して、メモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="98838-133">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)