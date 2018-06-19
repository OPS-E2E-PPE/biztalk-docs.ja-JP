---
title: エラー - テーブル ループ Functoid が無効の入力パラメーター数が |Microsoft ドキュメント
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
ms.openlocfilehash: 2df0a6780485b91fc89356aecb73823643276be1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968464"
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a><span data-ttu-id="ac4d3-102">エラー - テーブル ループ Functoid が無効の入力パラメーター数</span><span class="sxs-lookup"><span data-stu-id="ac4d3-102">Error - Input Parameter Count for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="ac4d3-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="ac4d3-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ac4d3-104">btm1070</span><span class="sxs-lookup"><span data-stu-id="ac4d3-104">btm1070</span></span>  
  
 <span data-ttu-id="ac4d3-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="ac4d3-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ac4d3-106">関連する指定された入力パラメーター数**テーブル ループ**functoid が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="ac4d3-106">The number of input parameters specified for the relevant **Table Looping** functoid is not valid.</span></span>  
  
 <span data-ttu-id="ac4d3-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="ac4d3-107">**User Action**</span></span>  
  
 <span data-ttu-id="ac4d3-108">入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="ac4d3-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="ac4d3-109">テーブル ループ Functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="ac4d3-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="ac4d3-110">Description</span><span class="sxs-lookup"><span data-stu-id="ac4d3-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="ac4d3-111">1</span><span class="sxs-lookup"><span data-stu-id="ac4d3-111">1</span></span>|<span data-ttu-id="ac4d3-112">入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="ac4d3-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="ac4d3-113">2</span><span class="sxs-lookup"><span data-stu-id="ac4d3-113">2</span></span>|<span data-ttu-id="ac4d3-114">使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="ac4d3-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="ac4d3-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="ac4d3-115">3 – 100</span></span>|<span data-ttu-id="ac4d3-116">テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。</span><span class="sxs-lookup"><span data-stu-id="ac4d3-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|