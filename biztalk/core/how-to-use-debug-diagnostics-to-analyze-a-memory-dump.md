---
title: デバッグ診断ツールを使用して、メモリ ダンプを分析する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a91a7-feab-4014-bbd5-e8b966b8b841
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc0faf72c9123ab7a501af8520f273e8c528b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256602"
---
# <a name="how-to-use-debug-diagnostics-to-analyze-a-memory-dump"></a><span data-ttu-id="e6d9f-102">デバッグ診断ツールを使用してメモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="e6d9f-102">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>
<span data-ttu-id="e6d9f-103">IIS 診断**デバッグ診断ツール**キャプチャされたメモリ ダンプ ファイルの基本分析が可能な機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-103">The IIS Diagnostics **Debug Diagnostics Tool** includes a feature that can provide a basic analysis of a captured memory dump file.</span></span> <span data-ttu-id="e6d9f-104">メモリ ダンプ ファイルの分析を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-104">To perform an analysis of a memory dump file follow these steps.</span></span>  
  
### <a name="to-analyze-the-dump-file"></a><span data-ttu-id="e6d9f-105">ダンプ ファイルを分析するには</span><span class="sxs-lookup"><span data-stu-id="e6d9f-105">To analyze the dump file</span></span>  
  
1.  <span data-ttu-id="e6d9f-106">デバッグ診断ツールを起動**開始**、**プログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-106">Launch the Debug Diagnostics tool from **Start**, **Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="e6d9f-107">クリックして、**高度な分析**タブです。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-107">Click the **Advanced Analysis** tab.</span></span>  
  
3.  <span data-ttu-id="e6d9f-108">**Available Analysis Scripts**をクリックして選択**Analyzers**クラッシュ/ハング ダンプを分析またはをクリックして選択する**Memory Pressure Analysis**メモリを分析するにはメモリ リークの発生が疑われるプロセスのダンプします。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-108">Under **Available Analysis Scripts** click to select **Crash/Hang Analyzers** to analyze a crash/hang dump or click to select **Memory Pressure Analysis** to analyze a memory dump of a process suspected of leaking memory.</span></span>  
  
4.  <span data-ttu-id="e6d9f-109">をクリックして、**データ ファイルを追加**生成されたダンプ ファイルを参照し、をクリックするボタン、**開く**ダンプ ファイルを分析するのにはデータ ファイルの可能な一覧に追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-109">Click the **Add Data Files** button to browse to the generated dump file and click the **Open** button to add the dump file to the possible list of data files to be analyzed.</span></span>  
  
5.  <span data-ttu-id="e6d9f-110">追加されたダンプ ファイルをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-110">Click to select the dump file that was added.</span></span>  
  
6.  <span data-ttu-id="e6d9f-111">クリックして、**分析の開始**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-111">Click the **Start Analysis** button.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6d9f-112">ローカル コンピューターにシンボル ファイルがインストールされていない場合、アナライザーは、インターネット経由で適切なシンボル ファイルの検索とダウンロードを試みます。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-112">The analyzer attempts to locate and download the appropriate symbol files from the internet if the symbol files are not installed on the local computer.</span></span> <span data-ttu-id="e6d9f-113">カスタム コードは、BTSNTSvc.exe プロセスで実行されているが場合、は、更新、**シンボル検索パスのデバッグ**オプションで使用できる、**フォルダーと検索パス**のタブ、**オプション (& a)設定**ダイアログを適切なシンボル ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-113">If custom code is being executed in the BTSNTSvc.exe process, update the **Symbol Search Path For Debugging** option available in the **Folder And Search Paths** tab of the **Options & Settings** dialog to include the appropriate symbol files.</span></span> <span data-ttu-id="e6d9f-114">クリックして、**ツール**メニューを選択**オプションと設定**を表示する、**オプションと設定**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-114">Click the **Tools** menu and select **Options And Settings** to display the **Options & Settings** dialog.</span></span>  
  
7.  <span data-ttu-id="e6d9f-115">分析が完了すると、.mht ファイル形式のレポートが生成され、Internet Explorer で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-115">Once the analysis is complete a report is generated in .mht file format and displayed in Internet Explorer.</span></span> <span data-ttu-id="e6d9f-116">既定では、このレポートは、ローカル コンピューターの \Program Files\IIS Resources\DebugDiag\Reports ディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e6d9f-116">By default this report is saved to the \Program Files\IIS Resources\DebugDiag\Reports directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d9f-117">参照</span><span class="sxs-lookup"><span data-stu-id="e6d9f-117">See Also</span></span>  
 [<span data-ttu-id="e6d9f-118">BizTalk プロセスのメモリ ダンプをキャプチャする方法</span><span class="sxs-lookup"><span data-stu-id="e6d9f-118">How to Capture a Memory Dump of a BizTalk Process</span></span>](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)