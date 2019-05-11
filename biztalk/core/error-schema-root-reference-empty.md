---
title: エラー - スキーマのルートの参照を空 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootRefEmpty
ms.assetid: 172e6ad8-6118-40db-9451-92808a3a2051
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c56119e88948211f7b2e93add1d6e23d08e1b9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346882"
---
# <a name="error---schema-root-reference-empty"></a><span data-ttu-id="7c79f-102">エラー - スキーマ ルート参照が空です。</span><span class="sxs-lookup"><span data-stu-id="7c79f-102">Error - Schema Root Reference Empty</span></span>
<span data-ttu-id="7c79f-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="7c79f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7c79f-104">BEC2005</span><span class="sxs-lookup"><span data-stu-id="7c79f-104">BEC2005</span></span>  
  
 <span data-ttu-id="7c79f-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="7c79f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7c79f-106">**ルート参照**のプロパティ、**スキーマ**ノードが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="7c79f-106">The **Root Reference** property of the **Schema** node is not set.</span></span> <span data-ttu-id="7c79f-107">ときに、**標準**のプロパティ、**スキーマ**ノードが以外の値に設定されて**XML**を設定する必要があります、**ルート参照**プロパティを子ノードを示す、**スキーマ**ノードはこのスキーマで定義されるメッセージのルートとして使用するためのものです。</span><span class="sxs-lookup"><span data-stu-id="7c79f-107">When the **Standard** property of the **Schema** node is set to a value other than **XML**, you must set the **Root Reference** property to indicate which child node of the **Schema** node is meant to be used as the root of the message defined by this schema.</span></span>  
  
 <span data-ttu-id="7c79f-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="7c79f-108">**User Action**</span></span>  
  
 <span data-ttu-id="7c79f-109">スキーマの適切な設定、**標準**のプロパティ、**スキーマ**ノードを**XML**、設定や、**ルート参照**プロパティ、**スキーマ**の適切な子ノードにノード、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="7c79f-109">As appropriate for your schema, either set the **Standard** property of the **Schema** node to **XML**, or set the **Root Reference** property of the **Schema** node to the appropriate child node of the **Schema** node.</span></span> <span data-ttu-id="7c79f-110">これらの子ノードがで使用できる、**ルート参照**プロパティ ボックスの一覧。</span><span class="sxs-lookup"><span data-stu-id="7c79f-110">These child nodes are the available in the **Root Reference** property drop-down list.</span></span>