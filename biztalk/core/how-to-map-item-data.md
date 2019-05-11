---
title: 項目のデータをマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data extraction
- orchestrations, data extraction
- orchestrations, tracking profiles
- tracking profiles, orchestrations
- tracking profiles, data extraction
ms.assetid: ae8b395e-152a-4e08-af31-3c9276f52711
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc3e5c4c4d2ddd4b0051ef5c8b838a0882baa5d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336597"
---
# <a name="how-to-map-item-data"></a><span data-ttu-id="76ef1-102">データ項目をマップする方法</span><span class="sxs-lookup"><span data-stu-id="76ef1-102">How to Map Item Data</span></span>
<span data-ttu-id="76ef1-103">オーケストレーションからのデータ抽出を定義する項目のデータをマップします。</span><span class="sxs-lookup"><span data-stu-id="76ef1-103">You map item data to define the data extraction from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76ef1-104">必要がありますに追跡プロファイルを作成するときにアクティビティ項目と互換性のあるデータ型の値をマップします。</span><span class="sxs-lookup"><span data-stu-id="76ef1-104">You must be certain to map data type values that are compatible with the activity items when creating tracking profiles.</span></span> <span data-ttu-id="76ef1-105">データ型に互換性がない場合、BAM ランタイム エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76ef1-105">If the data types are not compatible you will receive a BAM runtime error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76ef1-106">日付/時刻スタンプなどのマイルス トーンをマップするときマップされているデータは日付タイムスタンプの SQL の文字列形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ef1-106">When mapping milestones, such as Date/Time stamps, the data being mapped must conform to the SQL string representation of a date time stamp.</span></span> <span data-ttu-id="76ef1-107">YYYY、次のように書式設定されている XML の DateTime 形式の DateTime データ-MM-DDTHH:MM:SS.mmm-HH:MM ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76ef1-107">DateTime data in the XML DateTime format that is formatted in the following manner, YYYY-MM-DDTHH:MM:SS.mmm-HH:MM, is not supported.</span></span>  
>   
>  <span data-ttu-id="76ef1-108">たとえば、次の日付文字列、1999-05-31T13:20:00.000-05時 00分はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76ef1-108">For example, the following date string, 1999-05-31T13:20:00.000-05:00, is not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="76ef1-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="76ef1-109">Prerequisites</span></span>  
 <span data-ttu-id="76ef1-110">展開された BAM アクティビティ定義とオーケストレーションに接続します。</span><span class="sxs-lookup"><span data-stu-id="76ef1-110">Deployed BAM activity definitions and orchestrations that you will connect.</span></span>  
  
### <a name="how-to-map-item-data"></a><span data-ttu-id="76ef1-111">項目のデータをマップする方法</span><span class="sxs-lookup"><span data-stu-id="76ef1-111">How to map item data</span></span>  
  
1.  <span data-ttu-id="76ef1-112">既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="76ef1-112">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="76ef1-113">追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ef1-113">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="76ef1-114">シナリオでは、LoanProcessBamDef というアクティビティ定義をインポートします。</span><span class="sxs-lookup"><span data-stu-id="76ef1-114">In the scenario, an activity definition called LoanProcessBamDef is imported.</span></span> <span data-ttu-id="76ef1-115">含まれている、 **LoanProcess**アクティビティ ノードに、顧客の**SSN**が ActivityID として。</span><span class="sxs-lookup"><span data-stu-id="76ef1-115">It contains the **LoanProcess** activity node, with a customer's **SSN** as an ActivityID.</span></span> <span data-ttu-id="76ef1-116">詳細については、次を参照してください。[アクティビティ ノードと ActivityID ノード](../core/activity-and-activityid-nodes.md)します。</span><span class="sxs-lookup"><span data-stu-id="76ef1-116">For more information, see [Activity and ActivityID Nodes](../core/activity-and-activityid-nodes.md).</span></span>  
  
3.  <span data-ttu-id="76ef1-117">すべてのアクティビティに、ActivityID または ContinuationID データ項目を追跡するために顧客の SSN などのことを確認します。</span><span class="sxs-lookup"><span data-stu-id="76ef1-117">Ensure that every activity has an ActivityID or a ContinuationID data item, such as customer SSN, to track.</span></span>  
  
4.  <span data-ttu-id="76ef1-118">オーケストレーションのアクションを追跡するためにイベントを示すために、適切なビジネス イベント フォルダーにマップします。たとえば、ローン処理のシナリオでは、他のユーザーの間で、次の項目がドラッグ下、 **LoanProcess**アクティビティ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="76ef1-118">Map orchestration actions to the appropriate business events folder to indicate the event to track. For example, in a loan processing scenario the following items, among others, would be dragged under the **LoanProcess** activity folder:</span></span>  
  
    -   <span data-ttu-id="76ef1-119">**LoanApplicationReceived**</span><span class="sxs-lookup"><span data-stu-id="76ef1-119">**LoanApplicationReceived**</span></span>  
  
    -   <span data-ttu-id="76ef1-120">**CreditHistoryRequest**</span><span class="sxs-lookup"><span data-stu-id="76ef1-120">**CreditHistoryRequest**</span></span>  
  
    -   <span data-ttu-id="76ef1-121">**CreditHistoryResponse**</span><span class="sxs-lookup"><span data-stu-id="76ef1-121">**CreditHistoryResponse**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ef1-122">参照</span><span class="sxs-lookup"><span data-stu-id="76ef1-122">See Also</span></span>  
 <span data-ttu-id="76ef1-123">[データ項目ノード](../core/data-item-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="76ef1-123">[Data Item Nodes](../core/data-item-nodes.md) </span></span>  
 [<span data-ttu-id="76ef1-124">追跡プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="76ef1-124">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)