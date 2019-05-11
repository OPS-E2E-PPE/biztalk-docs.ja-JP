---
title: 分離アダプターをインスタンス化する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8359a3-b098-4bb6-87b4-d3432d2671b1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89f534ab91f940a179c765fba6f109a9da6df5ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331840"
---
# <a name="instantiating-isolated-adapters"></a><span data-ttu-id="c2fd5-102">分離アダプターをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-102">Instantiating Isolated Adapters</span></span>
<span data-ttu-id="c2fd5-103">既に説明したように、分離アダプタは BizTalk Server によってインスタンス化されません。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-103">As discussed earlier, isolated adapters are not instantiated by BizTalk Server.</span></span> <span data-ttu-id="c2fd5-104">代わりに、インスタンス化されており、別のプロセスでホストされています。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-104">Rather, they are instantiated and hosted in another process.</span></span> <span data-ttu-id="c2fd5-105">そのトランスポート プロキシを作成するアダプターの役割は**QueryInterface**の**IBTTransportProxy**を呼び出して**IBTTransportProxy**.**RegisterIsolatedReceiver**をメッセージング エンジンに登録します。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-105">It is the responsibility of the adapter to create its transport proxy, **QueryInterface**, for **IBTTransportProxy**, and then call **IBTTransportProxy**.**RegisterIsolatedReceiver** to register with the Messaging Engine.</span></span>  
  
 <span data-ttu-id="c2fd5-106">登録するには、アダプターのパスは、いずれか、構成済みで有効になっているが、メッセージング エンジンに場所を受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-106">Registration requires that the adapter pass one of its configured and enabled receive locations to the Messaging Engine.</span></span> <span data-ttu-id="c2fd5-107">アダプターのホスト プロセスの資格情報は、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-107">The adapter's host process credentials must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="c2fd5-108">ユーザーがそのグループのメンバーでない限りは、単に権限借用を使用してここで十分です。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-108">Simply using impersonation here is insufficient unless the user is a member of that group.</span></span> <span data-ttu-id="c2fd5-109">確実に正しいアダプターを照会するさらに、 **ClassID**がそのホスト インスタンス用に構成されたコンピューターで実行されているとします。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-109">In addition, the adapter is queried to ensure it has the correct **ClassID** and is running on the computer that was configured for that host instance.</span></span> <span data-ttu-id="c2fd5-110">アダプターは、そのトランスポート プロキシで登録が正常に、その構成がの Load メソッドを呼び出すことでに送信され、 **IPersistPropertyBag**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-110">After the adapter has successfully registered with its transport proxy, its configuration is sent to it using by calling the Load method of the **IPersistPropertyBag** interface.</span></span>  
  
 <span data-ttu-id="c2fd5-111">次の図は、この一連の API 呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-111">The following figure illustrates this sequence of API calls.</span></span> <span data-ttu-id="c2fd5-112">青で示されるインターフェイスは、アダプターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-112">The interfaces in blue are implemented by the adapter.</span></span>  
  
 <span data-ttu-id="c2fd5-113">![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")</span><span class="sxs-lookup"><span data-stu-id="c2fd5-113">![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")</span></span>  
  
 <span data-ttu-id="c2fd5-114">次のコード フラグメントは、登録 API の呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-114">The following code fragment illustrates the registration API calls:</span></span>  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,   
 IBaseComponent  
{  
...  
private IBTTransportProxy transportProxy;  
  
 public void Register(string uri)  
 {  
 // Create the Transport Proxy...  
 this.transportProxy =   
 (IBTTransportProxy)new BTTransportProxy();  
  
// Register on of the adapters uri’s with the TP  
 this.transportProxy.RegisterIsolatedReceiver(  
 uri,   
 (IBTTransportConfig)this );  
 }  
}  
```  
  
 <span data-ttu-id="c2fd5-115">**実装のヒン ト:** アダプターが進行中の作業の数を保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-115">**Implementation Tip:** We recommend that the adapter keep a count of the work in progress.</span></span> <span data-ttu-id="c2fd5-116">アダプターをブロックする必要があります**Terminate**メッセージ数が 0 に到達するまでです。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-116">The adapter should block **Terminate** until the message count has reached zero.</span></span> <span data-ttu-id="c2fd5-117">受信側では、この作業には、BizTalk Server に発行されていないが、未処理の要求が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-117">On the receive side this work includes any outstanding requests that have not been published to BizTalk Server.</span></span> <span data-ttu-id="c2fd5-118">応答メッセージは後に受信アダプターに配信されません**Terminate**が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-118">Response messages are not delivered to a receive adapter after **Terminate** has been called.</span></span>  
  
 <span data-ttu-id="c2fd5-119">送信アダプターの場合は、進行中のメッセージを適切に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-119">For send adapters, messages that are in progress should be handled appropriately.</span></span> <span data-ttu-id="c2fd5-120">つまりが正常に配信されたメッセージは、メッセージが複数回送信されていることを防ぐために、アダプターのプライベート アプリケーション メッセージ キューから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-120">This means any message that was successfully delivered should be deleted from the adapter's private application message queue to prevent messages from being sent more than once.</span></span>  
  
 <span data-ttu-id="c2fd5-121">後**Terminate**と呼ばれますが、メッセージング エンジンでは、送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを発行する要求は受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="c2fd5-121">After **Terminate** is called the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>