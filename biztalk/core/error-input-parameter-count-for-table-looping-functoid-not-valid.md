---
title: エラー - テーブル ループ functoid への無効の入力パラメーター数が |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.badParamCountForTableLooping
ms.assetid: 616e54aa-f6e3-4a49-afe2-278a0724e226
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68cc75282c7dd18925f39b339521d8ecb41911b9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530724"
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a><span data-ttu-id="ba120-102">エラー - テーブル ループ functoid への無効の入力パラメーター数</span><span class="sxs-lookup"><span data-stu-id="ba120-102">Error - Input Parameter Count for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="ba120-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="ba120-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ba120-104">btm1070</span><span class="sxs-lookup"><span data-stu-id="ba120-104">btm1070</span></span>  
  
 <span data-ttu-id="ba120-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="ba120-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ba120-106">関連する指定された入力パラメーター数**テーブル ループ**functoid が無効です。</span><span class="sxs-lookup"><span data-stu-id="ba120-106">The number of input parameters specified for the relevant **Table Looping** functoid is not valid.</span></span>  
  
 <span data-ttu-id="ba120-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="ba120-107">**User Action**</span></span>  
  
 <span data-ttu-id="ba120-108">入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="ba120-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="ba120-109">テーブル ループ functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="ba120-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="ba120-110">説明</span><span class="sxs-lookup"><span data-stu-id="ba120-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="ba120-111">1</span><span class="sxs-lookup"><span data-stu-id="ba120-111">1</span></span>|<span data-ttu-id="ba120-112">入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="ba120-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="ba120-113">2</span><span class="sxs-lookup"><span data-stu-id="ba120-113">2</span></span>|<span data-ttu-id="ba120-114">使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="ba120-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="ba120-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="ba120-115">3 – 100</span></span>|<span data-ttu-id="ba120-116">定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。</span><span class="sxs-lookup"><span data-stu-id="ba120-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|