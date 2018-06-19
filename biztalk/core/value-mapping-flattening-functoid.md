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
ms.openlocfilehash: d17d5d64409cd434075dfd4c556209864784e4d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287874"
---
# <a name="value-mapping-flattening-functoid"></a><span data-ttu-id="bbdff-102">値のマッピング (フラット化) Functoid</span><span class="sxs-lookup"><span data-stu-id="bbdff-102">Value Mapping (Flattening) Functoid</span></span>
<span data-ttu-id="bbdff-103">**値のマッピング (フラット化)** functoid では、複数のレコードを 1 つのレコードに変換することによって、入力インスタンス メッセージの一部をフラット化することができます。</span><span class="sxs-lookup"><span data-stu-id="bbdff-103">The **Value Mapping (Flattening)** functoid enables you to flatten a portion of an input instance message by converting multiple records into a single record.</span></span> <span data-ttu-id="bbdff-104">これは、Microsoft Commerce Server カタログを変換する場合の一般的な操作です。</span><span class="sxs-lookup"><span data-stu-id="bbdff-104">This is a common operation in converting Microsoft Commerce Server catalogs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbdff-105">**値のマッピング (フラット化)** で functoid を組み合わせることはできません、**ループ**functoid または**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="bbdff-105">The **Value Mapping (Flattening)** functoid should not be combined with the **Looping** functoid or the **Table Looping** functoid.</span></span> <span data-ttu-id="bbdff-106">結果として送信元の下にある対象ノードに依存関係のループはありませんが想定するコンパイル済みのマップにこれらを組み合わせた場合、**ループ**または**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="bbdff-106">If they are combined, it results in a compiled map that assumes there is no source looping dependency for the target nodes that are below the **Looping** or **Table Looping** functoid.</span></span>  
  
 <span data-ttu-id="bbdff-107">次のコードは、商品カタログの一部を示しています。各レコードの特徴をバリアントで示した商品のバリアントが一覧になっています。</span><span class="sxs-lookup"><span data-stu-id="bbdff-107">The following code shows a portion of a catalog listing product variants with each feature of the variant in a separate record.</span></span>  
  
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
  
 <span data-ttu-id="bbdff-108">変換は、カタログのこの部分をフラット化、**機能**レコードの属性を**ProductVariant**レコード。</span><span class="sxs-lookup"><span data-stu-id="bbdff-108">Flattening this portion of the catalog would convert the **Feature** records into attributes of the **ProductVariant** record.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsOut">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 <span data-ttu-id="bbdff-109">次の図は、この変換を実行するためのマップを示しています。</span><span class="sxs-lookup"><span data-stu-id="bbdff-109">The following figure shows a map that performs this conversion.</span></span>  
  
 <span data-ttu-id="bbdff-110">![Functoid を使用して基になるレコードをマップします。] (../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")</span><span class="sxs-lookup"><span data-stu-id="bbdff-110">![Map source records using a functoid.](../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")</span></span>  
<span data-ttu-id="bbdff-111">値のマッピング (フラット化) のマップ</span><span class="sxs-lookup"><span data-stu-id="bbdff-111">Value Mapping (Flattening) Functoid Map</span></span>  
  
 <span data-ttu-id="bbdff-112">**値のマッピング (フラット化)** functoid は、最初のパラメーターが true の場合に、2 番目のパラメーターの値を返します。</span><span class="sxs-lookup"><span data-stu-id="bbdff-112">The **Value Mapping (Flattening)** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="bbdff-113">このマップの最初の**等しい**functoid テストかどうかを**名前**属性が"Material"と等しい。</span><span class="sxs-lookup"><span data-stu-id="bbdff-113">In this map, the first **Equal** functoid tests to see if the **Name** attribute is equal to "Material".</span></span> <span data-ttu-id="bbdff-114">属性が"Material"と等しい場合、**等しい**functoid を返します**True**です。</span><span class="sxs-lookup"><span data-stu-id="bbdff-114">If the attribute is equal to "Material", the **Equal** functoid returns **True**.</span></span> <span data-ttu-id="bbdff-115">これにより、**値のマッピング (フラット化)** の値を代入する functoid、**値**属性の出力メッセージのフィールドにします。</span><span class="sxs-lookup"><span data-stu-id="bbdff-115">In turn, this causes the **Value Mapping (Flattening)** functoid to assign the value of the **Value** attribute to the field in the output message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbdff-116">参照</span><span class="sxs-lookup"><span data-stu-id="bbdff-116">See Also</span></span>  
 <span data-ttu-id="bbdff-117">[値のマッピング (フラット化) Functoid をマップに追加する方法](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="bbdff-117">[How to Add Value Mapping (Flattening) Functoids to a Map](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="bbdff-118">[カタログに対するフラット スキーマ](../core/flat-schema-to-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="bbdff-118">[Flat Schema to Catalog](../core/flat-schema-to-catalog.md) </span></span>  
 [<span data-ttu-id="bbdff-119">高度な Functoid</span><span class="sxs-lookup"><span data-stu-id="bbdff-119">Advanced Functoids</span></span>](../core/advanced-functoids.md)