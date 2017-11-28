---
title: "項目のデータをマップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data extraction
- orchestrations, data extraction
- orchestrations, tracking profiles
- tracking profiles, orchestrations
- tracking profiles, data extraction
ms.assetid: ae8b395e-152a-4e08-af31-3c9276f52711
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdfd722e1610be02c06dd6e2a9597e13c0f1e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-item-data"></a><span data-ttu-id="7c1bc-102">データ項目をマップする方法</span><span class="sxs-lookup"><span data-stu-id="7c1bc-102">How to Map Item Data</span></span>
<span data-ttu-id="7c1bc-103">データ項目をマップして、オーケストレーションからのデータ抽出を定義します。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-103">You map item data to define the data extraction from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c1bc-104">追跡プロファイルを作成する際には、マップする値がアクティビティ項目と互換性のあるデータ型の値であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-104">You must be certain to map data type values that are compatible with the activity items when creating tracking profiles.</span></span> <span data-ttu-id="7c1bc-105">データ型に互換性がないと、BAM 実行時エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-105">If the data types are not compatible you will receive a BAM runtime error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c1bc-106">日付時刻スタンプなど、マイルストーンをマップする際、マップするデータは日付時刻スタンプを表す SQL 文字列表記に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-106">When mapping milestones, such as Date/Time stamps, the data being mapped must conform to the SQL string representation of a date time stamp.</span></span> <span data-ttu-id="7c1bc-107">YYYY-MM-DDTHH:MM:SS.mmm-HH:MM という XML の DateTime 形式で表記された DateTime データはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-107">DateTime data in the XML DateTime format that is formatted in the following manner, YYYY-MM-DDTHH:MM:SS.mmm-HH:MM, is not supported.</span></span>  
>   
>  <span data-ttu-id="7c1bc-108">たとえば、1999-05-31T13:20:00.000-05:00 という日付文字列はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-108">For example, the following date string, 1999-05-31T13:20:00.000-05:00, is not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7c1bc-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="7c1bc-109">Prerequisites</span></span>  
 <span data-ttu-id="7c1bc-110">BAM アクティビティ定義と、接続先のオーケストレーションを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-110">Deployed BAM activity definitions and orchestrations that you will connect.</span></span>  
  
### <a name="how-to-map-item-data"></a><span data-ttu-id="7c1bc-111">項目のデータをマップする方法</span><span class="sxs-lookup"><span data-stu-id="7c1bc-111">How to map item data</span></span>  
  
1.  <span data-ttu-id="7c1bc-112">既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-112">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="7c1bc-113">追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)です。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-113">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="7c1bc-114">このシナリオでは、LoanProcessBamDef という名前のアクティビティ定義をインポートします。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-114">In the scenario, an activity definition called LoanProcessBamDef is imported.</span></span> <span data-ttu-id="7c1bc-115">含まれている、 **LoanProcess**アクティビティ ノードには、お客様の**SSN**が ActivityID として。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-115">It contains the **LoanProcess** activity node, with a customer's **SSN** as an ActivityID.</span></span> <span data-ttu-id="7c1bc-116">詳細については、次を参照してください。[アクティビティ ノードと ActivityID ノード](../core/activity-and-activityid-nodes.md)です。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-116">For more information, see [Activity and ActivityID Nodes](../core/activity-and-activityid-nodes.md).</span></span>  
  
3.  <span data-ttu-id="7c1bc-117">すべてのアクティビティに、顧客の SSN など、追跡する ActivityID データ項目または ContinuationID データ項目があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-117">Ensure that every activity has an ActivityID or a ContinuationID data item, such as customer SSN, to track.</span></span>  
  
4.  <span data-ttu-id="7c1bc-118">オーケストレーションのアクションを適切な Business Events フォルダーにマップして、追跡するイベントを示します。たとえば、ローン処理のシナリオでは、他のユーザー間で、次の項目はドロップ下にある、 **LoanProcess**アクティビティ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-118">Map orchestration actions to the appropriate business events folder to indicate the event to track. For example, in a loan processing scenario the following items, among others, would be dragged under the **LoanProcess** activity folder:</span></span>  
  
    -   <span data-ttu-id="7c1bc-119">**LoanApplicationReceived**</span><span class="sxs-lookup"><span data-stu-id="7c1bc-119">**LoanApplicationReceived**</span></span>  
  
    -   <span data-ttu-id="7c1bc-120">**CreditHistoryRequest**</span><span class="sxs-lookup"><span data-stu-id="7c1bc-120">**CreditHistoryRequest**</span></span>  
  
    -   <span data-ttu-id="7c1bc-121">**CreditHistoryResponse**</span><span class="sxs-lookup"><span data-stu-id="7c1bc-121">**CreditHistoryResponse**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1bc-122">参照</span><span class="sxs-lookup"><span data-stu-id="7c1bc-122">See Also</span></span>  
 <span data-ttu-id="7c1bc-123">[データ項目ノード](../core/data-item-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="7c1bc-123">[Data Item Nodes](../core/data-item-nodes.md) </span></span>  
 [<span data-ttu-id="7c1bc-124">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c1bc-124">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)