---
title: Web メッセージの構築 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web messages, about Web messages
- Web messages, message types
- Web services, Web messages
- Web messages, parts
- Web messages
- messages, Web messages
ms.assetid: ca1792be-5fba-4f5d-a88e-b854f6a8ce33
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa03c7eae853677c22a0c7160075cad8bdb269cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390324"
---
# <a name="constructing-web-messages"></a><span data-ttu-id="17e83-102">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="17e83-102">Constructing Web Messages</span></span>
<span data-ttu-id="17e83-103">Web メッセージの種類から Web メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="17e83-103">You construct a Web message from a Web message type.</span></span> <span data-ttu-id="17e83-104">Web 参照を追加すると、BizTalk には、Web メッセージの種類、BizTalk で、追加された Web サービスの Web メソッドに基づいて自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="17e83-104">When you add a Web reference, BizTalk automatically creates Web message types, which BizTalk creates based on the Web methods from the added Web service.</span></span> <span data-ttu-id="17e83-105">Web メッセージは、Web メッセージの種類のいずれかにメッセージの種類の設定をオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="17e83-105">You add a Web message to your orchestration, setting the message type to one of the Web message types.</span></span> <span data-ttu-id="17e83-106">部分がプリミティブ .NET 型またはスキーマ型に基づいて個々 のメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="17e83-106">You create individual message parts based on primitive .NET or schema types.</span></span> <span data-ttu-id="17e83-107">メッセージ部分を含まない Web メッセージを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="17e83-107">You can construct a Web message that contains no message parts.</span></span>  
  
 <span data-ttu-id="17e83-108">**Web メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="17e83-108">**Web message types**</span></span>  
  
 <span data-ttu-id="17e83-109">Web メッセージの種類、Reference.odx に定義されているは、変更、変更または削除できない点を除いて、通常のメッセージ型と同じです。</span><span class="sxs-lookup"><span data-stu-id="17e83-109">Web message types, defined in the Reference.odx, are identical to a normal message type, except you cannot modify, rename or delete them.</span></span> <span data-ttu-id="17e83-110">Web メッセージの種類を削除するには、BizTalk プロジェクトから Web 参照を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17e83-110">To delete a Web message type, you must remove the Web reference from your BizTalk project.</span></span>  
  
 <span data-ttu-id="17e83-111">BizTalk プロジェクトは、追加された Web サービスで 1 つの要求と応答 Web メソッドごとに Web メッセージの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="17e83-111">BizTalk project creates one request and one response Web message type for each Web method in the added Web service.</span></span> <span data-ttu-id="17e83-112">Web メソッドが一方向の操作の場合は、BizTalk は要求を Web メッセージの種類のみを作成します。</span><span class="sxs-lookup"><span data-stu-id="17e83-112">If the Web method is a one-way operation, BizTalk only creates a request Web message type.</span></span> <span data-ttu-id="17e83-113">Web メッセージの種類の要求には、Web メソッドの各入力パラメーターの 1 つのメッセージ部分が含まれています。</span><span class="sxs-lookup"><span data-stu-id="17e83-113">A request Web message type contains one message part for each input parameter of the Web method.</span></span> <span data-ttu-id="17e83-114">応答の Web メッセージの種類には、戻り値の 1 つのメッセージ部分と Web メソッドの場合は、各出力パラメーターの 1 つのメッセージ部分が含まれています。</span><span class="sxs-lookup"><span data-stu-id="17e83-114">A response Web message type contains one message part for the return value and one message part for each output parameter of the Web method.</span></span>  
  
 <span data-ttu-id="17e83-115">Web メソッド パラメータ (入力または出力) によっては、BizTalk はプリミティブ .NET 型またはスキーマの種類から Web メッセージの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="17e83-115">Depending on the Web method parameter (input or output), BizTalk creates a Web message type from a primitive .NET type or a schema type.</span></span> <span data-ttu-id="17e83-116">Web メソッド パラメータがプリミティブ .NET 型の場合、メッセージ部分はプリミティブ .NET 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="17e83-116">If the Web method parameter is a primitive .NET type, the message part uses a primitive .NET type.</span></span> <span data-ttu-id="17e83-117">Web メソッド パラメータがスキーマ型の場合、BizTalk では、BizTalk プロジェクトにスキーマの種類を Reference.xsd 内のスキーマとして追加します。</span><span class="sxs-lookup"><span data-stu-id="17e83-117">If the Web method parameter is a schema type, BizTalk adds the schema type to the BizTalk project as a schema in Reference.xsd.</span></span> <span data-ttu-id="17e83-118">スキーマは、メッセージ部分の基盤です。</span><span class="sxs-lookup"><span data-stu-id="17e83-118">The schema is the basis for the message part.</span></span> <span data-ttu-id="17e83-119">Reference.xsd は Web 参照フォルダにあります。</span><span class="sxs-lookup"><span data-stu-id="17e83-119">You can find Reference.xsd in the Web references folder.</span></span>  
  
 <span data-ttu-id="17e83-120">また、作成できますプリミティブとスキーマの両方の .NET 型の .NET クラスを呼び出すことによって。</span><span class="sxs-lookup"><span data-stu-id="17e83-120">Alternatively, you can create both primitive and schema .NET types by calling a .NET class.</span></span> <span data-ttu-id="17e83-121">.NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="17e83-121">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
 <span data-ttu-id="17e83-122">**Web メッセージ**</span><span class="sxs-lookup"><span data-stu-id="17e83-122">**Web messages**</span></span>  
  
 <span data-ttu-id="17e83-123">Web メッセージは、(呼び出し)、Web サービスを使用する際に使用するメッセージです。</span><span class="sxs-lookup"><span data-stu-id="17e83-123">Web messages are the messages you use when you consume (call) a Web service.</span></span> <span data-ttu-id="17e83-124">Web 参照を追加したときに、BizTalk によって作成された Web メッセージの種類のいずれかにメッセージの種類を設定する点を除いて、通常のメッセージを追加することと同様に、オーケストレーションを Web メッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e83-124">You add a Web message to an orchestration the same way that you add a regular message, except that you set the message type to one of the Web message types that BizTalk created when you added a Web reference.</span></span>  
  
 <span data-ttu-id="17e83-125">**メッセージ部分**</span><span class="sxs-lookup"><span data-stu-id="17e83-125">**Message parts**</span></span>  
  
 <span data-ttu-id="17e83-126">Web メッセージを作成した後は、個々 のメッセージ部分を構築します。</span><span class="sxs-lookup"><span data-stu-id="17e83-126">After you create the Web message, you construct the individual message parts.</span></span> <span data-ttu-id="17e83-127">使用して、メッセージ部分がプリミティブ .NET 型を使用する場合、**メッセージの割り当て**図形。</span><span class="sxs-lookup"><span data-stu-id="17e83-127">If your message part uses a primitive .NET type, you use a **Message Assignment** shape.</span></span> <span data-ttu-id="17e83-128">使用して、メッセージ部分は、スキーマの種類を使用している場合、**変換**図形または**メッセージの割り当て**図形。</span><span class="sxs-lookup"><span data-stu-id="17e83-128">If your message part uses a schema type, you use a **Transform** shape or **Message Assignment** shape.</span></span> <span data-ttu-id="17e83-129">詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="17e83-129">For more information, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17e83-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="17e83-130">In This Section</span></span>  
  
-   [<span data-ttu-id="17e83-131">Web メッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="17e83-131">How to Add Web Messages</span></span>](../core/how-to-add-web-messages.md)  
  
-   [<span data-ttu-id="17e83-132">Web メッセージ部分の型を確認する方法</span><span class="sxs-lookup"><span data-stu-id="17e83-132">How to Determine a Web Message Part Type</span></span>](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [<span data-ttu-id="17e83-133">プリミティブ .NET 型から Web メッセージ部分を構築する方法</span><span class="sxs-lookup"><span data-stu-id="17e83-133">How to Construct a Web Message Part from a Primitive .NET Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [<span data-ttu-id="17e83-134">スキーマの種類から Web メッセージ部分を構築する方法</span><span class="sxs-lookup"><span data-stu-id="17e83-134">How to Construct a Web Message Part from a Schema Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [<span data-ttu-id="17e83-135">メッセージ部分を含まない Web メッセージを構築する方法</span><span class="sxs-lookup"><span data-stu-id="17e83-135">How to Construct a Web Message with No Message Parts</span></span>](../core/how-to-construct-a-web-message-with-no-message-parts.md)