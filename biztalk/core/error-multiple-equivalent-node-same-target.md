---
title: エラー - 複数の等価のノードと同じターゲット |Microsoft Docs
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
ms.openlocfilehash: 7c4cf66fe587f483385c4729e4c34b0179c1710e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388647"
---
# <a name="error---multiple-equivalent-node-same-target"></a><span data-ttu-id="dbb77-102">エラー - 複数の等価のノードと同じターゲット</span><span class="sxs-lookup"><span data-stu-id="dbb77-102">Error - Multiple Equivalent Node Same Target</span></span>
<span data-ttu-id="dbb77-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="dbb77-103">**Error Code**</span></span>  
  
 <span data-ttu-id="dbb77-104">btm1025</span><span class="sxs-lookup"><span data-stu-id="dbb77-104">btm1025</span></span>  
  
 <span data-ttu-id="dbb77-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="dbb77-105">**Explanation**</span></span>  
  
 <span data-ttu-id="dbb77-106">競合する子ノードには、ソース スキーマで指定されたノードの**同等**グループ ノードでは、どちらも、送信先スキーマのノードにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="dbb77-106">The indicated nodes in the source schema, which are conflicting child nodes of an **Equivalent** group node, are both linked to the indicated node in the destination schema.</span></span> <span data-ttu-id="dbb77-107">送信元スキーマ内のこれらのノードの 1 つだけに特定のインスタンス メッセージで発生します。</span><span class="sxs-lookup"><span data-stu-id="dbb77-107">Only one of these nodes in the source schema can occur in a given instance message.</span></span>  
  
 <span data-ttu-id="dbb77-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="dbb77-108">**User Action**</span></span>  
  
 <span data-ttu-id="dbb77-109">子の 1 つだけのノードをことを確認、**同等**グループ ノードが送信先スキーマの特定のノードに接続します。</span><span class="sxs-lookup"><span data-stu-id="dbb77-109">Ensure that only one of the child nodes of the **Equivalent** group node is connected to a given node in the destination schema.</span></span>