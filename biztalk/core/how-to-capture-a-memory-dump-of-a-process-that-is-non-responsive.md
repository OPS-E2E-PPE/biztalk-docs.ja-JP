---
title: 応答のないプロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea2310f38c221147efdba5b1e2980a548fabfa86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387065"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a><span data-ttu-id="ed553-102">応答のないプロセスのメモリ ダンプをキャプチャする方法</span><span class="sxs-lookup"><span data-stu-id="ed553-102">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>
<span data-ttu-id="ed553-103">BizTalk プロセス BTSNTSvc.exe として定義されている**ぶら下げ**プロセスが応答を停止するようです。</span><span class="sxs-lookup"><span data-stu-id="ed553-103">The BizTalk process BTSNTSvc.exe is defined as **hanging** when the process seems to stop responding.</span></span> <span data-ttu-id="ed553-104">プロセスのハングの一般的な現象は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ed553-104">Common symptoms of a process hang include:</span></span>  
  
- <span data-ttu-id="ed553-105">実行を停止するオーケストレーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed553-105">Orchestrations appear to stop running.</span></span>  
  
- <span data-ttu-id="ed553-106">メッセージが処理されていません。</span><span class="sxs-lookup"><span data-stu-id="ed553-106">Messages aren’t being processed.</span></span>  
  
- <span data-ttu-id="ed553-107">一般的なタイムアウトの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="ed553-107">General timeout issues occur.</span></span>  
  
- <span data-ttu-id="ed553-108">BizTalk プロセス BTSNTSvc.exe が非常に大量の CPU サイクルに表示を使用する、**プロセス**タブ**タスク マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="ed553-108">The BizTalk process BTSNTSvc.exe consumes an unusually high amount of CPU cycles as viewed in the **Processes** tab of **Task Manager**.</span></span>  
  
  <span data-ttu-id="ed553-109">ハングしている BTSNTSvc.exe のメモリ ダンプをキャプチャするプロセスは、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ed553-109">To capture a memory dump of a hanging BTSNTSvc.exe process, follow these steps.</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a><span data-ttu-id="ed553-110">ハング ダンプをキャプチャするデバッグ診断ツールを構成するには</span><span class="sxs-lookup"><span data-stu-id="ed553-110">To configure the Debug Diagnostics tool to capture a hang dump</span></span>  
  
1.  <span data-ttu-id="ed553-111">デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。</span><span class="sxs-lookup"><span data-stu-id="ed553-111">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="ed553-112">場合、 **Select Rule Type**ルール構成ウィザードのダイアログが表示されたら、をクリックして、**キャンセル**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed553-112">If the **Select Rule Type** dialog of the Rules Configuration Wizard is displayed, click the **Cancel** button.</span></span>  
  
3.  <span data-ttu-id="ed553-113">をクリックして、**プロセス**デバッグ診断ツールのタブ。</span><span class="sxs-lookup"><span data-stu-id="ed553-113">Click the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="ed553-114">応答しない BTSNTSvc.exe プロセスを右クリックし、選択**Create Full Userdump**します。</span><span class="sxs-lookup"><span data-stu-id="ed553-114">Right click the unresponsive BTSNTSvc.exe process and select **Create Full Userdump**.</span></span> <span data-ttu-id="ed553-115">既定では、ローカル コンピューターの \Program Files\IIS \debugdiag\logs\misc ディレクトリにプロセスのメモリ ダンプが保存されます。</span><span class="sxs-lookup"><span data-stu-id="ed553-115">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed553-116">参照</span><span class="sxs-lookup"><span data-stu-id="ed553-116">See Also</span></span>  
 [<span data-ttu-id="ed553-117">デバッグ診断ツールを使用してメモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="ed553-117">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)