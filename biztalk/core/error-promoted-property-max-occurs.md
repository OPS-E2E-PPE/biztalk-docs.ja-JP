---
title: "エラー - 昇格させたプロパティ Max Occurs |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c8395757d19eff5241d47c31b15409a00b6faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---promoted-property-max-occurs"></a><span data-ttu-id="6a6f8-102">エラー - 昇格させたプロパティ Max Occurs します。</span><span class="sxs-lookup"><span data-stu-id="6a6f8-102">Error - Promoted Property Max Occurs</span></span>
<span data-ttu-id="6a6f8-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="6a6f8-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6a6f8-104">BEC2002</span><span class="sxs-lookup"><span data-stu-id="6a6f8-104">BEC2002</span></span>  
  
 <span data-ttu-id="6a6f8-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="6a6f8-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6a6f8-106">設定、 **Max Occurs** 、昇格するノードまたはその先祖ノードのいずれかのプロパティがプロパティの昇格と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="6a6f8-106">The setting of the **Max Occurs** property of the node being promoted, or of one of its ancestor nodes, is incompatible with property promotion.</span></span> <span data-ttu-id="6a6f8-107">インスタンス メッセージに複数回出現可能なノードでは、プロパティの昇格は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="6a6f8-107">Property promotion is disallowed for nodes that can occur more than once in an instance message.</span></span> <span data-ttu-id="6a6f8-108">したがって、 **Max Occurs**ルート ノードに昇格するノードからすべてのノードのプロパティを 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a6f8-108">Therefore, the **Max Occurs** properties of all nodes from the node being promoted back to the root node must be set to 1.</span></span>  
  
 <span data-ttu-id="6a6f8-109">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="6a6f8-109">**User Action**</span></span>  
  
 <span data-ttu-id="6a6f8-110">いることを確認、 **Max Occurs**昇格するノードとそのすべての先祖ノードのプロパティが 1 つ (1) に設定します。</span><span class="sxs-lookup"><span data-stu-id="6a6f8-110">Ensure that the **Max Occurs** property of the node being promoted and all of its ancestor nodes is set to one (1).</span></span>