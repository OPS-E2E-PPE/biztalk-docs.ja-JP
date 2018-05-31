---
title: どのように Namespace サンプルは、動作を追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c76a90a9-5898-43b3-98af-ff546dd97153
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212364030353001cae0589d4d7562641db4b77e6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22294386"
---
# <a name="how-the-add-namespace-sample-works"></a><span data-ttu-id="dbbee-102">どのように Namespace サンプルは、動作を追加</span><span class="sxs-lookup"><span data-stu-id="dbbee-102">How the Add Namespace Sample Works</span></span>
<span data-ttu-id="dbbee-103">1、2、および 4 番目のテストを使用して、**追加 Namespace** NamespaceSampleReceivePipeline パイプラインにコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="dbbee-103">The first, second, and fourth tests use the **Add Namespace** component located in the NamespaceSampleReceivePipeline pipeline.</span></span> <span data-ttu-id="dbbee-104">これは、ルート ノードで、次のよう、名前空間のないドキュメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="dbbee-104">It takes as input a document with no namespace on the root node, such as the following:</span></span>  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  
  
 <span data-ttu-id="dbbee-105">次の表は、プロパティ値の設定、**追加 Namespace**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="dbbee-105">The following table shows the property values set for the **Add Namespace** component.</span></span>  
  
|<span data-ttu-id="dbbee-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dbbee-106">Property</span></span>|<span data-ttu-id="dbbee-107">型</span><span class="sxs-lookup"><span data-stu-id="dbbee-107">Type</span></span>|<span data-ttu-id="dbbee-108">値</span><span class="sxs-lookup"><span data-stu-id="dbbee-108">Value</span></span>|  
|--------------|----------|-----------|  
|<span data-ttu-id="dbbee-109">ExtractionNodeXPath</span><span class="sxs-lookup"><span data-stu-id="dbbee-109">ExtractionNodeXPath</span></span>|<span data-ttu-id="dbbee-110">静的</span><span class="sxs-lookup"><span data-stu-id="dbbee-110">Static</span></span>|<span data-ttu-id="dbbee-111">(空)</span><span class="sxs-lookup"><span data-stu-id="dbbee-111">(empty)</span></span>|  
|<span data-ttu-id="dbbee-112">NamespaceBase</span><span class="sxs-lookup"><span data-stu-id="dbbee-112">NamespaceBase</span></span>|<span data-ttu-id="dbbee-113">静的</span><span class="sxs-lookup"><span data-stu-id="dbbee-113">Static</span></span>|http://schemas.microsoft.biztalk.esb.test.com/test|  
|<span data-ttu-id="dbbee-114">NamespacePrefix</span><span class="sxs-lookup"><span data-stu-id="dbbee-114">NamespacePrefix</span></span>|<span data-ttu-id="dbbee-115">静的</span><span class="sxs-lookup"><span data-stu-id="dbbee-115">Static</span></span>|<span data-ttu-id="dbbee-116">esbTest</span><span class="sxs-lookup"><span data-stu-id="dbbee-116">esbTest</span></span>|  
|<span data-ttu-id="dbbee-117">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="dbbee-117">Separator</span></span>|<span data-ttu-id="dbbee-118">静的</span><span class="sxs-lookup"><span data-stu-id="dbbee-118">Static</span></span>|/|  
|<span data-ttu-id="dbbee-119">XPaths</span><span class="sxs-lookup"><span data-stu-id="dbbee-119">XPaths</span></span>|<span data-ttu-id="dbbee-120">動的</span><span class="sxs-lookup"><span data-stu-id="dbbee-120">Dynamic</span></span>|<span data-ttu-id="dbbee-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span><span class="sxs-lookup"><span data-stu-id="dbbee-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span></span>|  
  
 <span data-ttu-id="dbbee-122">表に示すプロパティの設定により、コンポーネントは 2 つの XPath クエリを実行することによって、XML ドキュメントを検索する/CanonicalOrder/@OrderIDと/CanonicalOrder/@OrderDate(指定された 2 つのクエリ、 **Xpath** 「パイプ」で区切られたプロパティ文字)。</span><span class="sxs-lookup"><span data-stu-id="dbbee-122">The property settings shown in the table cause the component to search the XML document by executing the two XPath queries /CanonicalOrder/@OrderID and /CanonicalOrder/@OrderDate (the two queries specified for the **XPaths** property, separated by a "pipe" character).</span></span> <span data-ttu-id="dbbee-123">これらのクエリの値を返す、 **OrderID**と**OrderDate**属性; ドキュメントのこの例では、ルート ノードの 2 つの値は、"OrderID_0"および"OrderDate_1"です。</span><span class="sxs-lookup"><span data-stu-id="dbbee-123">These queries return the values of the **OrderID** and **OrderDate** attributes of the root node of the document; in this example, the two values are "OrderID_0" and "OrderDate_1".</span></span>  
  
 <span data-ttu-id="dbbee-124">コンポーネントでは、新しいルート名前空間を構築するためにこれらの値とその他のプロパティの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbbee-124">The component then uses these values, and the values of the other properties, to construct the new root namespace.</span></span> <span data-ttu-id="dbbee-125">組み合わされて、 **NamespaceBase**、 **NamespacePrefix**、**区切り**と、次の形式で 2 つの XPath クエリからの値。</span><span class="sxs-lookup"><span data-stu-id="dbbee-125">It combines the **NamespaceBase**, the **NamespacePrefix**, the **Separator**, and the values from the two XPath queries in the following format:</span></span>  
  
```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  
  
 <span data-ttu-id="dbbee-126">次のように、新しい名前空間が生成されます。</span><span class="sxs-lookup"><span data-stu-id="dbbee-126">This produces the new namespace, as shown here:</span></span>  
  
```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  
  
 <span data-ttu-id="dbbee-127">処理した後にそのため、更新されたドキュメント、 **NamespaceSampleReceivePipeline**パイプラインは、次。</span><span class="sxs-lookup"><span data-stu-id="dbbee-127">Therefore, the updated document after processing by the **NamespaceSampleReceivePipeline** pipeline is the following:</span></span>  
  
```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  
  
## <a name="using-the-extractionnodexpath-property"></a><span data-ttu-id="dbbee-128">ExtractionNodeXPath プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbbee-128">Using the ExtractionNodeXPath Property</span></span>  
 <span data-ttu-id="dbbee-129">既定では、**追加 Namespace**名前空間とプレフィックスの情報を追加するときに、コンポーネントがメッセージ内の XML ドキュメントのルート要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbbee-129">By default, the **Add Namespace** component uses the root element of the XML document within the message when adding namespace and prefix information.</span></span> <span data-ttu-id="dbbee-130">設定することができます (エンベロープの特定のシナリオで、または受信ドキュメントの一部だけに関連性がある場合に便利です)、メッセージの本文として XML ドキュメントのサブセットのみを使用する場合、 **ExtractionNodeXPath** を強制的にプロパティ**Namespace を追加**結果メッセージとして使用するための指定した要素をシークするコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="dbbee-130">If you want to use only a subset of the XML document as the message body (useful in certain envelope scenarios or when only a portion of an inbound document has relevance), you can set the **ExtractionNodeXPath** property to force the **Add Namespace** component to seek the specified element for use as the resultant message.</span></span> <span data-ttu-id="dbbee-131">たとえば、受信 CanonicalOrder メッセージを 1 つだけ持つことがわかっている場合**OrderDetails** 、そこに含まれるこのメッセージのコンシューマーを関連する要素を設定できます、 **ExtractionNodeXPath**へのパスを指定するプロパティ、 **OrderDetails**要素。</span><span class="sxs-lookup"><span data-stu-id="dbbee-131">For example, if you know that a received CanonicalOrder message will have only one **OrderDetails** element that is relevant for consumers of this message contained within it, you can set the **ExtractionNodeXPath** property to specify the path to the **OrderDetails** element.</span></span> <span data-ttu-id="dbbee-132">前に説明したパススルー テストに追加を使用して抽出でこのプロセスの例を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="dbbee-132">You can see an example of this process in the Add Via Extraction to Pass-through test described earlier.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbbee-133">**ExtractionNodeXPath**プロパティは、1 つだけの要素を返す XPath をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbbee-133">The **ExtractionNodeXPath** property must be an XPath that returns only one element.</span></span> <span data-ttu-id="dbbee-134">コンポーネントには、結果は要素ではない場合、または XPath クエリには複数の要素が返された場合に、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="dbbee-134">The component will raise an exception if the result is not an element or if the XPath query returns more than one element.</span></span>