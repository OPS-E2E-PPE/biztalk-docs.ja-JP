---
title: MQSeries アダプターがバッチ処理とトランザクションの処理 |Microsoft Docs
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
ms.openlocfilehash: 466201e88b55cd17300deaae3d1b1258e82a2c2c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531200"
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a><span data-ttu-id="59bef-102">MQSeries アダプターのバッチ処理とトランザクション処理</span><span class="sxs-lookup"><span data-stu-id="59bef-102">MQSeries Adapter Batching and Transaction Handling</span></span>
<span data-ttu-id="59bef-103">MQSeries アダプターは、すべてのデータが受信しない場合にのみ、トランザクションを停止します。</span><span class="sxs-lookup"><span data-stu-id="59bef-103">The MQSeries adapter stops a transaction only if it does not receive all the data.</span></span> <span data-ttu-id="59bef-104">アダプターのトランザクションの境界は、アダプターのエンドポイント (MQSeries サーバー上の MQSeries キュー) と、メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="59bef-104">The boundaries of a transaction for the adapter are the adapter endpoint (MQSeries queue on the MQSeries Server) and the MessageBox database.</span></span>  
  
 <span data-ttu-id="59bef-105">BizTalk アプリケーションがメッセージを無効にする場合、アダプターは、保留キューにメッセージを移動します。</span><span class="sxs-lookup"><span data-stu-id="59bef-105">If the BizTalk application invalidates a message, the adapter moves the message to the suspended queue.</span></span> <span data-ttu-id="59bef-106">ただし、アダプター (アダプターで受信したすべてのデータ) の有効なトランザクションの観点からではまだであるため、アダプターは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="59bef-106">However, because it is still a valid transaction from the point of view of the adapter (the adapter received all the data), the adapter commits the transaction.</span></span>  
  
 <span data-ttu-id="59bef-107">バッチ処理とトランザクション アダプターを構成するときにプロパティを設定して処理を制御できます。</span><span class="sxs-lookup"><span data-stu-id="59bef-107">You can control batching and transaction handling by setting properties when configuring the adapter.</span></span> <span data-ttu-id="59bef-108">詳細については、次を参照してください。 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="59bef-108">For more information, see [Configuring the MQSeries Adapter](../core/configuring-the-mqseries-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59bef-109">参照</span><span class="sxs-lookup"><span data-stu-id="59bef-109">See Also</span></span>  
 [<span data-ttu-id="59bef-110">MQSeries アダプター プロパティ</span><span class="sxs-lookup"><span data-stu-id="59bef-110">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)