---
title: "文字列 Values1 の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, configuring strings
- strings, left-justified
- strings, configuring
- strings, right-justified
ms.assetid: a180b818-1009-45f5-a503-d10ed7dd27fc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f32b29b9a8688fe8402730c1db8f12e42a67bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handling-string-values"></a><span data-ttu-id="2a892-102">文字列値の処理</span><span class="sxs-lookup"><span data-stu-id="2a892-102">Handling String Values</span></span>
<span data-ttu-id="2a892-103">このトピックでは、一部の文字列引数を右揃え (および左側に埋め込み) で構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a892-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="2a892-104">文字列値の種類</span><span class="sxs-lookup"><span data-stu-id="2a892-104">Types of String Values</span></span>  
 <span data-ttu-id="2a892-105">JD Edwards OneWorld は、その相互運用性レイヤーを通じて、次の 2 種類の文字列値を公開します。</span><span class="sxs-lookup"><span data-stu-id="2a892-105">JD Edwards OneWorld exposes two kinds of string values through its interoperability layer:</span></span>  
  
-   <span data-ttu-id="2a892-106">char: 単一の文字</span><span class="sxs-lookup"><span data-stu-id="2a892-106">Char: a single character</span></span>  
  
-   <span data-ttu-id="2a892-107">最大文字列長</span><span class="sxs-lookup"><span data-stu-id="2a892-107">maximum length string</span></span>  
  
 <span data-ttu-id="2a892-108">JD Edwards OneWorld のビジネス関数では、ハンガリアン記法を使用してこれらの型の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a892-108">JD Edwards OneWorld uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="2a892-109">たとえば、これらの種類の引数は以下から始まります。</span><span class="sxs-lookup"><span data-stu-id="2a892-109">For example, arguments of these types begin with:</span></span>  
  
-   <span data-ttu-id="2a892-110">c</span><span class="sxs-lookup"><span data-stu-id="2a892-110">c</span></span>  
  
-   <span data-ttu-id="2a892-111">sz</span><span class="sxs-lookup"><span data-stu-id="2a892-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="2a892-112">左揃えの値</span><span class="sxs-lookup"><span data-stu-id="2a892-112">Left-Justified Values</span></span>  
 <span data-ttu-id="2a892-113">sz 型の引数 (最大長の文字列または文字配列) の大半について、JD Edwards OneWorld では左揃えの値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a892-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards OneWorld expects a left-justified value.</span></span> <span data-ttu-id="2a892-114">たとえば最大長が 40 の住所行の場合、JD Edwards OneWorld では次のように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a892-114">For a street address line, which is of maximum length 40, JD Edwards OneWorld expects (for example):</span></span>  
  
 <span data-ttu-id="2a892-115">"4567 Main St"</span><span class="sxs-lookup"><span data-stu-id="2a892-115">"4567 Main St.       "</span></span>  
  
 <span data-ttu-id="2a892-116">長さ 40 の空白を埋めます。</span><span class="sxs-lookup"><span data-stu-id="2a892-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="2a892-117">空白の埋め込みは Microsoft BizTalk Adapter for JD Edwards OneWorld により行われます。</span><span class="sxs-lookup"><span data-stu-id="2a892-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards OneWorld provides this for you.</span></span> <span data-ttu-id="2a892-118">このため、クライアント コードに入力する必要があるのは「4567 Main St.」だけです。</span><span class="sxs-lookup"><span data-stu-id="2a892-118">You only need to enter "4567 Main St.", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="2a892-119">右揃えの値</span><span class="sxs-lookup"><span data-stu-id="2a892-119">Right-Justified Values</span></span>  
 <span data-ttu-id="2a892-120">この種類の値のサブセットについて、JD Edwards OneWorld では左側に空白が埋め込まれた右揃えの値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a892-120">For some subset of values for this type, JD Edwards OneWorld expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="2a892-121">たとえば、B4200310 ソース モジュールでのビジネス関数の場合、引数 szBusinessUnit 長さが 12 です。</span><span class="sxs-lookup"><span data-stu-id="2a892-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="2a892-122">この引数は、生産施設などのプラントを表します。</span><span class="sxs-lookup"><span data-stu-id="2a892-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="2a892-123">プラント番号が 30、j. d.</span><span class="sxs-lookup"><span data-stu-id="2a892-123">For a plant number of 30, J.D.</span></span> <span data-ttu-id="2a892-124">Edwards OneWorld XE では、値が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a892-124">Edwards OneWorld XE expects a value of:</span></span>  
  
 <span data-ttu-id="2a892-125">"          30"</span><span class="sxs-lookup"><span data-stu-id="2a892-125">"          30"</span></span>  
  
 <span data-ttu-id="2a892-126">右揃えになる値を入力するには、jdearglist.txt というファイルにパラメーターを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a892-126">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="2a892-127">スキーマを生成するときに、jdearglist.txt が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="2a892-127">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="2a892-128">このテキスト ファイルに記述される値は右揃えの値に自動変換され、左に空白が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="2a892-128">Any value that is listed in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="2a892-129">Jdearglist.txt をテキスト エディター、エントリを作成、これらのパラメーターを記述して、次のフォルダーに保存する必要があります: %BizTalk_Install_Adapter%\config\JDE\\</span><span class="sxs-lookup"><span data-stu-id="2a892-129">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder: %BizTalk_Install_Adapter%\config\JDE\\</span></span>  
  
 <span data-ttu-id="2a892-130">ここで**%biztalk_install_adapter**がインストールされている BizTalk Adapter for JD Edwards OneWorld ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="2a892-130">Where **%BizTalk_Install_Adapter%** is the directory in which you installed BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
 <span data-ttu-id="2a892-131">このファイルが存在しないか空の場合、Microsoft BizTalk Adapter for JD Edwards OneWorld が最初に開くときに情報メッセージがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="2a892-131">If this file does not exist or is empty, an informational message appears in the BizTalk Adapter for JD Edwards OneWorld log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a892-132">スキーマの生成後にこのファイルを変更した場合は、スキーマを再生成してスキーマに含まれるデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a892-132">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span>  
  
 <span data-ttu-id="2a892-133">このファイルに含まれる最新の情報を使用していることを確認するため、スキーマを再生成する前に、タスク マネージャーを使用して browsingagent.exe プロセスを停止することができます。ただし、この確認は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="2a892-133">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="2a892-134">以下は、jdearglist.txt に記述するエントリの形式の例です。</span><span class="sxs-lookup"><span data-stu-id="2a892-134">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 <span data-ttu-id="2a892-135">例:</span><span class="sxs-lookup"><span data-stu-id="2a892-135">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="2a892-136">同じビジネス モジュールに属するビジネス関数の場合、(同じ種類の引数で) 似た名前の付いた引数は、ビジネス関数の一部またはすべてにおいて共有されます。</span><span class="sxs-lookup"><span data-stu-id="2a892-136">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="2a892-137">ビジネス関数名の代わりにワイルドカード文字 (*) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a892-137">You can use the wildcard character (*) instead of the business function name.</span></span> <span data-ttu-id="2a892-138">例:</span><span class="sxs-lookup"><span data-stu-id="2a892-138">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  <span data-ttu-id="2a892-139">JD Edwards OneWorld ビジネス プロセスを別のコンピューターにインポートする場合は、手動で jdearglist.txt をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a892-139">When importing a JD Edwards OneWorld business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a892-140">参照</span><span class="sxs-lookup"><span data-stu-id="2a892-140">See Also</span></span>  
 <span data-ttu-id="2a892-141">[Jdearglist で文字列の位置揃えの設定](../core/setting-string-justification-in-jdearglist.md) </span><span class="sxs-lookup"><span data-stu-id="2a892-141">[Setting String Justification in Jdearglist](../core/setting-string-justification-in-jdearglist.md) </span></span>  
 [<span data-ttu-id="2a892-142">付録 a: データ型</span><span class="sxs-lookup"><span data-stu-id="2a892-142">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)