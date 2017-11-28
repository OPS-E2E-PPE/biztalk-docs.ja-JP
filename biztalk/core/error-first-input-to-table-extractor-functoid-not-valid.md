---
title: "エラー - テーブル抽出 Functoid が有効でないへの最初の入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2449f6c5572a3a29b620becdc4310f4152f2eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a><span data-ttu-id="0b053-102">エラー - テーブル抽出 Functoid が有効でないへの最初の入力</span><span class="sxs-lookup"><span data-stu-id="0b053-102">Error - First Input to Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="0b053-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="0b053-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0b053-104">btm1019</span><span class="sxs-lookup"><span data-stu-id="0b053-104">btm1019</span></span>  
  
 <span data-ttu-id="0b053-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="0b053-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0b053-106">最初の入力パラメーター**テーブル抽出**functoid がリンクからではなく、**テーブル ループ**functoid は、必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="0b053-106">The first input parameter to the indicated **Table Extractor** functoid is not a link from a **Table Looping** functoid, as required.</span></span>  
  
 <span data-ttu-id="0b053-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="0b053-107">**User Action**</span></span>  
  
 <span data-ttu-id="0b053-108">指定された間のリンクを作成する**テーブル抽出**functoid と適切な**テーブル ループ**もう一方のうちの 1 つをドラッグして functoid です。</span><span class="sxs-lookup"><span data-stu-id="0b053-108">Create a link between the indicated **Table Extractor** functoid and the appropriate **Table Looping** functoid by dragging one of them to the other.</span></span> <span data-ttu-id="0b053-109">マップ グリッド ページでは、テーブル抽出 Functoid が、テーブル ループ Functoid の右側に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b053-109">The former functoid must be located to the right of the latter functoid in a map grid page.</span></span> <span data-ttu-id="0b053-110">またを使用して、**構成\<Functoid > Functoid**  ダイアログ ボックスで、新しく作成したリンクがへの最初の入力パラメーターであることを確認**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="0b053-110">Also, using the **Configure \<Functoid> Functoid** dialog box, ensure that the newly created link is the first input parameter to the indicated **Table Extractor** functoid.</span></span>