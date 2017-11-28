---
title: "式を使用してオブジェクトを作成する方法およびオブジェクトのメソッドを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, parameters
- Expression shape [Orchestration Designer], calling objects
- Expression shape [Orchestration Designer], parameters
- Expression shape [Orchestration Designer], passing messages
- orchestrations, methods
- Expression shape [Orchestration Designer], calling methods
- orchestrations, objects
- Expression shape [Orchestration Designer], warning
- Use Default Constructor property
- .NET member invocation
ms.assetid: b6af67eb-8ba5-4c95-9b63-26ebb6617af0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b56cfa46098569863106485fef204f72b23a4ef5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a><span data-ttu-id="5e0f7-102">オブジェクトを作成する式とオブジェクトのメソッドを呼び出す式の使用方法</span><span class="sxs-lookup"><span data-stu-id="5e0f7-102">How to Use Expressions to Create Objects and Call Object Methods</span></span>
<span data-ttu-id="5e0f7-103">オブジェクトの作成またはメソッドの呼び出しには、式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-103">You might need to use expressions to create objects or invoke methods.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="5e0f7-104">オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="5e0f7-104">Creating objects</span></span>  
 <span data-ttu-id="5e0f7-105">内のオブジェクトを構築する .NET クラスである型を持つ変数を作成する、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-105">To create a variable that has a type which is a .NET class, you construct an object in the **Expression** shape.</span></span> <span data-ttu-id="5e0f7-106">.NET クラス変数のプロパティには、コンストラクターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-106">The properties of your .NET class variable include a constructor.</span></span> <span data-ttu-id="5e0f7-107">既定のコンストラクターを使用する場合は、他の bool 型や int 型のような変数と同様に、変数を直接宣言するだけでかまいません。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-107">If you use the default constructor, you simply declare the variable directly as you would any other variable, like one of type bool or int.</span></span>  
  
 <span data-ttu-id="5e0f7-108">キーワードを使用するパラメーターを受け取るコンス トラクターを使用する場合**新しい**オブジェクト クラス、およびパラメーターをかっこでと、その後。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-108">If you use a constructor that takes parameters, you use the keyword **new**, followed by the object class and any parameters in parentheses:</span></span>  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  <span data-ttu-id="5e0f7-109">**既定のコンス トラクターを使用**コンス トラクターが存在するためには、実際には、一部のオブジェクトのプロパティが表示されません。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-109">The **Use Default Constructor** property might not be displayed for some objects that do, in fact, have constructors.</span></span> <span data-ttu-id="5e0f7-110">この場合、既定のコンストラクターが自動的に使用されます。別のコンストラクターを使用すると、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-110">In this case, the default constructor will be used automatically, and an error will be raised if you attempt to use a different constructor.</span></span>  
  
## <a name="invoking-methods"></a><span data-ttu-id="5e0f7-111">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5e0f7-111">Invoking methods</span></span>  
 <span data-ttu-id="5e0f7-112">.NET クラス オブジェクトでメソッドを呼び出すには、オブジェクト参照にピリオド (.) とメソッドの名前を追加して、その後にパラメーターをかっこで囲んで続けます。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-112">To invoke a method on a .NET class object, you append a period and the name of the method to the object reference, followed by any parameters in parentheses:</span></span>  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a><span data-ttu-id="5e0f7-113">パラメーターとしてのメッセージの引き渡しと使用</span><span class="sxs-lookup"><span data-stu-id="5e0f7-113">Passing and using messages as parameters</span></span>  
 <span data-ttu-id="5e0f7-114">.NET クラスのメソッド呼び出しに対してパラメーターとしてメッセージを渡すには、まず、プロジェクト内のクラスを定義する Microsoft.XLANGs.BaseTypes.dll に参照を追加します。次に、XLANGMessage をメソッド シグネチャに使用します。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-114">To pass a message as a parameter to a method call on a .NET class, you first add a reference to Microsoft.XLANGs.BaseTypes.dll in the project that defines the class, and then use the type XLANGMessage in the method signature.</span></span>  
  
 <span data-ttu-id="5e0f7-115">マルチパート メッセージの種類を参照すると、XLANGPart を使用してメッセージのさまざまな部分にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-115">Referencing the multi-part message type enables you to access the various parts of the message by using the type XLANGPart:</span></span>  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 <span data-ttu-id="5e0f7-116">呼び出し自体には、他のパラメーターと同じようにメッセージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-116">In the call itself, you simply supply the name of the message as you would any other parameter:</span></span>  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 <span data-ttu-id="5e0f7-117">XLANGPart としてメッセージの部分を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-117">You can also pass a message part as type XLANGPart.</span></span>  
  
## <a name="net-member-invocation"></a><span data-ttu-id="5e0f7-118">.NET メンバーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5e0f7-118">.NET member invocation</span></span>  
 <span data-ttu-id="5e0f7-119">パブリック メンバーにアクセスできます。ただし、メッセージ部分のメンバーへの直接アクセスはできません。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-119">You can access public members except in the case of direct access to members of a message part.</span></span> <span data-ttu-id="5e0f7-120">メッセージ部分のメンバーに直接アクセスするには、そのメンバーが、識別フィールドとして昇格されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-120">To directly access a member of a message part it must be promoted as a distinguished field.</span></span>  
  
## <a name="comcom-component-invocation"></a><span data-ttu-id="5e0f7-121">COM/COM+ コンポーネントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5e0f7-121">COM/COM+ component invocation</span></span>  
 <span data-ttu-id="5e0f7-122">XLANGs は C# コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-122">XLANGs generates C# code.</span></span> <span data-ttu-id="5e0f7-123">ユーザーが宣言した XLANGs 変数はすべて C# 変数として生成されます。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-123">All user-declared XLANGs variables are generated as C# variables.</span></span> <span data-ttu-id="5e0f7-124">アトミック トランザクションの場合を除いて特別な動作はありません。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-124">There is no special behavior except in the case of atomic transactions.</span></span> <span data-ttu-id="5e0f7-125">ときにサービス コンポーネント (を実装するクラスのインスタンスである、 **System.EnterpriseServices.ServicedComponent**) し、のみアトミックのスコープで宣言されて、XLANGs を生成し、実際の COM + DTC トランザクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-125">When a serviced component (that is, an instance of a class that implements **System.EnterpriseServices.ServicedComponent**) is declared in an atomic scope, then and only then does XLANGs generate and use a real DTC COM+ transaction.</span></span>  
  
 <span data-ttu-id="5e0f7-126">アトミック スコープで左辺値として参照される変数 (値が書き込まれる変数) が外側のスコープで宣言された場合、ロールバックをサポートするためにその変数のクローンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-126">If a variable is referenced as an L-value (that is, it is written to) in the atomic scope, but is declared in an outer scope, the variable is cloned to support rollback.</span></span> <span data-ttu-id="5e0f7-127">ただし、オブジェクト (など、 **XmlDocument**)、.NET 関数呼び出しで、パラメーターとして渡されるときに内部で変更されることができ、オブジェクトに書き込まれています、これがロールバックされない正しく XLANGs が見逃したためです。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-127">However, an object (such as an **XmlDocument**) can be modified inside a .NET function call when passed as an in-parameter, and thus XLANGs will miss that the object is being written to and it will not roll back correctly.</span></span> <span data-ttu-id="5e0f7-128">この場合の回避策は、このようなオブジェクトを参照パラメーターとして渡すことです。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-128">The workaround in this case is to pass such objects as ref parameters.</span></span>  
  
 <span data-ttu-id="5e0f7-129">つまり、コンポーネントは、他の C# プログラム内のコンポーネントと同様に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e0f7-129">The bottom line is that components should behave as they do in other C# programs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0f7-130">参照</span><span class="sxs-lookup"><span data-stu-id="5e0f7-130">See Also</span></span>  
 [<span data-ttu-id="5e0f7-131">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="5e0f7-131">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)