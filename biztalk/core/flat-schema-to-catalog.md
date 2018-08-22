---
title: カタログに対するスキーマをフラット |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0e37afa-2329-4691-9fa1-82b8c7bcd59a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1dc8093d477773d5efbab46670bac7e9c839d8d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999043"
---
# <a name="flat-schema-to-catalog"></a>カタログに対するフラット スキーマ

## <a name="overview"></a>概要
使用することができます、**ループ**functoid を 1 つのレコードを複数のレコードにマップすることによって、フラット スキーマを階層のスキーマに変換します。 これは、フラット スキーマを Microsoft Commerce Server カタログに変換する場合の一般的な操作です。  
  
 次のコードは、商品カタログの一部を示しています。ここでは、個々の商品バリエーションが単独のレコードとして列挙されています。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 一部またはすべての変換は、カタログのこの部分を展開する、 **ProductVariant**属性をレコードにします。  
  
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
  
 ![ループ functoid の使用方法を示すマップ。](../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")  
ループ Functoid (フラット スキーマ マップ)  

## <a name="set-the-schema"></a>スキーマを設定します。  
 このタイプのマップを正しく動作させるためには、次の作業を行う必要があります。  
  
- 接続する各リンクについて、**名前**送信先スキーマのフィールドに、送信元スキーマの名前をコピーするリンクのプロパティを設定します。 詳細については、次を参照してください。[構成リンク](../core/configuring-links.md)します。 参照してください**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
- 接続する各リンクについて、**値**送信先スキーマのフィールドに、送信元スキーマ (既定値) の値をコピーするリンクのプロパティを設定します。  
  
- リンク接続するため、**ループ**という名前のレコードを functoid**機能**送信先スキーマでプロパティを設定、送信先スキーマのリンクを上から下へのリンクと一致します。  
  
  このマッピングの逆関数でのカタログ スキーマをフラット スキーマに変換するを参照してください[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)します。  
  
## <a name="see-also"></a>参照  
 [ループ マップに Functoid を追加する方法](../core/how-to-add-looping-functoids-to-a-map.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)