---
title: エラー - テーブル ループ データが有効ではありません |Microsoft ドキュメント
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
ms.openlocfilehash: 9478026980ecaf3e2049773737250c56d18262c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968539"
---
# <a name="error---table-looping-data-not-valid"></a><span data-ttu-id="a2dde-102">エラー - テーブル ループ データが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a2dde-102">Error - Table Looping Data Not Valid</span></span>
<span data-ttu-id="a2dde-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="a2dde-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a2dde-104">btm1065</span><span class="sxs-lookup"><span data-stu-id="a2dde-104">btm1065</span></span>  
  
 <span data-ttu-id="a2dde-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="a2dde-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a2dde-106">関連する関連付けられたデータのテーブル**テーブル ループ**functoid が正しくない可能性があります、functoid、または正しく構成されていない、テーブル ループ グリッドを 2 番目の入力パラメーターが正しく構成されているためです。</span><span class="sxs-lookup"><span data-stu-id="a2dde-106">The table of data associated with the relevant **Table Looping** functoid is not valid, probably due to an incorrectly configured second input parameter to the functoid, or an incorrectly configured table looping grid.</span></span>  
  
 <span data-ttu-id="a2dde-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="a2dde-107">**User Action**</span></span>  
  
 <span data-ttu-id="a2dde-108">入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="a2dde-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="a2dde-109">テーブル ループ Functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="a2dde-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="a2dde-110">Description</span><span class="sxs-lookup"><span data-stu-id="a2dde-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="a2dde-111">1</span><span class="sxs-lookup"><span data-stu-id="a2dde-111">1</span></span>|<span data-ttu-id="a2dde-112">入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a2dde-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="a2dde-113">2</span><span class="sxs-lookup"><span data-stu-id="a2dde-113">2</span></span>|<span data-ttu-id="a2dde-114">使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="a2dde-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="a2dde-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="a2dde-115">3 – 100</span></span>|<span data-ttu-id="a2dde-116">テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。</span><span class="sxs-lookup"><span data-stu-id="a2dde-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|  
  
 <span data-ttu-id="a2dde-117">また、[を介してアクセスされると、テーブル ループ グリッドを正しく構成することを確認してください、**テーブル ループ グリッド**プロパティおよび**テーブル ループの構成**] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a2dde-117">Also, ensure that you properly configure the table looping grid, as accessed through the **Table Looping Grid** property and the **Table Looping Configuration** dialog box.</span></span> <span data-ttu-id="a2dde-118">アクセスされるすべてのセルの定数またはリンク値を選択する必要があります、関連付け**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="a2dde-118">A constant or link value must be chosen for every cell that will be accessed by an associated **Table Extractor** functoid.</span></span>