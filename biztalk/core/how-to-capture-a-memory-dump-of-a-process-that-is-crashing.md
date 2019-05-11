---
title: クラッシュしたプロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f436b72-2b6a-4519-acc3-e7ba978651fe
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a425b3ca166c3de1726633b06193b2569dba34cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387038"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a><span data-ttu-id="27c75-102">クラッシュしたプロセスのメモリ ダンプをキャプチャする方法</span><span class="sxs-lookup"><span data-stu-id="27c75-102">How to Capture a Memory Dump of a Process that is Crashing</span></span>
<span data-ttu-id="27c75-103">BizTalk プロセス BTSNTSvc.exe として定義されている**クラッシュ**プロセスが Windows によって強制終了された場合。</span><span class="sxs-lookup"><span data-stu-id="27c75-103">The BizTalk process BTSNTSvc.exe is defined as **crashing** when the process is unexpectedly terminated by Windows.</span></span> <span data-ttu-id="27c75-104">クラッシュは通常、アクセス違反やスタック オーバーフローなどのプロセスで未処理の例外によって発生します。</span><span class="sxs-lookup"><span data-stu-id="27c75-104">A crash is typically caused by an unhandled exception in the process such as an access violation or a stack overflow.</span></span> <span data-ttu-id="27c75-105">このような場合は、Windows には、デバッガー、Dr が既定値します。ワトソン博士 (drwtsn32.exe) では、例外をキャッチし、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="27c75-105">In these situations, the Windows default debugger, Dr. Watson (drwtsn32.exe) catches the exception and terminates the process.</span></span>  
  
 <span data-ttu-id="27c75-106">クラッシュしたプロセスのメモリ ダンプをキャプチャするには、次の手順に従って、未処理の例外をキャッチするデバッグ診断ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="27c75-106">To capture a memory dump of a process that is crashing, configure the Debug Diagnostics tool to catch the unhandled exception by following these steps:</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a><span data-ttu-id="27c75-107">クラッシュ ダンプをキャプチャするデバッグ診断ツールを構成するには</span><span class="sxs-lookup"><span data-stu-id="27c75-107">To configure the Debug Diagnostics tool to capture a crash dump</span></span>  
  
1.  <span data-ttu-id="27c75-108">デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。</span><span class="sxs-lookup"><span data-stu-id="27c75-108">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="27c75-109">場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合、をクリックして、**ツール**クリックし、**ルール アクション**、 をクリック**規則の追加**規則の追加ウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="27c75-109">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="27c75-110">選択、**クラッシュ**オプション、 **Select Rule Type**ダイアログをクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="27c75-110">Select the **Crash** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="27c75-111">選択**特定のプロセス**で、 **Select Target Type**ダイアログをクリックします **[次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="27c75-111">Select **A specific process** in the **Select Target Type** dialog and click **Next**.</span></span>  
  
5.  <span data-ttu-id="27c75-112">BTSNTSvc.exe プロセスがクラッシュし、クリックを選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="27c75-112">Select the BTSNTSvc.exe process that is crashing and click **Next**.</span></span>  
  
6.  <span data-ttu-id="27c75-113">**Advanced Configuration**ダイアログ **[次へ]** 既定値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="27c75-113">In the **Advanced Configuration** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="27c75-114">**選択 Dump Location And Rule Name**ダイアログ **[次へ]** 既定値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="27c75-114">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
8.  <span data-ttu-id="27c75-115">**Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**します。</span><span class="sxs-lookup"><span data-stu-id="27c75-115">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
9. <span data-ttu-id="27c75-116">既定では、プロセスのメモリ ダンプを \Program Files\IIS Resources\DebugDiag\Logs に保存されます\\<*クラッシュ規則の名前*\>ローカル コンピューターの次のディレクトリの時間をプロセスでハンドルされない例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="27c75-116">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*\> directory of the local computer the next time that an unhandled exception occurs in the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c75-117">参照</span><span class="sxs-lookup"><span data-stu-id="27c75-117">See Also</span></span>  
 [<span data-ttu-id="27c75-118">デバッグ診断ツールを使用してメモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="27c75-118">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)