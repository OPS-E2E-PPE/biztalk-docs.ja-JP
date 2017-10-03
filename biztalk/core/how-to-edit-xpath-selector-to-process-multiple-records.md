---
title: "複数のレコードを処理する XPath セレクターを編集する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, editing multiple records
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: ef7e1f8d-2e29-4cef-b558-0090648bffc0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c9b45e3fce9f4ad5730d7f03d2a568b3701742
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a>複数のレコードを処理する XPath セレクターの編集方法
1 つの子 TypedXmlDocuments が作成、TypedXmlDocument がエンジンにアサートされる場合参照してください[Assert](../core/assert.md)です。 エンジンは、ルールで定義された XPath セレクターに基づいて、作成される子の TypedXmlDocuments を決定します。 作成ツールでルールを構築する場合、XPath セレクターの既定値は、ファクト エクスプローラーの [XML スキーマ] タブで選択されているノードよりも上位にあるノードになります。 選択したノード自体に、その親ノードに対する XPath フィールドの値が既定値です。  
  
 場合によっては、ルールを構築する際に、作成ツールで作成される既定の XPath をカスタマイズすることがあります。 次のサンプル XML ドキュメントを例として説明します。  
  
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
  
 各 "Orderline" の合計値を計算するルールを構築すると仮定します。 ルールは、次のようになります。  
  
 IF 1==1  
  
 **/Order/orderline//**合計 = (**/順序/order/orderline/Hat/**コスト + **/順序/order/orderline/シャツ/**コスト)  
  
 XPath の太字は、セレクター部分を示します。残りは、フィールド XPath を表します。 これらは、作成ツールによって作成される既定値です。 ただし、このポリシーを実行する 6 つのオブジェクトの作成になります: 2 つの Orderline オブジェクト、2 つの Hat オブジェクト、および 2 つの Shirt オブジェクト。 "Orderline" の合計値は、Hat オブジェクトおよび Shirt オブジェクトが合わせて計算されます。合計値は、同じ値が常に設定され、最後にルールが実行されてから出力されます。 ルールは 8 回実行されます。 これは、このシナリオで適切ではありません。  
  
 次のように、XPath の値を編集する解決方法が考えられます。  
  
 IF 1==1  
  
 **/Order/orderline//**合計 = (**/order/orderline//**Cost + **/order/orderline//**Cost)  
  
 3 つのすべてのフィールドのセレクター XPath 値は、同じ "/Order/Orderline" 値に設定されます。フィールド XPath 値は、適宜に編集されます。 ノードが [XML スキーマ] タブで選択されている場合に [プロパティ] ウィンドウの XPath セレクター値および XPath フィールド値を変更すると、この処理が実行されます。フィールドをルールの引数にドラッグする前に、この処理を実行する必要があります。  
  
 この変更を行ったポリシーの実行結果は、"Orderline" の Shirt ノードおよび Hat ノードの "Cost" 値に基づいて各 "Orderline" に対して計算されている合計値になります。