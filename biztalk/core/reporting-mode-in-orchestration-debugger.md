---
title: オーケストレーション デバッガーの報告モード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, breakpoints
- Orchestration Debugger, Reporting mode
- Reporting mode [Orchestration Debugger]
ms.assetid: 014a444c-2867-4156-b009-8518e8250d4d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f51c80c8e11545180720a5ec1cf0f28b7f8b6f6d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268570"
---
# <a name="reporting-mode-in-orchestration-debugger"></a><span data-ttu-id="34d3e-102">オーケストレーション デバッガーの報告モード</span><span class="sxs-lookup"><span data-stu-id="34d3e-102">Reporting Mode in Orchestration Debugger</span></span>
<span data-ttu-id="34d3e-103">報告モードでは、追跡したイベントを使用して、何が発生したかを示します。</span><span class="sxs-lookup"><span data-stu-id="34d3e-103">Reporting mode uses tracked events to show what has happened.</span></span> <span data-ttu-id="34d3e-104">使用して追跡データを使用して、**オーケストレーション イベント**オプション フラグ。</span><span class="sxs-lookup"><span data-stu-id="34d3e-104">It uses data tracked using the **Orchestration Events** option flag.</span></span> <span data-ttu-id="34d3e-105">このフラグは、オーケストレーション インスタンスの実行前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34d3e-105">This flag must be set prior to the execution of the orchestration instance.</span></span> <span data-ttu-id="34d3e-106">イベントの特定のオーケストレーションの追跡を有効にするを参照してください。[オーケストレーションの追跡を構成する方法](../core/how-to-configure-tracking-for-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="34d3e-106">To enable event tracking for a particular orchestration, see [How to Configure Tracking for an Orchestration](../core/how-to-configure-tracking-for-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="34d3e-107">**オーケストレーション イベント**オプションはこれが発生すると、オーケストレーション内の各図形の実行を追跡します。</span><span class="sxs-lookup"><span data-stu-id="34d3e-107">The **Orchestration Events** option tracks the execution of each shape in the orchestration as it happens.</span></span> <span data-ttu-id="34d3e-108">報告モードでは、手順を繰り返したり、オーケストレーションのクラスにブレークポイントを設定でき、その後、対話モードを使用して、新しいインスタンスをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="34d3e-108">In reporting mode, you can replay the steps or set breakpoints on the class of orchestration so that you can then debug new instances using interactive mode.</span></span>  
  
 <span data-ttu-id="34d3e-109">関心のあるビジネス プロセスを実行した後、調査するオーケストレーションに対して報告ビューのクエリのいずれか 1 つを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34d3e-109">After you have executed the business process you are interested in, you can use one of the Reporting view queries for the orchestration you wish to examine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d3e-110">参照</span><span class="sxs-lookup"><span data-stu-id="34d3e-110">See Also</span></span>  
 <span data-ttu-id="34d3e-111">[オーケストレーション デバッガーの対話モード](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="34d3e-111">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 <span data-ttu-id="34d3e-112">[オーケストレーションのデバッグ](../core/debugging-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="34d3e-112">[Debugging an Orchestration](../core/debugging-an-orchestration.md) </span></span>  
 [<span data-ttu-id="34d3e-113">オーケストレーション デバッガーのユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34d3e-113">Orchestration Debugger User Interface</span></span>](../core/orchestration-debugger-user-interface.md)