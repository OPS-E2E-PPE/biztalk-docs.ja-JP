---
title: 文字列 Values2 の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- string values, configuring
- formatting strings
- strings, formatting
- left-justified string values
- jdearglist.txt
- strings, left-justified
- right-justified string values
- strings, right-justified
ms.assetid: 23d54731-b2b9-4610-a533-e041237e0bb3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54d6e6ca9af087139b48465624a681aa5e6125d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344363"
---
# <a name="handling-string-values"></a><span data-ttu-id="d9752-102">文字列値の処理</span><span class="sxs-lookup"><span data-stu-id="d9752-102">Handling String Values</span></span>
<span data-ttu-id="d9752-103">このトピックでは右揃えとして特定の文字列引数を構成する方法について説明します (し、左側に埋め込み)。</span><span class="sxs-lookup"><span data-stu-id="d9752-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="d9752-104">文字列値の型</span><span class="sxs-lookup"><span data-stu-id="d9752-104">Types of String Values</span></span>  
 <span data-ttu-id="d9752-105">JD Edwards EnterpriseOne では、2 つの種類の相互運用性レイヤーを通じて文字列値を公開します。</span><span class="sxs-lookup"><span data-stu-id="d9752-105">JD Edwards EnterpriseOne exposes two kinds of string values through its interoperability layer:</span></span>  
  
- <span data-ttu-id="d9752-106">char: 単一の文字</span><span class="sxs-lookup"><span data-stu-id="d9752-106">char: a single character</span></span>  
  
- <span data-ttu-id="d9752-107">最大文字列長</span><span class="sxs-lookup"><span data-stu-id="d9752-107">maximum length string</span></span>  
  
  <span data-ttu-id="d9752-108">JD Edwards EnterpriseOne では、ハンガリアン記法を使用して、ビジネス関数でこれらの型の引数の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d9752-108">JD Edwards EnterpriseOne uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="d9752-109">たとえば、これらの型の引数で始まります。</span><span class="sxs-lookup"><span data-stu-id="d9752-109">For example, arguments of these types begin with:</span></span>  
  
- <span data-ttu-id="d9752-110">c</span><span class="sxs-lookup"><span data-stu-id="d9752-110">c</span></span>  
  
- <span data-ttu-id="d9752-111">sz</span><span class="sxs-lookup"><span data-stu-id="d9752-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="d9752-112">左揃えの値</span><span class="sxs-lookup"><span data-stu-id="d9752-112">Left-Justified Values</span></span>  
 <span data-ttu-id="d9752-113">Sz 型の引数の大半は、最大長の文字列または文字配列、JD Edwards EnterpriseOne には、左揃えの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9752-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards EnterpriseOne expects a left-justified value.</span></span> <span data-ttu-id="d9752-114">例については、住所行の場合これはの最大長が 40、JD Edwards EnterpriseOne は (たとえば) が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9752-114">For examples, for a street address line, which is of maximum length 40, JD Edwards EnterpriseOne expects (for example):</span></span>  
  
 <span data-ttu-id="d9752-115">"4567 Main St"</span><span class="sxs-lookup"><span data-stu-id="d9752-115">"4567 Main St.    "</span></span>  
  
 <span data-ttu-id="d9752-116">長さ 40 の空白で埋められます。</span><span class="sxs-lookup"><span data-stu-id="d9752-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="d9752-117">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne では、これを実現するための余白を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9752-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides this for you.</span></span> <span data-ttu-id="d9752-118">のみ、クライアント コードで"4567 Main St"を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9752-118">You only need to enter "4567 Main St ", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="d9752-119">右揃えの値</span><span class="sxs-lookup"><span data-stu-id="d9752-119">Right-Justified Values</span></span>  
 <span data-ttu-id="d9752-120">この種類の値のサブセットについては、JD Edwards EnterpriseOne には、左側の余白と右揃えで配置の値が期待しています。</span><span class="sxs-lookup"><span data-stu-id="d9752-120">For some subset of values for this type, JD Edwards EnterpriseOne expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="d9752-121">たとえば、B4200310 ソース モジュールでビジネス関数の場合、引数 szbusinessunit の長さは 12 です。</span><span class="sxs-lookup"><span data-stu-id="d9752-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="d9752-122">この引数は、生産施設などのプラントを表します。</span><span class="sxs-lookup"><span data-stu-id="d9752-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="d9752-123">プラント番号が 30、JD Edwards EnterpriseOne には、値が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9752-123">For a plant number of 30, JD Edwards EnterpriseOne expects a value of:</span></span>  
  
 <span data-ttu-id="d9752-124">"           30"</span><span class="sxs-lookup"><span data-stu-id="d9752-124">"           30"</span></span>  
  
 <span data-ttu-id="d9752-125">右揃えになる値を入力するには、jdearglist.txt という名前のファイルにパラメーターを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9752-125">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="d9752-126">スキーマを生成するときに、jdearglist.txt が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="d9752-126">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="d9752-127">このテキスト ファイル内の値は自動的に右揃えの値に変換され、左側に空白で埋められます。</span><span class="sxs-lookup"><span data-stu-id="d9752-127">Any value in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="d9752-128">エントリをこれらのパラメーターを記述して jdearglist.txt はテキスト エディターを作成し、次のフォルダーに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9752-128">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder:</span></span>  
  
 <span data-ttu-id="d9752-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span><span class="sxs-lookup"><span data-stu-id="d9752-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span></span>  
  
 <span data-ttu-id="d9752-130">このファイルが存在しないか、空では場合、情報メッセージが表示されます BizTalk adapter JD Edwards EnterpriseOne のログのアダプターが最初に開いたとき。</span><span class="sxs-lookup"><span data-stu-id="d9752-130">If this file does not exist or is empty, an informational message appears in BizTalk Adapter for JD Edwards EnterpriseOne log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9752-131">スキーマの生成後に、このファイルを変更する場合が含まれているデータを更新するスキーマを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9752-131">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="d9752-132">このファイルの最新の情報を使用していることを確認するには、スキーマを再生成する前に、browsingagent.exe プロセスを停止するのにタスク マネージャーを使用できます。ただし、この必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9752-132">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="d9752-133">Jdearglist.txt ファイル内のエントリの形式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d9752-133">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 <span data-ttu-id="d9752-134">例 :</span><span class="sxs-lookup"><span data-stu-id="d9752-134">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="d9752-135">(同じ型) のような名前付き引数は、同じビジネス モジュールに属するビジネス関数の一連のビジネス機能の一部またはすべての間で共有されます。</span><span class="sxs-lookup"><span data-stu-id="d9752-135">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="d9752-136">ビジネス関数名ではなく、ワイルドカード文字 (\*) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d9752-136">You can use the wildcard character (\*) instead of the business function name.</span></span> <span data-ttu-id="d9752-137">例 :</span><span class="sxs-lookup"><span data-stu-id="d9752-137">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="d9752-138">別のコンピューターに、JD Edwards EnterpriseOne のビジネス プロセスをインポートするときに、手動で jdearglist.txt をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9752-138">When importing a JD Edwards EnterpriseOne business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9752-139">参照</span><span class="sxs-lookup"><span data-stu-id="d9752-139">See Also</span></span>  
 [<span data-ttu-id="d9752-140">付録 b:データ型</span><span class="sxs-lookup"><span data-stu-id="d9752-140">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)