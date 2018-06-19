---
title: アダプターの受信要求-応答の同期用のインターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 9abd84bab5da623c2dff61c6e07a5898110588af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257810"
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a><span data-ttu-id="2a8c6-102">要求 - 応答の同期受信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a8c6-102">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>
<span data-ttu-id="2a8c6-103">すべての受信アダプターが要求 - 応答モードで動作するには、アダプターに次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-103">All receive adapters need to implement the following interfaces to work in request-response mode:</span></span>  
  
-   <span data-ttu-id="2a8c6-104">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="2a8c6-104">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="2a8c6-105">**IBTTransportControl** (標準アダプターのみ)</span><span class="sxs-lookup"><span data-stu-id="2a8c6-105">**IBTTransportControl** (regular adapters only)</span></span>  
  
-   <span data-ttu-id="2a8c6-106">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="2a8c6-106">**IBTTransportConfig**</span></span>  
  
-   <span data-ttu-id="2a8c6-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="2a8c6-107">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="2a8c6-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="2a8c6-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="2a8c6-109">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="2a8c6-109">**IBTBatchCallBack**</span></span>  
  
-   <span data-ttu-id="2a8c6-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="2a8c6-110">**IBTTransmitter**</span></span>  
  
 <span data-ttu-id="2a8c6-111">要求 - 応答プロトコルをサポートする受信アダプター (HTTP 受信アダプターなど) は、要求メッセージの送信時に、次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-111">Receive adapters that support request-response protocols (for example, the HTTP receive adapter) perform the following actions when submitting request messages:</span></span>  
  
1.  <span data-ttu-id="2a8c6-112">受信アダプターが、受信要求メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-112">The receive adapter receives incoming request messages.</span></span> <span data-ttu-id="2a8c6-113">呼び出して、トランスポート プロキシからバッチを取得、 **GetBatch**のメソッド、 **IBTTransportProxy**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-113">It obtains a batch from the transport proxy by calling the **GetBatch** method of the **IBTTransportProxy** interface.</span></span> <span data-ttu-id="2a8c6-114">この呼び出しで、アダプターはでコールバック ポインターに渡すの実装、 **IBTBatchCallBack.BatchComplete**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-114">In this call the adapter passes in a callback pointer to its implementation of the **IBTBatchCallBack.BatchComplete** method.</span></span>  
  
2.  <span data-ttu-id="2a8c6-115">呼び出して、アダプターがバッチに要求メッセージを追加、 **SubmitRequestMessage**のメソッド、 **IBTTransportBatch**要求メッセージごとに 1 回のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-115">The adapter adds request messages into the batch by calling the **SubmitRequestMessage** method of the **IBTTransportBatch** interface, once for each request message.</span></span>  
  
3.  <span data-ttu-id="2a8c6-116">アダプターが呼び出すすべてのメッセージが追加されると、**完了**のメソッド、 **IBTTransportBatch**インターフェイスで、トランスポート プロキシを経由してメッセージング エンジンにバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-116">When all the messages have been added, the adapter calls the **Done**method of the **IBTTransportBatch** interface, which submits the batch to the Messaging Engine through the transport proxy.</span></span>  
  
4.  <span data-ttu-id="2a8c6-117">メッセージング エンジンがアダプターを呼び出すバッチが処理された後**IBTBatchCallBack.BatchComplete**コールバック メソッドは、トランスポート プロキシを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-117">After the batch has been processed, the Messaging Engine invokes the adapter's **IBTBatchCallBack.BatchComplete** callback method through the transport proxy.</span></span> <span data-ttu-id="2a8c6-118">送信の状態が、バッチの各メッセージに対応する HRESULT 値の配列として、アダプターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-118">The status of the submission is passed to the adapter as an array of HRESULT values corresponding to each message in the batch.</span></span> <span data-ttu-id="2a8c6-119">パイプラインまたはオーケストレーションでバッチが失敗すると、SOAP エラー メッセージが応答としてアダプターに返されます。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-119">If the batch fails, either in the pipeline or in the orchestration, the SOAP fault message is returned to the adapter as a response.</span></span>  
  
5.  <span data-ttu-id="2a8c6-120">受信要求メッセージには、オーケストレーションのサブスクライバーが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-120">The incoming request messages may have orchestration subscribers.</span></span> <span data-ttu-id="2a8c6-121">呼び出して、アダプターに、メッセージング エンジンがアダプターにトランスポート プロキシを経由応答メッセージを送信、オーケストレーションが完了するし、要求メッセージが処理されて、 **TransmitMessage** からメソッド**IBTTransmitter**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-121">After the orchestration completes and the request message has been processed, the Messaging Engine sends the response message through the transport proxy to the adapter by calling the adapter's **TransmitMessage** method from the **IBTTransmitter** interface.</span></span>  
  
6.  <span data-ttu-id="2a8c6-122">アダプターは応答メッセージを送信し、元のメッセージをメッセージ ボックス データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-122">The adapter sends a response message and deletes the original message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="2a8c6-123">要求 - 応答の同期受信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a8c6-123">The following figure shows the object interactions involved in creating a synchronous request-response receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")  
<span data-ttu-id="2a8c6-124">同期メッセージを送信する受信アダプターのワークフロー</span><span class="sxs-lookup"><span data-stu-id="2a8c6-124">Workflow for a receive adapter submitting a synchronous message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a8c6-125">参照</span><span class="sxs-lookup"><span data-stu-id="2a8c6-125">See Also</span></span>  
 <span data-ttu-id="2a8c6-126">[アダプタの変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c6-126">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="2a8c6-127">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c6-127">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="2a8c6-128">[インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c6-128">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="2a8c6-129">[受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c6-129">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="2a8c6-130">[受信アダプターの分離用のインターフェイス](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c6-130">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="2a8c6-131">[受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2a8c6-131">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="2a8c6-132">受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a8c6-132">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)