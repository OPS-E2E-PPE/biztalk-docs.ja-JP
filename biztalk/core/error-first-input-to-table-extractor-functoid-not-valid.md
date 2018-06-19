---
title: エラー - テーブル抽出 Functoid が有効でないへの最初の入力 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d501c18bf104a0f538ef90d10510e7d9ec0f02
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969016"
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a><span data-ttu-id="f6e0d-102">エラー - テーブル抽出 Functoid が有効でないへの最初の入力</span><span class="sxs-lookup"><span data-stu-id="f6e0d-102">Error - First Input to Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="f6e0d-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="f6e0d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f6e0d-104">btm1019</span><span class="sxs-lookup"><span data-stu-id="f6e0d-104">btm1019</span></span>  
  
 <span data-ttu-id="f6e0d-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="f6e0d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f6e0d-106">最初の入力パラメーター**テーブル抽出**functoid がリンクからではなく、**テーブル ループ**functoid は、必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-106">The first input parameter to the indicated **Table Extractor** functoid is not a link from a **Table Looping** functoid, as required.</span></span>  
  
 <span data-ttu-id="f6e0d-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="f6e0d-107">**User Action**</span></span>  
  
 <span data-ttu-id="f6e0d-108">指定された間のリンクを作成する**テーブル抽出**functoid と適切な**テーブル ループ**もう一方のうちの 1 つをドラッグして functoid です。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-108">Create a link between the indicated **Table Extractor** functoid and the appropriate **Table Looping** functoid by dragging one of them to the other.</span></span> <span data-ttu-id="f6e0d-109">マップ グリッド ページでは、テーブル抽出 Functoid が、テーブル ループ Functoid の右側に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-109">The former functoid must be located to the right of the latter functoid in a map grid page.</span></span> <span data-ttu-id="f6e0d-110">またを使用して、**構成\<Functoid\> Functoid**  ダイアログ ボックスで、新しく作成したリンクがへの最初の入力パラメーターであることを確認**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="f6e0d-110">Also, using the **Configure \<Functoid\> Functoid** dialog box, ensure that the newly created link is the first input parameter to the indicated **Table Extractor** functoid.</span></span>