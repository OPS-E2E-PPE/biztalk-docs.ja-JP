---
title: メッセージの構築 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c2267863facd50af0f2c2c018d158fa6ee678cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354634"
---
# <a name="constructing-messages"></a><span data-ttu-id="6cbc9-102">メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="6cbc9-102">Constructing Messages</span></span>
<span data-ttu-id="6cbc9-103">いつでもメッセージを受信するか、メッセージ変数に値を割り当てることで、オーケストレーションに導入すること、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-103">You construct a message any time that you introduce a message into your orchestration, either by receiving it or by assigning values to a message variable.</span></span> <span data-ttu-id="6cbc9-104">すべてのメッセージを構築することは、ランタイム エンジンがある操作しているオブジェクトの完全な説明できるように、メッセージの種類にすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-104">Any message that you construct must have a message type, so that the runtime engine has a complete description of the object that it is working with.</span></span> <span data-ttu-id="6cbc9-105">マルチパート メッセージの種類は、ユーザー定義、おくと、.NET クラスまたはスキーマを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-105">The multi-part message type can be user-defined, it can be a .NET class, or it can be a schema.</span></span> <span data-ttu-id="6cbc9-106">さまざまな方法でメッセージを構築することができます。 メッセージを作成、間、1 つのメッセージを割り当てる、またはメッセージ内の特定の値を別のメッセージ内の値にマップする変換を使用する .NET クラスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-106">You can construct messages in various ways: you can invoke a .NET class to create a message, assign one message to another, or use a transform to map certain values within a message to values within another message.</span></span> <span data-ttu-id="6cbc9-107">メッセージは、受信アクションまたはオーケストレーションがパラメーターとしてメッセージを受け入れる場合にも作成されます。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-107">Messages are also constructed by a receive action or when your orchestration accepts a message as a parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cbc9-108">必ずしも、マルチパート メッセージの種類に複数の部分が含まれていません。1 つだけを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-108">A multi-part message type does not necessarily contain multiple parts; it might contain just one.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6cbc9-109">メッセージは BizTalk; に変更できません。つまり、これを作成した後、元は変更できません。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-109">Messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span> <span data-ttu-id="6cbc9-110">変更する必要がある場合は、メッセージの新しいコピーを作成およびを適切に値を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cbc9-110">If you need to make a change, you must construct a new copy of the message and assign values to it appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6cbc9-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6cbc9-111">In This Section</span></span>  
 [<span data-ttu-id="6cbc9-112">メッセージの構築図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6cbc9-112">How to Configure the Construct Message Shape</span></span>](../core/how-to-configure-the-construct-message-shape.md)  
  
 [<span data-ttu-id="6cbc9-113">メッセージの割り当て図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6cbc9-113">How to Configure the Message Assignment Shape</span></span>](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [<span data-ttu-id="6cbc9-114">変換図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6cbc9-114">How to Configure the Transform Shape</span></span>](../core/how-to-configure-the-transform-shape.md) 
  
 [<span data-ttu-id="6cbc9-115">メッセージの割り当て図形のメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="6cbc9-115">Message References in Message Assignment Shape</span></span>](../core/message-references-in-message-assignment-shape.md)  
  
 [<span data-ttu-id="6cbc9-116">ユーザー コードでのメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="6cbc9-116">Message References in User Code</span></span>](../core/message-references-in-user-code.md)  
  
 [<span data-ttu-id="6cbc9-117">メッセージ割り当てにおける XPath の使用</span><span class="sxs-lookup"><span data-stu-id="6cbc9-117">Using XPaths in Message Assignments</span></span>](../core/using-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="6cbc9-118">メッセージ割り当てにおける非正規 XPath の使用</span><span class="sxs-lookup"><span data-stu-id="6cbc9-118">Using Non-Canonical XPaths in Message Assignments</span></span>](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="6cbc9-119">ユーザー コードでのメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="6cbc9-119">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)  
  
 [<span data-ttu-id="6cbc9-120">ユーザー コードでのメッセージへのノードの追加</span><span class="sxs-lookup"><span data-stu-id="6cbc9-120">Appending Nodes to Messages in User Code</span></span>](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cbc9-121">参照</span><span class="sxs-lookup"><span data-stu-id="6cbc9-121">See Also</span></span>  
 [<span data-ttu-id="6cbc9-122">オーケストレーションでのメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="6cbc9-122">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)