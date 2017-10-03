---
title: "データ項目ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definition files [BAM], data items
- Data Item nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 95856bfa-90e3-49d9-b55b-5f1b35a23f78
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a968bf7533697922938eeb8953f17813c77147c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-item-nodes"></a><span data-ttu-id="714e9-102">データ項目ノード</span><span class="sxs-lookup"><span data-stu-id="714e9-102">Data Item Nodes</span></span>
<span data-ttu-id="714e9-103">データ項目ノードは、ビジネス アナリストが作成した監視モデルから開発者がインポートするアクティビティ定義ファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="714e9-103">Data Item nodes exist in the activity definition file that the developer imports from the created observation model created by the business analyst.</span></span> <span data-ttu-id="714e9-104">データ項目ノードには、追跡するデータ項目を反映した名前 (たとえば、Customer Name など) が追跡プロファイル エディター (TPE) によって付けられます。</span><span class="sxs-lookup"><span data-stu-id="714e9-104">The Tracking Profile Editor (TPE) names them for the data items they are tracking, such as Customer Name.</span></span> <span data-ttu-id="714e9-105">Customer Name に対応するノードには、メッセージ スキーマ ビューから 1 つ以上のデータ項目をドロップします。</span><span class="sxs-lookup"><span data-stu-id="714e9-105">You then drop one or more data items from the Message Schema View onto the node that corresponds to Customer Name.</span></span>  
  
## <a name="working-with-data-item-nodes"></a><span data-ttu-id="714e9-106">データ項目ノードの操作</span><span class="sxs-lookup"><span data-stu-id="714e9-106">Working with data item nodes</span></span>  
 <span data-ttu-id="714e9-107">データ項目ノードをマップする際に、ビジネス プロセスが複数の追跡プロファイルにまたがっていても、データ項目は 1 つのビジネス プロセスにつき 1 回だけ追跡するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="714e9-107">When mapping Data Item nodes you should only track data items once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="714e9-108">オーケストレーションに条件付きのパスが含まれている場合は、いずれか一方しか実行されないので、両方のパスからデータ項目を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="714e9-108">If you have a conditional path in your orchestration, you can select the data item from both paths because only one will run.</span></span> <span data-ttu-id="714e9-109">ただし、反復ごとにデータ項目の値が異なる場合を除き、ループ内の図形は選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="714e9-109">However, you should not choose a shape inside a loop unless the values will be different for the data item with each iteration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714e9-110">参照</span><span class="sxs-lookup"><span data-stu-id="714e9-110">See Also</span></span>  
 <span data-ttu-id="714e9-111">[項目のデータをマップする方法](../core/how-to-map-item-data.md) </span><span class="sxs-lookup"><span data-stu-id="714e9-111">[How to Map Item Data](../core/how-to-map-item-data.md) </span></span>  
 [<span data-ttu-id="714e9-112">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="714e9-112">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)