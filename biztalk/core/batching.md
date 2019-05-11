---
title: バッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- Messaging Engine, batching
- batching, batch size
- batching, about batching
- batching, configuring
- batching, Messaging Engine
ms.assetid: eadc177a-d395-4f99-8dab-aa706fd8ea00
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941ded3f6b88c835c2eae819099449ed7d4e6974
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529092"
---
# <a name="batching"></a><span data-ttu-id="7e2da-102">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="7e2da-102">Batching</span></span>
<span data-ttu-id="7e2da-103">*バッチ処理*をラウンド トリップのデータベースを最適化できるように、一連のメッセージのシリアル化された処理します。</span><span class="sxs-lookup"><span data-stu-id="7e2da-103">*Batching* is a serialized processing of a set of messages that allows for optimizations with respect to database round trips.</span></span> <span data-ttu-id="7e2da-104">バッチが; アトミック作業単位とはこれは、すべて成功するか、すべて失敗します。</span><span class="sxs-lookup"><span data-stu-id="7e2da-104">A batch is a unit of work that is atomic; that is, it either all succeeds or all fails.</span></span> <span data-ttu-id="7e2da-105">バッチ内の 1 つの操作が成功した場合は、別の操作が失敗したバッチを構成するすべての操作が無効になり、繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e2da-105">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and must be repeated.</span></span>  
  
 <span data-ttu-id="7e2da-106">BizTalk Server では、バッチ処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e2da-106">BizTalk Server uses batching to:</span></span>  
  
-   <span data-ttu-id="7e2da-107">複数のメッセージのトランザクションのコストを償却します。</span><span class="sxs-lookup"><span data-stu-id="7e2da-107">Amortize the cost of the transaction across many messages.</span></span>  
  
-   <span data-ttu-id="7e2da-108">ラウンド トリップの内部データベースの数を減らすことで速度を上げる。</span><span class="sxs-lookup"><span data-stu-id="7e2da-108">Increase speed by reducing the internal number of database round trips.</span></span>  
  
-   <span data-ttu-id="7e2da-109">BizTalk Server 非同期 API を使用して、BizTalk Server スレッド プールのより効率的に使用をします。</span><span class="sxs-lookup"><span data-stu-id="7e2da-109">Make more efficient use of the BizTalk Server thread pool by using the BizTalk Server Asynchronous API.</span></span>  
  
## <a name="applying-batching"></a><span data-ttu-id="7e2da-110">バッチ処理の適用</span><span class="sxs-lookup"><span data-stu-id="7e2da-110">Applying Batching</span></span>  
 <span data-ttu-id="7e2da-111">バッチ処理して、受信場所の高度なプロパティで構成されて、送信ポート側で自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="7e2da-111">Batching is configured in the advanced properties for a receive location and is enabled automatically on the send port side.</span></span>  
  
## <a name="lowering-the-batch-size"></a><span data-ttu-id="7e2da-112">バッチ サイズの縮小</span><span class="sxs-lookup"><span data-stu-id="7e2da-112">Lowering the Batch Size</span></span>  
 <span data-ttu-id="7e2da-113">次のインスタンスの場合、バッチ サイズを小さく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e2da-113">You should lower the batch size if in the following instances:</span></span>  
  
-   <span data-ttu-id="7e2da-114">サイズの大きいメッセージを処理するときに</span><span class="sxs-lookup"><span data-stu-id="7e2da-114">When processing large messages</span></span>  
  
-   <span data-ttu-id="7e2da-115">トリップがボトルネックでない場合、データベース ラウンド</span><span class="sxs-lookup"><span data-stu-id="7e2da-115">When database round trips are not your bottleneck</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e2da-116">変更するときに注意してください、 **LargeMessageThreshold**設定します。</span><span class="sxs-lookup"><span data-stu-id="7e2da-116">Be careful when changing the **LargeMessageThreshold** setting.</span></span> <span data-ttu-id="7e2da-117">バッチ サイズに平均メッセージ サイズを乗算より小さい**LargeMessageThreshold**しない限り、バッチ サイズは 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="7e2da-117">The batch size multiplied by the average message size should be less than the **LargeMessageThreshold** setting unless the batch size is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2da-118">参照</span><span class="sxs-lookup"><span data-stu-id="7e2da-118">See Also</span></span>  
 <span data-ttu-id="7e2da-119">[メッセージング エンジン](../core/the-messaging-engine.md) </span><span class="sxs-lookup"><span data-stu-id="7e2da-119">[The Messaging Engine](../core/the-messaging-engine.md) </span></span>  
 <span data-ttu-id="7e2da-120">[受信処理用メッセージをバッチ処理](../core/batching-messages-for-receive-processing.md) </span><span class="sxs-lookup"><span data-stu-id="7e2da-120">[Batching Messages for Receive Processing](../core/batching-messages-for-receive-processing.md) </span></span>  
 [<span data-ttu-id="7e2da-121">送信処理用メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="7e2da-121">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)