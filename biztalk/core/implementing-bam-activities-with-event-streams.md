---
title: "BAM アクティビティのイベント ストリームの実装 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], about activities
- activities [BAM]
- BAM, activities
ms.assetid: 94e6d9dd-93c3-4ab0-9de7-a860dd1e3406
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63594b956affc0f5b94f26ccdcb10d904ef171cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-bam-activities-with-event-streams"></a><span data-ttu-id="32c71-102">イベント ストリームを使用した BAM アクティビティの実装</span><span class="sxs-lookup"><span data-stu-id="32c71-102">Implementing BAM Activities with Event Streams</span></span>
<span data-ttu-id="32c71-103">BAM アクティビティは、注文書やローンの申し込みなど、ビジネスの作業単位を表します。</span><span class="sxs-lookup"><span data-stu-id="32c71-103">A BAM activity represents a unit of work in the business, such as purchase order or loan application.</span></span> <span data-ttu-id="32c71-104">アクティビティは、作業単位に関する履歴 (マイルストーン) とデータをビジネス エンド ユーザーまたはインフォメーション ワーカーに提示します。</span><span class="sxs-lookup"><span data-stu-id="32c71-104">The activity shows the history (milestones) and data about this unit of work to the business end user, or information worker.</span></span> <span data-ttu-id="32c71-105">たとえば、ローンの申し込みアクティビティには、"ローン承認済み" などのマイルストーンや、"申し込み者名" や "ローン金額" などのデータが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="32c71-105">For example, a loan application activity might contain milestones such as “Loan approved” and data such as “Applicant name” and “Loan amount.”</span></span> <span data-ttu-id="32c71-106">BAM アクティビティは、抽象化レベルが高いため実際に実装されている IT インフラストラクチャから独立していますが、ビジネス プロセスに直接マップされることもあります。</span><span class="sxs-lookup"><span data-stu-id="32c71-106">BAM activities often map directly to a business process, although as a high-level abstraction an activity is independent of the actual implementation of your IT infrastructure.</span></span>  
  
 <span data-ttu-id="32c71-107">開発者は、特定のアクティビティのコンテキストに含まれる実装から関連のあるマイルストーンとデータのみを公開することによって、この抽象化のレベルを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32c71-107">Your job as a developer is to maintain this abstraction by exposing only the relevant milestones and data from the implementation in the context of a specific activity.</span></span> <span data-ttu-id="32c71-108">アクティビティの使用方法を示すコード サンプルは、次を参照してください。 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="32c71-108">For a code sample that demonstrates the use of an activity, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32c71-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="32c71-109">In This Section</span></span>  
  
-   [<span data-ttu-id="32c71-110">BAM のコードを記述する理由</span><span class="sxs-lookup"><span data-stu-id="32c71-110">Why Write Code For BAM?</span></span>](../core/why-write-code-for-bam.md)  
  
-   [<span data-ttu-id="32c71-111">開発者用の BAM 概念</span><span class="sxs-lookup"><span data-stu-id="32c71-111">BAM Concepts for the Developer</span></span>](../core/bam-concepts-for-the-developer.md)  
  
-   [<span data-ttu-id="32c71-112">BAM 開発プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="32c71-112">Overview of the BAM Development Process</span></span>](../core/overview-of-the-bam-development-process.md)  
  
-   [<span data-ttu-id="32c71-113">EventStream クラス</span><span class="sxs-lookup"><span data-stu-id="32c71-113">EventStream Classes</span></span>](../core/eventstream-classes.md)  
  
-   [<span data-ttu-id="32c71-114">アクティビティを使用</span><span class="sxs-lookup"><span data-stu-id="32c71-114">Using an Activity</span></span>](../core/using-an-activity.md)  
  
-   [<span data-ttu-id="32c71-115">アクティビティの関係</span><span class="sxs-lookup"><span data-stu-id="32c71-115">Activity Relationships</span></span>](../core/activity-relationships.md)  
  
-   [<span data-ttu-id="32c71-116">アクティビティ Continuation</span><span class="sxs-lookup"><span data-stu-id="32c71-116">Activity Continuation</span></span>](../core/activity-continuation.md)  
  
-   [<span data-ttu-id="32c71-117">ループ アクティビティ</span><span class="sxs-lookup"><span data-stu-id="32c71-117">Looping Activities</span></span>](../core/looping-activities.md)  
  
-   [<span data-ttu-id="32c71-118">ソリューションのインストルメント化: API の使用方法の詳細な手順</span><span class="sxs-lookup"><span data-stu-id="32c71-118">Instrumenting a Solution: Step-by-Step API Usage</span></span>](../core/instrumenting-a-solution-step-by-step-api-usage.md)