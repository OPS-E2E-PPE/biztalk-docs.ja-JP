---
title: エラー - スキーマのルート参照空 |Microsoft ドキュメント
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
ms.openlocfilehash: b7217f6f9ea328aff4864cfdf3bee9ea71de3741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241922"
---
# <a name="error---schema-root-reference-empty"></a><span data-ttu-id="6526d-102">エラー - スキーマ ルート参照が空です。</span><span class="sxs-lookup"><span data-stu-id="6526d-102">Error - Schema Root Reference Empty</span></span>
<span data-ttu-id="6526d-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="6526d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6526d-104">BEC2005</span><span class="sxs-lookup"><span data-stu-id="6526d-104">BEC2005</span></span>  
  
 <span data-ttu-id="6526d-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="6526d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6526d-106">**ルート参照**のプロパティ、**スキーマ**ノードが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="6526d-106">The **Root Reference** property of the **Schema** node is not set.</span></span> <span data-ttu-id="6526d-107">ときに、**標準**のプロパティ、**スキーマ**ノードが以外の値に設定が**XML**、設定する必要があります、**ルート参照**プロパティを子ノードを示す、**スキーマ**ノードはこのスキーマによって定義されたメッセージのルートとして使用するためのものです。</span><span class="sxs-lookup"><span data-stu-id="6526d-107">When the **Standard** property of the **Schema** node is set to a value other than **XML**, you must set the **Root Reference** property to indicate which child node of the **Schema** node is meant to be used as the root of the message defined by this schema.</span></span>  
  
 <span data-ttu-id="6526d-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="6526d-108">**User Action**</span></span>  
  
 <span data-ttu-id="6526d-109">スキーマに適した、として設定するか、**標準**のプロパティ、**スキーマ**ノードを**XML**、設定や、**ルート参照**プロパティ、**スキーマ**ノードの適切な子ノードを**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="6526d-109">As appropriate for your schema, either set the **Standard** property of the **Schema** node to **XML**, or set the **Root Reference** property of the **Schema** node to the appropriate child node of the **Schema** node.</span></span> <span data-ttu-id="6526d-110">これらの子ノードで使用できる、**ルート参照**プロパティ ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="6526d-110">These child nodes are the available in the **Root Reference** property drop-down list.</span></span>