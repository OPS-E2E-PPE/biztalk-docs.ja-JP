---
title: IBaseMessage インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009c9df42e8dbce58f3b731932ef4077693f0f63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382808"
---
# <a name="ibasemessage-interface"></a><span data-ttu-id="c10eb-102">IBaseMessage インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c10eb-102">IBaseMessage Interface</span></span>
<span data-ttu-id="c10eb-103">使用して、受信アダプターが自身のプロトコルを介して受信データ パケットを受け入れる場合、 **IBaseMessage**メッセージング エンジンに渡すメッセージを作成するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c10eb-103">When a receive adapter accepts an incoming data packet through its protocol, it uses the **IBaseMessage** interface to create a message to pass to the Messaging Engine.</span></span> <span data-ttu-id="c10eb-104">すべてのメッセージは、このインターフェイスを使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="c10eb-104">All messages are represented by using this interface.</span></span>  
  
 <span data-ttu-id="c10eb-105">メッセージで 1 つまたは複数のメッセージ部分として表さ、 **IBaseMessagePart**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c10eb-105">A message has one or more message parts represented by the **IBaseMessagePart** interface.</span></span> <span data-ttu-id="c10eb-106">各メッセージ部分はそのデータ全体への参照、 **IStream**インターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="c10eb-106">Each message part has a reference to its data through an **IStream** interface pointer.</span></span> <span data-ttu-id="c10eb-107">メッセージのコンテキストがによって表される、 **IBaseMessageContext**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c10eb-107">The context of a message is represented by its **IBaseMessageContext** interface.</span></span> <span data-ttu-id="c10eb-108">次の図は、BizTalk メッセージ オブジェクト モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="c10eb-108">The following figure illustrates the BizTalk message object model.</span></span>  
  
 <span data-ttu-id="c10eb-109">![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")</span><span class="sxs-lookup"><span data-stu-id="c10eb-109">![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")</span></span>  
  
 <span data-ttu-id="c10eb-110">メッセージ コンテキストは、プロパティ名とプロパティの名前空間の組み合わせで識別されるディクショナリ。</span><span class="sxs-lookup"><span data-stu-id="c10eb-110">The message context is a dictionary that is keyed on a combination of the property name and the property namespace.</span></span> <span data-ttu-id="c10eb-111">これにより、たとえば、さまざまなソースから同様に名前付きプロパティの間に競合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム プロパティとカスタム アダプターのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c10eb-111">This prevents collisions between similarly named properties from different sources, for example, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system properties and custom adapter properties.</span></span> <span data-ttu-id="c10eb-112">これらのプロパティの値は、.NET 型の**オブジェクト**が、実際には、これらのプロパティは variant 型です。</span><span class="sxs-lookup"><span data-stu-id="c10eb-112">The values for these properties are of the .NET type **object**, but in fact these properties are VARIANTs.</span></span>  
  
 <span data-ttu-id="c10eb-113">各部分がディクショナリになっている部分コンテキストが、名前空間の概念です。</span><span class="sxs-lookup"><span data-stu-id="c10eb-113">Each part has a part context that is also a dictionary but without the notion of a namespace.</span></span> <span data-ttu-id="c10eb-114">一部のコンテキストの値は、その部分のデータを参照するメタデータです。</span><span class="sxs-lookup"><span data-stu-id="c10eb-114">The value of a part context is metadata referring to the data for that part.</span></span> <span data-ttu-id="c10eb-115">この例は、 **Charset**メッセージのエンコードに使用する文字セットを指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c10eb-115">An example of this is the **Charset** property that specifies the character set used for encoding the message.</span></span>  
  
 <span data-ttu-id="c10eb-116">プロパティに書き込まれ、メッセージ コンテキストから読み取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="c10eb-116">Properties may be written to and read from the message context.</span></span> <span data-ttu-id="c10eb-117">また、メッセージのルーティングに使用することも昇格可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c10eb-117">They may also be promoted to be used for message routing.</span></span> <span data-ttu-id="c10eb-118">昇格メッセージと共に渡されるメタデータの一部として書き込まれたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c10eb-118">Being promoted means they are written as a part of metadata that flows with the message.</span></span> <span data-ttu-id="c10eb-119">昇格させたプロパティは、送信ポートやオーケストレーションのフィルター式の作成に使用するには、その値を許可します。</span><span class="sxs-lookup"><span data-stu-id="c10eb-119">A promoted property allows its value to be used in the creation of filter expressions on send ports and orchestrations.</span></span> <span data-ttu-id="c10eb-120">下流コンポーネントやオーケストレーション内のユーザー コードが昇格させたプロパティの読み取りし、も新しい値を書き込みを行うことがあります。</span><span class="sxs-lookup"><span data-stu-id="c10eb-120">Downstream components and user code in orchestrations may read promoted properties and also write new values to them.</span></span>  
  
 <span data-ttu-id="c10eb-121">昇格させたプロパティは、既存のサブスクリプションに一致し、メッセージをルーティングするために使用されていますが、後に、プロパティは降格されます循環サブスクリプションと一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="c10eb-121">After a promoted property has been matched to an existing subscription and used to route a message, the property is demoted to prevent cyclic subscription matches.</span></span> <span data-ttu-id="c10eb-122">降格されたプロパティは、メタデータが、昇格状態を失うと、メッセージ コンテキストに残ります。</span><span class="sxs-lookup"><span data-stu-id="c10eb-122">A demoted property remains on the message context as metadata but loses its promoted status.</span></span>  
  
 <span data-ttu-id="c10eb-123">**実装のヒン ト:** メッセージ コンテキスト プロパティは、実行時にメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c10eb-123">**Implementation Tip:** Message context properties are loaded into memory at run time.</span></span> <span data-ttu-id="c10eb-124">この使用できなくなる可能性があるために、膨大なデータをメッセージ コンテキストに書き込まれませんする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]大きいメッセージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c10eb-124">Very large pieces of data should not be written to the message context because this could potentially break the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] large message support.</span></span> <span data-ttu-id="c10eb-125">実装すればメッセージ コンテキストにオブジェクトをシリアル化することがあります、 **IPersistStream**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c10eb-125">Objects may be serialized into the message context providing they implement the **IPersistStream** interface.</span></span> <span data-ttu-id="c10eb-126">また、昇格させたプロパティは、255 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="c10eb-126">Also, promoted properties are limited to 255 characters.</span></span>  
  
 <span data-ttu-id="c10eb-127">メッセージ ファクトリは、新しいメッセージを作成する常に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c10eb-127">The message factory should always be used to create new messages.</span></span>  <span data-ttu-id="c10eb-128">次のコード フラグメントは、アダプターで受信したデータ ストリームから新しい BizTalk メッセージを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c10eb-128">The following code fragment illustrates how to create a new BizTalk message from the data stream received by the adapter.</span></span>  
  
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