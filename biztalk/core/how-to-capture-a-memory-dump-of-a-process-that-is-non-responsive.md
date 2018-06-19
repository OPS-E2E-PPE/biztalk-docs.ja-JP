---
title: 応答のないプロセスのメモリ ダンプをキャプチャする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 520921010a8bbfd73de8c3b305a1270ca8363c46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248586"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a><span data-ttu-id="da1bd-102">応答のないプロセスのメモリ ダンプを取得する方法</span><span class="sxs-lookup"><span data-stu-id="da1bd-102">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>
<span data-ttu-id="da1bd-103">BizTalk プロセス BTSNTSvc.exe として定義されている**ぶら下げ**プロセスが応答を停止するようです。</span><span class="sxs-lookup"><span data-stu-id="da1bd-103">The BizTalk process BTSNTSvc.exe is defined as **hanging** when the process seems to stop responding.</span></span> <span data-ttu-id="da1bd-104">プロセスのハングに共通する現象は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da1bd-104">Common symptoms of a process hang include:</span></span>  
  
-   <span data-ttu-id="da1bd-105">オーケストレーションが実行を停止しているように見える。</span><span class="sxs-lookup"><span data-stu-id="da1bd-105">Orchestrations appear to stop running.</span></span>  
  
-   <span data-ttu-id="da1bd-106">メッセージが処理されていない。</span><span class="sxs-lookup"><span data-stu-id="da1bd-106">Messages aren’t being processed.</span></span>  
  
-   <span data-ttu-id="da1bd-107">全般的なタイムアウトの問題が発生する。</span><span class="sxs-lookup"><span data-stu-id="da1bd-107">General timeout issues occur.</span></span>  
  
-   <span data-ttu-id="da1bd-108">BizTalk プロセス BTSNTSvc.exe が非常に大量の CPU サイクルに表示されるを消費する、**プロセス**のタブ**タスク マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="da1bd-108">The BizTalk process BTSNTSvc.exe consumes an unusually high amount of CPU cycles as viewed in the **Processes** tab of **Task Manager**.</span></span>  
  
 <span data-ttu-id="da1bd-109">ハングしている BTSNTSvc.exe プロセスのメモリ ダンプを取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="da1bd-109">To capture a memory dump of a hanging BTSNTSvc.exe process, follow these steps.</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a><span data-ttu-id="da1bd-110">ハング ダンプを取得するようデバッグ診断ツールを構成するには</span><span class="sxs-lookup"><span data-stu-id="da1bd-110">To configure the Debug Diagnostics tool to capture a hang dump</span></span>  
  
1.  <span data-ttu-id="da1bd-111">デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="da1bd-111">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="da1bd-112">場合、 **Select Rule Type**ルール構成ウィザードのダイアログ ボックスが表示されたら、をクリックして、**キャンセル**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="da1bd-112">If the **Select Rule Type** dialog of the Rules Configuration Wizard is displayed, click the **Cancel** button.</span></span>  
  
3.  <span data-ttu-id="da1bd-113">クリックして、**プロセス**デバッグ診断ツールのタブです。</span><span class="sxs-lookup"><span data-stu-id="da1bd-113">Click the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="da1bd-114">応答しない BTSNTSvc.exe プロセスを右クリックし、選択**Create Full Userdump**です。</span><span class="sxs-lookup"><span data-stu-id="da1bd-114">Right click the unresponsive BTSNTSvc.exe process and select **Create Full Userdump**.</span></span> <span data-ttu-id="da1bd-115">既定では、プロセスのメモリ ダンプは、ローカル コンピューターの \Program Files\IIS Resources\DebugDiag\Logs\Misc ディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="da1bd-115">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da1bd-116">参照</span><span class="sxs-lookup"><span data-stu-id="da1bd-116">See Also</span></span>  
 [<span data-ttu-id="da1bd-117">デバッグ診断ツールを使用して、メモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="da1bd-117">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)