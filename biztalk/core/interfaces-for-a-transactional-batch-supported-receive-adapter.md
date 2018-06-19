---
title: 受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 27b51a67f63f3088ce64c9db35c368289ce156d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257578"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a><span data-ttu-id="0e5e8-102">バッチ処理に対応したトランザクション受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e5e8-102">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>
<span data-ttu-id="0e5e8-103">メッセージのトランザクション送信が必要な場合、受信アダプターはトランザクションを作成して制御します。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-103">A receive adapter creates and controls transactions when the transactional submission of messages is required.</span></span>  
  
 <span data-ttu-id="0e5e8-104">トランザクション受信アダプターを作成し、上の Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションにポインターを渡します、**完了**のメソッド、 **IBTTransportBatch**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-104">A transactional receive adapter creates and passes a pointer to a Microsoft Distributed Transaction Coordinator (MSDTC) transaction on the **Done** method of the **IBTTransportBatch** interface.</span></span> <span data-ttu-id="0e5e8-105">これにより、すべてのバッチ操作がその特定のトランザクション オブジェクトのスコープ内で実行されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-105">This ensures that all batch operations are performed in the scope of that specific transaction object.</span></span> <span data-ttu-id="0e5e8-106">バッチ送信が完了すると、アダプターのコールバック メソッドがトランザクションをコミットまたはロールバックします。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-106">When the batch submission completes, the adapter callback method commits or rolls back the transaction.</span></span> <span data-ttu-id="0e5e8-107">どちらのアクションを実行するかは、トランスポート プロキシから返されるステータス、および場合によっては、アダプターが実行する、トランスポート プロキシには認識されない他のトランザクション関連処理によって決まります。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-107">Which action it takes depends upon the status returned from the transport proxy, and possibly upon other transaction-related work that the adapter does that is not visible to the transport proxy.</span></span> <span data-ttu-id="0e5e8-108">アダプターは、トランザクションの失敗または成功を判断します。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-108">The adapter determines whether the transaction failed or succeeded.</span></span> <span data-ttu-id="0e5e8-109">アダプター (コミットまたはロールバック) トランザクションの結果に報告、トランスポート プロキシを使用して、 **DTCCommitConfirm**のメソッド、**IBTDTCCommitConfirm**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-109">The adapter reports the result of the transaction (commit or rollback) back to the transport proxy by using the **DTCCommitConfirm** method of the**IBTDTCCommitConfirm** interface.</span></span> <span data-ttu-id="0e5e8-110">トランザクションが成功した場合は `true` を渡し、失敗した場合は `false` を渡します。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-110">It passes in `true` for a successful transaction or `false` for a failure.</span></span>  
  
 <span data-ttu-id="0e5e8-111">バッチ処理に対応したトランザクション受信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0e5e8-111">The following figure shows the object interactions involved in creating a transactional batch-supported receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")  
<span data-ttu-id="0e5e8-112">DTC トランザクションを使用してメッセージのバッチを送信する受信アダプターのワークフロー</span><span class="sxs-lookup"><span data-stu-id="0e5e8-112">Workflow for a receive adapter submitting a batch of messages using DTC transactions</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5e8-113">参照</span><span class="sxs-lookup"><span data-stu-id="0e5e8-113">See Also</span></span>  
 <span data-ttu-id="0e5e8-114">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="0e5e8-114">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="0e5e8-115">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0e5e8-115">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="0e5e8-116">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0e5e8-116">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="0e5e8-117">[受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0e5e8-117">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="0e5e8-118">[受信アダプターの分離用のインターフェイス](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0e5e8-118">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="0e5e8-119">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0e5e8-119">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="0e5e8-120">アダプターの受信要求-応答の同期用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e5e8-120">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)