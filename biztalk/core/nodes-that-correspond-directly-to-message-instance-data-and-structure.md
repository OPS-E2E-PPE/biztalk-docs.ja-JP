---
title: メッセージに直接対応するノードがインスタンス データおよび構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: 1d5ed1aae517bb81e5a6cfb888300015e99ec017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263258"
---
# <a name="nodes-that-correspond-directly-to-message-instance-data-and-structure"></a><span data-ttu-id="ea991-102">メッセージ インスタンス データおよび構造に直接対応しているノード</span><span class="sxs-lookup"><span data-stu-id="ea991-102">Nodes That Correspond Directly to Message Instance Data and Structure</span></span>
<span data-ttu-id="ea991-103">スキーマによって管理されるインスタンス メッセージの XML 表現の要素および属性に直接対応して一部の BizTalk エディターでスキーマの作成に使用するノードの種類 (その他のインスタンス メッセージの書式設定、フラット ファイル形式などこれ対応のみ存在する場合と他の形式に変換する前に、その他の形式から変換後)。</span><span class="sxs-lookup"><span data-stu-id="ea991-103">Some of the node types that you use to create schemas in BizTalk Editor correspond directly to elements and attributes in XML representation of instance messages governed by the schema (for other instance message formats, such as flat file formats, this correspondence only exists after translation from the other format and before translation to the other format).</span></span> <span data-ttu-id="ea991-104">これらのノード型は**レコード**ノード (ルートを含む**レコード**ノード)、**フィールド要素**ノード、および**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="ea991-104">These node types are **Record** nodes (including root **Record** nodes), **Field Element** nodes, and **Field Attribute** nodes.</span></span>  
  
 <span data-ttu-id="ea991-105">値に、**ノード名**プロパティ**レコード**と**フィールド要素**ノードによって管理される XML インスタンス メッセージ内の対応する要素の名前を指定する、スキーマです。</span><span class="sxs-lookup"><span data-stu-id="ea991-105">The values you give to the **Node Name** property of **Record** and **Field Element** nodes specify the name of the corresponding element in XML instance messages governed by the schema.</span></span> <span data-ttu-id="ea991-106">同様に、値に付ける、**ノード名**プロパティ**フィールド属性**ノードがスキーマによって管理される XML インスタンス メッセージに対応する属性の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea991-106">Likewise, the values you give to the **Node Name** property of **Field Attribute** nodes specify the name of the corresponding attribute in XML instance messages governed by the schema.</span></span> <span data-ttu-id="ea991-107">このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea991-107">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="ea991-108">このセクションの残りの部分とルートのノードには、このクラスの詳細については、**レコード**ノードのスキーマで個別に扱うための特別な役割のを受信します。</span><span class="sxs-lookup"><span data-stu-id="ea991-108">The remainder of this section provides more information about this class of nodes, with root **Record** nodes receiving separate treatment due to their special role in schemas.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ea991-109">次の手順</span><span class="sxs-lookup"><span data-stu-id="ea991-109">Next steps</span></span> 
  
-   [<span data-ttu-id="ea991-110">ルート ノード</span><span class="sxs-lookup"><span data-stu-id="ea991-110">Root Nodes</span></span>](../core/root-nodes.md)  
  
-   [<span data-ttu-id="ea991-111">レコード ノード</span><span class="sxs-lookup"><span data-stu-id="ea991-111">Record Nodes</span></span>](../core/record-nodes.md)  
  
-   <span data-ttu-id="ea991-112">[[フィールド要素] ノード](../core/field-element-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="ea991-112">[Field Element Nodes](../core/field-element-nodes.md)</span></span>  
  
-   [<span data-ttu-id="ea991-113">フィールド属性 ノード</span><span class="sxs-lookup"><span data-stu-id="ea991-113">Field Attribute Nodes</span></span>](../core/field-attribute-nodes.md)