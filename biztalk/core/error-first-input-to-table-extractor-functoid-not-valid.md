---
title: エラー - テーブル抽出 Functoid の無効への最初の入力 |Microsoft Docs
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
ms.openlocfilehash: 9b96e673f33bfa7478b633c8254a62d81335cd61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348318"
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a><span data-ttu-id="83a9e-102">エラー - テーブル抽出 Functoid の無効への最初の入力</span><span class="sxs-lookup"><span data-stu-id="83a9e-102">Error - First Input to Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="83a9e-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="83a9e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="83a9e-104">btm1019</span><span class="sxs-lookup"><span data-stu-id="83a9e-104">btm1019</span></span>  
  
 <span data-ttu-id="83a9e-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="83a9e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="83a9e-106">最初の入力パラメーターを指定された**テーブル抽出**functoid がリンクからではなく、**テーブル ループ**functoid は、必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="83a9e-106">The first input parameter to the indicated **Table Extractor** functoid is not a link from a **Table Looping** functoid, as required.</span></span>  
  
 <span data-ttu-id="83a9e-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="83a9e-107">**User Action**</span></span>  
  
 <span data-ttu-id="83a9e-108">指定された間リンクを作成**テーブル抽出**functoid、適切な**テーブル ループ**他のうち 1 つをドラッグして functoid。</span><span class="sxs-lookup"><span data-stu-id="83a9e-108">Create a link between the indicated **Table Extractor** functoid and the appropriate **Table Looping** functoid by dragging one of them to the other.</span></span> <span data-ttu-id="83a9e-109">元の functoid は、マップ グリッド ページで functoid の右側にあるである必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a9e-109">The former functoid must be located to the right of the latter functoid in a map grid page.</span></span> <span data-ttu-id="83a9e-110">またを使用して、**構成\<Functoid\> Functoid**  ダイアログ ボックスで、新しく作成したリンクがへの最初の入力パラメーターであることを確認**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="83a9e-110">Also, using the **Configure \<Functoid\> Functoid** dialog box, ensure that the newly created link is the first input parameter to the indicated **Table Extractor** functoid.</span></span>