---
title: 受信アダプターの要求-応答の同期用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c60832-52b5-4d2c-81ec-94c46c375b15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcf63c64298c40152f0b7f01c764f514fde6f37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382001"
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a><span data-ttu-id="6d08d-102">要求 - 応答の同期受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d08d-102">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>
<span data-ttu-id="6d08d-103">すべての受信要求-応答モードで動作する次のインターフェイスを実装するためにアダプターが必要。</span><span class="sxs-lookup"><span data-stu-id="6d08d-103">All receive adapters need to implement the following interfaces to work in request-response mode:</span></span>  
  
- <span data-ttu-id="6d08d-104">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="6d08d-104">**IBTTransport**</span></span>  
  
- <span data-ttu-id="6d08d-105">**IBTTransportControl** (標準アダプターのみ)</span><span class="sxs-lookup"><span data-stu-id="6d08d-105">**IBTTransportControl** (regular adapters only)</span></span>  
  
- <span data-ttu-id="6d08d-106">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="6d08d-106">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="6d08d-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="6d08d-107">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="6d08d-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="6d08d-108">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="6d08d-109">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="6d08d-109">**IBTBatchCallBack**</span></span>  
  
- <span data-ttu-id="6d08d-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="6d08d-110">**IBTTransmitter**</span></span>  
  
  <span data-ttu-id="6d08d-111">要求-応答プロトコルをサポートする受信アダプター (たとえば、HTTP 受信アダプター) の要求メッセージを送信するときに、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d08d-111">Receive adapters that support request-response protocols (for example, the HTTP receive adapter) perform the following actions when submitting request messages:</span></span>  
  
1. <span data-ttu-id="6d08d-112">受信アダプターでは、着信要求メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6d08d-112">The receive adapter receives incoming request messages.</span></span> <span data-ttu-id="6d08d-113">呼び出すことによって、トランスポート プロキシからバッチを取得、 **GetBatch**のメソッド、 **IBTTransportProxy**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6d08d-113">It obtains a batch from the transport proxy by calling the **GetBatch** method of the **IBTTransportProxy** interface.</span></span> <span data-ttu-id="6d08d-114">この呼び出しで渡しますコールバック ポインターの実装に、 **IBTBatchCallBack.BatchComplete**メソッド。</span><span class="sxs-lookup"><span data-stu-id="6d08d-114">In this call the adapter passes in a callback pointer to its implementation of the **IBTBatchCallBack.BatchComplete** method.</span></span>  
  
2. <span data-ttu-id="6d08d-115">アダプターがバッチに呼び出すことで要求メッセージを追加、 **SubmitRequestMessage**のメソッド、 **IBTTransportBatch**各要求メッセージに対して 1 回のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6d08d-115">The adapter adds request messages into the batch by calling the **SubmitRequestMessage** method of the **IBTTransportBatch** interface, once for each request message.</span></span>  
  
3. <span data-ttu-id="6d08d-116">アダプターが呼び出すすべてのメッセージが追加されたときに、**完了**のメソッド、 **IBTTransportBatch**インターフェイスで、トランスポート プロキシを経由してメッセージング エンジンにバッチが送信されます。</span><span class="sxs-lookup"><span data-stu-id="6d08d-116">When all the messages have been added, the adapter calls the **Done**method of the **IBTTransportBatch** interface, which submits the batch to the Messaging Engine through the transport proxy.</span></span>  
  
4. <span data-ttu-id="6d08d-117">メッセージング エンジンがアダプターを呼び出すバッチが処理された後**IBTBatchCallBack.BatchComplete**トランスポート プロキシを使用してコールバック メソッド。</span><span class="sxs-lookup"><span data-stu-id="6d08d-117">After the batch has been processed, the Messaging Engine invokes the adapter's **IBTBatchCallBack.BatchComplete** callback method through the transport proxy.</span></span> <span data-ttu-id="6d08d-118">送信の状態は、バッチ内の各メッセージに対応する HRESULT 値の配列としてアダプターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6d08d-118">The status of the submission is passed to the adapter as an array of HRESULT values corresponding to each message in the batch.</span></span> <span data-ttu-id="6d08d-119">パイプラインまたはオーケストレーションでバッチが失敗した場合は、応答としてアダプターに SOAP エラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="6d08d-119">If the batch fails, either in the pipeline or in the orchestration, the SOAP fault message is returned to the adapter as a response.</span></span>  
  
5. <span data-ttu-id="6d08d-120">受信要求メッセージには、オーケストレーションのサブスクライバーがあります。</span><span class="sxs-lookup"><span data-stu-id="6d08d-120">The incoming request messages may have orchestration subscribers.</span></span> <span data-ttu-id="6d08d-121">呼び出して、アダプターに、メッセージング エンジンがアダプターにトランスポート プロキシを経由の応答メッセージを送信、オーケストレーションが完了するし、要求メッセージが処理された、 **TransmitMessage** からメソッド**IBTTransmitter**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6d08d-121">After the orchestration completes and the request message has been processed, the Messaging Engine sends the response message through the transport proxy to the adapter by calling the adapter's **TransmitMessage** method from the **IBTTransmitter** interface.</span></span>  
  
6. <span data-ttu-id="6d08d-122">アダプターは、応答メッセージを送信し、元のメッセージをメッセージ ボックス データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="6d08d-122">The adapter sends a response message and deletes the original message from the MessageBox database.</span></span>  
  
   <span data-ttu-id="6d08d-123">次の図は、受信アダプターの同期要求-応答の作成に関連するオブジェクトの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d08d-123">The following figure shows the object interactions involved in creating a synchronous request-response receive adapter.</span></span>  
  
   <span data-ttu-id="6d08d-124">![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")</span><span class="sxs-lookup"><span data-stu-id="6d08d-124">![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")</span></span>  
   <span data-ttu-id="6d08d-125">同期メッセージを送信する受信アダプターのワークフロー</span><span class="sxs-lookup"><span data-stu-id="6d08d-125">Workflow for a receive adapter submitting a synchronous message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d08d-126">参照</span><span class="sxs-lookup"><span data-stu-id="6d08d-126">See Also</span></span>  
 <span data-ttu-id="6d08d-127">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6d08d-127">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="6d08d-128">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6d08d-128">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="6d08d-129">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6d08d-129">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="6d08d-130">[受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6d08d-130">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="6d08d-131">[インターフェイスの分離受信アダプター](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6d08d-131">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="6d08d-132">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6d08d-132">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="6d08d-133">バッチ処理に対応したトランザクション受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d08d-133">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)