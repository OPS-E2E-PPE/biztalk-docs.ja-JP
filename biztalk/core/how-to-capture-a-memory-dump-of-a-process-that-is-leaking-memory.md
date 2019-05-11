---
title: メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67404919-33a6-40ac-b1c4-09841db12fcf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3df482776809fa9f1685d4466ca0688521c53e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342662"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="f08da-102">メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法</span><span class="sxs-lookup"><span data-stu-id="f08da-102">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>
<span data-ttu-id="f08da-103">BizTalk プロセス BTSNTSvc.exe が必要はありません、それによってメモリを解放に失敗した場合は、メモリ リークを持つものとして定義されているは時間の経過と共に使用可能なメモリの量を削減します。</span><span class="sxs-lookup"><span data-stu-id="f08da-103">The BizTalk process BTSNTSvc.exe is defined as having a memory leak when it fails to release memory that it no longer needs, thereby reducing the amount of available memory over time.</span></span> <span data-ttu-id="f08da-104">下の値を表示することによって、プロセスのメモリ使用量を決定できます、**メモリ使用量**の列、**プロセス** タブで使用できる**タスク マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-104">The memory usage of the process can be determined by viewing the value under the **Mem Usage** column of the **Processes** tab available in **Task Manager**.</span></span> <span data-ttu-id="f08da-105">メモリを解放しないまま時間の経過と共にメモリを消費するプロセスが解決しない場合は、システム全体のパフォーマンスに悪影響が。</span><span class="sxs-lookup"><span data-stu-id="f08da-105">If the process continues to consume memory over time without releasing memory then overall system performance will be adversely impacted.</span></span>  
  
 <span data-ttu-id="f08da-106">このトピックでは、ルールを使用して、または手動でメモリ ダンプをキャプチャすることで、メモリをリークの発生が疑われる BizTalk プロセスのメモリ ダンプをキャプチャするための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="f08da-106">This topic contains instructions for capturing a memory dump of a BizTalk process that is suspected of leaking memory by using a Rule or by manually capturing the memory dump.</span></span> <span data-ttu-id="f08da-107">メモリ リークの発生が予測可能でない場合は、メモリ ダンプをキャプチャの手動による方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="f08da-107">Use the manual method of capturing a memory dump if the occurrence of the memory leak is not predictable.</span></span>  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a><span data-ttu-id="f08da-108">ルールを使用してメモリがリークしているプロセスのメモリ ダンプをキャプチャするには</span><span class="sxs-lookup"><span data-stu-id="f08da-108">To capture a memory dump of a process that is leaking memory by using a rule</span></span>  
  
1.  <span data-ttu-id="f08da-109">デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-109">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="f08da-110">場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合、をクリックして、**ツール**クリックし、**ルール アクション**、 をクリック**規則の追加**規則の追加ウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="f08da-110">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="f08da-111">選択、 **Memory and Handle Leak**オプション、 **Select Rule Type**ダイアログをクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="f08da-111">Select the **Memory and Handle Leak** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="f08da-112">をクリックし、メモリ リークの発生が疑われる BTSNTSvc.exe プロセスを選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-112">Select the BTSNTSvc.exe process that is suspected of leaking memory and click **Next**.</span></span>  
  
5.  <span data-ttu-id="f08da-113">**Configure Tracking Duration**ダイアログに次の手順します。</span><span class="sxs-lookup"><span data-stu-id="f08da-113">In the **Configure Tracking Duration** dialog follow these steps:</span></span>  
  
    1.  <span data-ttu-id="f08da-114">観察対象のプロセス メモリの増加が直ちに発生した場合にオプションをオンに**メモリ追跡ルールがアクティブにするとすぐに開始**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-114">If the observed process memory growth occurs immediately, check the option to **Start memory tracking immediately when rule is activated**.</span></span> <span data-ttu-id="f08da-115">観察対象のプロセス メモリの増加が直ちに発生しない場合は、適切な数の分を指定、**ウォーム アップ時間**メモリ追跡を開始するまでテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="f08da-115">If the observed process memory growth doesn't occur immediately, specify an appropriate number of minutes in the **Warm-up time** text box after which memory tracking will start.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f08da-116">観察対象のプロセス メモリの増加は、特定のコンポーネントを BizTalk オーケストレーションが外部コンポーネントを参照する場合の例については、メモリに読み込む場合は、メモリ リークが原因の場合はすぐに発生しません。</span><span class="sxs-lookup"><span data-stu-id="f08da-116">The observed process memory growth may not occur immediately if the memory leak is caused when loading a particular component into memory, for example when a BizTalk orchestration references an external component.</span></span>  
  
    2.  <span data-ttu-id="f08da-117">適切な数の分を指定、**時間を追跡**メモリ追跡を停止するまでテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="f08da-117">Specify an appropriate number of minutes in the **Tracking time** text box after which memory tracking will stop.</span></span> <span data-ttu-id="f08da-118">これは、分の数値である必要があります、メモリ リークを再現するのに十分な長さ。</span><span class="sxs-lookup"><span data-stu-id="f08da-118">This should be a number of minutes long enough to reproduce the memory leak.</span></span> <span data-ttu-id="f08da-119">この期間が経過した後、プロセスのメモリ ダンプがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f08da-119">A memory dump of the process will be captured after this time period has elapsed.</span></span>  
  
    3.  <span data-ttu-id="f08da-120">オプションをオンに**userdump を予期しないプロセスの終了時に取得する規則のクラッシュを自動作成**です。</span><span class="sxs-lookup"><span data-stu-id="f08da-120">Check the option to **Auto-create a crash rule to get userdump on unexpected process exit**.</span></span>  
  
    4.  <span data-ttu-id="f08da-121">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f08da-121">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f08da-122">**選択 Dump Location And Rule Name**ダイアログ **[次へ]** 既定値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f08da-122">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="f08da-123">**Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-123">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
8.  <span data-ttu-id="f08da-124">既定では、プロセスのメモリ ダンプを \Program Files\IIS Resources\DebugDiag\Logs に保存されます\\<*クラッシュ規則の名前*\>時間間隔後に、ローカル コンピューターのディレクトリ指定されている、 **Configure Tracking Duration**ダイアログが経過しました。</span><span class="sxs-lookup"><span data-stu-id="f08da-124">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*\> directory of the local computer after the time intervals specified in the **Configure Tracking Duration** dialog has elapsed.</span></span>  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="f08da-125">手動でメモリをリークしているプロセスのメモリ ダンプをキャプチャするには</span><span class="sxs-lookup"><span data-stu-id="f08da-125">To manually capture a memory dump of a process that is leaking memory</span></span>  
  
1.  <span data-ttu-id="f08da-126">デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-126">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="f08da-127">場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されたら、クリックして**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-127">If the **Select Rule Type** dialog of the Add Rule Wizard is displayed, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="f08da-128">クリックして選択し、**プロセス**デバッグ診断ツールのタブ。</span><span class="sxs-lookup"><span data-stu-id="f08da-128">Click to select the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="f08da-129">をクリックし、メモリ リークの発生が疑われる BTSNTSvc.exe プロセスを右クリックして**リークを監視**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-129">Right-click the BTSNTSvc.exe process that is suspected of leaking memory and click **Monitor For Leaks**.</span></span>  
  
5.  <span data-ttu-id="f08da-130">プロセスのメモリ使用量を監視**タスク マネージャー**を右クリックし、プロセスのメモリ ダンプを手動でキャプチャ プロセスのメモリ使用量が BizTalk コンピューターで使用可能なメモリの 60 ~ 80% に近づくと、プロセスにオプションを選択して**Create Full Userdump**します。</span><span class="sxs-lookup"><span data-stu-id="f08da-130">Monitor the memory usage of the process in **Task Manager** and when the memory usage of the process approaches 60-80% of the memory available on the BizTalk computer; manually capture a memory dump of the process by right-clicking the process and selecting the option to **Create Full Userdump**.</span></span>  
  
6.  <span data-ttu-id="f08da-131">既定では、ローカル コンピューターの \Program Files\IIS \debugdiag\logs\misc\ ディレクトリにプロセスのメモリ ダンプが保存されます。</span><span class="sxs-lookup"><span data-stu-id="f08da-131">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc\ directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f08da-132">参照</span><span class="sxs-lookup"><span data-stu-id="f08da-132">See Also</span></span>  
 [<span data-ttu-id="f08da-133">デバッグ診断ツールを使用してメモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="f08da-133">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)