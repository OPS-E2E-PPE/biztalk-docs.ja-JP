---
title: レコードおよびフィールドの順序 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, sorting
- XSLT, sorting
ms.assetid: 7fa9b5cd-73bc-496f-a081-4a45da3afe42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826d46fef73400a5d54e2d1154a1647af85294e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263858"
---
# <a name="order-of-records-and-fields"></a><span data-ttu-id="940c9-102">レコードとフィールドの順序</span><span class="sxs-lookup"><span data-stu-id="940c9-102">Order of Records and Fields</span></span>
<span data-ttu-id="940c9-103">BizTalk マッパーで使用する XSLT (Extensible Stylesheet Language Transformations) では、出力要素および属性の出力順が保証されません。</span><span class="sxs-lookup"><span data-stu-id="940c9-103">Extensible Stylesheet Language Transformations (XSLT), as used by BizTalk Mapper, do not guarantee the output order of output elements and attributes.</span></span> <span data-ttu-id="940c9-104">これは、BizTalk マッパーが XSLT を生成するときに、送信先スキーマ構造を調べてからグリッド ページをとおして要素を反映し、送信元スキーマ構造からの値を抽出するためです。</span><span class="sxs-lookup"><span data-stu-id="940c9-104">This is because BizTalk Mapper generates XSLT by examining the destination schema structure, and then propagating elements back through the grid pages to extract values from the source schema structure.</span></span> <span data-ttu-id="940c9-105">たとえば、BillTo Address レコードを ShipTo Address レコードの前にリストされるように出力を作成するには、送信先スキーマで BillTo Address を ShipTo Address レコードより前に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="940c9-105">For example, if you want to create an output file that has the BillTo Address record listed before the ShipTo Address record, you must ensure that the BillTo Address precedes the ShipTo Address record in the destination schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="940c9-106">出力インスタンス メッセージに要素および属性が表示される順序は、対応する送信先スキーマのレコードおよびフィールドの順序に依存します。</span><span class="sxs-lookup"><span data-stu-id="940c9-106">The order in which elements and attributes appear in an output instance message depends on the order of the records and fields of the corresponding destination schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940c9-107">参照</span><span class="sxs-lookup"><span data-stu-id="940c9-107">See Also</span></span>  
 <span data-ttu-id="940c9-108">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="940c9-108">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="940c9-109">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="940c9-109">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)