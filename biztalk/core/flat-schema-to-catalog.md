---
title: "カタログにスキーマをフラット |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0e37afa-2329-4691-9fa1-82b8c7bcd59a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f3a45ad66ca10ab829a4cc7279891487124c3cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="flat-schema-to-catalog"></a>カタログに対するフラット スキーマ

## <a name="overview"></a>概要
使用することができます、**ループ**functoid を 1 つのレコードを複数のレコードにマップすることによって、フラット スキーマを階層的なスキーマに変換します。 これは、フラット スキーマを Microsoft Commerce Server カタログに変換する場合の一般的な操作です。  
  
 次のコードは、商品カタログの一部を示しています。ここでは、個々の商品バリエーションが単独のレコードとして列挙されています。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 一部またはすべての変換は、カタログのこの部分を展開する、 **ProductVariant**レコードの属性です。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.Catalog">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather"/>  
        <Feature Name="Color" Value="Black"/>  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl"/>  
        <Feature Name="Color" Value="Brown"/>  
    </ProductVariant>  
</ns0:Root>  
```  
  
 次の図は、この変換を実行するためのマップを示しています。  
  
 ![ループ functoid の使用方法を示すマップです。] (../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")  
ループ Functoid (フラット スキーマ マップ)  

## <a name="set-the-schema"></a>スキーマを設定します。  
 このタイプのマップを正しく動作させるためには、次の作業を行う必要があります。  
  
-   接続する各リンクについて、**名前**送信先スキーマのフィールドに、送信元スキーマの名前をコピーするリンクのプロパティを設定します。 詳細については、次を参照してください。[構成リンク](../core/configuring-links.md)です。 参照してください**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
-   接続する各リンクについて、**値**送信先スキーマのフィールドに、送信元スキーマ (既定値) の値をコピーするリンクのプロパティを設定します。  
  
-   リンクの接続するため、**ループ**という名前のレコードを functoid**機能**送信先スキーマのプロパティを設定、送信先スキーマのリンク上から下へのリンクを一致するようにします。  
  
 このマッピングの逆関数、カタログ スキーマをフラット スキーマに変換するを参照してください[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)です。  
  
## <a name="see-also"></a>参照  
 [マップにループ Functoid を追加する方法](../core/how-to-add-looping-functoids-to-a-map.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)