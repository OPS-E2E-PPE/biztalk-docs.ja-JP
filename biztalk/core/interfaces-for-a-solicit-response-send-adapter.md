---
title: 送信アダプターの送信請求応答用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3958629596a11bbfcb6ae109c36ab0237a780542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381869"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a><span data-ttu-id="75f8b-102">送信アダプターの送信請求応答用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="75f8b-102">Interfaces for a Solicit-Response Send Adapter</span></span>
<span data-ttu-id="75f8b-103">送信アダプターが受信サーバーに応答メッセージを送信するアダプターと同じバッチ メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="75f8b-103">Send adapters use the same batch mechanism as receive adapters to submit response messages back into the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75f8b-104">メッセージの処理を非同期的に送信請求-応答アダプターをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="75f8b-104">It is recommended that a solicit-response adapter is process messages asynchronously.</span></span> <span data-ttu-id="75f8b-105">同期的にメッセージの処理、メッセージの重複のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="75f8b-105">If the adapter processes message in a synchronous manner, there is a risk of message duplication.</span></span>  
  
 <span data-ttu-id="75f8b-106">送信請求-応答モードで動作する次のインターフェイスを実装するアダプターの必要性を送信するには。</span><span class="sxs-lookup"><span data-stu-id="75f8b-106">Send adapters need to implement the following interfaces to work in solicit-response mode:</span></span>  
  
- <span data-ttu-id="75f8b-107">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="75f8b-107">**IBTTransport**</span></span>  
  
- <span data-ttu-id="75f8b-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="75f8b-108">**IBaseComponent**</span></span>  
  
- <span data-ttu-id="75f8b-109">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="75f8b-109">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="75f8b-110">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="75f8b-110">**IPersistPropertyBag**</span></span>  
  
- <span data-ttu-id="75f8b-111">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="75f8b-111">**IBTTransmitter**</span></span>  
  
- <span data-ttu-id="75f8b-112">**IBTTransmitterBatch**と**IBTBatchTransmitter** (送信バッチ処理が必要な場合)</span><span class="sxs-lookup"><span data-stu-id="75f8b-112">**IBTTransmitterBatch** and **IBTBatchTransmitter** (if send batching is required)</span></span>  
  
- <span data-ttu-id="75f8b-113">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="75f8b-113">**IBTBatchCallBack**</span></span>  
  
  <span data-ttu-id="75f8b-114">オブジェクトの相互作用するための手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75f8b-114">The steps involved in the object interaction are as follows:</span></span>  
  
1. <span data-ttu-id="75f8b-115">アダプターは、送信請求メッセージを送信した後に戻す応答メッセージを受信送信先のサーバーから。</span><span class="sxs-lookup"><span data-stu-id="75f8b-115">After the adapter sends a solicit message, it receives back a response message from that destination server.</span></span> <span data-ttu-id="75f8b-116">トランスポート プロキシからバッチを取得します。</span><span class="sxs-lookup"><span data-stu-id="75f8b-116">It then obtains a batch from the transport proxy.</span></span>  
  
2. <span data-ttu-id="75f8b-117">アダプターのバッチに呼び出すことによって、応答メッセージを追加する**ibttransportproxy::submitresponsemessage**します。</span><span class="sxs-lookup"><span data-stu-id="75f8b-117">The adapter adds the response message to the batch by calling **IBTTransportProxy::SubmitResponseMessage**.</span></span>  
  
3. <span data-ttu-id="75f8b-118">アダプターが呼び出すことによって、バッチを送信する**ibttransportproxy::done**へのポインターを渡してその**IBTBatchComplete**メッセージング エンジンからコールバック インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="75f8b-118">The adapter submits the batch by calling **IBTTransportProxy::Done** passing in a pointer to its **IBTBatchComplete** interface for the callback from the Messaging Engine.</span></span>  
  
4. <span data-ttu-id="75f8b-119">メッセージング エンジンがアダプターの**ibtbatchcallback::batchcomplete**送信操作の結果を通知するトランスポート プロキシを使用してコールバック メソッド。</span><span class="sxs-lookup"><span data-stu-id="75f8b-119">The Messaging Engine calls the adapter's **IBTBatchCallBack::BatchComplete** callback method using the transport proxy notifying it of the result of submission operation.</span></span>  
  
   <span data-ttu-id="75f8b-120">次の図は、送信アダプターの送信請求-応答の作成に関連するオブジェクトの相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="75f8b-120">The following figure shows the object interactions involved in creating a solicit-response send adapter.</span></span>  
  
   <span data-ttu-id="75f8b-121">![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")</span><span class="sxs-lookup"><span data-stu-id="75f8b-121">![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")</span></span>  
   <span data-ttu-id="75f8b-122">送信請求-応答送信アダプターにおける対話</span><span class="sxs-lookup"><span data-stu-id="75f8b-122">Interaction diagram for a solicit-response send adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f8b-123">参照</span><span class="sxs-lookup"><span data-stu-id="75f8b-123">See Also</span></span>  
 <span data-ttu-id="75f8b-124">[アダプター変数](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="75f8b-124">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="75f8b-125">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="75f8b-125">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="75f8b-126">[インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="75f8b-126">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="75f8b-127">[送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="75f8b-127">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="75f8b-128">[送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="75f8b-128">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="75f8b-129">[同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="75f8b-129">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="75f8b-130">[バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="75f8b-130">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="75f8b-131">バッチ処理に対応したトランザクションとしての非同期送信アダプター用のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="75f8b-131">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)