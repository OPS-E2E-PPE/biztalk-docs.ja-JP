---
title: 文字列 Values2 の処理 |Microsoft ドキュメント
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
ms.openlocfilehash: 024663faa56d92361d861a61a0d64a4608839aa6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22246370"
---
# <a name="handling-string-values"></a><span data-ttu-id="b034e-102">文字列値の処理</span><span class="sxs-lookup"><span data-stu-id="b034e-102">Handling String Values</span></span>
<span data-ttu-id="b034e-103">このトピックでは、一部の文字列引数を右揃え (および左側に埋め込み) で構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b034e-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="b034e-104">文字列値の種類</span><span class="sxs-lookup"><span data-stu-id="b034e-104">Types of String Values</span></span>  
 <span data-ttu-id="b034e-105">JD Edwards EnterpriseOne は、その相互運用性レイヤーを通じて、次の 2 種類の文字列値を公開します。</span><span class="sxs-lookup"><span data-stu-id="b034e-105">JD Edwards EnterpriseOne exposes two kinds of string values through its interoperability layer:</span></span>  
  
-   <span data-ttu-id="b034e-106">char: 単一の文字</span><span class="sxs-lookup"><span data-stu-id="b034e-106">char: a single character</span></span>  
  
-   <span data-ttu-id="b034e-107">最大文字列長</span><span class="sxs-lookup"><span data-stu-id="b034e-107">maximum length string</span></span>  
  
 <span data-ttu-id="b034e-108">JD Edwards EnterpriseOne では、ハンガリアン記法を使用して、ビジネス関数でこれらの型の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b034e-108">JD Edwards EnterpriseOne uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="b034e-109">たとえば、これらの種類の引数は以下から始まります。</span><span class="sxs-lookup"><span data-stu-id="b034e-109">For example, arguments of these types begin with:</span></span>  
  
-   <span data-ttu-id="b034e-110">c</span><span class="sxs-lookup"><span data-stu-id="b034e-110">c</span></span>  
  
-   <span data-ttu-id="b034e-111">sz</span><span class="sxs-lookup"><span data-stu-id="b034e-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="b034e-112">左揃えの値</span><span class="sxs-lookup"><span data-stu-id="b034e-112">Left-Justified Values</span></span>  
 <span data-ttu-id="b034e-113">sz 型の引数 (最大長の文字列または文字配列) の大半について、JD Edwards EnterpriseOne では左揃えの値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards EnterpriseOne expects a left-justified value.</span></span> <span data-ttu-id="b034e-114">たとえば最大長が 40 の住所行の場合、JD Edwards EnterpriseOne では次のように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-114">For examples, for a street address line, which is of maximum length 40, JD Edwards EnterpriseOne expects (for example):</span></span>  
  
 <span data-ttu-id="b034e-115">"4567 Main St.    "</span><span class="sxs-lookup"><span data-stu-id="b034e-115">"4567 Main St.    "</span></span>  
  
 <span data-ttu-id="b034e-116">長さ 40 の空白を埋めます。</span><span class="sxs-lookup"><span data-stu-id="b034e-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="b034e-117">空白の埋め込みは Microsoft BizTalk Adapter for JD Edwards EnterpriseOne により行われます。</span><span class="sxs-lookup"><span data-stu-id="b034e-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides this for you.</span></span> <span data-ttu-id="b034e-118">クライアント コードで「4567 Main St」を入力する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="b034e-118">You only need to enter "4567 Main St ", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="b034e-119">右揃えの値</span><span class="sxs-lookup"><span data-stu-id="b034e-119">Right-Justified Values</span></span>  
 <span data-ttu-id="b034e-120">この種類の値のサブセットについて、JD Edwards EnterpriseOne では左側に空白が埋め込まれた右揃えの値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-120">For some subset of values for this type, JD Edwards EnterpriseOne expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="b034e-121">たとえば、B4200310 ソース モジュールでのビジネス関数では、場合、引数 szBusinessUnit 長さが 12 です。</span><span class="sxs-lookup"><span data-stu-id="b034e-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="b034e-122">この引数は、生産施設などのプラントを表します。</span><span class="sxs-lookup"><span data-stu-id="b034e-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="b034e-123">プラント番号が 30 の場合、J.D. Edwards EnterpriseOne では次のように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-123">For a plant number of 30, JD Edwards EnterpriseOne expects a value of:</span></span>  
  
 <span data-ttu-id="b034e-124">"           30"</span><span class="sxs-lookup"><span data-stu-id="b034e-124">"           30"</span></span>  
  
 <span data-ttu-id="b034e-125">右揃えの値を入力するには、jdearglist.txt というファイルにパラメーターを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-125">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="b034e-126">スキーマを生成すると、jdearglist.txt が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="b034e-126">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="b034e-127">このテキスト ファイルの任意の値は右揃えの値に自動変換され、左に空白が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="b034e-127">Any value in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="b034e-128">jdearglist.txt はテキスト エディターを使用し、これらのパラメーターを表すエントリを記述して、以下のフォルダーに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-128">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder:</span></span>  
  
 <span data-ttu-id="b034e-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span><span class="sxs-lookup"><span data-stu-id="b034e-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span></span>  
  
 <span data-ttu-id="b034e-130">このファイルが存在しないか空の場合、Microsoft BizTalk Adapter for JD Edwards EnterpriseOne が最初に開くときに情報メッセージがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="b034e-130">If this file does not exist or is empty, an informational message appears in BizTalk Adapter for JD Edwards EnterpriseOne log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b034e-131">スキーマの生成後にこのファイルを変更した場合は、スキーマを再生成してスキーマに含まれるデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-131">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="b034e-132">このファイルに含まれる最新の情報を使用していることを確認するため、スキーマを再生成する前に、タスク マネージャーを使用して browsingagent.exe プロセスを停止することができます。ただし、この確認は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="b034e-132">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="b034e-133">以下は、jdearglist.txt に記述するエントリの形式の例です。</span><span class="sxs-lookup"><span data-stu-id="b034e-133">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 <span data-ttu-id="b034e-134">例:</span><span class="sxs-lookup"><span data-stu-id="b034e-134">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="b034e-135">同じビジネス モジュールに属するビジネス関数の場合、(同じ種類の引数で) 似た名前の付いた引数は、ビジネス関数の一部またはすべてにおいて共有されます。</span><span class="sxs-lookup"><span data-stu-id="b034e-135">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="b034e-136">ビジネス関数名の代わりにワイルドカード文字 (\*) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b034e-136">You can use the wildcard character (\*) instead of the business function name.</span></span> <span data-ttu-id="b034e-137">例:</span><span class="sxs-lookup"><span data-stu-id="b034e-137">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="b034e-138">JD Edwards EnterpriseOne ビジネス プロセスを別のコンピューターにインポートする場合は、手動で jdearglist.txt をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b034e-138">When importing a JD Edwards EnterpriseOne business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b034e-139">参照</span><span class="sxs-lookup"><span data-stu-id="b034e-139">See Also</span></span>  
 [<span data-ttu-id="b034e-140">付録 B: データ型</span><span class="sxs-lookup"><span data-stu-id="b034e-140">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)