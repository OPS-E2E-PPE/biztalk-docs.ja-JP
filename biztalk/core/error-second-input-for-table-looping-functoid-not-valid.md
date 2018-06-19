---
title: エラー - の 2 番目の入力テーブル ループ Functoid は無効です |Microsoft ドキュメント
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
ms.openlocfilehash: abb321a26300a514357225713db1b197fb828851
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970264"
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a><span data-ttu-id="a690d-102">エラー - の 2 番目の入力テーブル ループ Functoid は無効です。</span><span class="sxs-lookup"><span data-stu-id="a690d-102">Error - Second Input for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="a690d-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="a690d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a690d-104">btm1072</span><span class="sxs-lookup"><span data-stu-id="a690d-104">btm1072</span></span>  
  
 <span data-ttu-id="a690d-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="a690d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a690d-106">2 番目の入力パラメーターを関連する**テーブル ループ**functoid が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a690d-106">The second input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="a690d-107">このパラメーターは、関連付けられているテーブル ループ グリッドの列数を示す正の整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a690d-107">This parameter must be a positive integer that indicates the number of columns in the associated table looping grid.</span></span>  
  
 <span data-ttu-id="a690d-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="a690d-108">**User Action**</span></span>  
  
 <span data-ttu-id="a690d-109">入力パラメーターを確認してください、**テーブル ループ**を介してアクセスされると、functoid、**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**  ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="a690d-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="a690d-110">テーブル ループ Functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="a690d-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="a690d-111">Description</span><span class="sxs-lookup"><span data-stu-id="a690d-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="a690d-112">1</span><span class="sxs-lookup"><span data-stu-id="a690d-112">1</span></span>|<span data-ttu-id="a690d-113">入力インスタンス メッセージが関連付けられている一連の回数を制御レコードからリンクまたは送信元スキーマ内のフィールドの出現回数を**テーブル抽出**functoid が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a690d-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="a690d-114">2</span><span class="sxs-lookup"><span data-stu-id="a690d-114">2</span></span>|<span data-ttu-id="a690d-115">使用して構成データ テーブル内の列の数、**テーブル ループ グリッド**の関連プロパティ**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="a690d-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="a690d-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="a690d-116">3 – 100</span></span>|<span data-ttu-id="a690d-117">テーブル ループのグリッドで使用できるデータ ソースとなる定数および (送信元スキーマまたは他の Functoid の出力からの) リンク。</span><span class="sxs-lookup"><span data-stu-id="a690d-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|