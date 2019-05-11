---
title: 式を使用してオブジェクトを作成する方法と、オブジェクトのメソッドを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adf0be16b7fa0fc78788386159672ce94823bbcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383440"
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a><span data-ttu-id="00cb1-102">式を使用してオブジェクトを作成する方法と、オブジェクトのメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="00cb1-102">How to Use Expressions to Create Objects and Call Object Methods</span></span>
<span data-ttu-id="00cb1-103">オブジェクトを作成またはメソッドの呼び出し式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00cb1-103">You might need to use expressions to create objects or invoke methods.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="00cb1-104">オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="00cb1-104">Creating objects</span></span>  
 <span data-ttu-id="00cb1-105">内のオブジェクトを構築する .NET クラスである型を持つ変数を作成する、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="00cb1-105">To create a variable that has a type which is a .NET class, you construct an object in the **Expression** shape.</span></span> <span data-ttu-id="00cb1-106">.NET クラス変数のプロパティには、コンス トラクターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00cb1-106">The properties of your .NET class variable include a constructor.</span></span> <span data-ttu-id="00cb1-107">既定のコンス トラクターを使用する場合、変数を宣言するだけ bool 型または整数のいずれかのように、その他の任意の変数と同様に直接</span><span class="sxs-lookup"><span data-stu-id="00cb1-107">If you use the default constructor, you simply declare the variable directly as you would any other variable, like one of type bool or int.</span></span>  
  
 <span data-ttu-id="00cb1-108">キーワードを使用するパラメーターを受け取るコンス トラクターを使用する場合**新しい**、その後にオブジェクトのクラスとパラメーターをかっこで。</span><span class="sxs-lookup"><span data-stu-id="00cb1-108">If you use a constructor that takes parameters, you use the keyword **new**, followed by the object class and any parameters in parentheses:</span></span>  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  <span data-ttu-id="00cb1-109">**既定のコンス トラクターを使用**コンス トラクターを指定することは、実際には、一部のオブジェクト プロパティが表示されません。</span><span class="sxs-lookup"><span data-stu-id="00cb1-109">The **Use Default Constructor** property might not be displayed for some objects that do, in fact, have constructors.</span></span> <span data-ttu-id="00cb1-110">この場合、既定のコンス トラクターが自動的に使用して、別のコンス トラクターを使用しようとした場合、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="00cb1-110">In this case, the default constructor will be used automatically, and an error will be raised if you attempt to use a different constructor.</span></span>  
  
## <a name="invoking-methods"></a><span data-ttu-id="00cb1-111">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="00cb1-111">Invoking methods</span></span>  
 <span data-ttu-id="00cb1-112">.NET クラス オブジェクトでメソッドを呼び出すには、パラメーターをかっこで囲まれた後に、オブジェクト参照にピリオドとメソッドの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="00cb1-112">To invoke a method on a .NET class object, you append a period and the name of the method to the object reference, followed by any parameters in parentheses:</span></span>  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a><span data-ttu-id="00cb1-113">渡すと、メッセージをパラメーターとして使用</span><span class="sxs-lookup"><span data-stu-id="00cb1-113">Passing and using messages as parameters</span></span>  
 <span data-ttu-id="00cb1-114">.NET クラスで、メッセージをパラメーターとしてメソッドの呼び出しに渡すするには、は、まずプロジェクト、クラスを定義する Microsoft.XLANGs.BaseTypes.dll に参照を追加し、XLANGMessage メソッド シグネチャでの型を使用しています。</span><span class="sxs-lookup"><span data-stu-id="00cb1-114">To pass a message as a parameter to a method call on a .NET class, you first add a reference to Microsoft.XLANGs.BaseTypes.dll in the project that defines the class, and then use the type XLANGMessage in the method signature.</span></span>  
  
 <span data-ttu-id="00cb1-115">マルチパート メッセージの種類を参照するには、xlangpart を使用して、メッセージのさまざまな部分にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="00cb1-115">Referencing the multi-part message type enables you to access the various parts of the message by using the type XLANGPart:</span></span>  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 <span data-ttu-id="00cb1-116">呼び出し自体で単純に名前を指定するメッセージのと同様、その他のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="00cb1-116">In the call itself, you simply supply the name of the message as you would any other parameter:</span></span>  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 <span data-ttu-id="00cb1-117">Xlangpart としてメッセージ部分を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="00cb1-117">You can also pass a message part as type XLANGPart.</span></span>  
  
## <a name="net-member-invocation"></a><span data-ttu-id="00cb1-118">.NET メンバーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="00cb1-118">.NET member invocation</span></span>  
 <span data-ttu-id="00cb1-119">メッセージ部分のメンバーに直接アクセスする場合を除くパブリック メンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="00cb1-119">You can access public members except in the case of direct access to members of a message part.</span></span> <span data-ttu-id="00cb1-120">メッセージ部分のメンバーに直接アクセスを識別フィールドとして昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00cb1-120">To directly access a member of a message part it must be promoted as a distinguished field.</span></span>  
  
## <a name="comcom-component-invocation"></a><span data-ttu-id="00cb1-121">COM と COM + コンポーネントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="00cb1-121">COM/COM+ component invocation</span></span>  
 <span data-ttu-id="00cb1-122">XLANGs 生成C#コード。</span><span class="sxs-lookup"><span data-stu-id="00cb1-122">XLANGs generates C# code.</span></span> <span data-ttu-id="00cb1-123">すべてのユーザーが宣言した XLANGs 変数として生成C#変数。</span><span class="sxs-lookup"><span data-stu-id="00cb1-123">All user-declared XLANGs variables are generated as C# variables.</span></span> <span data-ttu-id="00cb1-124">アトミック トランザクションの場合を除く特別な動作はありません。</span><span class="sxs-lookup"><span data-stu-id="00cb1-124">There is no special behavior except in the case of atomic transactions.</span></span> <span data-ttu-id="00cb1-125">サービス コンポーネント (実装するクラスのインスタンスである、 **System.EnterpriseServices.ServicedComponent**) だけに、アトミックのスコープで宣言された、XLANGs を生成し、実際の COM + DTC トランザクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="00cb1-125">When a serviced component (that is, an instance of a class that implements **System.EnterpriseServices.ServicedComponent**) is declared in an atomic scope, then and only then does XLANGs generate and use a real DTC COM+ transaction.</span></span>  
  
 <span data-ttu-id="00cb1-126">左辺値として変数が参照されているかどうか (つまりに書き込まれます) でアトミックのスコープが外側のスコープで宣言は、ロールバックをサポートするために、変数のクローンを作成します。</span><span class="sxs-lookup"><span data-stu-id="00cb1-126">If a variable is referenced as an L-value (that is, it is written to) in the atomic scope, but is declared in an outer scope, the variable is cloned to support rollback.</span></span> <span data-ttu-id="00cb1-127">ただし、オブジェクト (など、 **XmlDocument**) でのパラメーターとして渡されるときに、.NET 関数呼び出しの内部での修正、およびに書き込まれたオブジェクトをこれはロールバックしない正しく XLANGs を見逃すためです。</span><span class="sxs-lookup"><span data-stu-id="00cb1-127">However, an object (such as an **XmlDocument**) can be modified inside a .NET function call when passed as an in-parameter, and thus XLANGs will miss that the object is being written to and it will not roll back correctly.</span></span> <span data-ttu-id="00cb1-128">回避策は、この場合、ref パラメーターとしてこのようなオブジェクトを渡すには。</span><span class="sxs-lookup"><span data-stu-id="00cb1-128">The workaround in this case is to pass such objects as ref parameters.</span></span>  
  
 <span data-ttu-id="00cb1-129">一番下の行が他のようにコンポーネントが動作する必要があるC#プログラム。</span><span class="sxs-lookup"><span data-stu-id="00cb1-129">The bottom line is that components should behave as they do in other C# programs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00cb1-130">参照</span><span class="sxs-lookup"><span data-stu-id="00cb1-130">See Also</span></span>  
 [<span data-ttu-id="00cb1-131">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="00cb1-131">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)