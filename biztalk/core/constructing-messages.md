---
title: "メッセージの構築 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fa87c4f3400a80ce83df132747d0004232323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="constructing-messages"></a><span data-ttu-id="33131-102">メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="33131-102">Constructing Messages</span></span>
<span data-ttu-id="33131-103">オーケストレーションにメッセージを導入する場合は常に、メッセージを受信するか、メッセージ変数に値を割り当てることによって、メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="33131-103">You construct a message any time that you introduce a message into your orchestration, either by receiving it or by assigning values to a message variable.</span></span> <span data-ttu-id="33131-104">使用するオブジェクトの詳細な説明がランタイム エンジンによって認識されるように、構築するメッセージにはメッセージの種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33131-104">Any message that you construct must have a message type, so that the runtime engine has a complete description of the object that it is working with.</span></span> <span data-ttu-id="33131-105">マルチパート メッセージの種類には、ユーザー定義、.NET クラス、またはスキーマを指定できます。</span><span class="sxs-lookup"><span data-stu-id="33131-105">The multi-part message type can be user-defined, it can be a .NET class, or it can be a schema.</span></span> <span data-ttu-id="33131-106">さまざまな方法でメッセージを構築することができます。 メッセージを作成、間、1 つのメッセージを割り当てる、またはメッセージ内の特定の値を別のメッセージ内の値にマップする変換を使用する .NET クラスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="33131-106">You can construct messages in various ways: you can invoke a .NET class to create a message, assign one message to another, or use a transform to map certain values within a message to values within another message.</span></span> <span data-ttu-id="33131-107">また、メッセージは、受信アクションによって構築されたり、オーケストレーションがパラメーターとしてメッセージを受け取るときに構築されたりします。</span><span class="sxs-lookup"><span data-stu-id="33131-107">Messages are also constructed by a receive action or when your orchestration accepts a message as a parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33131-108">マルチパート メッセージの種類に含める部分は、複数とは限りません。1 つだけの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="33131-108">A multi-part message type does not necessarily contain multiple parts; it might contain just one.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33131-109">BizTalk 内ではメッセージは不変です。つまり、作成した後に元のメッセージに変更を加えることはできません。</span><span class="sxs-lookup"><span data-stu-id="33131-109">Messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span> <span data-ttu-id="33131-110">変更する必要がある場合は、メッセージの新しいコピーを構築して、適切な値を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="33131-110">If you need to make a change, you must construct a new copy of the message and assign values to it appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33131-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="33131-111">In This Section</span></span>  
 [<span data-ttu-id="33131-112">メッセージの構築図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="33131-112">How to Configure the Construct Message Shape</span></span>](../core/how-to-configure-the-construct-message-shape.md)  
  
 [<span data-ttu-id="33131-113">メッセージの割り当て図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="33131-113">How to Configure the Message Assignment Shape</span></span>](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [<span data-ttu-id="33131-114">変換図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="33131-114">How to Configure the Transform Shape</span></span>](../core/how-to-configure-the-transform-shape.md) 
  
 [<span data-ttu-id="33131-115">メッセージの割り当て図形でメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="33131-115">Message References in Message Assignment Shape</span></span>](../core/message-references-in-message-assignment-shape.md)  
  
 [<span data-ttu-id="33131-116">ユーザー コードでのメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="33131-116">Message References in User Code</span></span>](../core/message-references-in-user-code.md)  
  
 [<span data-ttu-id="33131-117">メッセージ割り当てにおける Xpath の使用</span><span class="sxs-lookup"><span data-stu-id="33131-117">Using XPaths in Message Assignments</span></span>](../core/using-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="33131-118">メッセージ割り当てにおける非正規 Xpath の使用</span><span class="sxs-lookup"><span data-stu-id="33131-118">Using Non-Canonical XPaths in Message Assignments</span></span>](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="33131-119">ユーザー コードでメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="33131-119">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)  
  
 [<span data-ttu-id="33131-120">ユーザー コード内のメッセージにノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33131-120">Appending Nodes to Messages in User Code</span></span>](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a><span data-ttu-id="33131-121">参照</span><span class="sxs-lookup"><span data-stu-id="33131-121">See Also</span></span>  
 [<span data-ttu-id="33131-122">オーケストレーションでメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="33131-122">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)