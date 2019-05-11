---
title: メッセージに直接対応しているノード インスタンスのデータおよび構造体 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18cf721c-2972-43c6-8ae4-f2f8f83ba2c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eef4c9c8ae710aa75b1cb05ad8f5b4732f06bd30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323628"
---
# <a name="nodes-that-correspond-directly-to-message-instance-data-and-structure"></a><span data-ttu-id="26f0e-102">メッセージ インスタンス データおよび構造に直接対応しているノード</span><span class="sxs-lookup"><span data-stu-id="26f0e-102">Nodes That Correspond Directly to Message Instance Data and Structure</span></span>
<span data-ttu-id="26f0e-103">スキーマによって管理するインスタンス メッセージの XML 表現の要素と属性に直接対応して一部の BizTalk エディターでスキーマを作成するために使用するノードの種類 (その他のインスタンス メッセージの書式設定、フラット ファイル形式などこれ対応のみ存在して、その他の形式に変換する前に他の形式から変換後)。</span><span class="sxs-lookup"><span data-stu-id="26f0e-103">Some of the node types that you use to create schemas in BizTalk Editor correspond directly to elements and attributes in XML representation of instance messages governed by the schema (for other instance message formats, such as flat file formats, this correspondence only exists after translation from the other format and before translation to the other format).</span></span> <span data-ttu-id="26f0e-104">これらのノード型は**レコード**ノード (ルートを含む**レコード**ノード)、**フィールド要素**ノード、および**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="26f0e-104">These node types are **Record** nodes (including root **Record** nodes), **Field Element** nodes, and **Field Attribute** nodes.</span></span>  
  
 <span data-ttu-id="26f0e-105">値に、**ノード名**のプロパティ**レコード**と**フィールド要素**ノードが準拠するもの、XML インスタンス メッセージ内の対応する要素の名前を指定しますスキーマです。</span><span class="sxs-lookup"><span data-stu-id="26f0e-105">The values you give to the **Node Name** property of **Record** and **Field Element** nodes specify the name of the corresponding element in XML instance messages governed by the schema.</span></span> <span data-ttu-id="26f0e-106">同様に、値に付ける、**ノード名**プロパティの**フィールド属性**ノードが XML インスタンス メッセージのスキーマ準拠するもので、対応する属性の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="26f0e-106">Likewise, the values you give to the **Node Name** property of **Field Attribute** nodes specify the name of the corresponding attribute in XML instance messages governed by the schema.</span></span> <span data-ttu-id="26f0e-107">このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="26f0e-107">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="26f0e-108">このセクションの残りの部分は、このクラスでは、ルート ノードの詳細情報を提供**レコード**ノードのスキーマで個別に扱うための特別な役割のを受信します。</span><span class="sxs-lookup"><span data-stu-id="26f0e-108">The remainder of this section provides more information about this class of nodes, with root **Record** nodes receiving separate treatment due to their special role in schemas.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="26f0e-109">次のステップ</span><span class="sxs-lookup"><span data-stu-id="26f0e-109">Next steps</span></span> 
  
-   [<span data-ttu-id="26f0e-110">ルート ノード</span><span class="sxs-lookup"><span data-stu-id="26f0e-110">Root Nodes</span></span>](../core/root-nodes.md)  
  
-   <span data-ttu-id="26f0e-111">[[レコード] ノード](../core/record-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="26f0e-111">[Record Nodes](../core/record-nodes.md)</span></span>  
  
-   <span data-ttu-id="26f0e-112">[[フィールド要素] ノード](../core/field-element-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="26f0e-112">[Field Element Nodes](../core/field-element-nodes.md)</span></span>  
  
-   <span data-ttu-id="26f0e-113">[[フィールド属性] ノード](../core/field-attribute-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="26f0e-113">[Field Attribute Nodes](../core/field-attribute-nodes.md)</span></span>