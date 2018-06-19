---
title: エラー - 有効でないインデックス Functoid への最初の入力 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToIndexNotValid
ms.assetid: f7dbe9cc-9cfa-4fc7-af3e-1241cb2b50a9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 163de330945cc085648188dffcb75821c11ec5d6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969648"
---
# <a name="error---first-input-to-index-functoid-not-valid"></a><span data-ttu-id="e2e2f-102">エラー - 有効でないインデックス Functoid への最初の入力</span><span class="sxs-lookup"><span data-stu-id="e2e2f-102">Error - First Input to Index Functoid Not Valid</span></span>
<span data-ttu-id="e2e2f-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="e2e2f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e2e2f-104">btm1015</span><span class="sxs-lookup"><span data-stu-id="e2e2f-104">btm1015</span></span>  
  
 <span data-ttu-id="e2e2f-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="e2e2f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e2e2f-106">最初の入力パラメーター**インデックス**functoid ではない、**フィールド**ループ内のノード**レコード**送信元スキーマ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="e2e2f-106">The first input parameter to the indicated **Index** functoid is not from a **Field** node within a looping **Record** node in the source schema.</span></span>  
  
 <span data-ttu-id="e2e2f-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="e2e2f-107">**User Action**</span></span>  
  
 <span data-ttu-id="e2e2f-108">間でドラッグして、適切な入力リンクを作成、**フィールド**ループ内のノード**レコード**、送信元スキーマと、指定されたノード**インデックス**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e2e2f-108">Create the appropriate input link by dragging between a **Field** node within a looping **Record** node in the source schema and the indicated **Index** functoid.</span></span> <span data-ttu-id="e2e2f-109">開く必要があります、**構成\<Functoid\> Functoid**ダイアログ ボックスで、指定された選択**インデックス**functoid、省略記号ボタンをクリックし、(**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]新しく作成したリンクがへの最初の入力パラメーターであることを確認するために [プロパティ] ウィンドウ**インデックス**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e2e2f-109">It may be necessary to open the **Configure \<Functoid\> Functoid** dialog box by selecting the indicated **Index** functoid and clicking the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window in order to ensure that the newly created link is the first input parameter to the indicated **Index** functoid.</span></span>