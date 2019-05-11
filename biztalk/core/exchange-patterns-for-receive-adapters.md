---
title: 受信アダプターの交換パターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e505559e-66be-4c32-a2a8-a242cba10000
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856200bbd511f580f8ef58fd0be78ee1fb6718b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388279"
---
# <a name="exchange-patterns-for-receive-adapters"></a><span data-ttu-id="067e4-102">受信アダプターの交換パターン</span><span class="sxs-lookup"><span data-stu-id="067e4-102">Exchange Patterns for Receive Adapters</span></span>
<span data-ttu-id="067e4-103">受信アダプターで「ネットワーク」からデータを受信およびにメッセージとして送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="067e4-103">Receive adapters receive data from the "wire" and submit it as a message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="067e4-104">この送信プロセスを一方向または双方向メッセージ交換パターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="067e4-104">This submittal process can be a one-way or a two-way message exchange pattern.</span></span>  
  
## <a name="one-way-submit"></a><span data-ttu-id="067e4-105">一方向の送信</span><span class="sxs-lookup"><span data-stu-id="067e4-105">One-Way Submit</span></span>  
 <span data-ttu-id="067e4-106">BizTalk メッセージング エンジンにメッセージを送信する受信アダプターの場合、新しい BizTalk メッセージの作成が必要最初です。</span><span class="sxs-lookup"><span data-stu-id="067e4-106">For a receive adapter to submit a message into the BizTalk Messaging Engine, it first needs to create a new BizTalk message.</span></span> <span data-ttu-id="067e4-107">IBaseMessage のトピックのコード サンプルでは、これを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="067e4-107">The code sample in the IBaseMessage topic shows how this is done.</span></span> <span data-ttu-id="067e4-108">アダプターがメッセージの本文として設定するストリームは、メモリに読み取られていたデータをキャッシュする必要がありますので、順方向専用ストリーム通常はずです。</span><span class="sxs-lookup"><span data-stu-id="067e4-108">The stream that the adapter sets as the message body should typically be a forward-only stream, meaning that it should not cache the data that it has previously read into memory.</span></span>  
  
 <span data-ttu-id="067e4-109">アダプターは、エンジンにメッセージを送信する前に書き込む必要があります、 **InboundTransportLocation**メッセージ コンテキスト プロパティを BizTalk メッセージに、system 名前空間。</span><span class="sxs-lookup"><span data-stu-id="067e4-109">Before the adapter submits the message into the engine, it must write the **InboundTransportLocation** message context property in the system namespace onto the BizTalk message.</span></span> <span data-ttu-id="067e4-110">これは、次のコード フラグメントに示します。</span><span class="sxs-lookup"><span data-stu-id="067e4-110">This is illustrated in the following code fragment:</span></span>  
  
 `Assembly References:`  
  
 `Microsoft.XLANGs.BaseTypes.dll`  
  
 `Microsoft.BizTalk.Pipeline.dll`  
  
 `Microsoft.BizTalk.GlobalPropertySchemas.dll`  
  
```  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.XLANGs.BaseTypes;  
  
private static readonly PropertyBase InboundTransportLocationProp =   
new BTS.InboundTransportLocation();  
  
private void StampMsgCtxProps(  
IBaseMessage msg, string uri, string adapterType)  
{  
msg.Context.Write(  
 InboundTransportLocationProp.Name.Name,   
 InboundTransportLocationProperty.Name.Namespace,   
  uri);  
}  
```  
  
 <span data-ttu-id="067e4-111">さらに、アダプターは、独自のプロパティ スキーマを定義し、メッセージを受信したことをエンドポイントに関連するメッセージ コンテキスト プロパティを書き込むことがあります。</span><span class="sxs-lookup"><span data-stu-id="067e4-111">In addition, the adapter may define its own property schemas and write message context properties pertaining to the endpoint over which it received the message.</span></span> <span data-ttu-id="067e4-112">たとえば、HTTP アダプターが HTTP ヘッダーをメッセージ コンテキストに書き込む可能性があり、SMTP レシーバーは、メッセージ コンテキストにメールの件名を書き込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="067e4-112">For example, an HTTP adapter might write the HTTP headers to the message context, and an SMTP receiver might write the subject of the mail to the message context.</span></span> <span data-ttu-id="067e4-113">この情報は、パイプライン コンポーネントやオーケストレーション スケジュール、送信アダプターなどの下流コンポーネントに役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="067e4-113">This information may be useful to downstream components such as pipeline components, orchestration schedules, or a send adapter.</span></span>  
  
 <span data-ttu-id="067e4-114">メッセージを準備すると後、は、メッセージング エンジンに送信できます。</span><span class="sxs-lookup"><span data-stu-id="067e4-114">After the messages are prepared, they can be submitted into the Messaging Engine.</span></span> <span data-ttu-id="067e4-115">表示する方法を一方向の受信アダプター可能性があります、エンジンにメッセージを送信をコード サンプルを参照して[SubmitDirect (BizTalk Server サンプル)](../core/submitdirect-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="067e4-115">To see how a one-way receive adapter might submit a message into the engine, see the code sample [SubmitDirect (BizTalk Server Sample)](../core/submitdirect-biztalk-server-sample.md).</span></span>  
  
## <a name="request-response"></a><span data-ttu-id="067e4-116">要求-応答</span><span class="sxs-lookup"><span data-stu-id="067e4-116">Request-Response</span></span>  
 <span data-ttu-id="067e4-117">双方向受信アダプターが一方向または双方向で使用される通常の受信ポート。</span><span class="sxs-lookup"><span data-stu-id="067e4-117">Two-way receive adapters are typically used on one-way or two-way receive ports.</span></span> <span data-ttu-id="067e4-118">アダプターでは、サービスを提供して、受信場所が一方向または双方向のポートを調べることによってがかどうかを決定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成プロパティ バッグを指定します。</span><span class="sxs-lookup"><span data-stu-id="067e4-118">The adapter determines whether the receive location it is servicing is a one-way or two-way port by inspecting the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration property bag.</span></span> <span data-ttu-id="067e4-119">このプロセスについては、 **IBTTransportConfig.AddReceiveEndpoint メソッド (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="067e4-119">This process is explained in the **IBTTransportConfig.AddReceiveEndpoint Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="067e4-120">次のオブジェクト相互作用の図は、要求-応答のメッセージ交換を実行するプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="067e4-120">The following object interaction diagram illustrates the process of performing a request-response message exchange.</span></span> <span data-ttu-id="067e4-121">アダプターがトランスポート プロキシから新しいバッチを要求し、自身の参照を渡す、 **IBTTransmitter**インターフェイスを通じて、 **SubmitRequestMessage**メソッド。</span><span class="sxs-lookup"><span data-stu-id="067e4-121">The adapter requests a new batch from the transport proxy and passes in its reference to the **IBTTransmitter** interface through the **SubmitRequestMessage** method.</span></span> <span data-ttu-id="067e4-122">メッセージング エンジンでは、このインターフェイスの応答メッセージを配信を使用して、 **TransmitMessage**メソッド。</span><span class="sxs-lookup"><span data-stu-id="067e4-122">The Messaging Engine delivers the response message on this interface by using the **TransmitMessage** method.</span></span>  
  
 <span data-ttu-id="067e4-123">エンジンはメッセージを非同期的に処理があるために、発生する次のことができます。</span><span class="sxs-lookup"><span data-stu-id="067e4-123">Because the engine is processing messages asynchronously, it is possible for the following to happen:</span></span>  
  
- <span data-ttu-id="067e4-124">**BatchComplete**する前に発生する可能性がコールバック**完了**が返されます。</span><span class="sxs-lookup"><span data-stu-id="067e4-124">The **BatchComplete** callback might occur before **Done** has returned.</span></span>  
  
- <span data-ttu-id="067e4-125">TransmitMessage の呼び出しは BatchComplete 前に行われ、実行前であってもに、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="067e4-125">The call to TransmitMessage might be made before BatchComplete and even before Done.</span></span>  
  
  <span data-ttu-id="067e4-126">これら両方のシナリオはまれですが、アダプターが自身を保護これです。</span><span class="sxs-lookup"><span data-stu-id="067e4-126">While both of these scenarios are rare, the adapter should protect itself against this.</span></span>  
  
  <span data-ttu-id="067e4-127">非同期の非ブロッキング呼び出しを使用して、応答メッセージを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="067e4-127">It is recommended that the response message is transmitted using an asynchronous non-blocking call.</span></span>  
  
  <span data-ttu-id="067e4-128">BaseAdapter プロジェクトには、ユーティリティ クラスが含まれる**StandardRequestResponseHandler**、このトピックで説明されている要求/応答セマンティクスをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="067e4-128">The BaseAdapter project has a utility class, **StandardRequestResponseHandler**, that encapsulates the request-response semantics explained in this topic.</span></span>  
  
## <a name="request-response-message-time-outs"></a><span data-ttu-id="067e4-129">要求-応答メッセージのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="067e4-129">Request-Response Message Time-Outs</span></span>  
 <span data-ttu-id="067e4-130">要求メッセージのタイムアウトを指定する必要がアダプターでは、要求-応答メッセージを送信するときにある、 **IBTTransportBatch.SubmitRequestMessage メソッド (COM)** API[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="067e4-130">When an adapter submits a request-request message, it needs to specify the time-out of the request message on the **IBTTransportBatch.SubmitRequestMessage Method (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="067e4-131">応答メッセージは、このタイムアウト期間内でのみ、アダプターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="067e4-131">A response message will be delivered to the adapter only within this time-out period.</span></span> <span data-ttu-id="067e4-132">タイムアウトに達すると、否定受信確認応答 (NACK) が応答メッセージではなく、アダプターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="067e4-132">After the time-out expires, a negative acknowledgment (NACK) will be delivered to the adapter instead of the response message.</span></span> <span data-ttu-id="067e4-133">アダプターがタイムアウト値を指定しない場合、エンジンは 20 分の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="067e4-133">If the adapter does not specify a time-out value, the engine uses the default value of 20 minutes.</span></span>  
  
 <span data-ttu-id="067e4-134">インプロセス受信アダプター用に次のレジストリ キーを使用して、要求-応答メッセージの既定のタイムアウトを制御できます。</span><span class="sxs-lookup"><span data-stu-id="067e4-134">The default time-out for request-response messages may be controlled by using the following registry key for in-process receive adapters:</span></span>  
  
 <span data-ttu-id="067e4-135">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="067e4-135">**DWORD**</span></span>  
  
 <span data-ttu-id="067e4-136">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**</span><span class="sxs-lookup"><span data-stu-id="067e4-136">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="067e4-137">レジストリ キーを別の場所では、分離受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="067e4-137">The registry key is in a different location for isolated receive adapters:</span></span>  
  
 <span data-ttu-id="067e4-138">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="067e4-138">**DWORD**</span></span>  
  
 <span data-ttu-id="067e4-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span><span class="sxs-lookup"><span data-stu-id="067e4-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="067e4-140">Nack (否定受信確認応答) は SOAP エラーと、それらを処理する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="067e4-140">NACKs (Negative ACKnowledgements) are SOAP faults and there are two ways to handle them.</span></span> <span data-ttu-id="067e4-141">通常、アダプターがクライアントに NACK を返すし、クライアントで NACK を処理します。</span><span class="sxs-lookup"><span data-stu-id="067e4-141">Typically the adapter returns the NACK to the client and the client handles the NACK.</span></span> <span data-ttu-id="067e4-142">または、マップまたはカスタム パイプライン コンポーネントを使用して、応答メッセージの内容を変更する応答メッセージを処理する送信パイプラインを構成することがあります。</span><span class="sxs-lookup"><span data-stu-id="067e4-142">Alternatively the transmit pipeline handling the response message may be configured to change the contents of the response message, by using either a map or a custom pipeline component.</span></span>