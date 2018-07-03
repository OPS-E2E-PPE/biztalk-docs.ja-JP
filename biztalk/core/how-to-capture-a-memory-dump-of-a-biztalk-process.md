---
title: BizTalk プロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8053fcf3-b331-4245-b3c3-21290463e0c0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3643dab17f8d1592f1e5fddce30aa12e537c817
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969139"
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a><span data-ttu-id="08289-102">BizTalk プロセスのメモリ ダンプを取得する方法</span><span class="sxs-lookup"><span data-stu-id="08289-102">How to Capture a Memory Dump of a BizTalk Process</span></span>
<span data-ttu-id="08289-103">状況によっては、BizTalk Server で実行中のプロセスのメモリ ダンプを取得し、そのプロセスの詳細な分析を実行する必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08289-103">Under certain circumstances it may be necessary to capture a memory dump of a process running on a BizTalk Server to perform an in depth analysis of the process.</span></span> <span data-ttu-id="08289-104">メモリ ダンプの分析が必要な状況として、以下のような場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="08289-104">Situations that may require analysis of a memory dump include the following:</span></span>  
  
- <span data-ttu-id="08289-105">プロセスが応答しない場合</span><span class="sxs-lookup"><span data-stu-id="08289-105">When a process is unresponsive.</span></span>  
  
- <span data-ttu-id="08289-106">プロセスがクラッシュしている場合</span><span class="sxs-lookup"><span data-stu-id="08289-106">When a process is crashing.</span></span>  
  
- <span data-ttu-id="08289-107">プロセスでメモリ リークが発生している場合</span><span class="sxs-lookup"><span data-stu-id="08289-107">When a process leaks memory.</span></span>  
  
  <span data-ttu-id="08289-108">ここでは、適切な種類のメモリ ダンプを取得する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="08289-108">This section includes the steps that should be followed to capture the appropriate type of memory dump.</span></span>  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a><span data-ttu-id="08289-109">IIS 診断ツールキットのインストール</span><span class="sxs-lookup"><span data-stu-id="08289-109">Installation of the IIS Diagnostics Toolkit</span></span>  
 <span data-ttu-id="08289-110">このセクションのトピックの使用が必要です、**デバッグ診断ツール**IIS 診断ツールキットのメモリ ダンプを取得します。</span><span class="sxs-lookup"><span data-stu-id="08289-110">Each of the topics in this section requires the use of the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit to capture a memory dump.</span></span> <span data-ttu-id="08289-111">インストールする、**デバッグ診断ツール**IIS 診断ツールキットの次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="08289-111">To install the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit follow these steps:</span></span>  
  
1.  <span data-ttu-id="08289-112">IIS 診断ツールキットをダウンロード[インターネット インフォメーション サービスの診断ツール](http://go.microsoft.com/fwlink/?LinkId=64426)します。</span><span class="sxs-lookup"><span data-stu-id="08289-112">Download the IIS Diagnostics Toolkit from [Internet Information Services Diagnostic Tools](http://go.microsoft.com/fwlink/?LinkId=64426).</span></span>  
  
2.  <span data-ttu-id="08289-113">ダブルクリックして、 **iisdiag.msi**パッケージを IIS 診断ツールキットのセットアップ プログラムを起動して、選択、**カスタム**セットアップの種類。</span><span class="sxs-lookup"><span data-stu-id="08289-113">Double-click the **iisdiag.msi** package to start the IIS Diagnostics Toolkit setup program and choose the **Custom** setup type.</span></span>  
  
3.  <span data-ttu-id="08289-114">**カスタム セットアップ**ダイアログ ボックスで、オプションのことを確認、 **Debug Diagnostics Tool 1.0**を有効にし、セットアップ プログラムで手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="08289-114">In the **Custom Setup** dialog, ensure that the option for the **Debug Diagnostics Tool 1.0** is enabled and complete the steps in the setup program.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08289-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="08289-115">In This Section</span></span>  
  
-   [<span data-ttu-id="08289-116">応答のないプロセスのメモリ ダンプをキャプチャする方法</span><span class="sxs-lookup"><span data-stu-id="08289-116">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [<span data-ttu-id="08289-117">クラッシュしたプロセスのメモリ ダンプをキャプチャする方法</span><span class="sxs-lookup"><span data-stu-id="08289-117">How to Capture a Memory Dump of a Process that is Crashing</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [<span data-ttu-id="08289-118">メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法</span><span class="sxs-lookup"><span data-stu-id="08289-118">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [<span data-ttu-id="08289-119">デバッグ診断ツールを使用してメモリ ダンプを分析する方法</span><span class="sxs-lookup"><span data-stu-id="08289-119">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)