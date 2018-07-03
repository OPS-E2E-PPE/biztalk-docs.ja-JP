---
title: メッセージのバッチ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f893d16-2670-4463-9a89-6f5be912a045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13936fc06807d0bdc4f8e13dbd7742919dc894b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990699"
---
# <a name="message-batches"></a><span data-ttu-id="fb7f9-102">メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="fb7f9-102">Message Batches</span></span>
<span data-ttu-id="fb7f9-103">一括処理する必要があるメッセージのグループがアダプターに存在する場合は、これらのメッセージをバッチで処理してパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-103">When your adapter has a group of messages that need to be processed at one time, you should batch these messages to optimize performance.</span></span> <span data-ttu-id="fb7f9-104">プログラム的には、メッセージ バッチとは関連する操作が含まれているメッセージの集まりということになります。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-104">Programmatically, message batches are collections of messages with an associated operation.</span></span> <span data-ttu-id="fb7f9-105">個別に各メッセージを送信するのではなく、バッチ内のメッセージをグループ化、によっては、リソースとタスクの処理の使用を最適化します。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-105">By grouping messages in a batch rather than submitting each message individually, you optimize the use of resources and processing tasks.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fb7f9-106"> バッチ処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-106"> uses batching to:</span></span>  

- <span data-ttu-id="fb7f9-107">トランザクションのコストを複数のメッセージに分割する。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-107">Amortize the cost of the transaction across many messages.</span></span>  

- <span data-ttu-id="fb7f9-108">内部的なデータベース ラウンド トリップ数を減らして速度を上げる。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-108">Increase speed by reducing the internal number of database round trips.</span></span>  

- <span data-ttu-id="fb7f9-109">メッセージを非同期的に処理することにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] スレッド プールの利用を効率化する。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-109">Make more efficient use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] thread pool by processing the messages asynchronously.</span></span>  

  <span data-ttu-id="fb7f9-110">バッチは、アトミックな作業単位です。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-110">A batch is a unit of work that is atomic.</span></span> <span data-ttu-id="fb7f9-111">つまり、操作はすべて成功するか、すべて失敗するかのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-111">That is, either all operations in it succeed or all operations in it fail.</span></span> <span data-ttu-id="fb7f9-112">バッチ内のある操作が成功しても、別の操作が失敗した場合は、そのバッチを構成するすべての操作が無効になり、メッセージを再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-112">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and the messages must be resubmitted.</span></span> <span data-ttu-id="fb7f9-113">そのため、アダプターは、失敗したバッチに対して 3 つの処理を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-113">This means that an adapter must do three things in response to a failed batch:</span></span>  

- <span data-ttu-id="fb7f9-114">どのメッセージの処理に失敗したのかを特定する。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-114">Determine which messages failed.</span></span>  

- <span data-ttu-id="fb7f9-115">失敗したメッセージに対する処理を決定する。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-115">Decide what to do with the failed messages.</span></span>  

- <span data-ttu-id="fb7f9-116">失敗しなかったメッセージを再送信する。</span><span class="sxs-lookup"><span data-stu-id="fb7f9-116">Resubmit the messages that did not fail.</span></span>
