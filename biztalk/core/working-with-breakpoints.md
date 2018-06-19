---
title: ブレークポイントの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, breakpoints
- Orchestration Debugger, suspended orchestrations
- Orchestration Debugger, Message Flow view
- Orchestration Debugger, service options
- Message Flow view [Orchestration Debugger]
ms.assetid: aad1a2b0-d705-49cd-85f7-b0ab2e473bcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e9cee77f105b132438e621651ee90c0090c1be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289210"
---
# <a name="working-with-breakpoints"></a><span data-ttu-id="515c9-102">ブレークポイントの操作</span><span class="sxs-lookup"><span data-stu-id="515c9-102">Working with Breakpoints</span></span>
<span data-ttu-id="515c9-103">ブレークポイントを設定するには、中断されたオーケストレーションに接続するか、またはクラスでブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="515c9-103">You can set breakpoints by attaching to a suspended orchestration, or by setting a breakpoint on a class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="515c9-104">アセンブリを展開解除すると、データベースは、追跡オプションおよびそのアセンブリのブレークポイント情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="515c9-104">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for that assembly.</span></span> <span data-ttu-id="515c9-105">その後、同じアセンブリを再度展開すると、そのアセンブリのオプションおよびブレークポイント情報が復元されます。</span><span class="sxs-lookup"><span data-stu-id="515c9-105">If you subsequently deploy the same assembly again, the options and breakpoint information for that assembly are restored.</span></span>  
  
### <a name="to-attach-to-a-suspended-orchestration"></a><span data-ttu-id="515c9-106">中断されたオーケストレーションに接続するには</span><span class="sxs-lookup"><span data-stu-id="515c9-106">To attach to a suspended orchestration</span></span>  
  
1.  <span data-ttu-id="515c9-107">自動的に中断されたオーケストレーションを中断図形を使用して選択し、手順 3. に進みます。</span><span class="sxs-lookup"><span data-stu-id="515c9-107">Select an automatically suspended orchestration using a suspend shape, and then go to Step 3.</span></span>  
  
2.  <span data-ttu-id="515c9-108">表示を更新して、インスタンスが現在中断された状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="515c9-108">Refresh the view to check that the instance now appears in a Suspended state.</span></span>  
  
3.  <span data-ttu-id="515c9-109">をクリックして**デバッグ モードで再開**です。</span><span class="sxs-lookup"><span data-stu-id="515c9-109">Click **Resume in Debug**.</span></span>  
  
     <span data-ttu-id="515c9-110">オーケストレーションは、"ブレークポイント" 状態で再開します。</span><span class="sxs-lookup"><span data-stu-id="515c9-110">The orchestration resumes in an In Breakpoint state.</span></span> <span data-ttu-id="515c9-111">これで、対話形式でデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="515c9-111">You can now debug interactively.</span></span>  
  
### <a name="to-switch-to-the-message-flow-view"></a><span data-ttu-id="515c9-112">メッセージ フロー ビューに切り替えるには</span><span class="sxs-lookup"><span data-stu-id="515c9-112">To switch to the Message Flow view</span></span>  
  
-   <span data-ttu-id="515c9-113">結果一覧のセルを右クリックし **メッセージ フロー**ショートカット メニューからです。</span><span class="sxs-lookup"><span data-stu-id="515c9-113">Right-click a cell in the Results list and select **Message Flow** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515c9-114">参照</span><span class="sxs-lookup"><span data-stu-id="515c9-114">See Also</span></span>  
 [<span data-ttu-id="515c9-115">オーケストレーション デバッガー ビューの操作</span><span class="sxs-lookup"><span data-stu-id="515c9-115">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)