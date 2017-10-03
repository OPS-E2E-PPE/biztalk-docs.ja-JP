---
title: "状態レポートをバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04dad016-e7bb-45cd-b36a-a9c83d073501
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c033f58432c8ae5a2d87b87b56223b8f64a7201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batch-status-report"></a><span data-ttu-id="305b8-102">バッチの状態レポート</span><span class="sxs-lookup"><span data-stu-id="305b8-102">Batch Status Report</span></span>
<span data-ttu-id="305b8-103">このレポートでは、バッチ オーケストレーションのインスタンスのアクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="305b8-103">This report shows the activity of instances of the batching orchestration.</span></span> <span data-ttu-id="305b8-104">レポートの各行には、バッチ オーケストレーションの単一のインスタンスによって処理されているバッチの状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="305b8-104">Each row in the report indicates the status of the batches being processed by a single instance of the batching orchestration.</span></span>  
  
 <span data-ttu-id="305b8-105">保存されたバッチの状態は、バッチの状態レポートでは報告されませんが、インターチェンジ/確認の状態レポートでは報告されます。</span><span class="sxs-lookup"><span data-stu-id="305b8-105">The status of preserved batches is not reported in the Batch Status Report, but is reported in the Interchange/ACK Status report.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="305b8-106">状態レポート内のフィールド</span><span class="sxs-lookup"><span data-stu-id="305b8-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="305b8-107">バッチの状態レポートには、バッチ化されたインターチェンジについての次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="305b8-107">The Batch Status Report displays the following information for batched interchanges:</span></span>  
  
-   <span data-ttu-id="305b8-108">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="305b8-108">Batch Status</span></span>  
  
-   <span data-ttu-id="305b8-109">バッチ名</span><span class="sxs-lookup"><span data-stu-id="305b8-109">Batch Name</span></span>  
  
-   <span data-ttu-id="305b8-110">送信先パーティ名</span><span class="sxs-lookup"><span data-stu-id="305b8-110">Destination Party Name</span></span>  
  
-   <span data-ttu-id="305b8-111">アクティベーション時間</span><span class="sxs-lookup"><span data-stu-id="305b8-111">Activation Time</span></span>  
  
-   <span data-ttu-id="305b8-112">バッチの発生</span><span class="sxs-lookup"><span data-stu-id="305b8-112">Batch Occurrence</span></span>  
  
-   <span data-ttu-id="305b8-113">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="305b8-113">EDI Encoding Type</span></span>  
  
-   <span data-ttu-id="305b8-114">バッチの種類</span><span class="sxs-lookup"><span data-stu-id="305b8-114">Batch Type</span></span>  
  
-   <span data-ttu-id="305b8-115">バッチの対象</span><span class="sxs-lookup"><span data-stu-id="305b8-115">Batch Target</span></span>  
  
-   <span data-ttu-id="305b8-116">バッチ要素数: バッチ要素の数によって累積されたバッチ処理オーケストレーション インスタンス</span><span class="sxs-lookup"><span data-stu-id="305b8-116">Batch Element Count: how many batch elements have been accumulated by the batching orchestration instance</span></span>  
  
-   <span data-ttu-id="305b8-117">拒否された要素数</span><span class="sxs-lookup"><span data-stu-id="305b8-117">Rejected Elements Count</span></span>  
  
-   <span data-ttu-id="305b8-118">バッチがアクティブ化、スケジュールされたリリース、カウントに基づくリリース、手動の上書きリリース、バッチの終了停止/リリース、要素を追加、または外部リリースできる最新のアクション。</span><span class="sxs-lookup"><span data-stu-id="305b8-118">Latest Action: Can be Batch Activated, Scheduled Release, Count Based Release, Manual Override Release, Batch Terminated/Stop Release, Element Added, or External Release</span></span>  
  
-   <span data-ttu-id="305b8-119">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="305b8-119">Interchange Control Number</span></span>  
  
-   <span data-ttu-id="305b8-120">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="305b8-120">Interchange Date Time</span></span>  
  
-   <span data-ttu-id="305b8-121">バッチ サイズ (文字) (既定では表示されません)</span><span class="sxs-lookup"><span data-stu-id="305b8-121">Batch Size (in characters) (not displayed by default)</span></span>  
  
## <a name="view-related-interchanges-status-reports"></a><span data-ttu-id="305b8-122">View Related Interchanges の状態レポート</span><span class="sxs-lookup"><span data-stu-id="305b8-122">View Related Interchanges Status Reports</span></span>  
 <span data-ttu-id="305b8-123">バッチの状態レポートに一覧表示されるインターチェンジまたは確認を右クリックすると、そのバッチに関連するインターチェンジの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="305b8-123">If you right-click an interchange or acknowledgment listed in the Batch Status Report, you can display details about the interchanges related to the batch.</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="305b8-124">状態レポートのクエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="305b8-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="305b8-125">バッチの状態レポートの表示データを指定するクエリ式のフィールドを変更することにより、バッチの状態レポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="305b8-125">You can customize the Batch Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="305b8-126">使用できるフィールドは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="305b8-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="305b8-127">クエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="305b8-127">Query Expression Field</span></span>|<span data-ttu-id="305b8-128">有効な演算子</span><span class="sxs-lookup"><span data-stu-id="305b8-128">Potential Operators</span></span>|<span data-ttu-id="305b8-129">潜在的な値</span><span class="sxs-lookup"><span data-stu-id="305b8-129">Potential Values</span></span>|<span data-ttu-id="305b8-130">既定で含まれますか。</span><span class="sxs-lookup"><span data-stu-id="305b8-130">Included By Default?</span></span>|  
|<span data-ttu-id="305b8-131">検索</span><span class="sxs-lookup"><span data-stu-id="305b8-131">Search for</span></span>|<span data-ttu-id="305b8-132">[等しい]</span><span class="sxs-lookup"><span data-stu-id="305b8-132">Equals</span></span>|<span data-ttu-id="305b8-133">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="305b8-133">Batch Status</span></span>|<span data-ttu-id="305b8-134">指定あり (必須)</span><span class="sxs-lookup"><span data-stu-id="305b8-134">Yes (required)</span></span>|  
|<span data-ttu-id="305b8-135">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="305b8-135">Batch Status</span></span>|<span data-ttu-id="305b8-136">[等しい]</span><span class="sxs-lookup"><span data-stu-id="305b8-136">Equals</span></span><br /><br /> <span data-ttu-id="305b8-137">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="305b8-137">Not Equals</span></span>|<span data-ttu-id="305b8-138">定義されています。 バッチ インスタンスが構成されているが、開始日時が現在の日時より後。</span><span class="sxs-lookup"><span data-stu-id="305b8-138">Defined: The batch instance is configured but the start date time is later than the current date time.</span></span><br /><br /> <span data-ttu-id="305b8-139">アクティブ (既定値): バッチ インスタンスが構成されており、バッチのトランザクション セットを収集します。</span><span class="sxs-lookup"><span data-stu-id="305b8-139">Active (default): The batch instance is configured and is collecting transaction sets for a batch.</span></span> <span data-ttu-id="305b8-140">開始日時が現在の日時よりも前になっています。</span><span class="sxs-lookup"><span data-stu-id="305b8-140">The start date time is earlier than the current date time.</span></span><br /><br /> <span data-ttu-id="305b8-141">リリース日: リリース条件が満たされると、バッチが送信されたやすべてのメッセージが処理される前に、バッチ オーケストレーションが停止したことです。</span><span class="sxs-lookup"><span data-stu-id="305b8-141">Released: The release criteria has been met, and the batch has been sent, or that the batch orchestration was stopped before any messages were processed.</span></span><br /><br /> <span data-ttu-id="305b8-142">完了しました: リリース条件が満たされているが、バッチが送信されていません。</span><span class="sxs-lookup"><span data-stu-id="305b8-142">Completed: The release criteria has been met, but the batch has not been sent.</span></span><br /><br /> <span data-ttu-id="305b8-143">All: 状態は、上記のいずれかであるバッチ インスタンスをすべてを表示します。</span><span class="sxs-lookup"><span data-stu-id="305b8-143">All: Display any batch instance that is in one of the above states.</span></span>|<span data-ttu-id="305b8-144">はい</span><span class="sxs-lookup"><span data-stu-id="305b8-144">Yes</span></span>|  
|<span data-ttu-id="305b8-145">[最大一致数]</span><span class="sxs-lookup"><span data-stu-id="305b8-145">Maximum Matches</span></span>|<span data-ttu-id="305b8-146">[等しい]</span><span class="sxs-lookup"><span data-stu-id="305b8-146">Equals</span></span>|<span data-ttu-id="305b8-147">整数 (既定値 50)</span><span class="sxs-lookup"><span data-stu-id="305b8-147">Integer (default of 50)</span></span>|<span data-ttu-id="305b8-148">はい</span><span class="sxs-lookup"><span data-stu-id="305b8-148">Yes</span></span>|  
|<span data-ttu-id="305b8-149">アクティベーション日時</span><span class="sxs-lookup"><span data-stu-id="305b8-149">Activation Date Time</span></span>|<span data-ttu-id="305b8-150">[以下]</span><span class="sxs-lookup"><span data-stu-id="305b8-150">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="305b8-151">[以上]</span><span class="sxs-lookup"><span data-stu-id="305b8-151">Greater Than or Equals</span></span>|<span data-ttu-id="305b8-152">日付時刻</span><span class="sxs-lookup"><span data-stu-id="305b8-152">Date Time</span></span><br /><br /> <span data-ttu-id="305b8-153">[今日]</span><span class="sxs-lookup"><span data-stu-id="305b8-153">Today</span></span><br /><br /> <span data-ttu-id="305b8-154">5 日前</span><span class="sxs-lookup"><span data-stu-id="305b8-154">Today - 5</span></span>|<span data-ttu-id="305b8-155">不可</span><span class="sxs-lookup"><span data-stu-id="305b8-155">No</span></span><br /><br /> <span data-ttu-id="305b8-156">メモ: クエリ式に 1 回以上含めることができます。</span><span class="sxs-lookup"><span data-stu-id="305b8-156">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="305b8-157">バッチ名</span><span class="sxs-lookup"><span data-stu-id="305b8-157">Batch Name</span></span>|<span data-ttu-id="305b8-158">[等しい]</span><span class="sxs-lookup"><span data-stu-id="305b8-158">Equals</span></span>|<span data-ttu-id="305b8-159">すべて (既定値)</span><span class="sxs-lookup"><span data-stu-id="305b8-159">All (Default)</span></span><br /><br /> <span data-ttu-id="305b8-160">特定のバッチ名</span><span class="sxs-lookup"><span data-stu-id="305b8-160">Specific batch name</span></span>|<span data-ttu-id="305b8-161">不可</span><span class="sxs-lookup"><span data-stu-id="305b8-161">No</span></span>|  
|<span data-ttu-id="305b8-162">送信先パーティ</span><span class="sxs-lookup"><span data-stu-id="305b8-162">Destination Party</span></span>|<span data-ttu-id="305b8-163">[等しい]</span><span class="sxs-lookup"><span data-stu-id="305b8-163">Equals</span></span>|<span data-ttu-id="305b8-164">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="305b8-164">All (default)</span></span><br /><br /> <span data-ttu-id="305b8-165">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="305b8-165">Specific party name</span></span>|<span data-ttu-id="305b8-166">不可</span><span class="sxs-lookup"><span data-stu-id="305b8-166">No</span></span>|  
|<span data-ttu-id="305b8-167">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="305b8-167">EDI encoding type</span></span>|<span data-ttu-id="305b8-168">[等しい]</span><span class="sxs-lookup"><span data-stu-id="305b8-168">Equals</span></span>|<span data-ttu-id="305b8-169">X12</span><span class="sxs-lookup"><span data-stu-id="305b8-169">X12</span></span><br /><br /> <span data-ttu-id="305b8-170">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="305b8-170">EDIFACT</span></span><br /><br /> <span data-ttu-id="305b8-171">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="305b8-171">All (default)</span></span>|<span data-ttu-id="305b8-172">不可</span><span class="sxs-lookup"><span data-stu-id="305b8-172">No</span></span>|  
  
