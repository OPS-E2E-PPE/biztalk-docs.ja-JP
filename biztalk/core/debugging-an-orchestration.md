---
title: "オーケストレーションのデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging, Orchestration Debugger
- debugging, orchestrations
- Orchestration Debugger, about Orchestration Debugger
- Orchestrations Debugger
- orchestrations, debugging
- debugging, HAT
- HAT, debugging
ms.assetid: aae99cfd-d3dd-41c8-ae7a-b2733352cd69
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c231513ad75520fcadd88e5dd7d88104ddeeced5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-an-orchestration"></a><span data-ttu-id="e1d37-102">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="e1d37-102">Debugging an Orchestration</span></span>
<span data-ttu-id="e1d37-103">オーケストレーション デバッガーを使用すると、単一のオーケストレーション インスタンスのアクティビティを図形ごとに追跡できます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-103">The Orchestration Debugger enables you to track the activity of a single orchestration instance on a shape-by-shape basis.</span></span> <span data-ttu-id="e1d37-104">これにより、オーケストレーション デザイナーで作成されたオーケストレーションの描画されたビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-104">It displays a rendered view of the orchestration created in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="e1d37-105">オーケストレーション デバッガーには、BizTalk Server 管理コンソールの [グループの概要] ページでアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e1d37-105">You access the Orchestration Debugger in the Group Overview Page in the BizTalk Server Administration Console.</span></span>  <span data-ttu-id="e1d37-106">それには、追跡クエリの出力から、オーケストレーションの種類に関連付けられたサービスまたはメッセージ インスタンスを右クリックして表示されるショートカット メニューにより行います。</span><span class="sxs-lookup"><span data-stu-id="e1d37-106">This is done from the output of a tracking query through a shortcut menu by right-clicking any service or message instance associated with an orchestration type.</span></span> <span data-ttu-id="e1d37-107">このページで、オーケストレーション デバッガーとメッセージ フロー ビューを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-107">Once you're in i this page, you can switch back and forth between the Orchestration Debugger and the Message Flow view.</span></span>  
  
 <span data-ttu-id="e1d37-108">オーケストレーション デバッガーには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="e1d37-108">The Orchestration Debugger provides the following functionality:</span></span>  
  
-   <span data-ttu-id="e1d37-109">特定のオーケストレーションの各処理手順を再生できる、そのオーケストレーションの描画されたビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="e1d37-109">Displays a rendered view of the orchestration in which you can replay each processing step for that particular orchestration.</span></span>  
  
-   <span data-ttu-id="e1d37-110">オーケストレーション図形の前にブレークポイントを設定して実行を続行できます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-110">Enables you to set breakpoints before any orchestration shape and continue execution.</span></span>  
  
-   <span data-ttu-id="e1d37-111">特定の変数およびメッセージ データを参照できます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-111">Enables you to look at specific variables and message data.</span></span>  
  
-   <span data-ttu-id="e1d37-112">特定のオーケストレーション インスタンスがオーケストレーション デバッガーで開かれるときにそのインスタンスのすべての追跡オプションを自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="e1d37-112">Automatically enables all of the tracking options for a particular orchestration instance when that instance opens in the Orchestration Debugger.</span></span>  
  
-   <span data-ttu-id="e1d37-113">特定のオーケストレーション インスタンスを、デバッグ モードで続行、再開、および終了することができます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-113">It gives you the ability to continue, resume in debug, and terminate the particular orchestration instance.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1d37-114">アセンブリの展開を解除すると、データベースには、展開を解除されたアセンブリの追跡オプションおよびブレークポイント情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-114">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for the undeployed assembly.</span></span> <span data-ttu-id="e1d37-115">その後、同じアセンブリを展開すると、そのアセンブリのオプションおよびブレークポイント情報が復元されます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-115">If you subsequently deploy the same assembly, the options and breakpoint information for that assembly are restored.</span></span>  
  
 <span data-ttu-id="e1d37-116">オーケストレーション デバッガーは、次の 2 つのモードで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1d37-116">The two modes for using the Orchestration Debugger are:</span></span>  
  
-   [<span data-ttu-id="e1d37-117">オーケストレーション デバッガーの報告モード</span><span class="sxs-lookup"><span data-stu-id="e1d37-117">Reporting Mode in Orchestration Debugger</span></span>](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [<span data-ttu-id="e1d37-118">オーケストレーション デバッガーの対話モード</span><span class="sxs-lookup"><span data-stu-id="e1d37-118">Interactive Mode in Orchestration Debugger</span></span>](../core/interactive-mode-in-orchestration-debugger.md)  
  
 <span data-ttu-id="e1d37-119">機能は、サービスの状態によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1d37-119">The capabilities differ depending on the state of the service.</span></span> <span data-ttu-id="e1d37-120">対話形式のデバッグを実行するには、現在 "ブレークポイント" 状態のサービス インスタンスを、任意のビューから呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e1d37-120">You can perform interactive debugging by invoking any service instance currently in the In Breakpoint state, from any view.</span></span> <span data-ttu-id="e1d37-121">オーケストレーションのデバッグ方法の詳細については、次を参照してください。[オーケストレーション デバッガーとメッセージ フロー ビューを呼び出す方法](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1d37-121">For information about debugging an orchestration, see [How to Invoke the Orchestration Debugger and the Message Flow Views](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1d37-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e1d37-122">In This Section</span></span>  
  
-   [<span data-ttu-id="e1d37-123">オーケストレーション デバッガーのユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1d37-123">Orchestration Debugger User Interface</span></span>](../core/orchestration-debugger-user-interface.md)  
  
-   [<span data-ttu-id="e1d37-124">オーケストレーション デバッガーを使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="e1d37-124">Considerations when Using Orchestration Debugger</span></span>](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [<span data-ttu-id="e1d37-125">オーケストレーション デバッガー ビューの操作</span><span class="sxs-lookup"><span data-stu-id="e1d37-125">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)