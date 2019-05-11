---
title: エラー - 昇格させたプロパティ Max Occurs |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fcaf06dc0fccbf838c401343b3ce1e8f3b538ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347056"
---
# <a name="error---promoted-property-max-occurs"></a><span data-ttu-id="e381f-102">エラー - 昇格させたプロパティ Max Occurs します。</span><span class="sxs-lookup"><span data-stu-id="e381f-102">Error - Promoted Property Max Occurs</span></span>
<span data-ttu-id="e381f-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="e381f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e381f-104">BEC2002</span><span class="sxs-lookup"><span data-stu-id="e381f-104">BEC2002</span></span>  
  
 <span data-ttu-id="e381f-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="e381f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e381f-106">設定、 **Max Occurs**またはその先祖ノードの 1 つの昇格を試みているノードのプロパティがプロパティの昇格と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="e381f-106">The setting of the **Max Occurs** property of the node being promoted, or of one of its ancestor nodes, is incompatible with property promotion.</span></span> <span data-ttu-id="e381f-107">インスタンス メッセージ内で複数回出現可能なノード プロパティの昇格は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="e381f-107">Property promotion is disallowed for nodes that can occur more than once in an instance message.</span></span> <span data-ttu-id="e381f-108">そのため、 **Max Occurs**ルート ノードに昇格するノードからすべてのノードのプロパティを 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e381f-108">Therefore, the **Max Occurs** properties of all nodes from the node being promoted back to the root node must be set to 1.</span></span>  
  
 <span data-ttu-id="e381f-109">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="e381f-109">**User Action**</span></span>  
  
 <span data-ttu-id="e381f-110">いることを確認、 **Max Occurs**昇格するノードとその祖先のノードのすべてのプロパティが 1 つ (1) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e381f-110">Ensure that the **Max Occurs** property of the node being promoted and all of its ancestor nodes is set to one (1).</span></span>