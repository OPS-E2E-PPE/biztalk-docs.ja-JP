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
ms.openlocfilehash: 78222848258ea4c1840b645c1357bceb49c0ac14
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531165"
---
# <a name="message-batches"></a><span data-ttu-id="67033-102">メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="67033-102">Message Batches</span></span>
<span data-ttu-id="67033-103">アダプターに同時に処理する必要があるメッセージのグループがある場合は、パフォーマンスを最適化するためにこれらのメッセージをバッチ処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67033-103">When your adapter has a group of messages that need to be processed at one time, you should batch these messages to optimize performance.</span></span> <span data-ttu-id="67033-104">プログラムでは、メッセージ バッチは、関連付けられている操作を使用したメッセージのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="67033-104">Programmatically, message batches are collections of messages with an associated operation.</span></span> <span data-ttu-id="67033-105">個別に各メッセージを送信するのではなく、バッチ内のメッセージをグループ化、によっては、リソースとタスクの処理の使用を最適化します。</span><span class="sxs-lookup"><span data-stu-id="67033-105">By grouping messages in a batch rather than submitting each message individually, you optimize the use of resources and processing tasks.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="67033-106">バッチ処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="67033-106">uses batching to:</span></span>  

- <span data-ttu-id="67033-107">複数のメッセージのトランザクションのコストを償却します。</span><span class="sxs-lookup"><span data-stu-id="67033-107">Amortize the cost of the transaction across many messages.</span></span>  

- <span data-ttu-id="67033-108">ラウンド トリップの内部データベースの数を減らすことで速度を上げる。</span><span class="sxs-lookup"><span data-stu-id="67033-108">Increase speed by reducing the internal number of database round trips.</span></span>  

- <span data-ttu-id="67033-109">より効率的に使用できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを非同期的に処理することによってスレッド プール。</span><span class="sxs-lookup"><span data-stu-id="67033-109">Make more efficient use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] thread pool by processing the messages asynchronously.</span></span>  

  <span data-ttu-id="67033-110">バッチはアトミック作業単位とは。</span><span class="sxs-lookup"><span data-stu-id="67033-110">A batch is a unit of work that is atomic.</span></span> <span data-ttu-id="67033-111">つまり、か、すべての操作の成功またはすべての操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="67033-111">That is, either all operations in it succeed or all operations in it fail.</span></span> <span data-ttu-id="67033-112">バッチ内の 1 つの操作が成功した場合は、別の操作が失敗したバッチを構成するすべての操作は無効になり、メッセージを再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67033-112">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and the messages must be resubmitted.</span></span> <span data-ttu-id="67033-113">つまり、アダプターが失敗したバッチに対して 3 つの処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="67033-113">This means that an adapter must do three things in response to a failed batch:</span></span>  

- <span data-ttu-id="67033-114">メッセージの失敗を決定します。</span><span class="sxs-lookup"><span data-stu-id="67033-114">Determine which messages failed.</span></span>  

- <span data-ttu-id="67033-115">失敗したメッセージの処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="67033-115">Decide what to do with the failed messages.</span></span>  

- <span data-ttu-id="67033-116">失敗しなかったメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="67033-116">Resubmit the messages that did not fail.</span></span>
