---
title: "エラー - 必須ターゲットに選択ノードのソースは |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.reqdTargetHasChoiceNodeSource
ms.assetid: 5b5af999-d100-4e5d-a959-c8b11d574d3b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c9ad912b03bbb475efcc9eb8207a388400b43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-has-choice-node-source"></a><span data-ttu-id="21e3f-102">エラー - 必須ターゲットに選択ノードのソース</span><span class="sxs-lookup"><span data-stu-id="21e3f-102">Error - Required Target Has Choice Node Source</span></span>
<span data-ttu-id="21e3f-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="21e3f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="21e3f-104">btm1029</span><span class="sxs-lookup"><span data-stu-id="21e3f-104">btm1029</span></span>  
  
 <span data-ttu-id="21e3f-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="21e3f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="21e3f-106">送信先スキーマのノードが指定されて、必須として内にある送信元スキーマ内のノードにリンクされて、**選択肢**ノード。</span><span class="sxs-lookup"><span data-stu-id="21e3f-106">The indicated node in the destination schema is specified as required but is linked to a node in the source schema that is within a **Choice** node.</span></span> <span data-ttu-id="21e3f-107">入力インスタンス メッセージには送信元スキーマのノードが表示されていないため、送信先スキーマに必須ノードを作成するための送信元が存在しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21e3f-107">Because the indicated node in the source schema may not appear in an input instance message, there may not be a source from which to create the required node in the destination schema.</span></span>  
  
 <span data-ttu-id="21e3f-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="21e3f-108">**User Action**</span></span>  
  
 <span data-ttu-id="21e3f-109">適宜、送信先スキーマの対象のノードを省略可能に変更するか、送信先スキーマのノードに、有効なすべての入力インスタンス メッセージに表示される別の送信元を設定します。</span><span class="sxs-lookup"><span data-stu-id="21e3f-109">As appropriate, either change the indicated node in the destination schema to optional, or provide a different source for the indicated node in the destination schema that must occur in all valid input instance messages.</span></span>