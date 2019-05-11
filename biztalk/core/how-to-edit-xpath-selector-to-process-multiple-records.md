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
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a>複数のレコードを処理する XPath セレクターの編集方法
別の子 TypedXmlDocument がエンジンにアサートされるときに TypedXmlDocuments が作成されました。参照してください[Assert](../core/assert.md)します。 エンジンは、規則で定義された XPath セレクターに基づいて、子の TypedXmlDocuments を作成を決定します。 ルール作成ツールをビルドすると、ファクト エクスプ ローラーで、XML スキーマ タブで選択したノード上のノードが XPath セレクター値に既定値です。 XPath フィールドの値は、その親ノードに相対的な自体には、選択したノードに既定値です。  
  
 状況によっては既定の規則を作成するときに、作成ツールを作成します XPath をカスタマイズすることがあります。 次のサンプル XML ドキュメントを想定しています。  
  
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
  
 各"orderline"の合計値を計算するルールを構築することを想定しています。 ルールは、次のようになります。  
  
 場合 1 1 = =  
  
 <strong>/Order/orderline//</strong>合計 = (<strong>/注文/order/orderline/Hat/</strong>コスト + <strong>/注文/order/orderline/シャツ/</strong>コスト)  
  
 Xpath の太字部分は、セレクター部分を示し、残りの部分は、フィールドの XPath を表します。 これらは、作成ツールによって作成される既定値です。 ただし、このポリシーを実行する 6 つのオブジェクトの作成時になります: 2 つの Orderline オブジェクト、2 つの Hat オブジェクト、および 2 つの Shirt オブジェクト。 Orderline 合計 Hat および Shirt オブジェクトの組み合わせごとに計算され、合計常に同じの値は、ルールの最後の実行結果に設定します。 このルールでは、8 回を実行します。 これは、このシナリオでは適切ではありません。  
  
 1 つのソリューションは、次のように XPath 値を編集することです。  
  
 場合 1 1 = =  
  
 <strong>/Order/orderline//</strong>合計 = (<strong>/order/orderline//</strong>Cost + <strong>/order/orderline//</strong>Cost)  
  
 次の 3 つのすべてのフィールドのセレクター XPath 値は、同じ/Order/Orderline 値に設定されているし、適宜フィールド XPath 値に編集します。 これは、XML スキーマ タブで、ノードを選択すると、プロパティ ウィンドウで、XPath セレクターおよび XPath フィールドの値を変更することで行います。これは、ルールの引数にフィールドをドラッグする前に実行する必要があります。  
  
 この変更により、ポリシーの実行は、行ったシャツおよび Hat ノードのコストの値に基づいて各"orderline"の計算されている合計値になります。