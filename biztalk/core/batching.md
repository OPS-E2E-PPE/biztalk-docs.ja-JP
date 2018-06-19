---
title: バッチ処理 |Microsoft ドキュメント
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
ms.openlocfilehash: ca31344e60daa88a37c21d0f90b6cf2d2a8aa5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230890"
---
# <a name="batching"></a><span data-ttu-id="2d7bb-102">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="2d7bb-102">Batching</span></span>
<span data-ttu-id="2d7bb-103">*バッチ処理*をラウンド トリップのデータベースを最適化できるようにする一連のメッセージのシリアル化された処理します。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-103">*Batching* is a serialized processing of a set of messages that allows for optimizations with respect to database round trips.</span></span> <span data-ttu-id="2d7bb-104">バッチは、アトミックな作業単位です。つまり、バッチはすべて成功するか、すべて失敗するかのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-104">A batch is a unit of work that is atomic; that is, it either all succeeds or all fails.</span></span> <span data-ttu-id="2d7bb-105">バッチ内のある操作が成功しても、別の操作が失敗した場合は、そのバッチを構成するすべての操作が無効になり、もう一度やり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-105">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and must be repeated.</span></span>  
  
 <span data-ttu-id="2d7bb-106">BizTalk Server では、次の目的でバッチ処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-106">BizTalk Server uses batching to:</span></span>  
  
-   <span data-ttu-id="2d7bb-107">トランザクションのコストを複数のメッセージに分割する。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-107">Amortize the cost of the transaction across many messages.</span></span>  
  
-   <span data-ttu-id="2d7bb-108">内部的なデータベース ラウンド トリップ数を減らして速度を上げる。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-108">Increase speed by reducing the internal number of database round trips.</span></span>  
  
-   <span data-ttu-id="2d7bb-109">BizTalk Server 非同期 API の使用により、BizTalk Server スレッド プールの利用を効率化する。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-109">Make more efficient use of the BizTalk Server thread pool by using the BizTalk Server Asynchronous API.</span></span>  
  
## <a name="applying-batching"></a><span data-ttu-id="2d7bb-110">バッチ処理の適用</span><span class="sxs-lookup"><span data-stu-id="2d7bb-110">Applying Batching</span></span>  
 <span data-ttu-id="2d7bb-111">バッチ処理は、受信場所の詳細プロパティで設定され、送信ポート側で自動的に有効化されます。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-111">Batching is configured in the advanced properties for a receive location and is enabled automatically on the send port side.</span></span>  
  
## <a name="lowering-the-batch-size"></a><span data-ttu-id="2d7bb-112">バッチ サイズの縮小</span><span class="sxs-lookup"><span data-stu-id="2d7bb-112">Lowering the Batch Size</span></span>  
 <span data-ttu-id="2d7bb-113">次の場合は、バッチ サイズを縮小する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-113">You should lower the batch size if in the following instances:</span></span>  
  
-   <span data-ttu-id="2d7bb-114">サイズの大きなメッセージを処理する場合</span><span class="sxs-lookup"><span data-stu-id="2d7bb-114">When processing large messages</span></span>  
  
-   <span data-ttu-id="2d7bb-115">データベース ラウンド トリップがボトルネックでない場合</span><span class="sxs-lookup"><span data-stu-id="2d7bb-115">When database round trips are not your bottleneck</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d7bb-116">変更するときに注意してください、 **LargeMessageThreshold**設定します。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-116">Be careful when changing the **LargeMessageThreshold** setting.</span></span> <span data-ttu-id="2d7bb-117">メッセージの平均サイズを乗算するバッチ サイズにする必要がありますよりも低い**LargeMessageThreshold**しない限り、バッチ サイズは 1 を設定します。</span><span class="sxs-lookup"><span data-stu-id="2d7bb-117">The batch size multiplied by the average message size should be less than the **LargeMessageThreshold** setting unless the batch size is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7bb-118">参照</span><span class="sxs-lookup"><span data-stu-id="2d7bb-118">See Also</span></span>  
 <span data-ttu-id="2d7bb-119">[メッセージング エンジン](../core/the-messaging-engine.md) </span><span class="sxs-lookup"><span data-stu-id="2d7bb-119">[The Messaging Engine](../core/the-messaging-engine.md) </span></span>  
 <span data-ttu-id="2d7bb-120">[受信処理用メッセージをバッチ処理](../core/batching-messages-for-receive-processing.md) </span><span class="sxs-lookup"><span data-stu-id="2d7bb-120">[Batching Messages for Receive Processing](../core/batching-messages-for-receive-processing.md) </span></span>  
 [<span data-ttu-id="2d7bb-121">送信処理のメッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="2d7bb-121">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)