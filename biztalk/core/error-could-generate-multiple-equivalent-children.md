---
title: エラー - の同等の複数の子要素が生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.couldGenMultipleEquivChildren
ms.assetid: ef3ea6db-6759-4f38-804c-e32a1f24d758
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfce7d5a5d4db35ae6677d3b45bad4df7842fbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389218"
---
# <a name="error---could-generate-multiple-equivalent-children"></a><span data-ttu-id="61850-102">エラー - が同等の複数の子要素を生成</span><span class="sxs-lookup"><span data-stu-id="61850-102">Error - Could Generate Multiple Equivalent Children</span></span>
<span data-ttu-id="61850-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="61850-103">**Error Code**</span></span>  
  
 <span data-ttu-id="61850-104">btm1026</span><span class="sxs-lookup"><span data-stu-id="61850-104">btm1026</span></span>  
  
 <span data-ttu-id="61850-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="61850-105">**Explanation**</span></span>  
  
 <span data-ttu-id="61850-106">送信先スキーマへのリンクには内で複数のノードに不適切な**同等**グループ ノードを生成します。</span><span class="sxs-lookup"><span data-stu-id="61850-106">Links to the destination schema inappropriately enable multiple nodes within an **Equivalent** group node to be generated.</span></span>  
  
 <span data-ttu-id="61850-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="61850-107">**User Action**</span></span>  
  
 <span data-ttu-id="61850-108">可能性があるため、論理演算 functoid を使用して、送信先スキーマへのリンクを修正内で 1 つのノードだけである、**同等**グループ ノードは、マッピング中に生成できます。</span><span class="sxs-lookup"><span data-stu-id="61850-108">Rework the links into the destination schema, potentially using logical functoids, so that only a single node within the **Equivalent** group node can be generated during mapping.</span></span>