---
title: メッセージとインスタンスの追跡の計画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, planning
- planning, HAT
ms.assetid: 69b0d30e-77df-4847-9a59-6dd806152b71
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506dcd8342b016b325544f63f95c76c87dcc0772
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263562"
---
# <a name="planning-for-message-and-instance-tracking"></a><span data-ttu-id="c810a-102">メッセージとインスタンスの追跡の計画</span><span class="sxs-lookup"><span data-stu-id="c810a-102">Planning for Message and Instance Tracking</span></span>
<span data-ttu-id="c810a-103">プロジェクトを展開した後に追跡オプションを指定し、追跡データの量を制限して必要な情報だけを取得するために、計画段階中に追跡する情報を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c810a-103">You should decide during the planning stages which information you need to track, so that after you deploy the project you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
 <span data-ttu-id="c810a-104">メッセージにアクセスするたびに BizTalk Server のメッセージとサーバー インスタンスの追跡により別のコピーが作成されるので、すべてのメッセージを追跡するのは避けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c810a-104">We recommend that you do not track all messages, because each time a message is touched, BizTalk Server message and server instance tracking makes another copy.</span></span> <span data-ttu-id="c810a-105">たとえば、特定のポートだけを追跡して、範囲を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c810a-105">For example, you can narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="c810a-106">これにより、システムのパフォーマンスを最大限に高め、データベースの整合性を維持できます。</span><span class="sxs-lookup"><span data-stu-id="c810a-106">This helps to maximize the performance of your system and keep the databases uncluttered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c810a-107">参照</span><span class="sxs-lookup"><span data-stu-id="c810a-107">See Also</span></span>  
 [<span data-ttu-id="c810a-108">管理と追跡アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c810a-108">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)