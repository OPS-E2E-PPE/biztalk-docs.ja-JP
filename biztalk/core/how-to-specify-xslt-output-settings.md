---
title: "出力設定の XSLT を指定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c541432-fd4e-41cc-8bcc-f570ce5df439
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1aa3eea4c3f2f4696d3dc1fdf8109aeddec3ff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="set-map-compilation-and-output-settings"></a><span data-ttu-id="90b20-102">マップのコンパイルを設定し、出力設定</span><span class="sxs-lookup"><span data-stu-id="90b20-102">Set map compilation and output settings</span></span>
<span data-ttu-id="90b20-103">BizTalk マッパーでマップのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="90b20-103">Set the map properties in the BizTalk mapper.</span></span> 

<span data-ttu-id="90b20-104">これらを使用してマップのプロパティは、マップのコンパイル方法を設定、含めるまたは、XML 宣言を除外するし、エンコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="90b20-104">Using these map properties, you can set how maps are compiled, include or exclude an XML declaration, and set the encoding.</span></span> 

<span data-ttu-id="90b20-105">このトピックでは、マップ上でこれらのプロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="90b20-105">This topic shows you how to set these properties on your map.</span></span>

## <a name="set-the-map-level-compilation"></a><span data-ttu-id="90b20-106">マップ レベルのコンパイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="90b20-106">Set the map-level compilation</span></span>

<span data-ttu-id="90b20-107">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**を選択する、`XslTransform`または`XslCompiledTransform`マップをコンパイルするクラス。</span><span class="sxs-lookup"><span data-stu-id="90b20-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you choose the `XslTransform` or the `XslCompiledTransform` class to compile your maps.</span></span> 

1. <span data-ttu-id="90b20-108">グリッド ビューでは、マップを開きます。</span><span class="sxs-lookup"><span data-stu-id="90b20-108">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="90b20-109">マッパー グリッドの任意の場所を右クリックし、選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="90b20-109">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="90b20-110">設定、**使用 XSL 変換**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="90b20-110">Set the **Use XSL Transform** property:</span></span> 

    | <span data-ttu-id="90b20-111">オプション</span><span class="sxs-lookup"><span data-stu-id="90b20-111">Option</span></span> | <span data-ttu-id="90b20-112">Description</span><span class="sxs-lookup"><span data-stu-id="90b20-112">Description</span></span> |
    | --- | --- |
    | <span data-ttu-id="90b20-113">未定義。</span><span class="sxs-lookup"><span data-stu-id="90b20-113">Undefined</span></span> | <span data-ttu-id="90b20-114">XslTransform 設定のレジストリ フラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="90b20-114">The registry flag for the XslTransform setting is used:</span></span> <ul><li><span data-ttu-id="90b20-115">64 ビット ホスト インスタンス:`HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="90b20-115">64-bit host instances: `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li><li><span data-ttu-id="90b20-116">32 ビット ホスト インスタンス、および Visual Studio のマップのテスト機能:`HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="90b20-116">32-bit host instances, and Visual Studio’s Test Map functionality: `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li></ul> | 
    | <span data-ttu-id="90b20-117">True</span><span class="sxs-lookup"><span data-stu-id="90b20-117">True</span></span> | <span data-ttu-id="90b20-118">マップのコンパイルのレベル プロパティに設定`XslTransform`(従来の動作)</span><span class="sxs-lookup"><span data-stu-id="90b20-118">The map level compilation property is set to `XslTransform` (legacy behavior)</span></span> | 
    | <span data-ttu-id="90b20-119">False</span><span class="sxs-lookup"><span data-stu-id="90b20-119">False</span></span> | <span data-ttu-id="90b20-120">マップのコンパイルのレベル プロパティに設定します。`XslCompiledTransform`</span><span class="sxs-lookup"><span data-stu-id="90b20-120">The map level compilation property is set to `XslCompiledTransform`</span></span> | 

> [!NOTE] 
> <span data-ttu-id="90b20-121">BizTalk Server 2013 以降では、マッパー コンパイルの動作が変更されたから`XslTransform`に`XslCompiledTransform`です。</span><span class="sxs-lookup"><span data-stu-id="90b20-121">Starting with BizTalk Server 2013, the mapper compilation behavior was changed from `XslTransform` to `XslCompiledTransform`.</span></span> <span data-ttu-id="90b20-122">[、マッパーの更新プログラムの意味を](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)ブログの投稿に説明優れたの動作とその考えられる影響します。</span><span class="sxs-lookup"><span data-stu-id="90b20-122">The [What the Mapper Updates Mean for You](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) blog post provides a great explanation of the behavior, and its potential impact.</span></span> 
> 
> <span data-ttu-id="90b20-123">以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、どのクラスをマップをコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="90b20-123">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can choose which class to compile your maps.</span></span> 
  
## <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="90b20-124">XML 宣言のエクスクルードまたはインクルード</span><span class="sxs-lookup"><span data-stu-id="90b20-124">Include or exclude an XML declaration</span></span>  
<span data-ttu-id="90b20-125">XML 宣言があるか出力かどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="90b20-125">You can choose whether an XML declaration is output or not.</span></span> 

1. <span data-ttu-id="90b20-126">グリッド ビューでは、マップを開きます。</span><span class="sxs-lookup"><span data-stu-id="90b20-126">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="90b20-127">マッパー グリッドの任意の場所を右クリックし、選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="90b20-127">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="90b20-128">ドロップダウン リストで、 **XML 宣言の省略**プロパティで、**はい**XML 宣言を省略する場合。</span><span class="sxs-lookup"><span data-stu-id="90b20-128">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration.</span></span> <span data-ttu-id="90b20-129">選択**いいえ**XML 宣言を省略するされません。</span><span class="sxs-lookup"><span data-stu-id="90b20-129">Select **No** not to omit an XML declaration.</span></span>  

<span data-ttu-id="90b20-130">XML 宣言が表示されます (選択した場合は**いいえ**) 次のようにします。</span><span class="sxs-lookup"><span data-stu-id="90b20-130">An XML declaration would appear (if you selected **No**) similar to the following.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="90b20-131">出力インスタンス データのエンコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="90b20-131">Set encoding for output instance data</span></span>  
<span data-ttu-id="90b20-132">"エンコード" プロパティによって、マップの出力結果の作成で必要となる文字セットに関する情報が、ランタイム エンジンに提供されます。</span><span class="sxs-lookup"><span data-stu-id="90b20-132">Encoding provides the run-time engine with the information it needs to determine which character set to use when creating the output result of a map.</span></span>  
   
1. <span data-ttu-id="90b20-133">グリッド ビューでは、マップを開きます。</span><span class="sxs-lookup"><span data-stu-id="90b20-133">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="90b20-134">マッパー グリッドの任意の場所を右クリックし、選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="90b20-134">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>    
3.  <span data-ttu-id="90b20-135">ドロップダウン リストで、 **XSLT エンコード**プロパティ、文字セットを選択する出力インスタンス データに使用します。</span><span class="sxs-lookup"><span data-stu-id="90b20-135">In the drop-down list for the **XSLT Encoding** property, select the character set you want used for the output instance data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b20-136">参照</span><span class="sxs-lookup"><span data-stu-id="90b20-136">See Also</span></span>  
 <span data-ttu-id="90b20-137">[コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="90b20-137">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="90b20-138">[BizTalk マッパーの使用](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="90b20-138">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="90b20-139">BizTalk マッパーの有効な XSLT エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="90b20-139">Valid BizTalk Mapper XSLT Encoding Types</span></span>](../core/valid-biztalk-mapper-xslt-encoding-types.md)