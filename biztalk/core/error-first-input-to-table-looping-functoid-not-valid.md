---
title: エラー - テーブル ループ Functoid の無効への最初の入力 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ecfb5402cc4c544acc208654cd7fe7459de985
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389296"
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a><span data-ttu-id="1c6ec-102">エラー - テーブル ループ Functoid の無効への最初の入力</span><span class="sxs-lookup"><span data-stu-id="1c6ec-102">Error - First Input to Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="1c6ec-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="1c6ec-103">**Error Code**</span></span>  
  
 <span data-ttu-id="1c6ec-104">btm1071</span><span class="sxs-lookup"><span data-stu-id="1c6ec-104">btm1071</span></span>  
  
 <span data-ttu-id="1c6ec-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="1c6ec-105">**Explanation**</span></span>  
  
 <span data-ttu-id="1c6ec-106">最初の入力パラメーターに関連する**テーブル ループ**functoid が無効です。</span><span class="sxs-lookup"><span data-stu-id="1c6ec-106">The first input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="1c6ec-107">このパラメーターは、送信元スキーマのノードからのリンクである必要があります-入力インスタンス メッセージ内の対応する要素の出現回数が関連付けられている、一連の回数を制御**テーブル抽出**functoid実行時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1c6ec-107">This parameter must be a link from a node in the source schema—the number of occurrences of the corresponding element in an input instance message will control the number of times that the set of associated **Table Extractor** functoids will be invoked at run time.</span></span>  
  
 <span data-ttu-id="1c6ec-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="1c6ec-108">**User Action**</span></span>  
  
 <span data-ttu-id="1c6ec-109">入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="1c6ec-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="1c6ec-110">テーブル ループ functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="1c6ec-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="1c6ec-111">説明</span><span class="sxs-lookup"><span data-stu-id="1c6ec-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="1c6ec-112">1</span><span class="sxs-lookup"><span data-stu-id="1c6ec-112">1</span></span>|<span data-ttu-id="1c6ec-113">入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="1c6ec-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="1c6ec-114">2</span><span class="sxs-lookup"><span data-stu-id="1c6ec-114">2</span></span>|<span data-ttu-id="1c6ec-115">使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="1c6ec-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="1c6ec-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="1c6ec-116">3 – 100</span></span>|<span data-ttu-id="1c6ec-117">定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。</span><span class="sxs-lookup"><span data-stu-id="1c6ec-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|