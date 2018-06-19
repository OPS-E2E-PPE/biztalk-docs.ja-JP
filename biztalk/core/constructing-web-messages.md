---
title: Web メッセージの構築 |Microsoft ドキュメント
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
ms.openlocfilehash: 8c344bbb836a6524ec1fd2656a5ba3f8bc8fad7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237986"
---
# <a name="constructing-web-messages"></a><span data-ttu-id="5194f-102">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="5194f-102">Constructing Web Messages</span></span>
<span data-ttu-id="5194f-103">[Web メッセージの種類] から Web メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="5194f-103">You construct a Web message from a Web message type.</span></span> <span data-ttu-id="5194f-104">Web 参照を追加すると、BizTalk では、追加された Web サービスの Web メソッドに基づいて Web メッセージの種類が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="5194f-104">When you add a Web reference, BizTalk automatically creates Web message types, which BizTalk creates based on the Web methods from the added Web service.</span></span> <span data-ttu-id="5194f-105">Web メッセージをオーケストレーションに追加するには、メッセージの種類を Web メッセージの種類のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="5194f-105">You add a Web message to your orchestration, setting the message type to one of the Web message types.</span></span> <span data-ttu-id="5194f-106">プリミティブ .NET 型またはスキーマ型に基づいて、個々のメッセージ部分を作成します。</span><span class="sxs-lookup"><span data-stu-id="5194f-106">You create individual message parts based on primitive .NET or schema types.</span></span> <span data-ttu-id="5194f-107">メッセージ部分を含まない Web メッセージも構築できます。</span><span class="sxs-lookup"><span data-stu-id="5194f-107">You can construct a Web message that contains no message parts.</span></span>  
  
 <span data-ttu-id="5194f-108">**Web メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="5194f-108">**Web message types**</span></span>  
  
 <span data-ttu-id="5194f-109">Web メッセージの種類は、Reference.odx に定義されています。Web メッセージの種類は、通常のメッセージの種類と同じですが、変更、名前変更、および削除を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="5194f-109">Web message types, defined in the Reference.odx, are identical to a normal message type, except you cannot modify, rename or delete them.</span></span> <span data-ttu-id="5194f-110">Web メッセージの種類を削除するには、BizTalk プロジェクトから Web 参照を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5194f-110">To delete a Web message type, you must remove the Web reference from your BizTalk project.</span></span>  
  
 <span data-ttu-id="5194f-111">BizTalk プロジェクトは、追加された Web サービスにある Web メソッドごとに、要求に使用する Web メッセージの種類を 1 つ、応答に使用する Web メッセージの種類を 1 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="5194f-111">BizTalk project creates one request and one response Web message type for each Web method in the added Web service.</span></span> <span data-ttu-id="5194f-112">Web メソッドが一方向の操作である場合、BizTalk は要求に使用する Web メッセージの種類のみを作成します。</span><span class="sxs-lookup"><span data-stu-id="5194f-112">If the Web method is a one-way operation, BizTalk only creates a request Web message type.</span></span> <span data-ttu-id="5194f-113">要求に使用する Web メッセージの種類には、Web メソッドの入力パラメータごとに 1 つのメッセージ部分が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5194f-113">A request Web message type contains one message part for each input parameter of the Web method.</span></span> <span data-ttu-id="5194f-114">応答に使用する Web メッセージの種類には、戻り値を格納するためのメッセージ部分が含まれ、Web メソッドの出力パラメータごとに 1 つのメッセージ部分が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5194f-114">A response Web message type contains one message part for the return value and one message part for each output parameter of the Web method.</span></span>  
  
 <span data-ttu-id="5194f-115">Web メソッド パラメータ (入力または出力) に応じて、BizTalk はプリミティブ .NET 型またはスキーマ型から Web メッセージの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="5194f-115">Depending on the Web method parameter (input or output), BizTalk creates a Web message type from a primitive .NET type or a schema type.</span></span> <span data-ttu-id="5194f-116">Web メソッド パラメータがプリミティブ .NET 型である場合、メッセージ部分はプリミティブ .NET 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="5194f-116">If the Web method parameter is a primitive .NET type, the message part uses a primitive .NET type.</span></span> <span data-ttu-id="5194f-117">Web メソッド パラメータがスキーマ型である場合、BizTalk は BizTalk プロジェクトに Reference.xsd 内のスキーマとして、スキーマ型を追加します。</span><span class="sxs-lookup"><span data-stu-id="5194f-117">If the Web method parameter is a schema type, BizTalk adds the schema type to the BizTalk project as a schema in Reference.xsd.</span></span> <span data-ttu-id="5194f-118">このスキーマがメッセージ部分の基礎になります。</span><span class="sxs-lookup"><span data-stu-id="5194f-118">The schema is the basis for the message part.</span></span> <span data-ttu-id="5194f-119">Reference.xsd は Web 参照フォルダにあります。</span><span class="sxs-lookup"><span data-stu-id="5194f-119">You can find Reference.xsd in the Web references folder.</span></span>  
  
 <span data-ttu-id="5194f-120">別の方法として、.NET クラスを呼び出すことで、プリミティブ .NET 型とスキーマ .NET 型の両方を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5194f-120">Alternatively, you can create both primitive and schema .NET types by calling a .NET class.</span></span> <span data-ttu-id="5194f-121">.NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="5194f-121">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
 <span data-ttu-id="5194f-122">**Web メッセージ**</span><span class="sxs-lookup"><span data-stu-id="5194f-122">**Web messages**</span></span>  
  
 <span data-ttu-id="5194f-123">Web メッセージは、Web サービスを利用 (呼び出し) するときに使用するメッセージです。</span><span class="sxs-lookup"><span data-stu-id="5194f-123">Web messages are the messages you use when you consume (call) a Web service.</span></span> <span data-ttu-id="5194f-124">Web メッセージは、通常のメッセージと同様にオーケストレーションに追加できます。ただし、メッセージの種類を、Web 参照を追加するときに作成されたいずれかの Web メッセージの種類に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5194f-124">You add a Web message to an orchestration the same way that you add a regular message, except that you set the message type to one of the Web message types that BizTalk created when you added a Web reference.</span></span>  
  
 <span data-ttu-id="5194f-125">**メッセージ部分**</span><span class="sxs-lookup"><span data-stu-id="5194f-125">**Message parts**</span></span>  
  
 <span data-ttu-id="5194f-126">Web メッセージを作成したら、個々のメッセージ部分を構築します。</span><span class="sxs-lookup"><span data-stu-id="5194f-126">After you create the Web message, you construct the individual message parts.</span></span> <span data-ttu-id="5194f-127">使用する、メッセージ部分は、プリミティブ .NET 型を使用している場合、**メッセージの割り当て**図形です。</span><span class="sxs-lookup"><span data-stu-id="5194f-127">If your message part uses a primitive .NET type, you use a **Message Assignment** shape.</span></span> <span data-ttu-id="5194f-128">使用する、メッセージ部分は、スキーマの種類を使用している場合、**変換**図形または**メッセージの割り当て**図形です。</span><span class="sxs-lookup"><span data-stu-id="5194f-128">If your message part uses a schema type, you use a **Transform** shape or **Message Assignment** shape.</span></span> <span data-ttu-id="5194f-129">詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="5194f-129">For more information, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5194f-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5194f-130">In This Section</span></span>  
  
-   [<span data-ttu-id="5194f-131">Web メッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="5194f-131">How to Add Web Messages</span></span>](../core/how-to-add-web-messages.md)  
  
-   [<span data-ttu-id="5194f-132">Web メッセージ部分の型を確認する方法</span><span class="sxs-lookup"><span data-stu-id="5194f-132">How to Determine a Web Message Part Type</span></span>](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [<span data-ttu-id="5194f-133">プリミティブ .NET 型から Web メッセージ部分を構築する方法</span><span class="sxs-lookup"><span data-stu-id="5194f-133">How to Construct a Web Message Part from a Primitive .NET Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [<span data-ttu-id="5194f-134">スキーマの種類から Web メッセージ部分を構築する方法</span><span class="sxs-lookup"><span data-stu-id="5194f-134">How to Construct a Web Message Part from a Schema Type</span></span>](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [<span data-ttu-id="5194f-135">メッセージ部分を含まない Web メッセージを構築する方法</span><span class="sxs-lookup"><span data-stu-id="5194f-135">How to Construct a Web Message with No Message Parts</span></span>](../core/how-to-construct-a-web-message-with-no-message-parts.md)