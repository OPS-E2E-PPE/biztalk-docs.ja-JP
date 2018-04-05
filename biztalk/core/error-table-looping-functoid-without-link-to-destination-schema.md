---
title: エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingNoLinkToDestSchema
ms.assetid: cf162e6a-5c61-4adc-978b-af641db67ed2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329e6670288f05382acf0ea014ba9ae84c4cb645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a><span data-ttu-id="d781c-102">エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません。</span><span class="sxs-lookup"><span data-stu-id="d781c-102">Error - Table Looping Functoid Without Link to Destination Schema</span></span>
<span data-ttu-id="d781c-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d781c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d781c-104">btm1077</span><span class="sxs-lookup"><span data-stu-id="d781c-104">btm1077</span></span>  
  
 <span data-ttu-id="d781c-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d781c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d781c-106">ほとんどの functoid とは異なり、**テーブル ループ**functoid が複数の出力。</span><span class="sxs-lookup"><span data-stu-id="d781c-106">Unlike most functoids, the **Table Looping** functoid has multiple outputs.</span></span> <span data-ttu-id="d781c-107">これらの出力の 1 つを除くすべての環境は、個別のインスタンスに最初の入力パラメーターとして接続されている必要があります、**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="d781c-107">All but one of these outputs must be connected as the first input parameter to separate instances of the **Table Extractor** functoid.</span></span> <span data-ttu-id="d781c-108">残りの出力に接続されている必要があります、**レコード**送信先スキーマのノード (の適切な繰り返し設定)。</span><span class="sxs-lookup"><span data-stu-id="d781c-108">The remaining output must be connected to a **Record** node (with appropriate recurrence settings) in the destination schema.</span></span> <span data-ttu-id="d781c-109">この後者の場合、このエラーが発生した出力リンクから、**テーブル ループ**functoid がありません。</span><span class="sxs-lookup"><span data-stu-id="d781c-109">This error occurs when this latter output link from a **Table Looping** functoid is missing.</span></span>  
  
 <span data-ttu-id="d781c-110">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d781c-110">**User Action**</span></span>  
  
 <span data-ttu-id="d781c-111">指定したドラッグ**テーブル ループ**を適切なレコード**レコード**不足しているリンクを作成する送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="d781c-111">Drag the indicated **Table Looping** record to the appropriate **Record** node in the destination schema to create the missing link.</span></span>