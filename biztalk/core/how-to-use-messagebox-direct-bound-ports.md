---
title: "メッセージ ボックスの直接バインド ポートを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1839184b-408e-4ac6-94a4-a0eb708183f6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fbe52d46847bdaa7caffbb4402ce8d380a73f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a><span data-ttu-id="03573-102">メッセージ ボックスの直接バインド ポートの使用方法</span><span class="sxs-lookup"><span data-stu-id="03573-102">How to Use MessageBox Direct Bound Ports</span></span>
<span data-ttu-id="03573-103">メッセージ ボックスの直接バインド ポートを使用すると、明示的な受信者がない状態でメッセージをメッセージ ボックス データベースに直接ドロップでき、特定の送信者からのメッセージではなく特定の条件を満たすメッセージをサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="03573-103">MessageBox direct bound ports enable you to drop messages directly into the MessageBox database without an explicit recipient, and to subscribe to messages that meet certain criteria rather than messages that come from a particular sender.</span></span>  
  
 <span data-ttu-id="03573-104">MessageBox でメッセージを送信の直接バインド ポートはメッセージ バスへのメッセージの公開に相当 — この場合、メッセージ ボックス データベースにします。</span><span class="sxs-lookup"><span data-stu-id="03573-104">Sending a message on a MessageBox direct bound port is equivalent to publishing the message to a message bus—in this case, to the MessageBox database.</span></span> <span data-ttu-id="03573-105">公開されたメッセージに対しては任意の数のサブスクライバーが存在することができ、メッセージを公開したときにメッセージに関連するサブスクライバーが存在しない場合は、"サブスクリプションが見つかりません。" 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="03573-105">There can be any number of subscribers for any published message, and if there are no subscribers interested in the message at the time you publish it, a "subscription not found" exception will be thrown.</span></span> <span data-ttu-id="03573-106">特定の受信者を念頭にメッセージ ボックスの直接バインド ポートを通じてメッセージを送信する可能性がある場合に特定の値に設定されたプロパティ、**メッセージの割り当て**を探して、目的のサブスクライバーの形状。</span><span class="sxs-lookup"><span data-stu-id="03573-106">If you send a message through a MessageBox direct bound port with a particular recipient in mind, you may want to set properties to particular values in the **Message Assignment** shape for your intended subscriber to look for.</span></span> <span data-ttu-id="03573-107">BizTalk Server 定義済みプロパティ定義または独自のプロパティ定義に基づいてプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="03573-107">You can set the properties based on BizTalk Server predefined property definitions or on your own property definitions.</span></span> <span data-ttu-id="03573-108">例:</span><span class="sxs-lookup"><span data-stu-id="03573-108">For example:</span></span>  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 <span data-ttu-id="03573-109">メッセージ ボックスの直接バインド ポートを使用したメッセージの受信は、フィルター条件を使用したメッセージ バスのサブスクライブに相当します。</span><span class="sxs-lookup"><span data-stu-id="03573-109">Receiving a message through a MessageBox direct bound port is equivalent to subscribing to a message bus with filter criteria.</span></span> <span data-ttu-id="03573-110">メッセージの受信者は、オーケストレーションおよび送信ポートを含む、メッセージをサブスクライブできる任意の種類のサービスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="03573-110">Recipients of the message can be any type of service that can subscribe to messages, which includes orchestrations and send ports.</span></span> <span data-ttu-id="03573-111">アクティブ化**受信**図形、サブスクリプションがメッセージの種類とフィルター式と非アクティブの**受信**図形、サブスクリプションがメッセージの種類と、相関関係を設定します。</span><span class="sxs-lookup"><span data-stu-id="03573-111">For an activating **Receive** shape the subscription is the message type and the filter expression, and for a non-activating **Receive** shape the subscription is the message type and the correlation set.</span></span> <span data-ttu-id="03573-112">各**受信**図形は常に、そのサブスクリプションの一部としてメッセージの種類を含めます。</span><span class="sxs-lookup"><span data-stu-id="03573-112">Every **Receive** shape always includes the message type as part of its subscription.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03573-113">アクティブ化がある場合は、フィルター式を使用する必要があります**受信**型のメッセージを受信図形**System.Xml.XmlDocument**または**という**直接バインド ポートでのサブスクリプション定義ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="03573-113">You must use a filter expression if you have an activating **Receive** shape receiving a message of type **System.Xml.XmlDocument** or **Microsoft.XLANGs.BaseTypes.Any** on a direct bound port with subscription-defined routing.</span></span>  
  
 <span data-ttu-id="03573-114">アクティブでいずれかのフィルター条件を指定しなかった場合**受信**図形は、メッセージ ボックスの直接バインド ポートに接続し、サブスクリプションは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="03573-114">If you did not specify any filter criteria in the activating **Receive** shape connected to a MessageBox direct bound port, then the subscription will look similar to the following:</span></span>  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 <span data-ttu-id="03573-115">前の例では、メッセージ ボックスの直接バインド受信ポートは、ポートの操作の構成対象であるメッセージの種類と一致するすべてのメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="03573-115">In the preceding example, the MessageBox direct bound receive port will receive every message that matches the message type that the port’s operation is configured for.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03573-116">メッセージ ボックスの直接バインド受信ポートを使用する場合は、フィルターをできるだけ具体的なものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="03573-116">When using MessageBox direct bound receive ports, you should make the filter as specific as possible.</span></span> <span data-ttu-id="03573-117">フィルターを十分に具体的なものにしなかった場合、オーケストレーションが不要なメッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03573-117">If you do not make the filter specific enough, your orchestration may receive unwanted messages.</span></span>  
  
 <span data-ttu-id="03573-118">メッセージ ボックスの直接バインド ポートを構成するには、選択**ポート間のルーティングが、メッセージ ボックス データベース内の着信メッセージのフィルター式によって定義される**ポート構成ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="03573-118">To configure a MessageBox direct bound port, select **Routing between ports will be defined by filter expressions on incoming messages in the Message Box database** in the Port Configuration Wizard.</span></span>  
  
 <span data-ttu-id="03573-119">メッセージ ボックスの直接バインド ポートを使用する方法の例を参照してください、SDK サンプル「直接バインドに、メッセージ ボックス データベースでオーケストレーション」 [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="03573-119">For an example of how to use MessageBox direct bound ports, see the SDK sample "Direct Binding to the MessageBox Database in Orchestrations" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03573-120">参照</span><span class="sxs-lookup"><span data-stu-id="03573-120">See Also</span></span>  
 <span data-ttu-id="03573-121">[自己関連付けを行う Direct を使用する方法のポートのバインド](../core/how-to-use-self-correlating-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="03573-121">[How to Use Self-Correlating Direct Bound Ports](../core/how-to-use-self-correlating-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="03573-122">パートナー オーケストレーション直接バインド ポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="03573-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)