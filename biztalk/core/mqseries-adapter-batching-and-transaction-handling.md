---
title: MQSeries アダプタのバッチ処理とトランザクション処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- transactions, MQSeries adapters
- MQSeries adapters, transactions
- MQSeries adapters, IBM WebSphere MQ queues
- MQSeries adapters, batching
- batching, MQSeries adapters
ms.assetid: 2e43fca9-acbd-4fd3-8df3-5f7398553830
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffcdec02c464b9398acbece35657e0c3d1dc4432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262986"
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a><span data-ttu-id="35faa-102">MQSeries アダプタのバッチ処理とトランザクション処理</span><span class="sxs-lookup"><span data-stu-id="35faa-102">MQSeries Adapter Batching and Transaction Handling</span></span>
<span data-ttu-id="35faa-103">MQSeries アダプタは、すべてのデータを受信していない場合に限り、トランザクションを停止します。</span><span class="sxs-lookup"><span data-stu-id="35faa-103">The MQSeries adapter stops a transaction only if it does not receive all the data.</span></span> <span data-ttu-id="35faa-104">MQSeries アダプタのトランザクションの境界は、アダプタのエンドポイント (MQSeries Server の MQSeries キュー) およびメッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="35faa-104">The boundaries of a transaction for the adapter are the adapter endpoint (MQSeries queue on the MQSeries Server) and the MessageBox database.</span></span>  
  
 <span data-ttu-id="35faa-105">BizTalk アプリケーションでメッセージが無効化された場合、そのメッセージはアダプタにより保留キューに移動されます。</span><span class="sxs-lookup"><span data-stu-id="35faa-105">If the BizTalk application invalidates a message, the adapter moves the message to the suspended queue.</span></span> <span data-ttu-id="35faa-106">しかし、アダプタから見ると (すべてのデータを受信しており) そのメッセージはまだ有効なトランザクションなので、トランザクションがコミットされます。</span><span class="sxs-lookup"><span data-stu-id="35faa-106">However, because it is still a valid transaction from the point of view of the adapter (the adapter received all the data), the adapter commits the transaction.</span></span>  
  
 <span data-ttu-id="35faa-107">アダプタを構成するときにプロパティを設定することで、バッチ処理とトランザクション処理を制御できます。</span><span class="sxs-lookup"><span data-stu-id="35faa-107">You can control batching and transaction handling by setting properties when configuring the adapter.</span></span> <span data-ttu-id="35faa-108">詳細については、次を参照してください。 [MQSeries アダプターを構成する](../core/configuring-the-mqseries-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="35faa-108">For more information, see [Configuring the MQSeries Adapter](../core/configuring-the-mqseries-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35faa-109">参照</span><span class="sxs-lookup"><span data-stu-id="35faa-109">See Also</span></span>  
 [<span data-ttu-id="35faa-110">MQSeries アダプターのプロパティ</span><span class="sxs-lookup"><span data-stu-id="35faa-110">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)