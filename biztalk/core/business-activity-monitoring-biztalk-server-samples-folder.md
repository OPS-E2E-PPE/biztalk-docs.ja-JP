---
title: "ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, BAM
- SDK examples
- BAM, examples
ms.assetid: 670931dd-ed00-477d-ade9-36c866f9234c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb13e92f7c4954de540d65f161afab359fe9ce8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="business-activity-monitoring-biztalk-server-samples-folder"></a><span data-ttu-id="3c245-102">ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="3c245-102">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="3c245-103">Microsoft BizTalk Server には、ソフトウェア開発キット (SDK) のいくつかのビジネス アクティビティ監視 (BAM) サンプルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c245-103">Microsoft BizTalk Server includes several Business Activity Monitoring (BAM) samples in its software development kit (SDK).</span></span> <span data-ttu-id="3c245-104">このセクションでは、各 BAM のサンプルをビルドして、サンプル、および予期される結果を実行する方法が示される機能に関する詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3c245-104">This section provides detailed information about the functionality demonstrated by each BAM sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c245-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3c245-105">In This Section</span></span>  
  
-   <span data-ttu-id="3c245-106">[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c245-106">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span> <span data-ttu-id="3c245-107">示していますか。</span><span class="sxs-lookup"><span data-stu-id="3c245-107">Demonstrates how:</span></span>  
  
    -   <span data-ttu-id="3c245-108">ビジネス アナリストがウィザードを使用して対象のデータを定義し、集計を調べて、アクティビティ データを照会する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3c245-108">A business analyst defines interesting data using a wizard, examines aggregations, and queries activity data.</span></span>  
  
    -   <span data-ttu-id="3c245-109">情報技術 (IT) 管理者が SQL、データ変換サービス (DTS)、およびオンライン分析処理 (OLAP) インフラストラクチャを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3c245-109">An information technology (IT) administrator creates SQL, Data Transformation Services (DTS), and Online Analytical Processing (OLAP) infrastructure.</span></span>  
  
    -   <span data-ttu-id="3c245-110">開発者がビジネスの実装をインストルメント化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3c245-110">A developer instruments the business implementation.</span></span>  
  
-   <span data-ttu-id="3c245-111">[BAM エンド ツー エンド (BizTalk Server サンプル)](../core/bam-end-to-end-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c245-111">[BAM End-to-End (BizTalk Server Sample)](../core/bam-end-to-end-biztalk-server-sample.md).</span></span> <span data-ttu-id="3c245-112">BAM を使用して、複数のコンポーネントのイベントを関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3c245-112">Demonstrates how to correlate events from multiple components using BAM.</span></span>  
  
-   <span data-ttu-id="3c245-113">[オーケストレーションの式 (BizTalk Server サンプル) から BAM API を](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c245-113">[BAM API from an Orchestration Expression (BizTalk Server Sample)](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md).</span></span> <span data-ttu-id="3c245-114">内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3c245-114">Demonstrates how to:</span></span>  
  
    -   <span data-ttu-id="3c245-115">BizTalk Server オーケストレーションから BAM API を使用する方法</span><span class="sxs-lookup"><span data-stu-id="3c245-115">Use the BAM API from a BizTalk Server orchestration.</span></span>  
  
    -   <span data-ttu-id="3c245-116">メッセージ内の繰り返し項目を個別のアクティビティ インスタンスとして追跡する方法</span><span class="sxs-lookup"><span data-stu-id="3c245-116">Track repetitive items inside a message as separate activity instances.</span></span>  
  
    -   <span data-ttu-id="3c245-117">追跡プロファイルを使用してオーケストレーションから追跡した BAM データと、API から追跡したデータとの関係を設定する方法</span><span class="sxs-lookup"><span data-stu-id="3c245-117">Establish a relationship between BAM data tracked from an orchestration using a tracking profile and data tracked from the API.</span></span>