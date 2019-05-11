---
title: 受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5289e8b8-4447-4196-9f7c-5e60c6598d8d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f46c7662fac5010c4f1effe56016fe2f5c5d5e8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331556"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a><span data-ttu-id="49aab-102">バッチ処理に対応したトランザクション受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="49aab-102">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>
<span data-ttu-id="49aab-103">受信アダプターは、作成し、メッセージのトランザクション送信が必要な場合は、トランザクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="49aab-103">A receive adapter creates and controls transactions when the transactional submission of messages is required.</span></span>  
  
 <span data-ttu-id="49aab-104">トランザクション受信アダプターは、作成し、Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションへのポインターを渡します、**完了**のメソッド、 **IBTTransportBatch**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="49aab-104">A transactional receive adapter creates and passes a pointer to a Microsoft Distributed Transaction Coordinator (MSDTC) transaction on the **Done** method of the **IBTTransportBatch** interface.</span></span> <span data-ttu-id="49aab-105">これにより、すべてのバッチ操作は、その特定のトランザクション オブジェクトのスコープ内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="49aab-105">This ensures that all batch operations are performed in the scope of that specific transaction object.</span></span> <span data-ttu-id="49aab-106">バッチ送信が完了したら、アダプターのコールバック メソッドがコミットまたはトランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="49aab-106">When the batch submission completes, the adapter callback method commits or rolls back the transaction.</span></span> <span data-ttu-id="49aab-107">トランスポート プロキシから返されたかかるアクション、状態によって異なります、可能性がある他のトランザクション関連の作業時に、アダプターは表示されませんをトランスポート プロキシ。</span><span class="sxs-lookup"><span data-stu-id="49aab-107">Which action it takes depends upon the status returned from the transport proxy, and possibly upon other transaction-related work that the adapter does that is not visible to the transport proxy.</span></span> <span data-ttu-id="49aab-108">アダプターは、トランザクションが失敗または成功したかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="49aab-108">The adapter determines whether the transaction failed or succeeded.</span></span> <span data-ttu-id="49aab-109">アダプター (コミットまたはロールバック) トランザクションの結果に報告、トランスポート プロキシを使用して、 **DTCCommitConfirm**のメソッド、**IBTDTCCommitConfirm**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="49aab-109">The adapter reports the result of the transaction (commit or rollback) back to the transport proxy by using the **DTCCommitConfirm** method of the**IBTDTCCommitConfirm** interface.</span></span> <span data-ttu-id="49aab-110">渡します`true`成功したトランザクションのまたは`false`エラー。</span><span class="sxs-lookup"><span data-stu-id="49aab-110">It passes in `true` for a successful transaction or `false` for a failure.</span></span>  
  
 <span data-ttu-id="49aab-111">次の図は、受信アダプターのバッチでサポートされているトランザクションの作成に関連するオブジェクトの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="49aab-111">The following figure shows the object interactions involved in creating a transactional batch-supported receive adapter.</span></span>  
  
 <span data-ttu-id="49aab-112">![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")</span><span class="sxs-lookup"><span data-stu-id="49aab-112">![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")</span></span>  
<span data-ttu-id="49aab-113">DTC トランザクションを使用してメッセージのバッチを送信する受信アダプターのワークフロー</span><span class="sxs-lookup"><span data-stu-id="49aab-113">Workflow for a receive adapter submitting a batch of messages using DTC transactions</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49aab-114">参照</span><span class="sxs-lookup"><span data-stu-id="49aab-114">See Also</span></span>  
 <span data-ttu-id="49aab-115">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="49aab-115">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="49aab-116">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="49aab-116">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="49aab-117">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="49aab-117">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="49aab-118">[受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="49aab-118">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="49aab-119">[インターフェイスの分離受信アダプター](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="49aab-119">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="49aab-120">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="49aab-120">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="49aab-121">要求 - 応答の同期受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="49aab-121">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)