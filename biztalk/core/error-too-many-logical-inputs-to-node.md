---
title: エラー - ノードへの論理入力が多すぎます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tooManyLogicalInputsToNode
ms.assetid: 9295d6a2-702d-4cf3-8f5d-26ba63b9fce0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4892eca0fc65fe281ab9464eba914603f7ab392b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346309"
---
# <a name="error---too-many-logical-inputs-to-node"></a><span data-ttu-id="e8be0-102">エラー - ノードへの論理入力が多すぎます</span><span class="sxs-lookup"><span data-stu-id="e8be0-102">Error - Too Many Logical Inputs to Node</span></span>
<span data-ttu-id="e8be0-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="e8be0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e8be0-104">btm1006</span><span class="sxs-lookup"><span data-stu-id="e8be0-104">btm1006</span></span>  
  
 <span data-ttu-id="e8be0-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="e8be0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e8be0-106">多くへの入力リンクの数よりも、送信先スキーマのノードに接続している論理リンクがある、**ループ**functoid、対象ノードの祖先のノードに接続されています。</span><span class="sxs-lookup"><span data-stu-id="e8be0-106">There are a greater number of logical links connected to the indicated node in the destination schema than the number of input links to the **Looping** functoid that is connected to an ancestor node of the indicated node.</span></span> <span data-ttu-id="e8be0-107">前者と後者の型のリンクの数が一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8be0-107">The number of links of the former and latter types should match.</span></span>  
  
 <span data-ttu-id="e8be0-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="e8be0-108">**User Action**</span></span>  
  
 <span data-ttu-id="e8be0-109">指定されたノードとリンクの数が接続されている作業のやり直し、**ループ**functoid が、祖先ノードに接続されている一致するものとします。</span><span class="sxs-lookup"><span data-stu-id="e8be0-109">Rework the number of links connected to the indicated node and to the **Looping** functoid connected to the ancestor node so that they match.</span></span>