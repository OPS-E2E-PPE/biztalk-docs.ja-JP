---
title: 状態レポートをバッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04dad016-e7bb-45cd-b36a-a9c83d073501
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a717d35073ead8a15aaec47cdcbe85e41988107
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529175"
---
# <a name="batch-status-report"></a><span data-ttu-id="ad545-102">バッチの状態レポート</span><span class="sxs-lookup"><span data-stu-id="ad545-102">Batch Status Report</span></span>
<span data-ttu-id="ad545-103">このレポートには、バッチ処理オーケストレーションのインスタンスのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad545-103">This report shows the activity of instances of the batching orchestration.</span></span> <span data-ttu-id="ad545-104">レポート内の各行では、バッチ処理オーケストレーションの単一のインスタンスによって処理されているバッチの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="ad545-104">Each row in the report indicates the status of the batches being processed by a single instance of the batching orchestration.</span></span>  
  
 <span data-ttu-id="ad545-105">保存されたバッチの状態は、バッチ状態レポートでは報告されませんが、インターチェンジ/確認の状態レポートで報告されます。</span><span class="sxs-lookup"><span data-stu-id="ad545-105">The status of preserved batches is not reported in the Batch Status Report, but is reported in the Interchange/ACK Status report.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="ad545-106">状態レポート内のフィールド</span><span class="sxs-lookup"><span data-stu-id="ad545-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="ad545-107">バッチの状態レポートには、バッチ インターチェンジに次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad545-107">The Batch Status Report displays the following information for batched interchanges:</span></span>  
  
-   <span data-ttu-id="ad545-108">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="ad545-108">Batch Status</span></span>  
  
-   <span data-ttu-id="ad545-109">バッチ名</span><span class="sxs-lookup"><span data-stu-id="ad545-109">Batch Name</span></span>  
  
-   <span data-ttu-id="ad545-110">送信先パーティ名</span><span class="sxs-lookup"><span data-stu-id="ad545-110">Destination Party Name</span></span>  
  
-   <span data-ttu-id="ad545-111">アクティブ化時刻</span><span class="sxs-lookup"><span data-stu-id="ad545-111">Activation Time</span></span>  
  
-   <span data-ttu-id="ad545-112">バッチの発生</span><span class="sxs-lookup"><span data-stu-id="ad545-112">Batch Occurrence</span></span>  
  
-   <span data-ttu-id="ad545-113">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="ad545-113">EDI Encoding Type</span></span>  
  
-   <span data-ttu-id="ad545-114">バッチの種類</span><span class="sxs-lookup"><span data-stu-id="ad545-114">Batch Type</span></span>  
  
-   <span data-ttu-id="ad545-115">バッチの対象</span><span class="sxs-lookup"><span data-stu-id="ad545-115">Batch Target</span></span>  
  
-   <span data-ttu-id="ad545-116">バッチ要素数: バッチ要素の数によって累積されたバッチ処理オーケストレーション インスタンス</span><span class="sxs-lookup"><span data-stu-id="ad545-116">Batch Element Count: how many batch elements have been accumulated by the batching orchestration instance</span></span>  
  
-   <span data-ttu-id="ad545-117">拒否された要素数</span><span class="sxs-lookup"><span data-stu-id="ad545-117">Rejected Elements Count</span></span>  
  
-   <span data-ttu-id="ad545-118">最新のアクション:バッチがアクティブ化、スケジュールされたリリース、カウントに基づくリリース、手動の上書きリリース、バッチの終了停止/リリース、要素が追加、または外部リリースすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad545-118">Latest Action: Can be Batch Activated, Scheduled Release, Count Based Release, Manual Override Release, Batch Terminated/Stop Release, Element Added, or External Release</span></span>  
  
-   <span data-ttu-id="ad545-119">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="ad545-119">Interchange Control Number</span></span>  
  
-   <span data-ttu-id="ad545-120">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="ad545-120">Interchange Date Time</span></span>  
  
-   <span data-ttu-id="ad545-121">バッチ サイズ (文字) (既定では表示されません)</span><span class="sxs-lookup"><span data-stu-id="ad545-121">Batch Size (in characters) (not displayed by default)</span></span>  
  
## <a name="view-related-interchanges-status-reports"></a><span data-ttu-id="ad545-122">関連するインターチェンジの状態レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="ad545-122">View Related Interchanges Status Reports</span></span>  
 <span data-ttu-id="ad545-123">インターチェンジまたは受信確認のバッチの状態レポートで一覧表示を右クリックした場合、バッチに関連するインターチェンジの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ad545-123">If you right-click an interchange or acknowledgment listed in the Batch Status Report, you can display details about the interchanges related to the batch.</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="ad545-124">状態レポートのクエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="ad545-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="ad545-125">表示されるデータを決定するクエリ式のフィールドを変更することで、バッチ状態レポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ad545-125">You can customize the Batch Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="ad545-126">使用できるフィールドは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad545-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ad545-127">クエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="ad545-127">Query Expression Field</span></span>|<span data-ttu-id="ad545-128">有効な演算子</span><span class="sxs-lookup"><span data-stu-id="ad545-128">Potential Operators</span></span>|<span data-ttu-id="ad545-129">潜在的な値</span><span class="sxs-lookup"><span data-stu-id="ad545-129">Potential Values</span></span>|<span data-ttu-id="ad545-130">既定で含まれますか。</span><span class="sxs-lookup"><span data-stu-id="ad545-130">Included By Default?</span></span>|  
|<span data-ttu-id="ad545-131">検索</span><span class="sxs-lookup"><span data-stu-id="ad545-131">Search for</span></span>|<span data-ttu-id="ad545-132">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ad545-132">Equals</span></span>|<span data-ttu-id="ad545-133">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="ad545-133">Batch Status</span></span>|<span data-ttu-id="ad545-134">指定あり (必須)</span><span class="sxs-lookup"><span data-stu-id="ad545-134">Yes (required)</span></span>|  
|<span data-ttu-id="ad545-135">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="ad545-135">Batch Status</span></span>|<span data-ttu-id="ad545-136">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ad545-136">Equals</span></span><br /><br /> <span data-ttu-id="ad545-137">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="ad545-137">Not Equals</span></span>|<span data-ttu-id="ad545-138">定義されています。バッチ インスタンスが構成されますが、開始日時は現在の日時よりも後。</span><span class="sxs-lookup"><span data-stu-id="ad545-138">Defined: The batch instance is configured but the start date time is later than the current date time.</span></span><br /><br /> <span data-ttu-id="ad545-139">アクティブ (既定値):バッチ インスタンスが構成され、バッチのトランザクション セットを収集します。</span><span class="sxs-lookup"><span data-stu-id="ad545-139">Active (default): The batch instance is configured and is collecting transaction sets for a batch.</span></span> <span data-ttu-id="ad545-140">開始日時は、現在の日時より前です。</span><span class="sxs-lookup"><span data-stu-id="ad545-140">The start date time is earlier than the current date time.</span></span><br /><br /> <span data-ttu-id="ad545-141">リリース日。リリース条件が満たされましたやバッチが送信されたすべてのメッセージが処理される前に、バッチ オーケストレーションが停止したことです。</span><span class="sxs-lookup"><span data-stu-id="ad545-141">Released: The release criteria has been met, and the batch has been sent, or that the batch orchestration was stopped before any messages were processed.</span></span><br /><br /> <span data-ttu-id="ad545-142">完了。リリース条件が満たされましたが、バッチが送信されていません。</span><span class="sxs-lookup"><span data-stu-id="ad545-142">Completed: The release criteria has been met, but the batch has not been sent.</span></span><br /><br /> <span data-ttu-id="ad545-143">すべての：上記の状態のいずれかであるバッチ インスタンスをすべてを表示します。</span><span class="sxs-lookup"><span data-stu-id="ad545-143">All: Display any batch instance that is in one of the above states.</span></span>|<span data-ttu-id="ad545-144">はい</span><span class="sxs-lookup"><span data-stu-id="ad545-144">Yes</span></span>|  
|<span data-ttu-id="ad545-145">[最大一致数]</span><span class="sxs-lookup"><span data-stu-id="ad545-145">Maximum Matches</span></span>|<span data-ttu-id="ad545-146">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ad545-146">Equals</span></span>|<span data-ttu-id="ad545-147">整数 (既定値 50)</span><span class="sxs-lookup"><span data-stu-id="ad545-147">Integer (default of 50)</span></span>|<span data-ttu-id="ad545-148">はい</span><span class="sxs-lookup"><span data-stu-id="ad545-148">Yes</span></span>|  
|<span data-ttu-id="ad545-149">アクティベーション日時</span><span class="sxs-lookup"><span data-stu-id="ad545-149">Activation Date Time</span></span>|<span data-ttu-id="ad545-150">[以下]</span><span class="sxs-lookup"><span data-stu-id="ad545-150">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="ad545-151">[以上]</span><span class="sxs-lookup"><span data-stu-id="ad545-151">Greater Than or Equals</span></span>|<span data-ttu-id="ad545-152">日付時刻</span><span class="sxs-lookup"><span data-stu-id="ad545-152">Date Time</span></span><br /><br /> <span data-ttu-id="ad545-153">[今日]</span><span class="sxs-lookup"><span data-stu-id="ad545-153">Today</span></span><br /><br /> <span data-ttu-id="ad545-154">今日 - 5</span><span class="sxs-lookup"><span data-stu-id="ad545-154">Today - 5</span></span>|<span data-ttu-id="ad545-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad545-155">No</span></span><br /><br /> <span data-ttu-id="ad545-156">注:できますに含めることが 1 回以上のクエリ式です。</span><span class="sxs-lookup"><span data-stu-id="ad545-156">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="ad545-157">バッチ名</span><span class="sxs-lookup"><span data-stu-id="ad545-157">Batch Name</span></span>|<span data-ttu-id="ad545-158">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ad545-158">Equals</span></span>|<span data-ttu-id="ad545-159">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="ad545-159">All (Default)</span></span><br /><br /> <span data-ttu-id="ad545-160">特定のバッチ名</span><span class="sxs-lookup"><span data-stu-id="ad545-160">Specific batch name</span></span>|<span data-ttu-id="ad545-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad545-161">No</span></span>|  
|<span data-ttu-id="ad545-162">送信先パーティ</span><span class="sxs-lookup"><span data-stu-id="ad545-162">Destination Party</span></span>|<span data-ttu-id="ad545-163">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ad545-163">Equals</span></span>|<span data-ttu-id="ad545-164">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="ad545-164">All (default)</span></span><br /><br /> <span data-ttu-id="ad545-165">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="ad545-165">Specific party name</span></span>|<span data-ttu-id="ad545-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad545-166">No</span></span>|  
|<span data-ttu-id="ad545-167">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="ad545-167">EDI encoding type</span></span>|<span data-ttu-id="ad545-168">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ad545-168">Equals</span></span>|<span data-ttu-id="ad545-169">X12</span><span class="sxs-lookup"><span data-stu-id="ad545-169">X12</span></span><br /><br /> <span data-ttu-id="ad545-170">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="ad545-170">EDIFACT</span></span><br /><br /> <span data-ttu-id="ad545-171">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="ad545-171">All (default)</span></span>|<span data-ttu-id="ad545-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="ad545-172">No</span></span>|  
  
