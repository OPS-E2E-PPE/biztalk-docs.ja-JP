---
title: トランザクション セットの詳細ステータス レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d81367c7-c74e-42cb-b856-748962b727ec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef31f7216eb011d95ab62ebf361dfcde8374ddd2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009955"
---
# <a name="transaction-set-details-status-report"></a><span data-ttu-id="82205-102">トランザクション セットの詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="82205-102">Transaction Set Details Status Report</span></span>
<span data-ttu-id="82205-103">このレポートには、インターチェンジ/確認の状態レポートで選択した特定の EDI インターチェンジにあるトランザクション セットに関する詳細が示されます。</span><span class="sxs-lookup"><span data-stu-id="82205-103">This report shows the details for transaction sets in a specific EDI interchange selected from within the Interchange/ACK Status report.</span></span> <span data-ttu-id="82205-104">この状態レポートを表示するには、インターチェンジをインターチェンジ/確認の状態レポートのクエリ結果ペインに一覧表示を右クリックし、順にクリックします**トランザクション セットの詳細**します。</span><span class="sxs-lookup"><span data-stu-id="82205-104">To display this status report, right-click an interchange listed in the Query results pane of the Interchange/ACK Status report, and then click **Transaction Set Details**.</span></span>  
  
 <span data-ttu-id="82205-105">このレポートは、選択した場合にのみ使用可能な**レポート用にトランザクション セット/ペイロードを格納**関連するパーティの EDI のプロパティ ダイアログ ボックスの 全般 ページのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="82205-105">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="82205-106">状態レポート内のフィールド</span><span class="sxs-lookup"><span data-stu-id="82205-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="82205-107">トランザクション セットの詳細の状態レポートには、受信または送信されたインターチェンジのトランザクション セットについて次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82205-107">The Transaction Set Details Status Report displays the following information for transaction sets in received or sent interchanges:</span></span>  
  
- <span data-ttu-id="82205-108">トランザクション セット ID</span><span class="sxs-lookup"><span data-stu-id="82205-108">Transaction Set ID</span></span>  
  
- <span data-ttu-id="82205-109">[ドキュメントの種類]</span><span class="sxs-lookup"><span data-stu-id="82205-109">Document type</span></span>  
  
- <span data-ttu-id="82205-110">送信者パーティ エイリアス</span><span class="sxs-lookup"><span data-stu-id="82205-110">Sender party alias</span></span>  
  
- <span data-ttu-id="82205-111">アプリケーション送信者</span><span class="sxs-lookup"><span data-stu-id="82205-111">Application Sender</span></span>  
  
- <span data-ttu-id="82205-112">受信者パーティのエイリアス</span><span class="sxs-lookup"><span data-stu-id="82205-112">Receiver party alias</span></span>  
  
- <span data-ttu-id="82205-113">アプリケーション受信者</span><span class="sxs-lookup"><span data-stu-id="82205-113">Application Receiver</span></span>  
  
- <span data-ttu-id="82205-114">Direction</span><span class="sxs-lookup"><span data-stu-id="82205-114">Direction</span></span>  
  
- <span data-ttu-id="82205-115">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="82205-115">Interchange Control Number</span></span>  
  
- <span data-ttu-id="82205-116">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="82205-116">Group Control Number</span></span>  
  
- <span data-ttu-id="82205-117">トランザクション セットの制御番号</span><span class="sxs-lookup"><span data-stu-id="82205-117">Transaction Set Control Number</span></span>  
  
- <span data-ttu-id="82205-118">トランザクション セットの状態</span><span class="sxs-lookup"><span data-stu-id="82205-118">Transaction Set Status</span></span>  
  
- <span data-ttu-id="82205-119">インターチェンジの日時 (既定では表示されません)</span><span class="sxs-lookup"><span data-stu-id="82205-119">Interchange Date Time (not displayed by default)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="82205-120">受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。</span><span class="sxs-lookup"><span data-stu-id="82205-120">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="82205-121">日付が 75 未満である場合は、20YY として表示されます。</span><span class="sxs-lookup"><span data-stu-id="82205-121">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="82205-122">たとえば、ISA09 の値が 991113 であるインターチェンジを受信した場合、インターチェンジの日時は 11/13/1999 としてレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="82205-122">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date Time will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="82205-123">処理の日時 (既定では表示されません)</span><span class="sxs-lookup"><span data-stu-id="82205-123">Processing Date/Time (not displayed by default)</span></span>  
  
- <span data-ttu-id="82205-124">グループの日時 (既定では表示されません)</span><span class="sxs-lookup"><span data-stu-id="82205-124">Group Date/Time (not displayed by default)</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="82205-125">状態レポートのクエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="82205-125">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="82205-126">表示されるデータを指定するクエリ式のフィールドを変更することにより、EDI インターチェンジと関連する ACK の状態レポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="82205-126">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="82205-127">使用できるフィールドは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82205-127">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="82205-128">クエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="82205-128">Query Expression Field</span></span>|<span data-ttu-id="82205-129">有効な演算子</span><span class="sxs-lookup"><span data-stu-id="82205-129">Potential Operators</span></span>|<span data-ttu-id="82205-130">潜在的な値</span><span class="sxs-lookup"><span data-stu-id="82205-130">Potential Values</span></span>|<span data-ttu-id="82205-131">既定で含まれますか。</span><span class="sxs-lookup"><span data-stu-id="82205-131">Included By Default?</span></span>|  
|<span data-ttu-id="82205-132">検索</span><span class="sxs-lookup"><span data-stu-id="82205-132">Search for</span></span>|<span data-ttu-id="82205-133">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-133">Equals</span></span>|<span data-ttu-id="82205-134">トランザクション セットの詳細</span><span class="sxs-lookup"><span data-stu-id="82205-134">Transaction Set Details</span></span>|<span data-ttu-id="82205-135">指定あり (必須)</span><span class="sxs-lookup"><span data-stu-id="82205-135">Yes (required)</span></span>|  
|<span data-ttu-id="82205-136">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="82205-136">Interchange Date Time</span></span>|<span data-ttu-id="82205-137">[以下]</span><span class="sxs-lookup"><span data-stu-id="82205-137">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="82205-138">[以上]</span><span class="sxs-lookup"><span data-stu-id="82205-138">Greater Than or Equals</span></span>|<span data-ttu-id="82205-139">特定の日時</span><span class="sxs-lookup"><span data-stu-id="82205-139">Specific Date Time</span></span><br /><br /> <span data-ttu-id="82205-140">[今日]</span><span class="sxs-lookup"><span data-stu-id="82205-140">Today</span></span><br /><br /> <span data-ttu-id="82205-141">昨日</span><span class="sxs-lookup"><span data-stu-id="82205-141">Today - 1</span></span>|<span data-ttu-id="82205-142">はい</span><span class="sxs-lookup"><span data-stu-id="82205-142">Yes</span></span><br /><br /> <span data-ttu-id="82205-143">メモ: クエリ式に 1 回以上含めることができます。</span><span class="sxs-lookup"><span data-stu-id="82205-143">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="82205-144">受信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="82205-144">Receiver Party Name</span></span>|<span data-ttu-id="82205-145">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-145">Equals</span></span>|<span data-ttu-id="82205-146">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="82205-146">All (default)</span></span><br /><br /> <span data-ttu-id="82205-147">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="82205-147">Specific party name</span></span>|<span data-ttu-id="82205-148">はい</span><span class="sxs-lookup"><span data-stu-id="82205-148">Yes</span></span>|  
|<span data-ttu-id="82205-149">送信者パーティ名</span><span class="sxs-lookup"><span data-stu-id="82205-149">Sender Party Name</span></span>|<span data-ttu-id="82205-150">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-150">Equals</span></span>|<span data-ttu-id="82205-151">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="82205-151">All (default)</span></span><br /><br /> <span data-ttu-id="82205-152">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="82205-152">Specific party name</span></span>|<span data-ttu-id="82205-153">はい</span><span class="sxs-lookup"><span data-stu-id="82205-153">Yes</span></span>|  
|<span data-ttu-id="82205-154">Direction</span><span class="sxs-lookup"><span data-stu-id="82205-154">Direction</span></span>|<span data-ttu-id="82205-155">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-155">Equals</span></span>|<span data-ttu-id="82205-156">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="82205-156">All (default)</span></span><br /><br /> <span data-ttu-id="82205-157">Receive</span><span class="sxs-lookup"><span data-stu-id="82205-157">Receive</span></span><br /><br /> <span data-ttu-id="82205-158">Send</span><span class="sxs-lookup"><span data-stu-id="82205-158">Send</span></span>|<span data-ttu-id="82205-159">はい</span><span class="sxs-lookup"><span data-stu-id="82205-159">Yes</span></span>|  
|<span data-ttu-id="82205-160">制御 ID</span><span class="sxs-lookup"><span data-stu-id="82205-160">Control ID</span></span>|<span data-ttu-id="82205-161">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-161">Equals</span></span>|<span data-ttu-id="82205-162">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="82205-162">Interchange Control ID</span></span>|<span data-ttu-id="82205-163">はい</span><span class="sxs-lookup"><span data-stu-id="82205-163">Yes</span></span>|  
|<span data-ttu-id="82205-164">トランザクション セット関連付け ID</span><span class="sxs-lookup"><span data-stu-id="82205-164">Transaction Set Correlation Id</span></span>|<span data-ttu-id="82205-165">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-165">Equals</span></span>|<span data-ttu-id="82205-166">関連付け Id</span><span class="sxs-lookup"><span data-stu-id="82205-166">Correlation Id</span></span>|<span data-ttu-id="82205-167">はい</span><span class="sxs-lookup"><span data-stu-id="82205-167">Yes</span></span>|  
|<span data-ttu-id="82205-168">[最大一致数]</span><span class="sxs-lookup"><span data-stu-id="82205-168">Maximum Matches</span></span>|<span data-ttu-id="82205-169">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-169">Equals</span></span>|<span data-ttu-id="82205-170">整数 (既定値 50)</span><span class="sxs-lookup"><span data-stu-id="82205-170">Integer (default of 50)</span></span>|<span data-ttu-id="82205-171">はい</span><span class="sxs-lookup"><span data-stu-id="82205-171">Yes</span></span>|  
|<span data-ttu-id="82205-172">状態</span><span class="sxs-lookup"><span data-stu-id="82205-172">Status</span></span>|<span data-ttu-id="82205-173">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-173">Equals</span></span><br /><br /> <span data-ttu-id="82205-174">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="82205-174">Not Equals</span></span>|<span data-ttu-id="82205-175">受理</span><span class="sxs-lookup"><span data-stu-id="82205-175">Accepted</span></span><br /><br /> <span data-ttu-id="82205-176">受理 (ただしエラーが発生)</span><span class="sxs-lookup"><span data-stu-id="82205-176">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="82205-177">送信済み</span><span class="sxs-lookup"><span data-stu-id="82205-177">Sent</span></span><br /><br /> <span data-ttu-id="82205-178">All</span><span class="sxs-lookup"><span data-stu-id="82205-178">All</span></span><br /><br /> <span data-ttu-id="82205-179">確認が必要</span><span class="sxs-lookup"><span data-stu-id="82205-179">Ack Expected</span></span><br /><br /> <span data-ttu-id="82205-180">確認は不要</span><span class="sxs-lookup"><span data-stu-id="82205-180">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="82205-181">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="82205-181">Rejected</span></span>|<span data-ttu-id="82205-182">いいえ</span><span class="sxs-lookup"><span data-stu-id="82205-182">No</span></span>|  
|<span data-ttu-id="82205-183">トランザクション セット ID</span><span class="sxs-lookup"><span data-stu-id="82205-183">Transaction Set Id</span></span>|<span data-ttu-id="82205-184">[等しい]</span><span class="sxs-lookup"><span data-stu-id="82205-184">Equals</span></span>|<span data-ttu-id="82205-185">トランザクション セット ID</span><span class="sxs-lookup"><span data-stu-id="82205-185">Transaction Set Id</span></span>|<span data-ttu-id="82205-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="82205-186">No</span></span>|  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="82205-187">このレポートで表示されるその他のレポート</span><span class="sxs-lookup"><span data-stu-id="82205-187">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="82205-188">トランザクション セットのトランザクション セットの詳細レポートに示すように、次の追加の状態レポートを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="82205-188">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report:</span></span>  
  
-   <span data-ttu-id="82205-189">メッセージ コンテンツの状態レポート。</span><span class="sxs-lookup"><span data-stu-id="82205-189">Message Content status report.</span></span> <span data-ttu-id="82205-190">このレポートを表示するには、詳細レポートで任意のトランザクション セットを右クリックし、[トランザクション セット数の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82205-190">You access this report by right-clicking a transaction set in the details reports, and then clicking View Transaction Set Content.</span></span> <span data-ttu-id="82205-191">詳細については、次を参照してください。 [EDI メッセージ コンテンツ状態レポート](../core/edi-message-content-status-report.md)します。</span><span class="sxs-lookup"><span data-stu-id="82205-191">For more information, see [EDI Message Content Status Report](../core/edi-message-content-status-report.md).</span></span>  
  
-   <span data-ttu-id="82205-192">インターチェンジ/確認の状態レポート。</span><span class="sxs-lookup"><span data-stu-id="82205-192">Interchange/ACK Status report.</span></span> <span data-ttu-id="82205-193">このレポートと同じユーザー インターフェイスを使用して、 [EDI インターチェンジと関連する ACK の状態レポート](../core/edi-interchange-and-correlated-ack-status-report.md)を複数のインターチェンジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82205-193">This report uses the same user interface as the [EDI Interchange and Correlated ACK Status Report](../core/edi-interchange-and-correlated-ack-status-report.md) that is displayed for multiple interchanges.</span></span> <span data-ttu-id="82205-194">相違点は、このトランザクション セットを含むインターチェンジに関するデータだけが報告されることです</span><span class="sxs-lookup"><span data-stu-id="82205-194">The difference is that this report data for only the interchange that contains this transaction set.</span></span>  
  
