---
title: ブレークポイントの操作 |Microsoft Docs
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
ms.openlocfilehash: 7d1129e2eaa6c31a90e89e99f377f825990ee614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398541"
---
# <a name="working-with-breakpoints"></a><span data-ttu-id="83e24-102">ブレークポイントの操作</span><span class="sxs-lookup"><span data-stu-id="83e24-102">Working with Breakpoints</span></span>
<span data-ttu-id="83e24-103">中断されたオーケストレーションにアタッチすることで、またはクラスにブレークポイントを設定して、ブレークポイントを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="83e24-103">You can set breakpoints by attaching to a suspended orchestration, or by setting a breakpoint on a class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83e24-104">アセンブリの展開を解除すると、データベースは、追跡オプションおよびそのアセンブリのブレークポイント情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="83e24-104">When you undeploy an assembly, the database maintains the tracking options and breakpoint information for that assembly.</span></span> <span data-ttu-id="83e24-105">その後、同じアセンブリを展開する場合は、オプションおよびそのアセンブリのブレークポイント情報が復元されます。</span><span class="sxs-lookup"><span data-stu-id="83e24-105">If you subsequently deploy the same assembly again, the options and breakpoint information for that assembly are restored.</span></span>  
  
### <a name="to-attach-to-a-suspended-orchestration"></a><span data-ttu-id="83e24-106">中断したオーケストレーションにアタッチするには</span><span class="sxs-lookup"><span data-stu-id="83e24-106">To attach to a suspended orchestration</span></span>  
  
1.  <span data-ttu-id="83e24-107">中断図形を使用して自動的に中断されたオーケストレーションを選択し、手順 3. に進みます。</span><span class="sxs-lookup"><span data-stu-id="83e24-107">Select an automatically suspended orchestration using a suspend shape, and then go to Step 3.</span></span>  
  
2.  <span data-ttu-id="83e24-108">インスタンスが中断された状態で表示されることを確認するビューを更新します。</span><span class="sxs-lookup"><span data-stu-id="83e24-108">Refresh the view to check that the instance now appears in a Suspended state.</span></span>  
  
3.  <span data-ttu-id="83e24-109">クリックして**デバッグ モードで再開**します。</span><span class="sxs-lookup"><span data-stu-id="83e24-109">Click **Resume in Debug**.</span></span>  
  
     <span data-ttu-id="83e24-110">ブレークポイント状態のオーケストレーションを再開します。</span><span class="sxs-lookup"><span data-stu-id="83e24-110">The orchestration resumes in an In Breakpoint state.</span></span> <span data-ttu-id="83e24-111">これで対話的にデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="83e24-111">You can now debug interactively.</span></span>  
  
### <a name="to-switch-to-the-message-flow-view"></a><span data-ttu-id="83e24-112">メッセージ フロー ビューに切り替える</span><span class="sxs-lookup"><span data-stu-id="83e24-112">To switch to the Message Flow view</span></span>  
  
-   <span data-ttu-id="83e24-113">結果一覧のセルを右クリックして**メッセージ フロー**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="83e24-113">Right-click a cell in the Results list and select **Message Flow** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e24-114">参照</span><span class="sxs-lookup"><span data-stu-id="83e24-114">See Also</span></span>  
 [<span data-ttu-id="83e24-115">オーケストレーション デバッガー ビューの操作</span><span class="sxs-lookup"><span data-stu-id="83e24-115">Working with the Orchestration Debugger View</span></span>](../core/working-with-the-orchestration-debugger-view.md)