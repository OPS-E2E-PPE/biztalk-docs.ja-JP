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
# <a name="flat-schema-to-catalog"></a><span data-ttu-id="a3a6d-102">カタログに対するフラット スキーマ</span><span class="sxs-lookup"><span data-stu-id="a3a6d-102">Flat Schema to Catalog</span></span>

## <a name="overview"></a><span data-ttu-id="a3a6d-103">概要</span><span class="sxs-lookup"><span data-stu-id="a3a6d-103">Overview</span></span>
<span data-ttu-id="a3a6d-104">使用することができます、**ループ**functoid を 1 つのレコードを複数のレコードにマップすることによって、フラット スキーマを階層のスキーマに変換します。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-104">You can use the **Looping** functoid to convert a flat schema to an hierarchical schema by mapping a single record to multiple records.</span></span> <span data-ttu-id="a3a6d-105">これは、フラット スキーマを Microsoft Commerce Server カタログに変換する場合の一般的な操作です。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-105">This is a common operation in converting flat schemas to Microsoft Commerce Server catalogs.</span></span>  
  
 <span data-ttu-id="a3a6d-106">次のコードは、商品カタログの一部を示しています。ここでは、個々の商品バリエーションが単独のレコードとして列挙されています。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-106">The following code shows a portion of a catalog listing product variants with each variant as its own record.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 <span data-ttu-id="a3a6d-107">一部またはすべての変換は、カタログのこの部分を展開する、 **ProductVariant**属性をレコードにします。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-107">Expanding this portion of the catalog would convert some or all of the **ProductVariant** attributes into records.</span></span>  
  
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
  
 <span data-ttu-id="a3a6d-108">次の図は、この変換を実行するためのマップを示しています。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-108">The following figure shows a map that performs this conversion.</span></span>  
  
 <span data-ttu-id="a3a6d-109">![ループ functoid の使用方法を示すマップ。](../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")</span><span class="sxs-lookup"><span data-stu-id="a3a6d-109">![Map showing the use of the looping functoid.](../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")</span></span>  
<span data-ttu-id="a3a6d-110">ループ Functoid (フラット スキーマ マップ)</span><span class="sxs-lookup"><span data-stu-id="a3a6d-110">Looping Functoid, Flat Schema Map</span></span>  

## <a name="set-the-schema"></a><span data-ttu-id="a3a6d-111">スキーマを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-111">Set the schema</span></span>  
 <span data-ttu-id="a3a6d-112">このタイプのマップを正しく動作させるためには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-112">For this type of map to work correctly, you must do the following:</span></span>  
  
- <span data-ttu-id="a3a6d-113">接続する各リンクについて、**名前**送信先スキーマのフィールドに、送信元スキーマの名前をコピーするリンクのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-113">For each link connecting to the **Name** field in the destination schema, set the source-schema link properties to copy the name.</span></span> <span data-ttu-id="a3a6d-114">詳細については、[構成リンク](../core/configuring-links.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-114">For more information, see [Configuring Links](../core/configuring-links.md).</span></span> <span data-ttu-id="a3a6d-115">参照してください**リンク プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-115">Also see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="a3a6d-116">接続する各リンクについて、**値**送信先スキーマのフィールドに、送信元スキーマ (既定値) の値をコピーするリンクのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-116">For each link connecting to the **Value** field in the destination schema, set the source-schema link properties to copy the value (the default).</span></span>  
  
- <span data-ttu-id="a3a6d-117">リンク接続するため、**ループ**という名前のレコードを functoid**機能**送信先スキーマでプロパティを設定、送信先スキーマのリンクを上から下へのリンクと一致します。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-117">For the link connecting the **Looping** functoid to the record named **Feature** in the destination schema, set the destination-schema link properties to match links top-down.</span></span>  
  
  <span data-ttu-id="a3a6d-118">このマッピングの逆関数でのカタログ スキーマをフラット スキーマに変換するを参照してください[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="a3a6d-118">For the inverse of this mapping, converting a catalog schema to a flat schema, see [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a6d-119">参照</span><span class="sxs-lookup"><span data-stu-id="a3a6d-119">See Also</span></span>  
 <span data-ttu-id="a3a6d-120">[ループ マップに Functoid を追加する方法](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="a3a6d-120">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="a3a6d-121">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="a3a6d-121">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="a3a6d-122">値のマッピング (フラット化) Functoid</span><span class="sxs-lookup"><span data-stu-id="a3a6d-122">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)