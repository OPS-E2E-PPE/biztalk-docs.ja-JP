---
title: エラー - 複数のノードと等しい同じターゲット |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleEquivNodeSameTarget
ms.assetid: d8ca9f94-1d87-41bb-9479-6a01a5b6702d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12df4f7a68bb1eceaa3211c6aad6e9a581f17a4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-equivalent-node-same-target"></a><span data-ttu-id="9b28c-102">エラー - 複数のノードと等しい同じターゲット</span><span class="sxs-lookup"><span data-stu-id="9b28c-102">Error - Multiple Equivalent Node Same Target</span></span>
<span data-ttu-id="9b28c-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="9b28c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="9b28c-104">btm1025</span><span class="sxs-lookup"><span data-stu-id="9b28c-104">btm1025</span></span>  
  
 <span data-ttu-id="9b28c-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="9b28c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="9b28c-106">競合する子ノードである送信元スキーマのノードの**等価**送信先スキーマのノードにリンクされている両方は、グループ ノード。</span><span class="sxs-lookup"><span data-stu-id="9b28c-106">The indicated nodes in the source schema, which are conflicting child nodes of an **Equivalent** group node, are both linked to the indicated node in the destination schema.</span></span> <span data-ttu-id="9b28c-107">任意の 1 つのインスタンス メッセージ内で使用できるのは、送信元スキーマ内のこれらのノードのうち、1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="9b28c-107">Only one of these nodes in the source schema can occur in a given instance message.</span></span>  
  
 <span data-ttu-id="9b28c-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="9b28c-108">**User Action**</span></span>  
  
 <span data-ttu-id="9b28c-109">ノードが 1 つだけの子を確認してください、**等価**グループ ノードが送信先スキーマの特定のノードに接続されています。</span><span class="sxs-lookup"><span data-stu-id="9b28c-109">Ensure that only one of the child nodes of the **Equivalent** group node is connected to a given node in the destination schema.</span></span>