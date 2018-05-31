---
title: コンポーネント インターフェイス ユーザー定義メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, user-defined methods
- user-defined methods, component interface
- custom component interfaces, limitations
- collection limitations
- custom methods, samples
- samples, custom methods
- component interfaces, limitations for custom CI
ms.assetid: e4b15889-35ff-44aa-819d-eade9690bdd6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 139117ffb26c8fec355dcfe481657817bc64bc0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233834"
---
# <a name="component-interface-user-defined-methods"></a><span data-ttu-id="aeccc-102">コンポーネント インターフェイス ユーザー定義メソッド</span><span class="sxs-lookup"><span data-stu-id="aeccc-102">Component Interface User-Defined Methods</span></span>
<span data-ttu-id="aeccc-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスでユーザー定義メソッドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="aeccc-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise supports user-defined methods in component interfaces.</span></span> <span data-ttu-id="aeccc-104">署名の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-104">The signatures are of the form:</span></span>  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 <span data-ttu-id="aeccc-105">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-105">where:</span></span>  
  
-   <span data-ttu-id="aeccc-106">`parameter1`、`parameter2` は入力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-106">`parameter1`, `parameter2` are input parameters.</span></span>  
  
-   <span data-ttu-id="aeccc-107">`myRet` は戻り値です。</span><span class="sxs-lookup"><span data-stu-id="aeccc-107">`myRet` is the return value.</span></span>  
  
 <span data-ttu-id="aeccc-108">パラメーターに指定できるのは、メソッドへの入力パラメーターだけです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-108">The parameters can only be input parameters to the method.</span></span> <span data-ttu-id="aeccc-109">戻りパラメーターとしてメソッドから返すことができるのは 1 つの値のみです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-109">Only one value can be returned from the method as the return parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aeccc-110">ユーザー定義メソッドを含むコンポーネント インターフェイスは、有効な PeopleSoft `Get` 関数だけを保持している必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeccc-110">The component interface that contains user-defined methods should only have the PeopleSoft `Get` function enabled.</span></span> <span data-ttu-id="aeccc-111">コンポーネント インターフェイスにキーがある場合は、カスタム メソッドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="aeccc-111">If the component interface has keys, then custom methods will not work.</span></span>  
  
## <a name="custom-ci-limitation"></a><span data-ttu-id="aeccc-112">カスタム CI の制限</span><span class="sxs-lookup"><span data-stu-id="aeccc-112">Custom CI Limitation</span></span>  
 <span data-ttu-id="aeccc-113">BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスにキーが存在しない場合にのみ、カスタム PeopleSoft メソッドを処理できます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-113">BizTalk Adapter for PeopleSoft Enterprise can handle custom PeopleSoft methods provided that the component interface does not have keys.</span></span> <span data-ttu-id="aeccc-114">コンポーネント インターフェイスにキーが存在すると、カスタム メソッドは動作しません。</span><span class="sxs-lookup"><span data-stu-id="aeccc-114">If the component interface has keys, custom methods will not work.</span></span>  
  
### <a name="workaround"></a><span data-ttu-id="aeccc-115">回避策</span><span class="sxs-lookup"><span data-stu-id="aeccc-115">Workaround</span></span>  
 <span data-ttu-id="aeccc-116">キーを含まない新しいコンポーネント インターフェイスを作成し、呼び出しパラメーターの一部としてキーを含む新しいカスタム メソッドを書きます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-116">Create a new component interface that does not have keys, and write a new custom method that incorporates the keys as part of the calling parameters.</span></span> <span data-ttu-id="aeccc-117">たとえば、SetPassword カスタム メソッドは USER_PROFILE コンポーネント インターフェイスで使用できますが、USER_PROFILE にはキーがあります。</span><span class="sxs-lookup"><span data-stu-id="aeccc-117">For example, you could use the SetPassword custom method in the USER_PROFILE component interface; however USER_PROFILE has keys.</span></span> <span data-ttu-id="aeccc-118">キーのない新しいコンポーネント インターフェイスを作成し、新しいコンポーネント インターフェイスにカスタム メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-118">You can create a new component interface that has no keys, and then create a custom method in your new component interface.</span></span> <span data-ttu-id="aeccc-119">このメソッドで、ユーザー ID とパスワードの 2 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="aeccc-119">This method would accept two parameters, user ID and password.</span></span> <span data-ttu-id="aeccc-120">このカスタム メソッドは、`Get` を使用して USER_PROFILE を呼び出し、さらに `SetPassword` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-120">The custom method could then invoke USER_PROFILE with a `Get` and then invoke `SetPassword`.</span></span> <span data-ttu-id="aeccc-121">詳細については、PeopleSoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeccc-121">Consult the PeopleSoft documentation for more details.</span></span>  
  
 <span data-ttu-id="aeccc-122">PeopleSoft の制限により、ユーザー定義メソッドに使用される `Date`、`DateTime`、および `Time` の型は、クライアント コードの文字列に対応しています。</span><span class="sxs-lookup"><span data-stu-id="aeccc-122">Due to a limitation in PeopleSoft, `Date`, `DateTime`, and `Time` types appearing in user-defined methods are mapped as strings in the client code.</span></span>  
  
## <a name="collection-limitation"></a><span data-ttu-id="aeccc-123">コレクションの制限</span><span class="sxs-lookup"><span data-stu-id="aeccc-123">Collection Limitation</span></span>  
 <span data-ttu-id="aeccc-124">ユーザー定義メソッドでは、コレクションを返すことはできません。より一般的に、API オブジェクトを返せません。</span><span class="sxs-lookup"><span data-stu-id="aeccc-124">User-defined methods cannot return a collection, or more generally, any API object.</span></span> <span data-ttu-id="aeccc-125">したがって、返すことができるのは、文字列や数値などの単純な型だけです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-125">This means that you can only return simple types, for example, strings and numbers.</span></span> <span data-ttu-id="aeccc-126">この制限を回避するには、コレクションを XML 文字列として送信し、クライアントが文字列を解析してアイテムを正しい形式で抽出するようにプログラミングします。</span><span class="sxs-lookup"><span data-stu-id="aeccc-126">You can get around this limitation by sending a collection as an XML string and programming the client to parse the strings to extract the items into the correct format.</span></span> <span data-ttu-id="aeccc-127">GET_CI_INFO カスタム コンポーネント インターフェイスを調べると、この対応策の例を確認できます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-127">You can examine the GET_CI_INFO custom component interface to see an example of this workaround.</span></span>  
  
## <a name="sample-custom-method"></a><span data-ttu-id="aeccc-128">サンプル カスタム メソッド</span><span class="sxs-lookup"><span data-stu-id="aeccc-128">Sample Custom Method</span></span>  
 <span data-ttu-id="aeccc-129">次の基本的なカスタム メソッド SayHello を使用して、カスタム メソッドを使用するコンポーネント インターフェイスの機能性をテストできます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-129">You can use the following basic custom method, SayHello, to test the functionality of your component interface using custom methods.</span></span>  
  
 <span data-ttu-id="aeccc-130">次の PeopleCode 関数は、ACB_EMPLOYEE という名前の PeopleSoft コンポーネント インターフェイスのユーザー定義メソッドです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-130">The following PeopleCode function is a user-defined method of a PeopleSoft component interface named ACB_EMPLOYEE.</span></span> <span data-ttu-id="aeccc-131">このサンプルは、戻り値が文字列を返します**こんにちは**後に、入力パラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="aeccc-131">The sample returns a string where the return value is **Hello** followed by the value of the input parameter.</span></span>  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  <span data-ttu-id="aeccc-132">(1 つのコマンドで) 複数のテーブルを同時に変更するには、別のコンポーネント インターフェイスを作成するか、またはユーザー定義メソッドを含むコンポーネント インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-132">To modify multiple tables at the same time (using one command) you can either create another component interface or create a component interface user-defined method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeccc-133">参照</span><span class="sxs-lookup"><span data-stu-id="aeccc-133">See Also</span></span>  
 [<span data-ttu-id="aeccc-134">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="aeccc-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)