---
title: "IBaseMessage インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de478b27105ee6c01d582aa9b728bd0496d0487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ibasemessage-interface"></a><span data-ttu-id="4b008-102">IBaseMessage インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b008-102">IBaseMessage Interface</span></span>
<span data-ttu-id="4b008-103">使用して、受信アダプターがそのプロトコルを介して受信データ パケットを受け入れるときに、 **IBaseMessage**メッセージング エンジンに渡すメッセージを作成するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4b008-103">When a receive adapter accepts an incoming data packet through its protocol, it uses the **IBaseMessage** interface to create a message to pass to the Messaging Engine.</span></span> <span data-ttu-id="4b008-104">すべてのメッセージは、このインターフェイスで表現されます。</span><span class="sxs-lookup"><span data-stu-id="4b008-104">All messages are represented by using this interface.</span></span>  
  
 <span data-ttu-id="4b008-105">メッセージが 1 つまたは複数のメッセージ部分がによって表される、 **IBaseMessagePart**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4b008-105">A message has one or more message parts represented by the **IBaseMessagePart** interface.</span></span> <span data-ttu-id="4b008-106">各メッセージ部分はを通じてデータへの参照、 **IStream**インターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="4b008-106">Each message part has a reference to its data through an **IStream** interface pointer.</span></span> <span data-ttu-id="4b008-107">メッセージのコンテキストとして表されますその**IBaseMessageContext**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4b008-107">The context of a message is represented by its **IBaseMessageContext** interface.</span></span> <span data-ttu-id="4b008-108">次の図は、BizTalk メッセージ オブジェクト モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="4b008-108">The following figure illustrates the BizTalk message object model.</span></span>  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 <span data-ttu-id="4b008-109">メッセージ コンテキストは、プロパティ名とプロパティの名前空間の組み合わせをキーとするディクショナリです。</span><span class="sxs-lookup"><span data-stu-id="4b008-109">The message context is a dictionary that is keyed on a combination of the property name and the property namespace.</span></span> <span data-ttu-id="4b008-110">これにより、ソースの異なる類似した名前のプロパティ ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のシステム プロパティとカスタム アダプター プロパティなど) の間の競合を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="4b008-110">This prevents collisions between similarly named properties from different sources, for example, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system properties and custom adapter properties.</span></span> <span data-ttu-id="4b008-111">これらのプロパティの値は、.NET 型**オブジェクト**、実際のバリアントは、これらのプロパティが、します。</span><span class="sxs-lookup"><span data-stu-id="4b008-111">The values for these properties are of the .NET type **object**, but in fact these properties are VARIANTs.</span></span>  
  
 <span data-ttu-id="4b008-112">各部分には部分コンテキストがあり、同じくディクショナリとして機能しますが、名前空間の概念はありません。</span><span class="sxs-lookup"><span data-stu-id="4b008-112">Each part has a part context that is also a dictionary but without the notion of a namespace.</span></span> <span data-ttu-id="4b008-113">部分コンテキストの値は、その部分に対応するデータを参照するメタデータです。</span><span class="sxs-lookup"><span data-stu-id="4b008-113">The value of a part context is metadata referring to the data for that part.</span></span> <span data-ttu-id="4b008-114">この例は、 **Charset**メッセージのエンコードを使用した文字セットを指定するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4b008-114">An example of this is the **Charset** property that specifies the character set used for encoding the message.</span></span>  
  
 <span data-ttu-id="4b008-115">プロパティは、メッセージ コンテキストに書き込むことも、メッセージ コンテキストから読み取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="4b008-115">Properties may be written to and read from the message context.</span></span> <span data-ttu-id="4b008-116">また、昇格させてメッセージのルーティングに使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b008-116">They may also be promoted to be used for message routing.</span></span> <span data-ttu-id="4b008-117">昇格させたプロパティは、メッセージと共に渡されるメタデータの一部として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4b008-117">Being promoted means they are written as a part of metadata that flows with the message.</span></span> <span data-ttu-id="4b008-118">昇格させたプロパティの値は、送信ポートやオーケストレーションのフィルター式の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b008-118">A promoted property allows its value to be used in the creation of filter expressions on send ports and orchestrations.</span></span> <span data-ttu-id="4b008-119">下流コンポーネントやオーケストレーション内のユーザー コードで、昇格させたプロパティを読み取ったり新しい値を書き込んだりできます。</span><span class="sxs-lookup"><span data-stu-id="4b008-119">Downstream components and user code in orchestrations may read promoted properties and also write new values to them.</span></span>  
  
 <span data-ttu-id="4b008-120">昇格させたプロパティが既存のサブスクリプションと照合されてメッセージのルーティングに使用されると、サブスクリプションの照合が繰り返されないように、そのプロパティは降格されます。</span><span class="sxs-lookup"><span data-stu-id="4b008-120">After a promoted property has been matched to an existing subscription and used to route a message, the property is demoted to prevent cyclic subscription matches.</span></span> <span data-ttu-id="4b008-121">降格されたプロパティはメタデータとしてメッセージ コンテキストに残りますが、昇格状態は失われます。</span><span class="sxs-lookup"><span data-stu-id="4b008-121">A demoted property remains on the message context as metadata but loses its promoted status.</span></span>  
  
 <span data-ttu-id="4b008-122">**実装のヒン ト:**メッセージ コンテキスト プロパティは、実行時にメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="4b008-122">**Implementation Tip:** Message context properties are loaded into memory at run time.</span></span> <span data-ttu-id="4b008-123">膨大なデータをメッセージ コンテキストに書き込むことは、サイズの大きいメッセージをサポートする [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能を損なう可能性があるのでお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="4b008-123">Very large pieces of data should not be written to the message context because this could potentially break the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] large message support.</span></span> <span data-ttu-id="4b008-124">実装すればメッセージ コンテキストにオブジェクトをシリアル化することがあります、 **IPersistStream**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4b008-124">Objects may be serialized into the message context providing they implement the **IPersistStream** interface.</span></span> <span data-ttu-id="4b008-125">なお、昇格させたプロパティは 255 文字までに制限されます。</span><span class="sxs-lookup"><span data-stu-id="4b008-125">Also, promoted properties are limited to 255 characters.</span></span>  
  
 <span data-ttu-id="4b008-126">新しいメッセージの作成には、必ずメッセージ ファクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b008-126">The message factory should always be used to create new messages.</span></span>  <span data-ttu-id="4b008-127">次のコードは、アダプターで受信したデータ ストリームから新しい BizTalk メッセージを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b008-127">The following code fragment illustrates how to create a new BizTalk message from the data stream received by the adapter.</span></span>  
  
```  
using Microsoft.BizTalk.Message.Interop;  
  
IBaseMessage CreateMessage( Stream s, IBaseMessageFactory msgFactory )  
{  
IBaseMessage msg = null;  
IBaseMessagePart part = msgFactory.CreateMessagePart();  
part.Data = s;  
msg = msgFactory.CreateMessage();  
msg.AddPart("body", part, true);  
return msg;  
}  
```