---
title: 開発者のための BAM 概念 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c26d0aed-821c-4e1f-9cc9-9375a2ba28de
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc6d74eb8b14479776febea1530e142e6897729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967451"
---
# <a name="bam-concepts-for-the-developer"></a><span data-ttu-id="b5b58-102">開発者のための BAM 概念</span><span class="sxs-lookup"><span data-stu-id="b5b58-102">BAM Concepts for the Developer</span></span>
<span data-ttu-id="b5b58-103">BAM 開発者は、アクティビティ、Continuation、参照など重要な BAM 概念を十分に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5b58-103">As a BAM developer, you need to be familiar with important BAM concepts, such as activities, continuations, and references.</span></span> <span data-ttu-id="b5b58-104">また、追跡とトランザクション処理の違いについても理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5b58-104">You should also understand the differences between tracking and transactional processing.</span></span>  
  
## <a name="what-is-a-bam-activity"></a><span data-ttu-id="b5b58-105">BAM アクティビティについて</span><span class="sxs-lookup"><span data-stu-id="b5b58-105">What Is a BAM Activity?</span></span>  
 <span data-ttu-id="b5b58-106">BAM アクティビティは、ビジネス プロセスの 1 つの項目 (1 つの注文書など) の対象となるデータの定義です。</span><span class="sxs-lookup"><span data-stu-id="b5b58-106">A BAM activity is the definition of what data is interesting for an item in the business process (such as a single PO).</span></span> <span data-ttu-id="b5b58-107">BAM データベース内に格納される列を定義します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-107">It defines what columns are in the BAM database.</span></span>  
  
 <span data-ttu-id="b5b58-108">アクティビティのインスタンスは、注文書やローンの申し込みなど、ビジネスの作業単位を表します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-108">An instance of an activity represents a unit of work in the business, such as a purchase order or a loan application.</span></span> <span data-ttu-id="b5b58-109">アクティビティは、マイルストーン (アクティビティの履歴) の一覧と対象データを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-109">An activity specifies a list of milestones (the history of the activity) and data of interest.</span></span> <span data-ttu-id="b5b58-110">アクティビティのインスタンスは、BAM プライマリ インポート データベース内の単一の行として示されます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-110">An instance of an activity is manifested as a single row in the BAM Primary Import database.</span></span> <span data-ttu-id="b5b58-111">アクティビティのそのインスタンスに対するデータ項目の値は 1 つだけ存在します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-111">There is one and only one value for any data item for that instance of the activity.</span></span>  
  
 <span data-ttu-id="b5b58-112">アクティビティを使用して、作業単位に関するマイルストーンとデータをビジネス エンド ユーザーまたはインフォメーション ワーカーに提示します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-112">An activity is used to show the milestones and data about this unit of work to the business end user, or information worker.</span></span> <span data-ttu-id="b5b58-113">たとえば、BAM SDK サンプルで定義されているアクティビティには、"支払い済み" や "送信" などのマイルストーンに加え、"合計金額" などの対象データも含まれています。</span><span class="sxs-lookup"><span data-stu-id="b5b58-113">For example, the activity defined in the BAM SDK sample contains milestones such as “Paid” and "Send," as well data of interest such as “Total Amount.”</span></span>  
  
 <span data-ttu-id="b5b58-114">BAM アクティビティは、抽象化レベルが高いため実際に実装されている IT インフラストラクチャから独立していますが、ビジネス プロセスに直接マップされることもあります。</span><span class="sxs-lookup"><span data-stu-id="b5b58-114">BAM activities often map directly to a business process, although as a high-level abstraction an activity is independent of the actual implementation of your IT infrastructure.</span></span>  
  
 <span data-ttu-id="b5b58-115">開発者は、特定のアクティビティのコンテキストに含まれる実装から関連のあるマイルストーンとデータのみを公開することによって、この抽象化のレベルを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5b58-115">Your job as a developer is to maintain this abstraction by exposing only the relevant milestones and data from the implementation in the context of a specific activity.</span></span>  
  
## <a name="what-is-a-continuation"></a><span data-ttu-id="b5b58-116">Continuation について</span><span class="sxs-lookup"><span data-stu-id="b5b58-116">What Is a Continuation?</span></span>  
 <span data-ttu-id="b5b58-117">Continuation は、次の情報に関するガイダンスを BAM インフラストラクチャに提供します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-117">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
- <span data-ttu-id="b5b58-118">イベントの発生順序</span><span class="sxs-lookup"><span data-stu-id="b5b58-118">The order in which events are expected to occur</span></span>  
  
- <span data-ttu-id="b5b58-119">イベント項目が関連付けられている一意 ID が変更された場合の処理方法</span><span class="sxs-lookup"><span data-stu-id="b5b58-119">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
  <span data-ttu-id="b5b58-120">継続タスクとその使用方法の詳細については、[Continuation ノードと ContinuationID ノード](../core/continuation-and-continuationid-nodes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5b58-120">For more information about Continuations and how they are used, see [Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md).</span></span>  
  
## <a name="what-is-a-reference"></a><span data-ttu-id="b5b58-121">参照について</span><span class="sxs-lookup"><span data-stu-id="b5b58-121">What Is a Reference?</span></span>  
 <span data-ttu-id="b5b58-122">参照 (関連アクティビティとも呼びます) は、アクティビティと他の項目間の関係を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-122">A reference (also known as a related activity) specifies a relationship between an activity and some other item.</span></span> <span data-ttu-id="b5b58-123">関連付けることができる項目には、別のアクティビティやドキュメントの場所などがあります。</span><span class="sxs-lookup"><span data-stu-id="b5b58-123">Examples of items that can be related are another activity or a document location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5b58-124">アクティビティを関連アクティビティとして指定すると、Continuation アクティビティとは異なり、関連アクティビティが完了していない場合でも現在のアクティビティは完了対象から除外されません。</span><span class="sxs-lookup"><span data-stu-id="b5b58-124">When you specify an activity as a related activity, the current activity is not, unlike a continuation activity, precluded from completing if the related activity has not completed.</span></span>  
  
## <a name="tracking-and-transactional-processing"></a><span data-ttu-id="b5b58-125">追跡とトランザクション処理</span><span class="sxs-lookup"><span data-stu-id="b5b58-125">Tracking and Transactional Processing</span></span>  
 <span data-ttu-id="b5b58-126">BAM のコードを記述して、データの追跡方法、つまり追跡機能を使用するか、トランザクション処理を使用するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-126">Writing code for BAM gives you control of the way data is tracked, that is, through tracking or transactional processing.</span></span> <span data-ttu-id="b5b58-127">既定では、BAM は追跡と処理を同等に重視します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-127">By default, BAM assigns equal importance to tracking and processing.</span></span> <span data-ttu-id="b5b58-128">つまり、追跡機能またはトランザクション処理が失敗すると、どちらも続行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b5b58-128">This means that if either the tracking function or the transaction process fails, neither is allowed to proceed.</span></span> <span data-ttu-id="b5b58-129">追跡データベースには何も記録されず、トランザクションはロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-129">Nothing is recorded in the tracking database and the transaction is rolled back.</span></span> <span data-ttu-id="b5b58-130">この方法は、ソリューションに対して推奨される追跡方法ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5b58-130">This may not be the preferred method of tracking for your solution.</span></span> <span data-ttu-id="b5b58-131">BAM 用に開発することで、追跡機能とトランザクション処理のどちらを優先するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-131">By developing for BAM you can determine whether tracking or transactional processing takes precedence.</span></span>  
  
 <span data-ttu-id="b5b58-132">次の表に、BAM でのデータ追跡モードを示します。</span><span class="sxs-lookup"><span data-stu-id="b5b58-132">The following table describes the modes of tracking data in BAM.</span></span>  
  
|<span data-ttu-id="b5b58-133">シナリオ</span><span class="sxs-lookup"><span data-stu-id="b5b58-133">Scenario</span></span>|<span data-ttu-id="b5b58-134">[説明]</span><span class="sxs-lookup"><span data-stu-id="b5b58-134">Descriptions</span></span>|  
|--------------|------------------|  
|<span data-ttu-id="b5b58-135">処理よりも追跡を優先</span><span class="sxs-lookup"><span data-stu-id="b5b58-135">Tracking Over Processing</span></span>|<span data-ttu-id="b5b58-136">処理が成功すると、追跡情報が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-136">If the process succeeds, write tracking information.</span></span><br /><br /> <span data-ttu-id="b5b58-137">処理が失敗すると、エラーに関する情報が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-137">If the process fails, write information about the failure.</span></span>|  
|<span data-ttu-id="b5b58-138">処理と追跡は同等</span><span class="sxs-lookup"><span data-stu-id="b5b58-138">Processing Equal to Tracking</span></span>|<span data-ttu-id="b5b58-139">追跡または処理が失敗すると、すべてがロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-139">If either tracking or processing fails, roll back everything.</span></span>|  
|<span data-ttu-id="b5b58-140">追跡よりも処理を優先</span><span class="sxs-lookup"><span data-stu-id="b5b58-140">Processing Over Tracking</span></span>|<span data-ttu-id="b5b58-141">処理が成功し、追跡機能が失敗すると、処理は続行されます。</span><span class="sxs-lookup"><span data-stu-id="b5b58-141">If the process succeeds and the tracking function fails, continue processing.</span></span>|