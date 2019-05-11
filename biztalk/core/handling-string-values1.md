---
title: 文字列 Values1 の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, configuring strings
- strings, left-justified
- strings, configuring
- strings, right-justified
ms.assetid: a180b818-1009-45f5-a503-d10ed7dd27fc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a86b4b04b481e094efe703190c8da7dd86e0c14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387605"
---
# <a name="handling-string-values"></a><span data-ttu-id="02840-102">文字列値の処理</span><span class="sxs-lookup"><span data-stu-id="02840-102">Handling String Values</span></span>
<span data-ttu-id="02840-103">このトピックでは右揃えとして特定の文字列引数を構成する方法について説明します (し、左側に埋め込み)。</span><span class="sxs-lookup"><span data-stu-id="02840-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="02840-104">文字列値の型</span><span class="sxs-lookup"><span data-stu-id="02840-104">Types of String Values</span></span>  
 <span data-ttu-id="02840-105">JD Edwards OneWorld では、2 つの種類の相互運用性レイヤーを通じて文字列値を公開します。</span><span class="sxs-lookup"><span data-stu-id="02840-105">JD Edwards OneWorld exposes two kinds of string values through its interoperability layer:</span></span>  
  
- <span data-ttu-id="02840-106">char: 単一の文字</span><span class="sxs-lookup"><span data-stu-id="02840-106">Char: a single character</span></span>  
  
- <span data-ttu-id="02840-107">最大文字列長</span><span class="sxs-lookup"><span data-stu-id="02840-107">maximum length string</span></span>  
  
  <span data-ttu-id="02840-108">JD Edwards OneWorld では、ハンガリアン記法を使用して、ビジネス関数でこれらの型の引数の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="02840-108">JD Edwards OneWorld uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="02840-109">たとえば、これらの型の引数で始まります。</span><span class="sxs-lookup"><span data-stu-id="02840-109">For example, arguments of these types begin with:</span></span>  
  
- <span data-ttu-id="02840-110">c</span><span class="sxs-lookup"><span data-stu-id="02840-110">c</span></span>  
  
- <span data-ttu-id="02840-111">sz</span><span class="sxs-lookup"><span data-stu-id="02840-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="02840-112">左揃えの値</span><span class="sxs-lookup"><span data-stu-id="02840-112">Left-Justified Values</span></span>  
 <span data-ttu-id="02840-113">Sz 型の引数の大半は、最大長の文字列または文字配列、JD Edwards OneWorld には、左揃えの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="02840-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards OneWorld expects a left-justified value.</span></span> <span data-ttu-id="02840-114">住所行のことで、最大長が 40 は、JD Edwards OneWorld で必要があります (たとえば)。</span><span class="sxs-lookup"><span data-stu-id="02840-114">For a street address line, which is of maximum length 40, JD Edwards OneWorld expects (for example):</span></span>  
  
 <span data-ttu-id="02840-115">"4567 Main St"</span><span class="sxs-lookup"><span data-stu-id="02840-115">"4567 Main St.       "</span></span>  
  
 <span data-ttu-id="02840-116">長さ 40 の空白で埋められます。</span><span class="sxs-lookup"><span data-stu-id="02840-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="02840-117">Microsoft BizTalk Adapter for JD Edwards OneWorld では、これを実現するための余白を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="02840-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards OneWorld provides this for you.</span></span> <span data-ttu-id="02840-118">のみ、クライアント コードで「4567 Main st.」を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02840-118">You only need to enter "4567 Main St.", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="02840-119">右揃えの値</span><span class="sxs-lookup"><span data-stu-id="02840-119">Right-Justified Values</span></span>  
 <span data-ttu-id="02840-120">この種類の値のサブセットについては、JD Edwards OneWorld には、左側の余白と右揃えで配置の値が期待しています。</span><span class="sxs-lookup"><span data-stu-id="02840-120">For some subset of values for this type, JD Edwards OneWorld expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="02840-121">たとえば、B4200310 ソース モジュールでビジネス関数の場合、引数 szbusinessunit の長さは 12 です。</span><span class="sxs-lookup"><span data-stu-id="02840-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="02840-122">この引数は、生産施設などのプラントを表します。</span><span class="sxs-lookup"><span data-stu-id="02840-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="02840-123">プラント番号が 30、j. d.</span><span class="sxs-lookup"><span data-stu-id="02840-123">For a plant number of 30, J.D.</span></span> <span data-ttu-id="02840-124">Edwards OneWorld XE では、値が必要です。</span><span class="sxs-lookup"><span data-stu-id="02840-124">Edwards OneWorld XE expects a value of:</span></span>  
  
 <span data-ttu-id="02840-125">"          30"</span><span class="sxs-lookup"><span data-stu-id="02840-125">"          30"</span></span>  
  
 <span data-ttu-id="02840-126">右揃えになる値を入力するには、jdearglist.txt という名前のファイルにパラメーターを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02840-126">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="02840-127">スキーマを生成するときに、jdearglist.txt が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="02840-127">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="02840-128">このテキスト ファイルに記載されている任意の値は自動的に右揃えの値に変換され、左側に空白で埋められます。</span><span class="sxs-lookup"><span data-stu-id="02840-128">Any value that is listed in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="02840-129">エントリをこれらのパラメーターを記述して jdearglist.txt はテキスト エディターを作成し、次のフォルダーに保存する必要があります: %BizTalk_Install_Adapter%\config\JDE\\</span><span class="sxs-lookup"><span data-stu-id="02840-129">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder: %BizTalk_Install_Adapter%\config\JDE\\</span></span>  
  
 <span data-ttu-id="02840-130">場所 **%biztalk_install_adapter** JD Edwards OneWorld を BizTalk Adapter をインストールしたディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="02840-130">Where **%BizTalk_Install_Adapter%** is the directory in which you installed BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
 <span data-ttu-id="02840-131">このファイルが存在しないか、空では場合、アダプターが最初に開いたときに、BizTalk Adapter for JD Edwards OneWorld のログで情報メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02840-131">If this file does not exist or is empty, an informational message appears in the BizTalk Adapter for JD Edwards OneWorld log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02840-132">スキーマの生成後に、このファイルを変更する場合が含まれているデータを更新するスキーマを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02840-132">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span>  
  
 <span data-ttu-id="02840-133">このファイルの最新の情報を使用していることを確認するには、スキーマを再生成する前に、browsingagent.exe プロセスを停止するのにタスク マネージャーを使用できます。ただし、この必要はありません。</span><span class="sxs-lookup"><span data-stu-id="02840-133">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="02840-134">Jdearglist.txt ファイル内のエントリの形式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02840-134">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 <span data-ttu-id="02840-135">例 :</span><span class="sxs-lookup"><span data-stu-id="02840-135">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="02840-136">(同じ型) のような名前付き引数は、同じビジネス モジュールに属するビジネス関数の一連のビジネス機能の一部またはすべての間で共有されます。</span><span class="sxs-lookup"><span data-stu-id="02840-136">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="02840-137">ビジネス関数名ではなく、ワイルドカード文字 (\*) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="02840-137">You can use the wildcard character (\*) instead of the business function name.</span></span> <span data-ttu-id="02840-138">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="02840-138">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  <span data-ttu-id="02840-139">別のコンピューターに、JD Edwards OneWorld のビジネス プロセスをインポートするときに、手動で jdearglist.txt をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02840-139">When importing a JD Edwards OneWorld business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02840-140">参照</span><span class="sxs-lookup"><span data-stu-id="02840-140">See Also</span></span>  
 <span data-ttu-id="02840-141">[Jdearglist での文字列の位置](../core/setting-string-justification-in-jdearglist.md) </span><span class="sxs-lookup"><span data-stu-id="02840-141">[Setting String Justification in Jdearglist](../core/setting-string-justification-in-jdearglist.md) </span></span>  
 [<span data-ttu-id="02840-142">付録 a:データ型</span><span class="sxs-lookup"><span data-stu-id="02840-142">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)