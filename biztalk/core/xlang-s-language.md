---
title: "XLANG の言語 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, properties
ms.assetid: 97b62f17-5a8d-4d87-8563-1f6d941f027f
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2329d4bc42617d70227481a0d70064d368f3c0e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-language"></a><span data-ttu-id="5023d-102">XLANG の言語</span><span class="sxs-lookup"><span data-stu-id="5023d-102">XLANG-s Language</span></span>
<span data-ttu-id="5023d-103">XLANG/s は、XML、XSD、Web Services Description Language (WSDL) などのインターネット標準を使用するように設計されており、.NET ベースのオブジェクトおよびメッセージの操作に対するサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="5023d-103">XLANG/s was designed to use Internet standards such as XML, XSD, and Web Services Description Language (WSDL), and has embedded support for working with .NET-based objects and messages.</span></span> <span data-ttu-id="5023d-104">XLANG/s は、C# の表現機能を備えたメッセージング言語と見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="5023d-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="5023d-105">ただし、XLANG/s と C# の間でコードを移植することはできません。</span><span class="sxs-lookup"><span data-stu-id="5023d-105">However, code is not portable between XLANG/s and C#.</span></span>  
  
 <span data-ttu-id="5023d-106">XLANG/s では、プロセスと実装を明確に区別することが推奨されています。</span><span class="sxs-lookup"><span data-stu-id="5023d-106">XLANG/s encourages a clear separation between process and implementation.</span></span> <span data-ttu-id="5023d-107">たとえば、ビジネス プロセスまたはプロトコルを XLANG/s で指定し、アプリケーションのローカルな側面 (データベース アクセスなど) を他の .NET プログラミング言語 (C# や Visual Basic.NET など) で実装します。</span><span class="sxs-lookup"><span data-stu-id="5023d-107">For example, the business process or protocol is specified in XLANG/s, and the local aspects of the application, such as database access, are implemented in other .NET programming languages such as C# or Visual Basic.NET.</span></span>  
  
 <span data-ttu-id="5023d-108">XLANG/s の割り当て構文および式構文は C# をモデルとしています。したがって、正確な構文については、C# の仕様を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5023d-108">XLANG/s assignment and expression syntax is modeled after C#, and you should reference the C# specification for exact syntax.</span></span> <span data-ttu-id="5023d-109">XLANG/s では、ビジネス プロセスの定義に使用される高レベルのコンストラクターが多数定義されています。</span><span class="sxs-lookup"><span data-stu-id="5023d-109">XLANG/s defines a rich set of high-level constructs that are used to define business processes.</span></span> <span data-ttu-id="5023d-110">XLANG/s では、文字列や整数などの低レベルのデータ型がサポートされていますが、メッセージ、ポート、関連付け、サービス リンクなどの高レベルのデータ型も定義されています。</span><span class="sxs-lookup"><span data-stu-id="5023d-110">While XLANG/s provides support for low-level data types like string and integer, high-level data types are also defined: messages, ports, correlations, and service links.</span></span> <span data-ttu-id="5023d-111">これらのデータ型が厳密に定義する、ビジネス プロセスに関連付けられているセマンティクスが使用され、プロセスによって補完されます制御ステートメントなど**中**または**スコープ**です。</span><span class="sxs-lookup"><span data-stu-id="5023d-111">These data types are used to rigorously define the semantics associated with a business process, and are complemented by process control statements such as **while** or **scope**.</span></span>  
  
 <span data-ttu-id="5023d-112">Xlang/s ステートメントは一般に、2 つのカテゴリのいずれかに分類: 単純なステートメントなど、独自に作用する**受信**または**送信**、および複雑なステートメントに含まれているいずれかの単純なステートメントをグループ化またはその他の複雑なステートメントなど**スコープ**、**並列**、および**リッスン**です。</span><span class="sxs-lookup"><span data-stu-id="5023d-112">XLANG/s statements generally fall into one of two categories: simple statements that act on their own, such as **receive** or **send**, and complex statements that contain or group either simple statements or other complex statements, such as **scope**, **parallel**, and **listen**.</span></span> <span data-ttu-id="5023d-113">XLANG/s に組み込まれているセマンティクスは、Microsoft、IBM、および BEA がビジネス プロセスのセマンティクスを定義するために公開した Business Process Execution Language for Web Services (BPEL4WS) 仕様に定義されているセマンティクスを反映したものです。</span><span class="sxs-lookup"><span data-stu-id="5023d-113">The semantics embodied in XLANG/s are a reflection of those defined in the Business Process Execution Language for Web Services (BPEL4WS) specification published by Microsoft, IBM, and BEA for the definition of business process semantics.</span></span>  
  
 <span data-ttu-id="5023d-114">XLANG/s の主なコンストラクターは、BizTalk オーケストレーション デザイナーでオーケストレーション ダイアグラムを描画することによって生成されます。したがって、これらのコンストラクターについて理解する必要は必ずしもありません。</span><span class="sxs-lookup"><span data-stu-id="5023d-114">Understanding the main constructs of XLANG/s is optional because they are produced as a result of drawing orchestration diagrams in BizTalk Orchestration Designer.</span></span> <span data-ttu-id="5023d-115">オーケストレーション デザイナーは、ビジネス プロセスを視覚的にデザインするための機能豊富なグラフィカル ツールです。</span><span class="sxs-lookup"><span data-stu-id="5023d-115">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="5023d-116">オーケストレーション デザイナーは、.odx という拡張子を持つ XLANG/s ファイルを生成します。このファイルのヘッダーには追加の視覚的情報が格納され、本文にはカスタム属性情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5023d-116">It generates XLANG/s files that have an .odx extension and contain additional visual information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5023d-117">XLANG/s 言語は独自に開発されたもので、仕様は一部非公開となっています。</span><span class="sxs-lookup"><span data-stu-id="5023d-117">The XLANG/s language is proprietary and is not fully documented.</span></span> <span data-ttu-id="5023d-118">このセクションでは、この言語について、オーケストレーションを作成する際に注意するべき項目を説明します。</span><span class="sxs-lookup"><span data-stu-id="5023d-118">This section exposes certain parts of the language that you might need to be aware of as you develop your orchestrations.</span></span> <span data-ttu-id="5023d-119">.odx ファイルを直接変更することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5023d-119">Direct modification of the .odx files is not supported.</span></span>  
  
## <a name="xlangs-programs"></a><span data-ttu-id="5023d-120">XLANG/s プログラム</span><span class="sxs-lookup"><span data-stu-id="5023d-120">XLANG/s Programs</span></span>  
 <span data-ttu-id="5023d-121">最も単純な XLANG/s プログラムでは、メッセージの種類を定義することにより、操作を開始するためのデータをオーケストレーションに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5023d-121">The simplest XLANG/s program requires that a message type be defined, which gives the orchestration some data to start to work with.</span></span> <span data-ttu-id="5023d-122">オーケストレーションは、ポート経由でメッセージを受信してから終了します。</span><span class="sxs-lookup"><span data-stu-id="5023d-122">The orchestration receives the message over a port and then terminates.</span></span> <span data-ttu-id="5023d-123">コード例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5023d-123">The following code is an example:</span></span>  
  
```  
module HelloWorldApp  
{  
     private porttype ptPOReceive  
     {  
      oneway opPOReceive  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private porttype ptPOSend  
     {  
      oneway opPOSend  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private service  HelloWorld  
     {  
      port implements HelloWorldApp.ptPOReceive poPOReceive;  
      port uses HelloWorldApp.ptPOSend poPOSend;  
      message HelloWorldApp.PurchaseOrder msgPO;  
      body ()  
      {  
       activate receive (poPOReceive.opPOReceive, msgPO);  
       send (poPOSend.opPOSend, msgPO);  
       }  
     }  
}  
```  
  
 <span data-ttu-id="5023d-124">上記の XLANG/s プログラムでは、XLANG/s プログラムのコンパイル単位を `module` キーワードで定義しています。</span><span class="sxs-lookup"><span data-stu-id="5023d-124">In the preceding XLANG/s program, the `module` keyword defines the unit of compilations for an XLANG/s program.</span></span> <span data-ttu-id="5023d-125">プログラムで使用されるすべての型: など**porttype**、 **correlationsettype**、 **servicelinktype**、および**messagetype**— スコープにはこのレベルです。</span><span class="sxs-lookup"><span data-stu-id="5023d-125">All types used in the program—such as **porttype**, **correlationsettype**, **servicelinktype**, and **messagetype**—are scoped at this level.</span></span>  
  
 <span data-ttu-id="5023d-126">ポートは、xlang/s を送信または受信メッセージを送受信するコンストラクトであり、ポートと呼ばれる定義済みの型**porttype**です。</span><span class="sxs-lookup"><span data-stu-id="5023d-126">A port is a construct that XLANG/s can send or receive messages to or from, and the port has a defined type called **porttype**.</span></span> <span data-ttu-id="5023d-127">**Porttype**構成体は、ポートで使用できる操作のコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="5023d-127">The **porttype** construct defines a collection of operations that can be used on the port.</span></span> <span data-ttu-id="5023d-128">これらの操作は、ポート経由での単一の有効なメッセージ交換を定義します。</span><span class="sxs-lookup"><span data-stu-id="5023d-128">These operations define a single valid message exchange over the port.</span></span> <span data-ttu-id="5023d-129">定義に**porttype**、 **messagetype**、 **servicelinktype**、または**correlationsettype**に xlang/s の作成者を構築します。基本的に、プログラムが複雑なデータの種類の定義を作成しています。</span><span class="sxs-lookup"><span data-stu-id="5023d-129">In defining **porttype**, **messagetype**, **servicelinktype**, or **correlationsettype** constructs, the author of an XLANG/s program is essentially creating complex data type definitions.</span></span> <span data-ttu-id="5023d-130">これらの定義に同じメリットが持っている場合は他の言語で複雑なデータ型: データ型の上位のレベルに組み込まれた概念が abstract であり、これにより、データ型の再利用が容易です。</span><span class="sxs-lookup"><span data-stu-id="5023d-130">These definitions have the same advantages as complex data types do in other languages: They abstract the notions embodied in the data type to a higher level, and they allow for easy reuse of the data type.</span></span>  
  
 <span data-ttu-id="5023d-131">**PtPOReceive**で上記の HelloWorldApp モジュールが、一方向で定義されているポートの受信ポート操作で**opPOReceive**です。</span><span class="sxs-lookup"><span data-stu-id="5023d-131">The **ptPOReceive** port in the preceding HelloWorldApp module is defined with a one-way receive port operation, **opPOReceive**.</span></span> <span data-ttu-id="5023d-132">このサービスの HelloWorld ブロックでは、プロセスの実際の実装と、ポート変数やメッセージ変数などプロセスで使用される変数を定義しています。</span><span class="sxs-lookup"><span data-stu-id="5023d-132">The service HelloWorld block defines the actual implementation of the process and any variables it may use, including port and message variables.</span></span> <span data-ttu-id="5023d-133">このブロック内のコードの最初の 3 つの行がポートの変数を定義する**poPOReceive**と**poPOSend**メッセージ**msgPO**それぞれします。</span><span class="sxs-lookup"><span data-stu-id="5023d-133">The first three lines of code within this block define the port variables **poPOReceive** and **poPOSend** and the message **msgPO** respectively.</span></span> <span data-ttu-id="5023d-134">本文には、サービスに渡すパラメーターと実行動作を表すコードが記述されています。</span><span class="sxs-lookup"><span data-stu-id="5023d-134">The body contains the code describing parameters to the service and the execution behavior.</span></span> <span data-ttu-id="5023d-135">入れ子になったスコープ ブロックで定義されているものを除くすべての変数は、このレベルにスコープ設定されます。</span><span class="sxs-lookup"><span data-stu-id="5023d-135">All variables, unless defined with a nested scope block, are scoped to this level.</span></span> <span data-ttu-id="5023d-136">アクティブ化受信である、receive ステートメントを受信、 **msgPO**からのメッセージ、 **poPOReceive.opPOReceive**ポートし、オーケストレーションの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5023d-136">The receive statement, which is an activate receive, receives the **msgPO** message from the **poPOReceive.opPOReceive** port and creates a new instance of the orchestration.</span></span> <span data-ttu-id="5023d-137">メッセージを受信した後、send ステートメントでそのメッセージを送信ポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="5023d-137">After the message is received, the send statement directs the message to a send port.</span></span> <span data-ttu-id="5023d-138">上記のコードでは、2 つのポート宣言で**poPOReceive** implements 修飾子を使用しますが、 **poPOSend** uses 修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="5023d-138">In the two port declarations in the preceding code, **poPOReceive** uses the implements modifier, whereas **poPOSend** uses the uses modifier.</span></span> <span data-ttu-id="5023d-139">implements 修飾子は、そのポート経由でメッセージを受信することをランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="5023d-139">The implements modifier tells the runtime it will be receiving a message over that port.</span></span> <span data-ttu-id="5023d-140">uses 修飾子は、そのポート経由でメッセージを送信することをランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="5023d-140">The uses modifier tells the runtime that it will be sending a message over that port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5023d-141">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5023d-141">In This Section</span></span>  
  
-   [<span data-ttu-id="5023d-142">XLANG のデータ型</span><span class="sxs-lookup"><span data-stu-id="5023d-142">XLANG-s Data Types</span></span>](../core/xlang-s-data-types.md)  
  
-   [<span data-ttu-id="5023d-143">XLANG のステートメント</span><span class="sxs-lookup"><span data-stu-id="5023d-143">XLANG-s Statements</span></span>](../core/xlang-s-statements.md)  
  
-   [<span data-ttu-id="5023d-144">XLANG の変数および演算子</span><span class="sxs-lookup"><span data-stu-id="5023d-144">XLANG-s Variables and Operators</span></span>](../core/xlang-s-variables-and-operators.md)  
  
-   [<span data-ttu-id="5023d-145">XLANG の式</span><span class="sxs-lookup"><span data-stu-id="5023d-145">XLANG-s Expressions</span></span>](../core/xlang-s-expressions.md)  
  
-   [<span data-ttu-id="5023d-146">XLANG s の予約語</span><span class="sxs-lookup"><span data-stu-id="5023d-146">XLANG-s Reserved Words</span></span>](../core/xlang-s-reserved-words.md)  
  
-   [<span data-ttu-id="5023d-147">XLANG-s BPEL4WS 型への変換から</span><span class="sxs-lookup"><span data-stu-id="5023d-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a><span data-ttu-id="5023d-148">参照</span><span class="sxs-lookup"><span data-stu-id="5023d-148">See Also</span></span>  
 [<span data-ttu-id="5023d-149">BizTalk オーケストレーション エンジンについて</span><span class="sxs-lookup"><span data-stu-id="5023d-149">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)