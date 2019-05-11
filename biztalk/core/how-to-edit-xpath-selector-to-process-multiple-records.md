---
title: 複数のレコードを処理する XPath セレクターを編集する方法 |Microsoft Docs
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
ms.openlocfilehash: 826158471dbff3116df55a00f653740ab183e2d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338060"
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a><span data-ttu-id="b4877-102">複数のレコードを処理する XPath セレクターの編集方法</span><span class="sxs-lookup"><span data-stu-id="b4877-102">How to Edit XPath Selector to Process Multiple Records</span></span>
<span data-ttu-id="b4877-103">別の子 TypedXmlDocument がエンジンにアサートされるときに TypedXmlDocuments が作成されました。参照してください[Assert](../core/assert.md)します。</span><span class="sxs-lookup"><span data-stu-id="b4877-103">Separate child TypedXmlDocuments are created when a TypedXmlDocument is asserted into the engine; see [Assert](../core/assert.md).</span></span> <span data-ttu-id="b4877-104">エンジンは、規則で定義された XPath セレクターに基づいて、子の TypedXmlDocuments を作成を決定します。</span><span class="sxs-lookup"><span data-stu-id="b4877-104">The engine determines which child TypedXmlDocuments to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="b4877-105">ルール作成ツールをビルドすると、ファクト エクスプ ローラーで、XML スキーマ タブで選択したノード上のノードが XPath セレクター値に既定値です。</span><span class="sxs-lookup"><span data-stu-id="b4877-105">When you build rules in the Composer, the XPath Selector value defaults to the node above the node selected in the XML Schemas tab in the Facts Explorer.</span></span> <span data-ttu-id="b4877-106">XPath フィールドの値は、その親ノードに相対的な自体には、選択したノードに既定値です。</span><span class="sxs-lookup"><span data-stu-id="b4877-106">The XPath Field value defaults to the selected node itself, relative to its parent node.</span></span>  
  
 <span data-ttu-id="b4877-107">状況によっては既定の規則を作成するときに、作成ツールを作成します XPath をカスタマイズすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b4877-107">In some situations you may want to customize the default XPath that the Composer creates when building rules.</span></span> <span data-ttu-id="b4877-108">次のサンプル XML ドキュメントを想定しています。</span><span class="sxs-lookup"><span data-stu-id="b4877-108">Assume the following sample XML document.</span></span>  
  
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
  
 <span data-ttu-id="b4877-109">各"orderline"の合計値を計算するルールを構築することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="b4877-109">Assume that you want to build a rule that calculates the Total value for each Orderline.</span></span> <span data-ttu-id="b4877-110">ルールは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b4877-110">Your rule would look like the following.</span></span>  
  
 <span data-ttu-id="b4877-111">場合 1 1 = =</span><span class="sxs-lookup"><span data-stu-id="b4877-111">IF 1==1</span></span>  
  
 <span data-ttu-id="b4877-112"><strong>/Order/orderline//</strong>合計 = (<strong>/注文/order/orderline/Hat/</strong>コスト + <strong>/注文/order/orderline/シャツ/</strong>コスト)</span><span class="sxs-lookup"><span data-stu-id="b4877-112">THEN <strong>/Order/Orderline/</strong>Total = (<strong>/Order/Orderline/Hat/</strong>Cost + <strong>/Order/Orderline/Shirt/</strong>Cost)</span></span>  
  
 <span data-ttu-id="b4877-113">Xpath の太字部分は、セレクター部分を示し、残りの部分は、フィールドの XPath を表します。</span><span class="sxs-lookup"><span data-stu-id="b4877-113">The bold portion of the XPaths indicate the Selector portion and the remainder represents the Field XPath.</span></span> <span data-ttu-id="b4877-114">これらは、作成ツールによって作成される既定値です。</span><span class="sxs-lookup"><span data-stu-id="b4877-114">These are the defaults built by the Composer.</span></span> <span data-ttu-id="b4877-115">ただし、このポリシーを実行する 6 つのオブジェクトの作成時になります: 2 つの Orderline オブジェクト、2 つの Hat オブジェクト、および 2 つの Shirt オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b4877-115">Running this policy, however, would result in the creation of 6 objects—2 Orderline objects, 2 Hat objects, and 2 Shirt objects.</span></span> <span data-ttu-id="b4877-116">Orderline 合計 Hat および Shirt オブジェクトの組み合わせごとに計算され、合計常に同じの値は、ルールの最後の実行結果に設定します。</span><span class="sxs-lookup"><span data-stu-id="b4877-116">The Orderline totals would be calculated for each combination of Hat and Shirt objects and the totals would always be set to the same value, which resulted from the last execution of the rule.</span></span> <span data-ttu-id="b4877-117">このルールでは、8 回を実行します。</span><span class="sxs-lookup"><span data-stu-id="b4877-117">The rule would fire 8 times.</span></span> <span data-ttu-id="b4877-118">これは、このシナリオでは適切ではありません。</span><span class="sxs-lookup"><span data-stu-id="b4877-118">This is not what is intended in this scenario.</span></span>  
  
 <span data-ttu-id="b4877-119">1 つのソリューションは、次のように XPath 値を編集することです。</span><span class="sxs-lookup"><span data-stu-id="b4877-119">One solution would be to edit the XPath values to be as follows.</span></span>  
  
 <span data-ttu-id="b4877-120">場合 1 1 = =</span><span class="sxs-lookup"><span data-stu-id="b4877-120">IF 1==1</span></span>  
  
 <span data-ttu-id="b4877-121"><strong>/Order/orderline//</strong>合計 = (<strong>/order/orderline//</strong>Cost + <strong>/order/orderline//</strong>Cost)</span><span class="sxs-lookup"><span data-stu-id="b4877-121">THEN <strong>/Order/Orderline/</strong>Total = (<strong>/Order/Orderline/</strong>Hat/Cost + <strong>/Order/Orderline/</strong>Shirt/Cost)</span></span>  
  
 <span data-ttu-id="b4877-122">次の 3 つのすべてのフィールドのセレクター XPath 値は、同じ/Order/Orderline 値に設定されているし、適宜フィールド XPath 値に編集します。</span><span class="sxs-lookup"><span data-stu-id="b4877-122">The Selector XPath values for all three fields have been set to the same /Order/Orderline value and the Field XPath values have been edited accordingly.</span></span> <span data-ttu-id="b4877-123">これは、XML スキーマ タブで、ノードを選択すると、プロパティ ウィンドウで、XPath セレクターおよび XPath フィールドの値を変更することで行います。これは、ルールの引数にフィールドをドラッグする前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4877-123">This is done by changing the XPath Selector and XPath Field values in the Properties window when a node is selected in the XML Schemas tab. This should be done prior to dragging the field into a rule argument.</span></span>  
  
 <span data-ttu-id="b4877-124">この変更により、ポリシーの実行は、行ったシャツおよび Hat ノードのコストの値に基づいて各"orderline"の計算されている合計値になります。</span><span class="sxs-lookup"><span data-stu-id="b4877-124">Executing the policy with this change would result in the Total value being correctly calculated for each Orderline based on the Cost values of the Shirt and Hat nodes within that Orderline.</span></span>