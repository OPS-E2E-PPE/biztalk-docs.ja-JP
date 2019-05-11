---
title: 設定の出力に XSLT を指定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c541432-fd4e-41cc-8bcc-f570ce5df439
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1174466897c94b1a7797c32620e88dae6ae57c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334034"
---
# <a name="set-map-compilation-and-output-settings"></a><span data-ttu-id="f42e6-102">マップのコンパイルの設定し、出力の設定</span><span class="sxs-lookup"><span data-stu-id="f42e6-102">Set map compilation and output settings</span></span>
<span data-ttu-id="f42e6-103">BizTalk マッパーでマップのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-103">Set the map properties in the BizTalk mapper.</span></span> 

<span data-ttu-id="f42e6-104">マップを使用してこれらのプロパティ、マップのコンパイル方法を設定、含めるまたは XML 宣言を除外およびエンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-104">Using these map properties, you can set how maps are compiled, include or exclude an XML declaration, and set the encoding.</span></span> 

<span data-ttu-id="f42e6-105">このトピックでは、マップ上でこれらのプロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-105">This topic shows you how to set these properties on your map.</span></span>

## <a name="set-the-map-level-compilation"></a><span data-ttu-id="f42e6-106">マップ レベルのコンパイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-106">Set the map-level compilation</span></span>

<span data-ttu-id="f42e6-107">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、選択した、`XslTransform`または`XslCompiledTransform`マップをコンパイルするクラス。</span><span class="sxs-lookup"><span data-stu-id="f42e6-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you choose the `XslTransform` or the `XslCompiledTransform` class to compile your maps.</span></span> 

1. <span data-ttu-id="f42e6-108">グリッド ビューでは、マップを開きます。</span><span class="sxs-lookup"><span data-stu-id="f42e6-108">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="f42e6-109">マッパー グリッドで任意の場所を右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-109">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="f42e6-110">設定、 **XSL 変換を使用して**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f42e6-110">Set the **Use XSL Transform** property:</span></span> 

    | <span data-ttu-id="f42e6-111">オプション</span><span class="sxs-lookup"><span data-stu-id="f42e6-111">Option</span></span> | <span data-ttu-id="f42e6-112">説明</span><span class="sxs-lookup"><span data-stu-id="f42e6-112">Description</span></span> |
    | --- | --- |
    | <span data-ttu-id="f42e6-113">未定義。</span><span class="sxs-lookup"><span data-stu-id="f42e6-113">Undefined</span></span> | <span data-ttu-id="f42e6-114">XslTransform 設定のレジストリ フラグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f42e6-114">The registry flag for the XslTransform setting is used:</span></span> <ul><li><span data-ttu-id="f42e6-115">64 ビット ホスト インスタンス: `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="f42e6-115">64-bit host instances: `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li><li><span data-ttu-id="f42e6-116">32 ビットのホスト インスタンス、および Visual Studio のマップのテスト機能: `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="f42e6-116">32-bit host instances, and Visual Studio’s Test Map functionality: `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li></ul> | 
    | <span data-ttu-id="f42e6-117">True</span><span class="sxs-lookup"><span data-stu-id="f42e6-117">True</span></span> | <span data-ttu-id="f42e6-118">マップのコンパイルのレベル プロパティに設定されて`XslTransform`(従来の動作)</span><span class="sxs-lookup"><span data-stu-id="f42e6-118">The map level compilation property is set to `XslTransform` (legacy behavior)</span></span> | 
    | <span data-ttu-id="f42e6-119">False</span><span class="sxs-lookup"><span data-stu-id="f42e6-119">False</span></span> | <span data-ttu-id="f42e6-120">マップのコンパイルのレベル プロパティに設定します。 `XslCompiledTransform`</span><span class="sxs-lookup"><span data-stu-id="f42e6-120">The map level compilation property is set to `XslCompiledTransform`</span></span> | 

> [!NOTE]
> <span data-ttu-id="f42e6-121">BizTalk Server 2013 以降では、コンパイルのマッパーの動作がから変更されました`XslTransform`に`XslCompiledTransform`します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-121">Starting with BizTalk Server 2013, the mapper compilation behavior was changed from `XslTransform` to `XslCompiledTransform`.</span></span> <span data-ttu-id="f42e6-122">[、マッパーの更新プログラムにとって何を意味する](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)ブログの投稿の動作とその潜在的な影響の優れた説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-122">The [What the Mapper Updates Mean for You](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) blog post provides a great explanation of the behavior, and its potential impact.</span></span> 
> 
> <span data-ttu-id="f42e6-123">以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]マップをコンパイルするには、どのクラスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f42e6-123">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can choose which class to compile your maps.</span></span> 
  
## <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="f42e6-124">含めるか、XML 宣言を除外</span><span class="sxs-lookup"><span data-stu-id="f42e6-124">Include or exclude an XML declaration</span></span>  
<span data-ttu-id="f42e6-125">XML 宣言があるか出力かどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f42e6-125">You can choose whether an XML declaration is output or not.</span></span> 

1. <span data-ttu-id="f42e6-126">グリッド ビューでは、マップを開きます。</span><span class="sxs-lookup"><span data-stu-id="f42e6-126">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="f42e6-127">マッパー グリッドで任意の場所を右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-127">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="f42e6-128">ドロップダウン リストで、 **XML 宣言の省略**プロパティで、**はい**XML 宣言を省略する場合。</span><span class="sxs-lookup"><span data-stu-id="f42e6-128">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration.</span></span> <span data-ttu-id="f42e6-129">選択**いいえ**XML 宣言を省略するされません。</span><span class="sxs-lookup"><span data-stu-id="f42e6-129">Select **No** not to omit an XML declaration.</span></span>  

<span data-ttu-id="f42e6-130">XML 宣言が表示されます (選択した場合**いいえ**)、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f42e6-130">An XML declaration would appear (if you selected **No**) similar to the following.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="f42e6-131">出力インスタンス データのエンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-131">Set encoding for output instance data</span></span>  
<span data-ttu-id="f42e6-132">エンコードは、マップの出力結果を作成するときに使用する文字のセットを決定する必要がある情報を使用して、実行時エンジンを提供します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-132">Encoding provides the run-time engine with the information it needs to determine which character set to use when creating the output result of a map.</span></span>  
   
1. <span data-ttu-id="f42e6-133">グリッド ビューでは、マップを開きます。</span><span class="sxs-lookup"><span data-stu-id="f42e6-133">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="f42e6-134">マッパー グリッドで任意の場所を右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-134">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>    
3.  <span data-ttu-id="f42e6-135">ドロップダウン リストで、 **XSLT エンコード**プロパティ、文字セットを選択は、出力インスタンス データに使用します。</span><span class="sxs-lookup"><span data-stu-id="f42e6-135">In the drop-down list for the **XSLT Encoding** property, select the character set you want used for the output instance data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42e6-136">参照</span><span class="sxs-lookup"><span data-stu-id="f42e6-136">See Also</span></span>  
 <span data-ttu-id="f42e6-137">[コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="f42e6-137">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="f42e6-138">[BizTalk マッパーの使用](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="f42e6-138">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="f42e6-139">BizTalk マッパーでの有効な XSLT エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="f42e6-139">Valid BizTalk Mapper XSLT Encoding Types</span></span>](../core/valid-biztalk-mapper-xslt-encoding-types.md)