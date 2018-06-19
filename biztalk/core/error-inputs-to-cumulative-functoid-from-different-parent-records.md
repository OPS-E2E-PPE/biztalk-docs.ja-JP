---
title: エラー - の異なる親レコードから累積 Functoid へ入力 |Microsoft ドキュメント
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
ms.openlocfilehash: b3c919001e05ca99383ffce72c8d450f6d04624b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240402"
---
# <a name="error---inputs-to-cumulative-functoid-from-different-parent-records"></a><span data-ttu-id="edda9-102">エラー - 異なる親レコードから累積 Functoid への入力</span><span class="sxs-lookup"><span data-stu-id="edda9-102">Error - Inputs to Cumulative Functoid from Different Parent Records</span></span>
<span data-ttu-id="edda9-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="edda9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="edda9-104">btm1032</span><span class="sxs-lookup"><span data-stu-id="edda9-104">btm1032</span></span>  
  
 <span data-ttu-id="edda9-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="edda9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="edda9-106">対象**累積**functoid は、最初の入力パラメーター (蓄積するノード) として機能しているノードよりも、送信元スキーマの異なる部分は、2 番目の入力パラメーター (蓄積範囲)。</span><span class="sxs-lookup"><span data-stu-id="edda9-106">For the indicated **Cumulative** functoid, the second input parameter (the accumulation scope) is from a different part of the source schema than the node serving as the first input parameter (the node to accumulate).</span></span>  
  
 <span data-ttu-id="edda9-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="edda9-107">**User Action**</span></span>  
  
 <span data-ttu-id="edda9-108">両方の入力パラメーターを指定されたことを確認してください。**累積**functoid が、同じ親レコードを共有または定数入力パラメーターが提供する 2 番目の入力パラメーター (蓄積範囲)。</span><span class="sxs-lookup"><span data-stu-id="edda9-108">Ensure that both input parameters to the indicated **Cumulative** functoid share the same parent record, or that the second input parameter (the accumulation scope) you provide has a constant input parameter.</span></span>