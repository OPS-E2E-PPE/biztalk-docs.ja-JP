---
title: "エラー - テーブル ループ Functoid が有効でないへの最初の入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2cfa89175d566ed152caa852dfc7aef2b435447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a><span data-ttu-id="59b9d-102">エラー - テーブル ループ Functoid が有効でないへの最初の入力</span><span class="sxs-lookup"><span data-stu-id="59b9d-102">Error - First Input to Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="59b9d-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="59b9d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="59b9d-104">btm1071</span><span class="sxs-lookup"><span data-stu-id="59b9d-104">btm1071</span></span>  
  
 <span data-ttu-id="59b9d-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="59b9d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="59b9d-106">関連する最初の入力パラメーター**テーブル ループ**functoid が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="59b9d-106">The first input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="59b9d-107">このパラメーターは、送信元スキーマ内のノードからのリンクを指定する必要があります: 入力インスタンス メッセージ内の対応する要素の出現回数が関連付けられている一連の回数を制御する**テーブル抽出**functoid実行時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="59b9d-107">This parameter must be a link from a node in the source schema—the number of occurrences of the corresponding element in an input instance message will control the number of times that the set of associated **Table Extractor** functoids will be invoked at run time.</span></span>  
  
 <span data-ttu-id="59b9d-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="59b9d-108">**User Action**</span></span>  
  
 <span data-ttu-id="59b9d-109">入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid > Functoid**  ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="59b9d-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="59b9d-110">テーブル ループ Functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="59b9d-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="59b9d-111">Description</span><span class="sxs-lookup"><span data-stu-id="59b9d-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="59b9d-112">1</span><span class="sxs-lookup"><span data-stu-id="59b9d-112">1</span></span>|<span data-ttu-id="59b9d-113">入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="59b9d-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="59b9d-114">2</span><span class="sxs-lookup"><span data-stu-id="59b9d-114">2</span></span>|<span data-ttu-id="59b9d-115">使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="59b9d-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="59b9d-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="59b9d-116">3 – 100</span></span>|<span data-ttu-id="59b9d-117">テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。</span><span class="sxs-lookup"><span data-stu-id="59b9d-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|