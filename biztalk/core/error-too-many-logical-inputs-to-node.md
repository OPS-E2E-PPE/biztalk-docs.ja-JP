---
title: "エラー - ノードへの論理入力が多すぎます |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tooManyLogicalInputsToNode
ms.assetid: 9295d6a2-702d-4cf3-8f5d-26ba63b9fce0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e363d79a2b013b8e90533c4e6e36cff5b5798b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---too-many-logical-inputs-to-node"></a><span data-ttu-id="c7673-102">エラー - ノードへの論理入力が多すぎます</span><span class="sxs-lookup"><span data-stu-id="c7673-102">Error - Too Many Logical Inputs to Node</span></span>
<span data-ttu-id="c7673-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="c7673-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c7673-104">btm1006</span><span class="sxs-lookup"><span data-stu-id="c7673-104">btm1006</span></span>  
  
 <span data-ttu-id="c7673-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="c7673-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c7673-106">入力リンクの数よりも、送信先スキーマのノードに接続している論理リンク数がある、**ループ**functoid のノードの祖先のノードに接続されています。</span><span class="sxs-lookup"><span data-stu-id="c7673-106">There are a greater number of logical links connected to the indicated node in the destination schema than the number of input links to the **Looping** functoid that is connected to an ancestor node of the indicated node.</span></span> <span data-ttu-id="c7673-107">この 2 種類のリンクの数は、一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7673-107">The number of links of the former and latter types should match.</span></span>  
  
 <span data-ttu-id="c7673-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c7673-108">**User Action**</span></span>  
  
 <span data-ttu-id="c7673-109">作業のやり直しのノードにされ、接続されているリンクの数、**ループ**functoid が、祖先ノードに接続されている一致するものとします。</span><span class="sxs-lookup"><span data-stu-id="c7673-109">Rework the number of links connected to the indicated node and to the **Looping** functoid connected to the ancestor node so that they match.</span></span>