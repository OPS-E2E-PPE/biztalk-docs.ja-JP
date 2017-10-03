---
title: "分離アダプターをインスタンス化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8359a3-b098-4bb6-87b4-d3432d2671b1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e3090252f63221547604a4fdf88388bcbf8296f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-isolated-adapters"></a><span data-ttu-id="70604-102">分離アダプターのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="70604-102">Instantiating Isolated Adapters</span></span>
<span data-ttu-id="70604-103">分離アダプターは BizTalk Server によってインスタンス化されません。</span><span class="sxs-lookup"><span data-stu-id="70604-103">As discussed earlier, isolated adapters are not instantiated by BizTalk Server.</span></span> <span data-ttu-id="70604-104">代わりに、別のプロセスでインスタンス化され、ホストされます。</span><span class="sxs-lookup"><span data-stu-id="70604-104">Rather, they are instantiated and hosted in another process.</span></span> <span data-ttu-id="70604-105">トランスポート プロキシを作成するアダプターの責任**QueryInterface**の**IBTTransportProxy**、およびを呼び出す**IBTTransportProxy**.**RegisterIsolatedReceiver**メッセージング エンジンに登録します。</span><span class="sxs-lookup"><span data-stu-id="70604-105">It is the responsibility of the adapter to create its transport proxy, **QueryInterface**, for **IBTTransportProxy**, and then call **IBTTransportProxy**.**RegisterIsolatedReceiver** to register with the Messaging Engine.</span></span>  
  
 <span data-ttu-id="70604-106">登録には、構成済みで有効になっている受信場所の 1 つをアダプターからメッセージ エンジンに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="70604-106">Registration requires that the adapter pass one of its configured and enabled receive locations to the Messaging Engine.</span></span> <span data-ttu-id="70604-107">アダプターのホスト プロセスの資格情報は、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="70604-107">The adapter's host process credentials must be a member of the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="70604-108">ここで単に権限借用を使用しても、ユーザーがそのグループのメンバーでなければ不十分です。</span><span class="sxs-lookup"><span data-stu-id="70604-108">Simply using impersonation here is insufficient unless the user is a member of that group.</span></span> <span data-ttu-id="70604-109">アダプターのクエリが実行が正しいことを確認するさらに、 **ClassID**がそのホスト インスタンス用に構成されたコンピューターで実行されているとします。</span><span class="sxs-lookup"><span data-stu-id="70604-109">In addition, the adapter is queried to ensure it has the correct **ClassID** and is running on the computer that was configured for that host instance.</span></span> <span data-ttu-id="70604-110">Load メソッドを呼び出すことによりを使用してその構成が送信アダプターがそのトランスポート プロキシで正常に登録された後、 **IPersistPropertyBag**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="70604-110">After the adapter has successfully registered with its transport proxy, its configuration is sent to it using by calling the Load method of the **IPersistPropertyBag** interface.</span></span>  
  
 <span data-ttu-id="70604-111">この API 呼び出しの順序は、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="70604-111">The following figure illustrates this sequence of API calls.</span></span> <span data-ttu-id="70604-112">アダプターは、青色で示されるインターフェイスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="70604-112">The interfaces in blue are implemented by the adapter.</span></span>  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 <span data-ttu-id="70604-113">次のコードは、登録 API の呼び出し方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="70604-113">The following code fragment illustrates the registration API calls:</span></span>  
  
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
  
 <span data-ttu-id="70604-114">**実装のヒン ト:**アダプターが進行中の作業の数を記録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70604-114">**Implementation Tip:** We recommend that the adapter keep a count of the work in progress.</span></span> <span data-ttu-id="70604-115">アダプターはブロック**Terminate**メッセージの数が 0 に到達するまでです。</span><span class="sxs-lookup"><span data-stu-id="70604-115">The adapter should block **Terminate** until the message count has reached zero.</span></span> <span data-ttu-id="70604-116">受信側では、BizTalk Server に対して公開されていない未処理の要求がこの作業に含まれます。</span><span class="sxs-lookup"><span data-stu-id="70604-116">On the receive side this work includes any outstanding requests that have not been published to BizTalk Server.</span></span> <span data-ttu-id="70604-117">後に受信アダプターに応答メッセージは配信されません**Terminate**が呼び出されています。</span><span class="sxs-lookup"><span data-stu-id="70604-117">Response messages are not delivered to a receive adapter after **Terminate** has been called.</span></span>  
  
 <span data-ttu-id="70604-118">送信アダプターでは、処理中のメッセージが適切に処理される必要があります。</span><span class="sxs-lookup"><span data-stu-id="70604-118">For send adapters, messages that are in progress should be handled appropriately.</span></span> <span data-ttu-id="70604-119">つまり、正常に配信されたメッセージをアダプターのプライベート アプリケーション メッセージ キューから削除して、メッセージが 2 回以上送信されるのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="70604-119">This means any message that was successfully delivered should be deleted from the adapter's private application message queue to prevent messages from being sent more than once.</span></span>  
  
 <span data-ttu-id="70604-120">後**Terminate**と呼ばれますが、メッセージング エンジンでは、送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを公開する要求は受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="70604-120">After **Terminate** is called the Messaging Engine does not accept requests to publish new messages, with the exception of response messages for solicit-response pairs.</span></span>