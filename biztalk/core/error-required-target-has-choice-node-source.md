---
title: エラー - 必須ターゲットに選択ノードのソースが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetHasChoiceNodeSource
ms.assetid: 5b5af999-d100-4e5d-a959-c8b11d574d3b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a33a5fc9bbcfe44e71b0caab6569279aeb9c32f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388468"
---
# <a name="error---required-target-has-choice-node-source"></a><span data-ttu-id="c7cba-102">エラー - 必須ターゲットに選択ノードのソース</span><span class="sxs-lookup"><span data-stu-id="c7cba-102">Error - Required Target Has Choice Node Source</span></span>
<span data-ttu-id="c7cba-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="c7cba-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c7cba-104">btm1029</span><span class="sxs-lookup"><span data-stu-id="c7cba-104">btm1029</span></span>  
  
 <span data-ttu-id="c7cba-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="c7cba-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c7cba-106">送信先スキーマのノードが指定されたとして必要ですが、内にある送信元スキーマ内のノードにリンクされて、**選択肢**ノード。</span><span class="sxs-lookup"><span data-stu-id="c7cba-106">The indicated node in the destination schema is specified as required but is linked to a node in the source schema that is within a **Choice** node.</span></span> <span data-ttu-id="c7cba-107">入力インスタンス メッセージに、送信元スキーマのノードが表示されない、ため、ある可能性がありますいない必須ノードを送信先スキーマの作成元のソース。</span><span class="sxs-lookup"><span data-stu-id="c7cba-107">Because the indicated node in the source schema may not appear in an input instance message, there may not be a source from which to create the required node in the destination schema.</span></span>  
  
 <span data-ttu-id="c7cba-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c7cba-108">**User Action**</span></span>  
  
 <span data-ttu-id="c7cba-109">必要に応じて、省略可能な送信先スキーマのノードに変更か、または、すべての有効な入力インスタンス メッセージで発生する必要がある、送信先スキーマのノードのさまざまなソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="c7cba-109">As appropriate, either change the indicated node in the destination schema to optional, or provide a different source for the indicated node in the destination schema that must occur in all valid input instance messages.</span></span>