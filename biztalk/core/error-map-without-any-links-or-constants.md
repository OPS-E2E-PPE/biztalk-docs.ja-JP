---
title: エラー - マップにリンクまたは定数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapWithoutAnyLinksOrConstants
ms.assetid: 8d1cdbcd-4bd0-4ddc-9e94-746e82b6ec48
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa01eff9df2582a00418530e87e9658565722c23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347816"
---
# <a name="error---map-without-any-links-or-constants"></a><span data-ttu-id="c8918-102">エラー - マップにリンクまたは定数</span><span class="sxs-lookup"><span data-stu-id="c8918-102">Error - Map Without Any Links or Constants</span></span>
<span data-ttu-id="c8918-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="c8918-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c8918-104">btm1000</span><span class="sxs-lookup"><span data-stu-id="c8918-104">btm1000</span></span>  
  
 <span data-ttu-id="c8918-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="c8918-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c8918-106">マップにスキーマ間のリンクがまったく指定されていないか、送信先スキーマに定数値が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="c8918-106">The map does not contain any links between the schemas, or constant values in the destination schema.</span></span> <span data-ttu-id="c8918-107">そのため、このマップから出力を作成できません。</span><span class="sxs-lookup"><span data-stu-id="c8918-107">Therefore, no output can be created from this map.</span></span>  
  
 <span data-ttu-id="c8918-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c8918-108">**User Action**</span></span>  
  
 <span data-ttu-id="c8918-109">適切なリンクを追加し、適宜、マップのグリッドに Functoid を追加するか、送信先スキーマに定数を追加して、送信元スキーマに準拠しているインスタンス メッセージを送信先スキーマに準拠したインスタンス メッセージに変換する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8918-109">Add the appropriate links and, if appropriate, functoids to the map grid, or constants to the destination schema, to specify how instance messages conforming to the source schema should be transformed into instance messages conforming to the destination schema.</span></span>