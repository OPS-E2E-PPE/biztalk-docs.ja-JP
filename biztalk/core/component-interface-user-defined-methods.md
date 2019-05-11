---
title: コンポーネント インターフェイス ユーザー定義メソッド |Microsoft Docs
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
ms.openlocfilehash: 1574a73b45f5048910d5df8fee43d75502c2938b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356719"
---
# <a name="component-interface-user-defined-methods"></a><span data-ttu-id="4031f-102">コンポーネント インターフェイス ユーザー定義メソッド</span><span class="sxs-lookup"><span data-stu-id="4031f-102">Component Interface User-Defined Methods</span></span>
<span data-ttu-id="4031f-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、コンポーネント インターフェイス ユーザー定義メソッドをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4031f-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise supports user-defined methods in component interfaces.</span></span> <span data-ttu-id="4031f-104">署名は、フォームのことです。</span><span class="sxs-lookup"><span data-stu-id="4031f-104">The signatures are of the form:</span></span>  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 <span data-ttu-id="4031f-105">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4031f-105">where:</span></span>  
  
- <span data-ttu-id="4031f-106">`parameter1`、`parameter2`は入力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="4031f-106">`parameter1`, `parameter2` are input parameters.</span></span>  
  
- <span data-ttu-id="4031f-107">`myRet` 戻り値です。</span><span class="sxs-lookup"><span data-stu-id="4031f-107">`myRet` is the return value.</span></span>  
  
  <span data-ttu-id="4031f-108">パラメーターは、メソッドへの入力パラメーターにできるだけです。</span><span class="sxs-lookup"><span data-stu-id="4031f-108">The parameters can only be input parameters to the method.</span></span> <span data-ttu-id="4031f-109">1 つの値は、戻りパラメーターとしてメソッドから返さことができます。</span><span class="sxs-lookup"><span data-stu-id="4031f-109">Only one value can be returned from the method as the return parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4031f-110">ユーザー定義メソッドを含むコンポーネント インターフェイスは、PeopleSoft にのみが`Get`機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4031f-110">The component interface that contains user-defined methods should only have the PeopleSoft `Get` function enabled.</span></span> <span data-ttu-id="4031f-111">コンポーネント インターフェイスにキーがある場合は、カスタム メソッドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4031f-111">If the component interface has keys, then custom methods will not work.</span></span>  
  
## <a name="custom-ci-limitation"></a><span data-ttu-id="4031f-112">カスタム CI の制限</span><span class="sxs-lookup"><span data-stu-id="4031f-112">Custom CI Limitation</span></span>  
 <span data-ttu-id="4031f-113">BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスでキーを持っていないこと、カスタム PeopleSoft メソッドを処理できます。</span><span class="sxs-lookup"><span data-stu-id="4031f-113">BizTalk Adapter for PeopleSoft Enterprise can handle custom PeopleSoft methods provided that the component interface does not have keys.</span></span> <span data-ttu-id="4031f-114">コンポーネント インターフェイスにキーがある場合は、カスタム メソッドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4031f-114">If the component interface has keys, custom methods will not work.</span></span>  
  
### <a name="workaround"></a><span data-ttu-id="4031f-115">回避策</span><span class="sxs-lookup"><span data-stu-id="4031f-115">Workaround</span></span>  
 <span data-ttu-id="4031f-116">無効なキーを呼び出しのパラメーターの一部として、キーが組み込まれている新しいカスタム メソッドを作成、新しいコンポーネント インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4031f-116">Create a new component interface that does not have keys, and write a new custom method that incorporates the keys as part of the calling parameters.</span></span> <span data-ttu-id="4031f-117">たとえばは USER_PROFILE コンポーネント インターフェイスで SetPassword カスタム メソッドを使用できます。ただし USER_PROFILE には、キーがあります。</span><span class="sxs-lookup"><span data-stu-id="4031f-117">For example, you could use the SetPassword custom method in the USER_PROFILE component interface; however USER_PROFILE has keys.</span></span> <span data-ttu-id="4031f-118">キーのない新しいコンポーネント インターフェイスを作成し、新しいコンポーネント インターフェイスでカスタム メソッドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4031f-118">You can create a new component interface that has no keys, and then create a custom method in your new component interface.</span></span> <span data-ttu-id="4031f-119">このメソッドは、2 つのパラメーター、ユーザー ID とパスワードを受け入れるとします。</span><span class="sxs-lookup"><span data-stu-id="4031f-119">This method would accept two parameters, user ID and password.</span></span> <span data-ttu-id="4031f-120">カスタム メソッドでした USER_PROFILE を呼び出し、 `Get` 、呼び出す`SetPassword`します。</span><span class="sxs-lookup"><span data-stu-id="4031f-120">The custom method could then invoke USER_PROFILE with a `Get` and then invoke `SetPassword`.</span></span> <span data-ttu-id="4031f-121">詳細については、PeopleSoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4031f-121">Consult the PeopleSoft documentation for more details.</span></span>  
  
 <span data-ttu-id="4031f-122">Peoplesoft の制限により`Date`、 `DateTime`、および`Time`クライアント コードで文字列としてユーザー定義メソッドに出現する型がマップされます。</span><span class="sxs-lookup"><span data-stu-id="4031f-122">Due to a limitation in PeopleSoft, `Date`, `DateTime`, and `Time` types appearing in user-defined methods are mapped as strings in the client code.</span></span>  
  
## <a name="collection-limitation"></a><span data-ttu-id="4031f-123">コレクションの制限</span><span class="sxs-lookup"><span data-stu-id="4031f-123">Collection Limitation</span></span>  
 <span data-ttu-id="4031f-124">ユーザー定義のメソッドは、コレクション、または複数を返すことはできません、API オブジェクトでは一般に、します。</span><span class="sxs-lookup"><span data-stu-id="4031f-124">User-defined methods cannot return a collection, or more generally, any API object.</span></span> <span data-ttu-id="4031f-125">これは、文字列や数値などの単純型を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4031f-125">This means that you can only return simple types, for example, strings and numbers.</span></span> <span data-ttu-id="4031f-126">正しい形式に項目を抽出する文字列を解析する XML 文字列としてコレクションを送信して、クライアントをプログラミングでこの制限を回避取得できます。</span><span class="sxs-lookup"><span data-stu-id="4031f-126">You can get around this limitation by sending a collection as an XML string and programming the client to parse the strings to extract the items into the correct format.</span></span> <span data-ttu-id="4031f-127">この回避策の例を参照する GET_CI_INFO カスタム コンポーネント インターフェイスを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4031f-127">You can examine the GET_CI_INFO custom component interface to see an example of this workaround.</span></span>  
  
## <a name="sample-custom-method"></a><span data-ttu-id="4031f-128">サンプル カスタム メソッド</span><span class="sxs-lookup"><span data-stu-id="4031f-128">Sample Custom Method</span></span>  
 <span data-ttu-id="4031f-129">次基本的なカスタム メソッド SayHello を使用すると、カスタム メソッドを使用してコンポーネント インターフェイスの機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="4031f-129">You can use the following basic custom method, SayHello, to test the functionality of your component interface using custom methods.</span></span>  
  
 <span data-ttu-id="4031f-130">次の PeopleCode 関数は、ACB_EMPLOYEE という名前の PeopleSoft コンポーネント インターフェイスのユーザー定義メソッドです。</span><span class="sxs-lookup"><span data-stu-id="4031f-130">The following PeopleCode function is a user-defined method of a PeopleSoft component interface named ACB_EMPLOYEE.</span></span> <span data-ttu-id="4031f-131">このサンプルは、戻り値が文字列を返します**こんにちは**後に、入力パラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="4031f-131">The sample returns a string where the return value is **Hello** followed by the value of the input parameter.</span></span>  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  <span data-ttu-id="4031f-132">(1 つのコマンドを使用) と同時に複数のテーブルを変更するには、別のコンポーネント インターフェイスを作成するか、コンポーネント インターフェイス ユーザー定義メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="4031f-132">To modify multiple tables at the same time (using one command) you can either create another component interface or create a component interface user-defined method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4031f-133">参照</span><span class="sxs-lookup"><span data-stu-id="4031f-133">See Also</span></span>  
 [<span data-ttu-id="4031f-134">付録 a:コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="4031f-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)