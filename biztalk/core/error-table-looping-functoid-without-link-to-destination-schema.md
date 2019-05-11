---
title: エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません |Microsoft Docs
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
ms.openlocfilehash: ee53c8317b3b5d36c6856123354aab5746d5e84d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346606"
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a><span data-ttu-id="d12e5-102">エラー - テーブル ループ Functoid に送信先スキーマへのリンクがありません。</span><span class="sxs-lookup"><span data-stu-id="d12e5-102">Error - Table Looping Functoid Without Link to Destination Schema</span></span>
<span data-ttu-id="d12e5-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d12e5-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d12e5-104">btm1077</span><span class="sxs-lookup"><span data-stu-id="d12e5-104">btm1077</span></span>  
  
 <span data-ttu-id="d12e5-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d12e5-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d12e5-106">ほとんどの functoid とは異なり、**テーブル ループ**functoid が複数の出力。</span><span class="sxs-lookup"><span data-stu-id="d12e5-106">Unlike most functoids, the **Table Looping** functoid has multiple outputs.</span></span> <span data-ttu-id="d12e5-107">これらの出力の 1 つを除くすべての個別のインスタンスへの最初の入力パラメーターとして接続する必要があります、**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="d12e5-107">All but one of these outputs must be connected as the first input parameter to separate instances of the **Table Extractor** functoid.</span></span> <span data-ttu-id="d12e5-108">残りの出力に接続する必要があります、**レコード**(適切な繰り返しの設定) で、送信先スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="d12e5-108">The remaining output must be connected to a **Record** node (with appropriate recurrence settings) in the destination schema.</span></span> <span data-ttu-id="d12e5-109">このエラーは、この後者の場合に発生します。 出力リンクから、**テーブル ループ**functoid が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="d12e5-109">This error occurs when this latter output link from a **Table Looping** functoid is missing.</span></span>  
  
 <span data-ttu-id="d12e5-110">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d12e5-110">**User Action**</span></span>  
  
 <span data-ttu-id="d12e5-111">指定したドラッグ**テーブル ループ**を適切なレコード**レコード**不足しているリンクを作成する送信先スキーマ内のノード。</span><span class="sxs-lookup"><span data-stu-id="d12e5-111">Drag the indicated **Table Looping** record to the appropriate **Record** node in the destination schema to create the missing link.</span></span>