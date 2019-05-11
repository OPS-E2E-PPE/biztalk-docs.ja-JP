---
title: エラー - 異なる親レコードから累積 functoid 入力の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputsToCumulativeFromDiffParents
ms.assetid: a2dcfe6f-0cd4-41ed-a69f-e510a74760a9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01e55e1d4bf09ecdb086ec99fde44008cf85829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388782"
---
# <a name="error---inputs-to-cumulative-functoid-from-different-parent-records"></a><span data-ttu-id="df0d9-102">エラー - 異なる親レコードから累積 Functoid への入力</span><span class="sxs-lookup"><span data-stu-id="df0d9-102">Error - Inputs to Cumulative Functoid from Different Parent Records</span></span>
<span data-ttu-id="df0d9-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="df0d9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="df0d9-104">btm1032</span><span class="sxs-lookup"><span data-stu-id="df0d9-104">btm1032</span></span>  
  
 <span data-ttu-id="df0d9-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="df0d9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="df0d9-106">対象**累積**functoid は、最初の入力パラメーター (蓄積するノード) として提供しているノードよりも、送信元スキーマの別の部分が 2 番目の入力パラメーター (蓄積範囲)。</span><span class="sxs-lookup"><span data-stu-id="df0d9-106">For the indicated **Cumulative** functoid, the second input parameter (the accumulation scope) is from a different part of the source schema than the node serving as the first input parameter (the node to accumulate).</span></span>  
  
 <span data-ttu-id="df0d9-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="df0d9-107">**User Action**</span></span>  
  
 <span data-ttu-id="df0d9-108">両方の入力パラメーターを指定されたことを確認**累積**functoid が、同じ親レコードを共有したり、定数入力パラメーターを持つ指定した 2 番目の入力パラメーター (蓄積範囲)。</span><span class="sxs-lookup"><span data-stu-id="df0d9-108">Ensure that both input parameters to the indicated **Cumulative** functoid share the same parent record, or that the second input parameter (the accumulation scope) you provide has a constant input parameter.</span></span>