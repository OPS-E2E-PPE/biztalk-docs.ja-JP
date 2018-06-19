---
title: 複数のレコードを処理する XPath セレクターを編集する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, editing multiple records
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: ef7e1f8d-2e29-4cef-b558-0090648bffc0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c9b45e3fce9f4ad5730d7f03d2a568b3701742
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254162"
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a><span data-ttu-id="c6097-102">複数のレコードを処理する XPath セレクターの編集方法</span><span class="sxs-lookup"><span data-stu-id="c6097-102">How to Edit XPath Selector to Process Multiple Records</span></span>
<span data-ttu-id="c6097-103">1 つの子 TypedXmlDocuments が作成、TypedXmlDocument がエンジンにアサートされる場合参照してください[Assert](../core/assert.md)です。</span><span class="sxs-lookup"><span data-stu-id="c6097-103">Separate child TypedXmlDocuments are created when a TypedXmlDocument is asserted into the engine; see [Assert](../core/assert.md).</span></span> <span data-ttu-id="c6097-104">エンジンは、ルールで定義された XPath セレクターに基づいて、作成される子の TypedXmlDocuments を決定します。</span><span class="sxs-lookup"><span data-stu-id="c6097-104">The engine determines which child TypedXmlDocuments to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="c6097-105">作成ツールでルールを構築する場合、XPath セレクターの既定値は、ファクト エクスプローラーの [XML スキーマ] タブで選択されているノードよりも上位にあるノードになります。</span><span class="sxs-lookup"><span data-stu-id="c6097-105">When you build rules in the Composer, the XPath Selector value defaults to the node above the node selected in the XML Schemas tab in the Facts Explorer.</span></span> <span data-ttu-id="c6097-106">選択したノード自体に、その親ノードに対する XPath フィールドの値が既定値です。</span><span class="sxs-lookup"><span data-stu-id="c6097-106">The XPath Field value defaults to the selected node itself, relative to its parent node.</span></span>  
  
 <span data-ttu-id="c6097-107">場合によっては、ルールを構築する際に、作成ツールで作成される既定の XPath をカスタマイズすることがあります。</span><span class="sxs-lookup"><span data-stu-id="c6097-107">In some situations you may want to customize the default XPath that the Composer creates when building rules.</span></span> <span data-ttu-id="c6097-108">次のサンプル XML ドキュメントを例として説明します。</span><span class="sxs-lookup"><span data-stu-id="c6097-108">Assume the following sample XML document.</span></span>  
  
```  
<Order>  
   <Orderline>  
      <Hat style="Baseball">                        
         <Cost>10</Cost>  
      </Hat>  
      <Shirt color="Black">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
   <Orderline>  
      <Hat style="Bowler">                        
         <Cost>20</Cost>  
      </Hat>  
      <Shirt color="Red">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
</Order>  
```  
  
 <span data-ttu-id="c6097-109">各 "Orderline" の合計値を計算するルールを構築すると仮定します。</span><span class="sxs-lookup"><span data-stu-id="c6097-109">Assume that you want to build a rule that calculates the Total value for each Orderline.</span></span> <span data-ttu-id="c6097-110">ルールは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c6097-110">Your rule would look like the following.</span></span>  
  
 <span data-ttu-id="c6097-111">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="c6097-111">IF 1==1</span></span>  
  
 <span data-ttu-id="c6097-112">**/Order/orderline//** 合計 = (**/順序/order/orderline/Hat/** コスト + **/順序/order/orderline/シャツ/** コスト)</span><span class="sxs-lookup"><span data-stu-id="c6097-112">THEN **/Order/Orderline/** Total = (**/Order/Orderline/Hat/** Cost + **/Order/Orderline/Shirt/** Cost)</span></span>  
  
 <span data-ttu-id="c6097-113">XPath の太字は、セレクター部分を示します。残りは、フィールド XPath を表します。</span><span class="sxs-lookup"><span data-stu-id="c6097-113">The bold portion of the XPaths indicate the Selector portion and the remainder represents the Field XPath.</span></span> <span data-ttu-id="c6097-114">これらは、作成ツールによって作成される既定値です。</span><span class="sxs-lookup"><span data-stu-id="c6097-114">These are the defaults built by the Composer.</span></span> <span data-ttu-id="c6097-115">ただし、このポリシーを実行する 6 つのオブジェクトの作成になります: 2 つの Orderline オブジェクト、2 つの Hat オブジェクト、および 2 つの Shirt オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c6097-115">Running this policy, however, would result in the creation of 6 objects—2 Orderline objects, 2 Hat objects, and 2 Shirt objects.</span></span> <span data-ttu-id="c6097-116">"Orderline" の合計値は、Hat オブジェクトおよび Shirt オブジェクトが合わせて計算されます。合計値は、同じ値が常に設定され、最後にルールが実行されてから出力されます。</span><span class="sxs-lookup"><span data-stu-id="c6097-116">The Orderline totals would be calculated for each combination of Hat and Shirt objects and the totals would always be set to the same value, which resulted from the last execution of the rule.</span></span> <span data-ttu-id="c6097-117">ルールは 8 回実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6097-117">The rule would fire 8 times.</span></span> <span data-ttu-id="c6097-118">これは、このシナリオで適切ではありません。</span><span class="sxs-lookup"><span data-stu-id="c6097-118">This is not what is intended in this scenario.</span></span>  
  
 <span data-ttu-id="c6097-119">次のように、XPath の値を編集する解決方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="c6097-119">One solution would be to edit the XPath values to be as follows.</span></span>  
  
 <span data-ttu-id="c6097-120">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="c6097-120">IF 1==1</span></span>  
  
 <span data-ttu-id="c6097-121">**/Order/orderline//** 合計 = (**/order/orderline//** Cost + **/order/orderline//** Cost)</span><span class="sxs-lookup"><span data-stu-id="c6097-121">THEN **/Order/Orderline/** Total = (**/Order/Orderline/** Hat/Cost + **/Order/Orderline/** Shirt/Cost)</span></span>  
  
 <span data-ttu-id="c6097-122">3 つのすべてのフィールドのセレクター XPath 値は、同じ "/Order/Orderline" 値に設定されます。フィールド XPath 値は、適宜に編集されます。</span><span class="sxs-lookup"><span data-stu-id="c6097-122">The Selector XPath values for all three fields have been set to the same /Order/Orderline value and the Field XPath values have been edited accordingly.</span></span> <span data-ttu-id="c6097-123">ノードが [XML スキーマ] タブで選択されている場合に [プロパティ] ウィンドウの XPath セレクター値および XPath フィールド値を変更すると、この処理が実行されます。フィールドをルールの引数にドラッグする前に、この処理を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6097-123">This is done by changing the XPath Selector and XPath Field values in the Properties window when a node is selected in the XML Schemas tab. This should be done prior to dragging the field into a rule argument.</span></span>  
  
 <span data-ttu-id="c6097-124">この変更を行ったポリシーの実行結果は、"Orderline" の Shirt ノードおよび Hat ノードの "Cost" 値に基づいて各 "Orderline" に対して計算されている合計値になります。</span><span class="sxs-lookup"><span data-stu-id="c6097-124">Executing the policy with this change would result in the Total value being correctly calculated for each Orderline based on the Cost values of the Shirt and Hat nodes within that Orderline.</span></span>