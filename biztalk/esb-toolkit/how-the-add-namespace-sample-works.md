---
title: どの Namespace サンプルは、動作の追加 |Microsoft Docs
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
ms.openlocfilehash: dccb5aebb19895e05ed424f64b4f2ba431174f6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397110"
---
# <a name="how-the-add-namespace-sample-works"></a><span data-ttu-id="b9270-102">どの Namespace サンプルは、動作を追加</span><span class="sxs-lookup"><span data-stu-id="b9270-102">How the Add Namespace Sample Works</span></span>
<span data-ttu-id="b9270-103">1、2、および 4 番目のテストを使用して、**追加 Namespace** NamespaceSampleReceivePipeline パイプラインにコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="b9270-103">The first, second, and fourth tests use the **Add Namespace** component located in the NamespaceSampleReceivePipeline pipeline.</span></span> <span data-ttu-id="b9270-104">として、次のよう、ルート ノードの名前空間のないドキュメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="b9270-104">It takes as input a document with no namespace on the root node, such as the following:</span></span>  

```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  

 <span data-ttu-id="b9270-105">次の表は、プロパティの値の設定、**追加 Namespace**コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="b9270-105">The following table shows the property values set for the **Add Namespace** component.</span></span>  


|      <span data-ttu-id="b9270-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9270-106">Property</span></span>       |  <span data-ttu-id="b9270-107">型</span><span class="sxs-lookup"><span data-stu-id="b9270-107">Type</span></span>   |                          <span data-ttu-id="b9270-108">値</span><span class="sxs-lookup"><span data-stu-id="b9270-108">Value</span></span>                           |
|---------------------|---------|----------------------------------------------------------|
| <span data-ttu-id="b9270-109">ExtractionNodeXPath</span><span class="sxs-lookup"><span data-stu-id="b9270-109">ExtractionNodeXPath</span></span> | <span data-ttu-id="b9270-110">スタティック</span><span class="sxs-lookup"><span data-stu-id="b9270-110">Static</span></span>  |                         <span data-ttu-id="b9270-111">(空)</span><span class="sxs-lookup"><span data-stu-id="b9270-111">(empty)</span></span>                          |
|    <span data-ttu-id="b9270-112">NamespaceBase</span><span class="sxs-lookup"><span data-stu-id="b9270-112">NamespaceBase</span></span>    | <span data-ttu-id="b9270-113">スタティック</span><span class="sxs-lookup"><span data-stu-id="b9270-113">Static</span></span>  |    http://schemas.microsoft.biztalk.esb.test.com/test    |
|   <span data-ttu-id="b9270-114">NamespacePrefix</span><span class="sxs-lookup"><span data-stu-id="b9270-114">NamespacePrefix</span></span>   | <span data-ttu-id="b9270-115">スタティック</span><span class="sxs-lookup"><span data-stu-id="b9270-115">Static</span></span>  |                         <span data-ttu-id="b9270-116">esbTest</span><span class="sxs-lookup"><span data-stu-id="b9270-116">esbTest</span></span>                          |
|      <span data-ttu-id="b9270-117">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="b9270-117">Separator</span></span>      | <span data-ttu-id="b9270-118">スタティック</span><span class="sxs-lookup"><span data-stu-id="b9270-118">Static</span></span>  |                            /                             |
|       <span data-ttu-id="b9270-119">Xpath</span><span class="sxs-lookup"><span data-stu-id="b9270-119">XPaths</span></span>        | <span data-ttu-id="b9270-120">動的</span><span class="sxs-lookup"><span data-stu-id="b9270-120">Dynamic</span></span> | <span data-ttu-id="b9270-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span><span class="sxs-lookup"><span data-stu-id="b9270-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span></span> |

 <span data-ttu-id="b9270-122">表に示したプロパティの設定により、2 つの XPath クエリを実行することによって、XML ドキュメントを検索するコンポーネント/CanonicalOrder/@OrderIDと/CanonicalOrder/@OrderDate(指定された 2 つのクエリ、 **Xpath** 「パイプ」で区切られたプロパティ文字)。</span><span class="sxs-lookup"><span data-stu-id="b9270-122">The property settings shown in the table cause the component to search the XML document by executing the two XPath queries /CanonicalOrder/@OrderID and /CanonicalOrder/@OrderDate (the two queries specified for the **XPaths** property, separated by a "pipe" character).</span></span> <span data-ttu-id="b9270-123">これらのクエリの値を返す、 **OrderID**と**OrderDate**属性は、ドキュメントのこの例では、ルート ノードの 2 つの値は、"OrderID_0"および"OrderDate_1"。</span><span class="sxs-lookup"><span data-stu-id="b9270-123">These queries return the values of the **OrderID** and **OrderDate** attributes of the root node of the document; in this example, the two values are "OrderID_0" and "OrderDate_1".</span></span>  

 <span data-ttu-id="b9270-124">コンポーネントでは、新しいルート名前空間を作成するのにこれらの値とその他のプロパティの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9270-124">The component then uses these values, and the values of the other properties, to construct the new root namespace.</span></span> <span data-ttu-id="b9270-125">組み合わされています、 **NamespaceBase**、 **NamespacePrefix**、**区切り**、および次の形式では、2 つの XPath クエリから値。</span><span class="sxs-lookup"><span data-stu-id="b9270-125">It combines the **NamespaceBase**, the **NamespacePrefix**, the **Separator**, and the values from the two XPath queries in the following format:</span></span>  

```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  

 <span data-ttu-id="b9270-126">次のように、新しい名前空間が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b9270-126">This produces the new namespace, as shown here:</span></span>  

```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  

 <span data-ttu-id="b9270-127">処理後にそのため、更新されたドキュメント、 **NamespaceSampleReceivePipeline**パイプラインは、次。</span><span class="sxs-lookup"><span data-stu-id="b9270-127">Therefore, the updated document after processing by the **NamespaceSampleReceivePipeline** pipeline is the following:</span></span>  

```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  

## <a name="using-the-extractionnodexpath-property"></a><span data-ttu-id="b9270-128">ExtractionNodeXPath プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="b9270-128">Using the ExtractionNodeXPath Property</span></span>  
 <span data-ttu-id="b9270-129">既定で、**追加 Namespace**名前空間とプレフィックスの情報を追加するときに、コンポーネントがメッセージ内の XML ドキュメントのルート要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9270-129">By default, the **Add Namespace** component uses the root element of the XML document within the message when adding namespace and prefix information.</span></span> <span data-ttu-id="b9270-130">設定することができます (エンベロープの特定のシナリオで、または受信ドキュメントの一部のみに関連性がある場合に便利です)、メッセージ本文として XML ドキュメントのサブセットのみを使用する場合、 **ExtractionNodeXPath**プロパティ、を強制するには**追加 Namespace**結果メッセージとして使用するための指定した要素を検索するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="b9270-130">If you want to use only a subset of the XML document as the message body (useful in certain envelope scenarios or when only a portion of an inbound document has relevance), you can set the **ExtractionNodeXPath** property to force the **Add Namespace** component to seek the specified element for use as the resultant message.</span></span> <span data-ttu-id="b9270-131">たとえば、受信 CanonicalOrder メッセージを 1 つだけ持つことがわかっている場合**OrderDetails**はそれに含まれるこのメッセージのコンシューマーに関連する要素を設定できます、 **ExtractionNodeXPath**へのパスを指定するプロパティ、 **OrderDetails**要素。</span><span class="sxs-lookup"><span data-stu-id="b9270-131">For example, if you know that a received CanonicalOrder message will have only one **OrderDetails** element that is relevant for consumers of this message contained within it, you can set the **ExtractionNodeXPath** property to specify the path to the **OrderDetails** element.</span></span> <span data-ttu-id="b9270-132">前に説明したパススルー テストに追加を使用して抽出では、このプロセスの例を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="b9270-132">You can see an example of this process in the Add Via Extraction to Pass-through test described earlier.</span></span>  

> [!NOTE]
>  <span data-ttu-id="b9270-133">**ExtractionNodeXPath**プロパティを 1 つだけの要素を返す XPath をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9270-133">The **ExtractionNodeXPath** property must be an XPath that returns only one element.</span></span> <span data-ttu-id="b9270-134">コンポーネントには、結果は要素ではない場合、または XPath クエリが 1 つ以上の要素を返す場合に、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="b9270-134">The component will raise an exception if the result is not an element or if the XPath query returns more than one element.</span></span>