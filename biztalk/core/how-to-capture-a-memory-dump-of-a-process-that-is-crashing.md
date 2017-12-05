---
title: "クラッシュしたプロセスのメモリ ダンプをキャプチャする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f436b72-2b6a-4519-acc3-e7ba978651fe
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e87664180b7ad4d5fdcd121542974a08b8634d55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a><span data-ttu-id="0d93b-102">クラッシュしたプロセスのメモリ ダンプを取得する方法</span><span class="sxs-lookup"><span data-stu-id="0d93b-102">How to Capture a Memory Dump of a Process that is Crashing</span></span>
<span data-ttu-id="0d93b-103">BizTalk プロセス BTSNTSvc.exe として定義されている**クラッシュ**プロセスが予期せず Windows によって終了する場合。</span><span class="sxs-lookup"><span data-stu-id="0d93b-103">The BizTalk process BTSNTSvc.exe is defined as **crashing** when the process is unexpectedly terminated by Windows.</span></span> <span data-ttu-id="0d93b-104">クラッシュは通常、プロセス内でアクセス違反やスタック オーバーフローなどの未処理の例外が発生したことが原因で起こります。</span><span class="sxs-lookup"><span data-stu-id="0d93b-104">A crash is typically caused by an unhandled exception in the process such as an access violation or a stack overflow.</span></span> <span data-ttu-id="0d93b-105">これらの状況で、Windows の既定のデバッガー、災害復旧します。ワトソン博士 (drwtsn32.exe) は、例外をキャッチし、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="0d93b-105">In these situations, the Windows default debugger, Dr. Watson (drwtsn32.exe) catches the exception and terminates the process.</span></span>  
  
 <span data-ttu-id="0d93b-106">クラッシュしたプロセスのメモリ ダンプを取得するには、次の手順に従って、未処理の例外をキャッチするようデバッグ診断ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="0d93b-106">To capture a memory dump of a process that is crashing, configure the Debug Diagnostics tool to catch the unhandled exception by following these steps:</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a><span data-ttu-id="0d93b-107">クラッシュ ダンプを取得するようデバッグ診断ツールを構成するには</span><span class="sxs-lookup"><span data-stu-id="0d93b-107">To configure the Debug Diagnostics tool to capture a crash dump</span></span>  
  
1.  <span data-ttu-id="0d93b-108">デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="0d93b-108">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="0d93b-109">場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合をクリックして、**ツール** メニューの 選択**ルール アクション**、 をクリック**ルールの追加**を規則の追加ウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="0d93b-109">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="0d93b-110">選択、**クラッシュ**オプション、 **Select Rule Type**ダイアログとクリック**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="0d93b-110">Select the **Crash** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="0d93b-111">選択**特定のプロセス**で、 **Select Target Type**ダイアログとクリック**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="0d93b-111">Select **A specific process** in the **Select Target Type** dialog and click **Next**.</span></span>  
  
5.  <span data-ttu-id="0d93b-112">クラッシュしてクリックして、いる BTSNTSvc.exe プロセスを選択**次**です。</span><span class="sxs-lookup"><span data-stu-id="0d93b-112">Select the BTSNTSvc.exe process that is crashing and click **Next**.</span></span>  
  
6.  <span data-ttu-id="0d93b-113">**高度な構成**ダイアログ**[次へ]**既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d93b-113">In the **Advanced Configuration** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="0d93b-114">**選択 Dump Location And Rule Name**ダイアログ**[次へ]**既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d93b-114">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
8.  <span data-ttu-id="0d93b-115">**Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**です。</span><span class="sxs-lookup"><span data-stu-id="0d93b-115">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
9. <span data-ttu-id="0d93b-116">\Program Files\IIS Resources\DebugDiag\Logs に既定では、プロセスのメモリ ダンプが保存される\\<*クラッシュ ルールの名前*\>れたときに、ローカル コンピューターの次のディレクトリ、プロセスで未処理の例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="0d93b-116">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*\> directory of the local computer the next time that an unhandled exception occurs in the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d93b-117">参照</span><span class="sxs-lookup"><span data-stu-id="0d93b-117">See Also</span></span>  
 [<span data-ttu-id="0d93b-118">デバッグ診断ツールを使用して、メモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="0d93b-118">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)