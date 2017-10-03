---
title: "EDI トランザクション セット メッセージの構造体要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: caea8408-c09c-4525-a9c9-18abe4432594
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d49288e9a311c9766e61fe985b9e279a8660f4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-transaction-set-message-structural-element"></a><span data-ttu-id="14377-102">EDI トランザクション セット メッセージの構造体要素</span><span class="sxs-lookup"><span data-stu-id="14377-102">EDI Transaction Set-Message Structural Element</span></span>
<span data-ttu-id="14377-103">トランザクション セット (X12 エンコード) またはメッセージ (EDIFACT エンコード) には、メッセージ データを構成するセグメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14377-103">The transaction set (in X12 encoding) or message (in EDIFACT encoding) contains segments that make up the message data.</span></span> <span data-ttu-id="14377-104">トランザクション セットは、ヘッダー、データ セグメントのコレクション、およびトレーラで構成されています。</span><span class="sxs-lookup"><span data-stu-id="14377-104">The transaction set consists of a header, a collection of data segments, and a trailer.</span></span> <span data-ttu-id="14377-105">トランザクションの処理に必要なすべての詳細情報は、トランザクション セット内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="14377-105">All details that are required to process the transaction are available within the transaction set.</span></span>  
  
 <span data-ttu-id="14377-106">トランザクション セットは、ST トランザクション セット ヘッダー (X12 の場合) または UNH メッセージ ヘッダー (EDIFACT の場合) で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14377-106">A transaction set must start with a ST Transaction Set Header (in X12) or a UNH Message Header (in EDIFACT).</span></span> <span data-ttu-id="14377-107">また、SE トランザクション セット トレーラ (X12 の場合) または UNT メッセージ トレーラ (EDIFACT の場合) で終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14377-107">It must end with a SE Transaction Set Trailer (in X12) or a UNT Message Trailer (in EDIFACT).</span></span> <span data-ttu-id="14377-108">トレーラは、ヘッダー セグメントとトレーラ セグメントを含めたデータ セグメントの数を提供します。</span><span class="sxs-lookup"><span data-stu-id="14377-108">The trailer provides a count of the data segments that includes the header and trailer segments.</span></span>  
  
 <span data-ttu-id="14377-109">トランザクション セットには、関連するセグメントのコレクションを繰り返すために必要なループを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="14377-109">A transaction set can contain one or more loops, which are required to repeat a collection of related segments.</span></span>