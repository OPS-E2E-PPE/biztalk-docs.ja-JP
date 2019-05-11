---
title: エラー - の 2 番目の入力テーブル ループ Functoid が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableLoopingNotValid
ms.assetid: 22771f36-5969-40b1-a957-3ca67e19c3fd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24ab38e947667e894445399e1916fe9e0a3b26fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346917"
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a><span data-ttu-id="f933a-102">エラー - の 2 番目の入力テーブル ループ Functoid が無効です。</span><span class="sxs-lookup"><span data-stu-id="f933a-102">Error - Second Input for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="f933a-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="f933a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f933a-104">btm1072</span><span class="sxs-lookup"><span data-stu-id="f933a-104">btm1072</span></span>  
  
 <span data-ttu-id="f933a-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="f933a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f933a-106">2 番目の入力パラメーターを関連する**テーブル ループ**functoid が無効です。</span><span class="sxs-lookup"><span data-stu-id="f933a-106">The second input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="f933a-107">このパラメーターは、関連付けられているテーブル ループ グリッド内の列の数を示す正の整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f933a-107">This parameter must be a positive integer that indicates the number of columns in the associated table looping grid.</span></span>  
  
 <span data-ttu-id="f933a-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="f933a-108">**User Action**</span></span>  
  
 <span data-ttu-id="f933a-109">入力パラメーターを必ず、**テーブル ループ**functoid を使用してアクセス、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="f933a-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="f933a-110">テーブル ループ functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="f933a-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="f933a-111">説明</span><span class="sxs-lookup"><span data-stu-id="f933a-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="f933a-112">1</span><span class="sxs-lookup"><span data-stu-id="f933a-112">1</span></span>|<span data-ttu-id="f933a-113">入力インスタンス メッセージが関連付けられている、一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールド、うちの出現回数**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f933a-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="f933a-114">2</span><span class="sxs-lookup"><span data-stu-id="f933a-114">2</span></span>|<span data-ttu-id="f933a-115">使用して構成データのテーブルの列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="f933a-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="f933a-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="f933a-116">3 – 100</span></span>|<span data-ttu-id="f933a-117">定数と、テーブル ループ グリッドを使用してデータの取得元となる (送信元スキーマまたは他の functoid からの出力の場合) からのリンク。</span><span class="sxs-lookup"><span data-stu-id="f933a-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|