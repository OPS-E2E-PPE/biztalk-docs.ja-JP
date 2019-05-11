---
title: 値のマッピング (フラット化) Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping (Flattening) functoids
ms.assetid: d30c3ffe-d3ed-46fd-a692-cd26d042033c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 783bcb19bacfde3833065ddcc18f5889b83881d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292575"
---
# <a name="value-mapping-flattening-functoid"></a>値のマッピング (フラット化) Functoid
**値のマッピング (フラット化)** functoid では、複数のレコードを 1 つのレコードに変換することによって、入力インスタンス メッセージの一部をフラット化することができます。 これは、Microsoft Commerce Server カタログを変換する場合の一般的な操作です。  
  
> [!NOTE]
>  **値のマッピング (フラット化)** で functoid を組み合わせることはできません、**ループ**functoid または**テーブル ループ**functoid です。 結果として送信元の下にある対象ノードに依存関係のループはありませんが想定するコンパイル済みのマップにこれらを組み合わせた場合、**ループ**または**テーブル ループ**functoid です。  
  
 次のコードは、商品カタログの一部を示しています。各レコードの特徴をバリアントで示した商品のバリアントが一覧になっています。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsIn">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather" />  
        <Feature Name="Color" Value="Black" />  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl" />  
        <Feature Name="Color" Value="Brown" />  
    </ProductVariant>  
</nso0:Root>  
```  
  
 変換は、カタログのこの部分をフラット化、**機能**レコードの属性を**ProductVariant**レコード。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsOut">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 次の図は、この変換を実行するためのマップを示しています。  
  
 ![Functoid を使用して基になるレコードをマップします。](../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")  
値のマッピング (フラット化) のマップ  
  
 **値のマッピング (フラット化)** functoid は、最初のパラメーターが true の場合に、2 番目のパラメーターの値を返します。 このマップの最初の**等しい**functoid テストかどうかを**名前**属性が"Material"と等しい。 属性が"Material"と等しい場合、**等しい**functoid を返します**True**です。 これにより、**値のマッピング (フラット化)** の値を代入する functoid、**値**属性の出力メッセージのフィールドにします。  
  
## <a name="see-also"></a>参照  
 [値のマッピング (フラット化) Functoid をマップに追加する方法](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)   
 [カタログに対するフラット スキーマ](../core/flat-schema-to-catalog.md)   
 [高度な Functoid](../core/advanced-functoids.md)