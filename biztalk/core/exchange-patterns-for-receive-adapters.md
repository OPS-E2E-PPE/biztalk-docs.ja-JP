---
title: "受信アダプターの交換パターンの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e505559e-66be-4c32-a2a8-a242cba10000
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cf8f36bb128d82a6d6b2e143320f89408f26680
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exchange-patterns-for-receive-adapters"></a><span data-ttu-id="e7108-102">受信アダプターの交換パターン</span><span class="sxs-lookup"><span data-stu-id="e7108-102">Exchange Patterns for Receive Adapters</span></span>
<span data-ttu-id="e7108-103">受信アダプターは、外部からデータを受信し、これをメッセージとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信します。</span><span class="sxs-lookup"><span data-stu-id="e7108-103">Receive adapters receive data from the "wire" and submit it as a message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e7108-104">この送信プロセスには、一方向または双方向のメッセージ交換パターンが可能です。</span><span class="sxs-lookup"><span data-stu-id="e7108-104">This submittal process can be a one-way or a two-way message exchange pattern.</span></span>  
  
## <a name="one-way-submit"></a><span data-ttu-id="e7108-105">一方向の送信</span><span class="sxs-lookup"><span data-stu-id="e7108-105">One-Way Submit</span></span>  
 <span data-ttu-id="e7108-106">受信アダプターから BizTalk メッセージング エンジンにメッセージを送信するには、まず受信アダプターで新しい BizTalk メッセージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7108-106">For a receive adapter to submit a message into the BizTalk Messaging Engine, it first needs to create a new BizTalk message.</span></span> <span data-ttu-id="e7108-107">IBaseMessage のトピックのコード例では、この方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e7108-107">The code sample in the IBaseMessage topic shows how this is done.</span></span> <span data-ttu-id="e7108-108">アダプターがメッセージ本文として設定するストリームは通常、順方向専用のストリームである必要があります。つまり、このストリームで以前メモリに読み込んだデータを、再度ストリームにキャッシュすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e7108-108">The stream that the adapter sets as the message body should typically be a forward-only stream, meaning that it should not cache the data that it has previously read into memory.</span></span>  
  
 <span data-ttu-id="e7108-109">書き込む必要がありますが、アダプターは、エンジンにメッセージを送信する前に、 **InboundTransportLocation**メッセージ コンテキスト プロパティを BizTalk メッセージに system 名前空間。</span><span class="sxs-lookup"><span data-stu-id="e7108-109">Before the adapter submits the message into the engine, it must write the **InboundTransportLocation** message context property in the system namespace onto the BizTalk message.</span></span> <span data-ttu-id="e7108-110">次のコードはこの処理を示すものです。</span><span class="sxs-lookup"><span data-stu-id="e7108-110">This is illustrated in the following code fragment:</span></span>  
  
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
  
 <span data-ttu-id="e7108-111">アダプターではさらに、独自のプロパティ スキーマを定義して、メッセージを受信したエンドポイントのメッセージ コンテキスト プロパティを書き込む場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e7108-111">In addition, the adapter may define its own property schemas and write message context properties pertaining to the endpoint over which it received the message.</span></span> <span data-ttu-id="e7108-112">たとえば、HTTP アダプターではメッセージ コンテキストに HTTP ヘッダーを書き込む場合があり、SMTP レシーバーではメッセージ コンテキストにメールの件名を書き込む場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7108-112">For example, an HTTP adapter might write the HTTP headers to the message context, and an SMTP receiver might write the subject of the mail to the message context.</span></span> <span data-ttu-id="e7108-113">この情報は、パイプライン コンポーネント、オーケストレーション スケジュール、送信アダプターなどの下流コンポーネントで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7108-113">This information may be useful to downstream components such as pipeline components, orchestration schedules, or a send adapter.</span></span>  
  
 <span data-ttu-id="e7108-114">メッセージを作成したら、メッセージング エンジンに送信できます。</span><span class="sxs-lookup"><span data-stu-id="e7108-114">After the messages are prepared, they can be submitted into the Messaging Engine.</span></span> <span data-ttu-id="e7108-115">どの一方向の受信アダプターを表示する場合があります、エンジンにメッセージを送信、コード サンプルを参照して[SubmitDirect (BizTalk Server サンプル)](../core/submitdirect-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7108-115">To see how a one-way receive adapter might submit a message into the engine, see the code sample [SubmitDirect (BizTalk Server Sample)](../core/submitdirect-biztalk-server-sample.md).</span></span>  
  
## <a name="request-response"></a><span data-ttu-id="e7108-116">要求-応答</span><span class="sxs-lookup"><span data-stu-id="e7108-116">Request-Response</span></span>  
 <span data-ttu-id="e7108-117">通常、双方向の受信アダプターは、一方向または双方向の受信ポートで使用します。</span><span class="sxs-lookup"><span data-stu-id="e7108-117">Two-way receive adapters are typically used on one-way or two-way receive ports.</span></span> <span data-ttu-id="e7108-118">このアダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成プロパティ バッグを調べて、サービスを提供する受信場所が一方向と双方向のどちらのポートであるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e7108-118">The adapter determines whether the receive location it is servicing is a one-way or two-way port by inspecting the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration property bag.</span></span> <span data-ttu-id="e7108-119">このプロセスは」で説明されて、 **IBTTransportConfig.AddReceiveEndpoint メソッド (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e7108-119">This process is explained in the **IBTTransportConfig.AddReceiveEndpoint Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="e7108-120">下の図に、オブジェクト間の対話処理における要求 - 応答のメッセージ交換の実行手順を示します。</span><span class="sxs-lookup"><span data-stu-id="e7108-120">The following object interaction diagram illustrates the process of performing a request-response message exchange.</span></span> <span data-ttu-id="e7108-121">アダプターは、トランスポート プロキシから新しいバッチを要求しへの参照を渡します、 **IBTTransmitter**によってインターフェイスを**SubmitRequestMessage**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e7108-121">The adapter requests a new batch from the transport proxy and passes in its reference to the **IBTTransmitter** interface through the **SubmitRequestMessage** method.</span></span> <span data-ttu-id="e7108-122">メッセージング エンジンでは、このインターフェイスの応答メッセージを配信を使用して、 **TransmitMessage**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e7108-122">The Messaging Engine delivers the response message on this interface by using the **TransmitMessage** method.</span></span>  
  
 <span data-ttu-id="e7108-123">メッセージング エンジンはメッセージを非同期的に処理します。したがって、次の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7108-123">Because the engine is processing messages asynchronously, it is possible for the following to happen:</span></span>  
  
-   <span data-ttu-id="e7108-124">**BatchComplete**する前に発生する可能性がコールバック**完了**が返されました。</span><span class="sxs-lookup"><span data-stu-id="e7108-124">The **BatchComplete** callback might occur before **Done** has returned.</span></span>  
  
-   <span data-ttu-id="e7108-125">TransmitMessage の呼び出しが、BatchComplete や、場合によっては Done より前に行われる。</span><span class="sxs-lookup"><span data-stu-id="e7108-125">The call to TransmitMessage might be made before BatchComplete and even before Done.</span></span>  
  
 <span data-ttu-id="e7108-126">どちらも発生の可能性は低いものですが、アダプターではこのような問題への対策を用意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7108-126">While both of these scenarios are rare, the adapter should protect itself against this.</span></span>  
  
 <span data-ttu-id="e7108-127">応答メッセージは、非同期の非ブロッキング呼び出しを使用して送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7108-127">It is recommended that the response message is transmitted using an asynchronous non-blocking call.</span></span>  
  
 <span data-ttu-id="e7108-128">BaseAdapter プロジェクトでは、ユーティリティ クラス**StandardRequestResponseHandler**、このトピックで説明されている要求-応答のセマンティクスをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="e7108-128">The BaseAdapter project has a utility class, **StandardRequestResponseHandler**, that encapsulates the request-response semantics explained in this topic.</span></span>  
  
## <a name="request-response-message-time-outs"></a><span data-ttu-id="e7108-129">要求 - 応答メッセージのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="e7108-129">Request-Response Message Time-Outs</span></span>  
 <span data-ttu-id="e7108-130">アダプターは、要求-応答メッセージを送信するときに、要求メッセージのタイムアウトを指定する必要があります、 **IBTTransportBatch.SubmitRequestMessage メソッド (COM)** API[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e7108-130">When an adapter submits a request-request message, it needs to specify the time-out of the request message on the **IBTTransportBatch.SubmitRequestMessage Method (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="e7108-131">指定したタイムアウトまでの間は応答メッセージが配信され、</span><span class="sxs-lookup"><span data-stu-id="e7108-131">A response message will be delivered to the adapter only within this time-out period.</span></span> <span data-ttu-id="e7108-132">タイムアウトに達すると、応答メッセージの代わりに否定受信確認応答 (NACK) がアダプターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="e7108-132">After the time-out expires, a negative acknowledgment (NACK) will be delivered to the adapter instead of the response message.</span></span> <span data-ttu-id="e7108-133">アダプターでタイムアウト値を指定していない場合、エンジンでは既定値の 20 分が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7108-133">If the adapter does not specify a time-out value, the engine uses the default value of 20 minutes.</span></span>  
  
 <span data-ttu-id="e7108-134">要求 - 応答メッセージのタイムアウトの既定値は、レジストリ キーを使用して設定できます。インプロセス受信アダプター用のレジストリ キーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="e7108-134">The default time-out for request-response messages may be controlled by using the following registry key for in-process receive adapters:</span></span>  
  
 <span data-ttu-id="e7108-135">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="e7108-135">**DWORD**</span></span>  
  
 <span data-ttu-id="e7108-136">**Hkey_local_machine \system\currentcontrolset\services\btssvc {guid} ホスト \MessagingReqRespTTL**</span><span class="sxs-lookup"><span data-stu-id="e7108-136">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="e7108-137">分離受信アダプター用のレジストリ キーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="e7108-137">The registry key is in a different location for isolated receive adapters:</span></span>  
  
 <span data-ttu-id="e7108-138">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="e7108-138">**DWORD**</span></span>  
  
 <span data-ttu-id="e7108-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span><span class="sxs-lookup"><span data-stu-id="e7108-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="e7108-140">NACK (否定受信確認応答) は SOAP エラーとなります。これは 2 つの方法で処理できます。</span><span class="sxs-lookup"><span data-stu-id="e7108-140">NACKs (Negative ACKnowledgements) are SOAP faults and there are two ways to handle them.</span></span> <span data-ttu-id="e7108-141">通常は、アダプターからクライアントに NACK を返し、クライアントで NACK を処理します。</span><span class="sxs-lookup"><span data-stu-id="e7108-141">Typically the adapter returns the NACK to the client and the client handles the NACK.</span></span> <span data-ttu-id="e7108-142">または、応答メッセージを処理する送信パイプラインで、マップまたはカスタム パイプライン コンポーネントを使用して、応答メッセージのコンテンツを変更するよう構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7108-142">Alternatively the transmit pipeline handling the response message may be configured to change the contents of the response message, by using either a map or a custom pipeline component.</span></span>