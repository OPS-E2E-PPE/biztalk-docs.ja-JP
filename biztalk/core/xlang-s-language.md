---
title: Xlang-s 言語 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, properties
ms.assetid: 97b62f17-5a8d-4d87-8563-1f6d941f027f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b04a28390546e4e22e5f293d772f88371f76696
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394727"
---
# <a name="xlang-s-language"></a><span data-ttu-id="5f660-102">Xlang-s 言語</span><span class="sxs-lookup"><span data-stu-id="5f660-102">XLANG-s Language</span></span>
<span data-ttu-id="5f660-103">Xlang/s では、XML、XSD、および Web サービス記述言語 (WSDL) などのインターネット標準を使用するように設計され、操作するためのサポートが組み込まれています。NET ベースのオブジェクトとメッセージです。</span><span class="sxs-lookup"><span data-stu-id="5f660-103">XLANG/s was designed to use Internet standards such as XML, XSD, and Web Services Description Language (WSDL), and has embedded support for working with .NET-based objects and messages.</span></span> <span data-ttu-id="5f660-104">一部の式の機能を備えたメッセージング言語として XLANG/秒を表示できますC#します。</span><span class="sxs-lookup"><span data-stu-id="5f660-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="5f660-105">ただし、コードは xlang/s の間で移植性とC#します。</span><span class="sxs-lookup"><span data-stu-id="5f660-105">However, code is not portable between XLANG/s and C#.</span></span>  
  
 <span data-ttu-id="5f660-106">XLANG/秒では、プロセスと実装が明確に分離を促進します。</span><span class="sxs-lookup"><span data-stu-id="5f660-106">XLANG/s encourages a clear separation between process and implementation.</span></span> <span data-ttu-id="5f660-107">たとえば、ビジネス プロセスまたはプロトコル xlang/s で指定され、他の .NET プログラミング言語などに、ローカル データベースへのアクセスなど、アプリケーションの側面が実装されてC#または Visual Basic.NET します。</span><span class="sxs-lookup"><span data-stu-id="5f660-107">For example, the business process or protocol is specified in XLANG/s, and the local aspects of the application, such as database access, are implemented in other .NET programming languages such as C# or Visual Basic.NET.</span></span>  
  
 <span data-ttu-id="5f660-108">XLANG/秒の割り当てと式の構文については、裏付けC#を参照する必要があります、C#正確な構文の仕様。</span><span class="sxs-lookup"><span data-stu-id="5f660-108">XLANG/s assignment and expression syntax is modeled after C#, and you should reference the C# specification for exact syntax.</span></span> <span data-ttu-id="5f660-109">XLANG/秒では、ビジネス プロセスの定義に使用される高レベルの構造の豊富なセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="5f660-109">XLANG/s defines a rich set of high-level constructs that are used to define business processes.</span></span> <span data-ttu-id="5f660-110">Xlang/s では、文字列や整数などの低レベルのデータ型をサポートして、高度なデータ型も定義されています。 メッセージ、ポート、相関関係、およびサービスへのリンク。</span><span class="sxs-lookup"><span data-stu-id="5f660-110">While XLANG/s provides support for low-level data types like string and integer, high-level data types are also defined: messages, ports, correlations, and service links.</span></span> <span data-ttu-id="5f660-111">これらのデータ型は、ビジネス プロセスに関連付けられているセマンティクスを厳密に定義を使用して行い、プロセスによって補完されます制御ステートメントなど**中**または**スコープ**します。</span><span class="sxs-lookup"><span data-stu-id="5f660-111">These data types are used to rigorously define the semantics associated with a business process, and are complemented by process control statements such as **while** or **scope**.</span></span>  
  
 <span data-ttu-id="5f660-112">Xlang/s ステートメントは一般に 2 つのカテゴリのいずれかに分類されますなど、自身で動作する単純なステートメント**受信**または**送信**、と複雑なステートメントを含むまたはいずれかの単純なステートメントをグループ化または。他の複合ステートメントなど**スコープ**、**並列**、および**リッスン**します。</span><span class="sxs-lookup"><span data-stu-id="5f660-112">XLANG/s statements generally fall into one of two categories: simple statements that act on their own, such as **receive** or **send**, and complex statements that contain or group either simple statements or other complex statements, such as **scope**, **parallel**, and **listen**.</span></span> <span data-ttu-id="5f660-113">Xlang/s に組み込まれているセマンティクスは、ビジネス プロセスのセマンティクスの定義については、Microsoft、IBM、および BEA によって公開されている Web Services (BPEL4WS) 仕様の Business Process Execution Language で定義されているのです。</span><span class="sxs-lookup"><span data-stu-id="5f660-113">The semantics embodied in XLANG/s are a reflection of those defined in the Business Process Execution Language for Web Services (BPEL4WS) specification published by Microsoft, IBM, and BEA for the definition of business process semantics.</span></span>  
  
 <span data-ttu-id="5f660-114">BizTalk オーケストレーション デザイナーでオーケストレーション ダイアグラムの描画の結果として生成されるため、xlang/s の主な構造を理解することもあります。</span><span class="sxs-lookup"><span data-stu-id="5f660-114">Understanding the main constructs of XLANG/s is optional because they are produced as a result of drawing orchestration diagrams in BizTalk Orchestration Designer.</span></span> <span data-ttu-id="5f660-115">オーケストレーション デザイナーは、ビジネス プロセスを視覚的に設計するための豊富なグラフィカル ツールです。</span><span class="sxs-lookup"><span data-stu-id="5f660-115">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="5f660-116">Xlang/s ファイルを .odx という拡張子を持ち、ヘッダーの追加のビジュアル情報と、本文にカスタム属性情報が含まれますが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f660-116">It generates XLANG/s files that have an .odx extension and contain additional visual information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f660-117">Xlang/s 言語は、専用なっています。</span><span class="sxs-lookup"><span data-stu-id="5f660-117">The XLANG/s language is proprietary and is not fully documented.</span></span> <span data-ttu-id="5f660-118">このセクションでは、オーケストレーションを開発する際に注意する必要があります言語の特定の部分を公開します。</span><span class="sxs-lookup"><span data-stu-id="5f660-118">This section exposes certain parts of the language that you might need to be aware of as you develop your orchestrations.</span></span> <span data-ttu-id="5f660-119">.Odx ファイルの直接的な変更はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5f660-119">Direct modification of the .odx files is not supported.</span></span>  
  
## <a name="xlangs-programs"></a><span data-ttu-id="5f660-120">Xlang/s プログラム</span><span class="sxs-lookup"><span data-stu-id="5f660-120">XLANG/s Programs</span></span>  
 <span data-ttu-id="5f660-121">最も単純な xlang/s プログラムでは、メッセージの種類が定義されている必要があります、オーケストレーションを付与する操作を開始するデータの一部です。</span><span class="sxs-lookup"><span data-stu-id="5f660-121">The simplest XLANG/s program requires that a message type be defined, which gives the orchestration some data to start to work with.</span></span> <span data-ttu-id="5f660-122">オーケストレーションでは、ポート経由でメッセージを受信し、し終了します。</span><span class="sxs-lookup"><span data-stu-id="5f660-122">The orchestration receives the message over a port and then terminates.</span></span> <span data-ttu-id="5f660-123">次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5f660-123">The following code is an example:</span></span>  
  
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
  
 <span data-ttu-id="5f660-124">上記の xlang/s プログラムで、`module`キーワードは、xlang/s プログラムのコンパイル単位を定義します。</span><span class="sxs-lookup"><span data-stu-id="5f660-124">In the preceding XLANG/s program, the `module` keyword defines the unit of compilations for an XLANG/s program.</span></span> <span data-ttu-id="5f660-125">プログラムで使用されるすべての型: など**porttype**、 **correlationsettype**、 **servicelinktype**、および**messagetype**— でスコープが設定このレベルです。</span><span class="sxs-lookup"><span data-stu-id="5f660-125">All types used in the program—such as **porttype**, **correlationsettype**, **servicelinktype**, and **messagetype**—are scoped at this level.</span></span>  
  
 <span data-ttu-id="5f660-126">ポートとは、xlang/s が送信または受信メッセージを送受信するコンストラクトと、ポートと呼ばれる定義済みの型には**porttype**します。</span><span class="sxs-lookup"><span data-stu-id="5f660-126">A port is a construct that XLANG/s can send or receive messages to or from, and the port has a defined type called **porttype**.</span></span> <span data-ttu-id="5f660-127">**Porttype**構成体は、ポートで使用できる操作のコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="5f660-127">The **porttype** construct defines a collection of operations that can be used on the port.</span></span> <span data-ttu-id="5f660-128">これらの操作は、ポート経由で、1 つの有効なメッセージ交換を定義します。</span><span class="sxs-lookup"><span data-stu-id="5f660-128">These operations define a single valid message exchange over the port.</span></span> <span data-ttu-id="5f660-129">定義する**porttype**、 **messagetype**、 **servicelinktype**、または**correlationsettype**に xlang/s の作成者を構築します。基本的に、プログラムが複雑なデータの種類の定義を作成しています。</span><span class="sxs-lookup"><span data-stu-id="5f660-129">In defining **porttype**, **messagetype**, **servicelinktype**, or **correlationsettype** constructs, the author of an XLANG/s program is essentially creating complex data type definitions.</span></span> <span data-ttu-id="5f660-130">これらの定義では、複合データ型と他の言語で同様に同じ利点があります。データ型の上位のレベルに組み込まれている概念を抽象化され、データ型を簡単に再利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="5f660-130">These definitions have the same advantages as complex data types do in other languages: They abstract the notions embodied in the data type to a higher level, and they allow for easy reuse of the data type.</span></span>  
  
 <span data-ttu-id="5f660-131">**PtPOReceive**で上記の HelloWorldApp モジュールが一方向で定義されているポートの受信ポート操作で**opPOReceive**します。</span><span class="sxs-lookup"><span data-stu-id="5f660-131">The **ptPOReceive** port in the preceding HelloWorldApp module is defined with a one-way receive port operation, **opPOReceive**.</span></span> <span data-ttu-id="5f660-132">サービスの HelloWorld ブロックでは、プロセス、ポートとメッセージ変数を含め、使用される任意の変数の実際の実装を定義します。</span><span class="sxs-lookup"><span data-stu-id="5f660-132">The service HelloWorld block defines the actual implementation of the process and any variables it may use, including port and message variables.</span></span> <span data-ttu-id="5f660-133">このブロック内のコードの最初の 3 つの行は、ポートの変数を定義**poPOReceive**と**poPOSend**メッセージ**msgPO**それぞれします。</span><span class="sxs-lookup"><span data-stu-id="5f660-133">The first three lines of code within this block define the port variables **poPOReceive** and **poPOSend** and the message **msgPO** respectively.</span></span> <span data-ttu-id="5f660-134">本文には、サービス、および実行の動作へのパラメーターを記述するコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f660-134">The body contains the code describing parameters to the service and the execution behavior.</span></span> <span data-ttu-id="5f660-135">すべての変数を入れ子になったスコープ ブロックで定義されていない場合は、このレベルにスコープされます。</span><span class="sxs-lookup"><span data-stu-id="5f660-135">All variables, unless defined with a nested scope block, are scoped to this level.</span></span> <span data-ttu-id="5f660-136">アクティブ化受信である、receive ステートメントを受信、 **msgPO**からのメッセージ、 **poPOReceive.opPOReceive**ポートし、オーケストレーションの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f660-136">The receive statement, which is an activate receive, receives the **msgPO** message from the **poPOReceive.opPOReceive** port and creates a new instance of the orchestration.</span></span> <span data-ttu-id="5f660-137">メッセージを受信すると、後に、send ステートメントは、送信ポートにメッセージを指示します。</span><span class="sxs-lookup"><span data-stu-id="5f660-137">After the message is received, the send statement directs the message to a send port.</span></span> <span data-ttu-id="5f660-138">上記のコードでは、2 つのポート宣言で**poPOReceive** implements 修飾子を使用しますが、 **poPOSend** uses 修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f660-138">In the two port declarations in the preceding code, **poPOReceive** uses the implements modifier, whereas **poPOSend** uses the uses modifier.</span></span> <span data-ttu-id="5f660-139">Implements 修飾子は、そのポート経由でメッセージを受信するには、ランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="5f660-139">The implements modifier tells the runtime it will be receiving a message over that port.</span></span> <span data-ttu-id="5f660-140">Uses 修飾子は、メッセージが送信ポート経由ですることをランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="5f660-140">The uses modifier tells the runtime that it will be sending a message over that port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f660-141">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5f660-141">In This Section</span></span>  
  
-   [<span data-ttu-id="5f660-142">XLANG-s データ型</span><span class="sxs-lookup"><span data-stu-id="5f660-142">XLANG-s Data Types</span></span>](../core/xlang-s-data-types.md)  
  
-   [<span data-ttu-id="5f660-143">XLANG-s ステートメント</span><span class="sxs-lookup"><span data-stu-id="5f660-143">XLANG-s Statements</span></span>](../core/xlang-s-statements.md)  
  
-   [<span data-ttu-id="5f660-144">XLANG-s の変数および演算子</span><span class="sxs-lookup"><span data-stu-id="5f660-144">XLANG-s Variables and Operators</span></span>](../core/xlang-s-variables-and-operators.md)  
  
-   [<span data-ttu-id="5f660-145">XLANG-s 式</span><span class="sxs-lookup"><span data-stu-id="5f660-145">XLANG-s Expressions</span></span>](../core/xlang-s-expressions.md)  
  
-   [<span data-ttu-id="5f660-146">XLANG-s の予約語</span><span class="sxs-lookup"><span data-stu-id="5f660-146">XLANG-s Reserved Words</span></span>](../core/xlang-s-reserved-words.md)  
  
-   [<span data-ttu-id="5f660-147">XLANG-s から BPEL4WS への種類の変換</span><span class="sxs-lookup"><span data-stu-id="5f660-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f660-148">参照</span><span class="sxs-lookup"><span data-stu-id="5f660-148">See Also</span></span>  
 [<span data-ttu-id="5f660-149">BizTalk オーケストレーション エンジンについて</span><span class="sxs-lookup"><span data-stu-id="5f660-149">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)