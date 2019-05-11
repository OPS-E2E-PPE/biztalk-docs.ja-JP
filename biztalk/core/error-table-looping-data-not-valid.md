---
title: エラー - テーブル ループ データが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e62678e7dc4e0aceee128cb24bc0ff34129168cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388407"
---
# <a name="error---table-looping-data-not-valid"></a><span data-ttu-id="2a9c0-102">エラー - テーブル ループ データが無効です。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-102">Error - Table Looping Data Not Valid</span></span>
<span data-ttu-id="2a9c0-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="2a9c0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2a9c0-104">btm1065</span><span class="sxs-lookup"><span data-stu-id="2a9c0-104">btm1065</span></span>  
  
 <span data-ttu-id="2a9c0-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="2a9c0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2a9c0-106">関連付けられた、関連するデータのテーブル**テーブル ループ**functoid が無効で、functoid、または正しく構成されていない、テーブル ループ グリッドを 2 番目の入力パラメーター構成が正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-106">The table of data associated with the relevant **Table Looping** functoid is not valid, probably due to an incorrectly configured second input parameter to the functoid, or an incorrectly configured table looping grid.</span></span>  
  
 <span data-ttu-id="2a9c0-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="2a9c0-107">**User Action**</span></span>  
  
 <span data-ttu-id="2a9c0-108">入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="2a9c0-109">テーブル ループ functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="2a9c0-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="2a9c0-110">説明</span><span class="sxs-lookup"><span data-stu-id="2a9c0-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="2a9c0-111">1</span><span class="sxs-lookup"><span data-stu-id="2a9c0-111">1</span></span>|<span data-ttu-id="2a9c0-112">入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="2a9c0-113">2</span><span class="sxs-lookup"><span data-stu-id="2a9c0-113">2</span></span>|<span data-ttu-id="2a9c0-114">使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="2a9c0-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="2a9c0-115">3 – 100</span></span>|<span data-ttu-id="2a9c0-116">定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|  
  
 <span data-ttu-id="2a9c0-117">またを正しくテーブル ループ グリッドを構成することを確認、**テーブル ループ グリッド**プロパティおよび**テーブル ループの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-117">Also, ensure that you properly configure the table looping grid, as accessed through the **Table Looping Grid** property and the **Table Looping Configuration** dialog box.</span></span> <span data-ttu-id="2a9c0-118">アクセスするすべてのセルの定数またはリンクの値を選択する必要が、関連付けられた**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="2a9c0-118">A constant or link value must be chosen for every cell that will be accessed by an associated **Table Extractor** functoid.</span></span>