---
title: EDI インターチェンジと関連する ACK の状態レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08a94eeb97b731f38d5785ab733d50d0edaa1a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982939"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a><span data-ttu-id="ebe66-102">EDI インターチェンジと関連する ACK の状態レポート</span><span class="sxs-lookup"><span data-stu-id="ebe66-102">EDI Interchange and Correlated ACK Status Report</span></span>
<span data-ttu-id="ebe66-103">このレポートでは、EDI 送信パイプラインおよび受信パイプラインで処理されるすべての EDI インターチェンジ、およびそれらのインターチェンジに関連した確認を示します。</span><span class="sxs-lookup"><span data-stu-id="ebe66-103">This report shows all EDI interchanges that are processed by the EDI send and receive pipelines, and the acknowledgment correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="ebe66-104">状態レポート内のフィールド</span><span class="sxs-lookup"><span data-stu-id="ebe66-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="ebe66-105">EDI インターチェンジと関連する ACK の状態レポートには、受信インターチェンジや送信インターチェンジ、および関連した確認に関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-105">The EDI Interchange and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
- <span data-ttu-id="ebe66-106">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="ebe66-106">Sender Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ebe66-107">送信者パーティは、次のように決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebe66-107">The sender party will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="ebe66-108">インターチェンジのパーティ名がパーティの EDI プロパティで構成された名前と一致する場合、構成済みの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-108">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="ebe66-109">インターチェンジのパーティ名が既存のパーティの EDI プロパティで構成された名前のいずれにも一致しない場合、インターチェンジで指定されたパーティ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-109">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="ebe66-110">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="ebe66-110">Receiver Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ebe66-111">受信者パーティ名は、次のように決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebe66-111">The receiver party name will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="ebe66-112">インターチェンジのパーティ名がパーティの EDI プロパティで構成された名前と一致する場合、構成済みの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-112">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="ebe66-113">インターチェンジのパーティ名が既存のパーティの EDI プロパティで構成された名前のいずれにも一致しない場合、インターチェンジで指定されたパーティ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-113">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="ebe66-114">制御 ID</span><span class="sxs-lookup"><span data-stu-id="ebe66-114">Control ID</span></span>  
  
- <span data-ttu-id="ebe66-115">Direction</span><span class="sxs-lookup"><span data-stu-id="ebe66-115">Direction</span></span>  
  
- <span data-ttu-id="ebe66-116">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="ebe66-116">Interchange Date Time</span></span>  
  
- <span data-ttu-id="ebe66-117">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="ebe66-117">EDI encoding type</span></span>  
  
- <span data-ttu-id="ebe66-118">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="ebe66-118">Interchange Status</span></span>  
  
- <span data-ttu-id="ebe66-119">グループ数</span><span class="sxs-lookup"><span data-stu-id="ebe66-119">Group Count</span></span>  
  
- <span data-ttu-id="ebe66-120">ポート ID</span><span class="sxs-lookup"><span data-stu-id="ebe66-120">Port ID</span></span>  
  
- <span data-ttu-id="ebe66-121">送信者パーティ エイリアス</span><span class="sxs-lookup"><span data-stu-id="ebe66-121">Sender Party Alias</span></span>  
  
- <span data-ttu-id="ebe66-122">受信者パーティ エイリアス</span><span class="sxs-lookup"><span data-stu-id="ebe66-122">Receiver Party Alias</span></span>  
  
- <span data-ttu-id="ebe66-123">トランザクション セットの関連付け ID</span><span class="sxs-lookup"><span data-stu-id="ebe66-123">Transaction Set Correlation ID</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="ebe66-124">状態レポートのクエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="ebe66-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="ebe66-125">表示されるデータを指定するクエリ式のフィールドを変更することにより、EDI インターチェンジと関連する ACK の状態レポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-125">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="ebe66-126">使用できるフィールドは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ebe66-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ebe66-127">クエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="ebe66-127">Query Expression Field</span></span>|<span data-ttu-id="ebe66-128">有効な演算子</span><span class="sxs-lookup"><span data-stu-id="ebe66-128">Potential Operators</span></span>|<span data-ttu-id="ebe66-129">潜在的な値</span><span class="sxs-lookup"><span data-stu-id="ebe66-129">Potential Values</span></span>|<span data-ttu-id="ebe66-130">既定で含まれますか。</span><span class="sxs-lookup"><span data-stu-id="ebe66-130">Included By Default?</span></span>|  
|<span data-ttu-id="ebe66-131">検索</span><span class="sxs-lookup"><span data-stu-id="ebe66-131">Search for</span></span>|<span data-ttu-id="ebe66-132">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ebe66-132">Equals</span></span>|<span data-ttu-id="ebe66-133">インターチェンジ/確認の状態</span><span class="sxs-lookup"><span data-stu-id="ebe66-133">Interchange/ACK Status</span></span>|<span data-ttu-id="ebe66-134">指定あり (必須)</span><span class="sxs-lookup"><span data-stu-id="ebe66-134">Yes (required)</span></span>|  
|<span data-ttu-id="ebe66-135">状態</span><span class="sxs-lookup"><span data-stu-id="ebe66-135">Status</span></span>|<span data-ttu-id="ebe66-136">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ebe66-136">Equals</span></span><br /><br /> <span data-ttu-id="ebe66-137">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="ebe66-137">Not Equals</span></span>|<span data-ttu-id="ebe66-138">受理</span><span class="sxs-lookup"><span data-stu-id="ebe66-138">Accepted</span></span><br /><br /> <span data-ttu-id="ebe66-139">受理 (ただしエラーが発生)</span><span class="sxs-lookup"><span data-stu-id="ebe66-139">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="ebe66-140">送信済み</span><span class="sxs-lookup"><span data-stu-id="ebe66-140">Sent</span></span><br /><br /> <span data-ttu-id="ebe66-141">All</span><span class="sxs-lookup"><span data-stu-id="ebe66-141">All</span></span><br /><br /> <span data-ttu-id="ebe66-142">確認が必要</span><span class="sxs-lookup"><span data-stu-id="ebe66-142">Ack Expected</span></span><br /><br /> <span data-ttu-id="ebe66-143">確認は不要</span><span class="sxs-lookup"><span data-stu-id="ebe66-143">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="ebe66-144">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="ebe66-144">Rejected</span></span><br /><br /> <span data-ttu-id="ebe66-145">(それぞれの値とその定義を次に示します。)</span><span class="sxs-lookup"><span data-stu-id="ebe66-145">(These values are defined below.)</span></span>|<span data-ttu-id="ebe66-146">はい</span><span class="sxs-lookup"><span data-stu-id="ebe66-146">Yes</span></span>|  
|<span data-ttu-id="ebe66-147">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="ebe66-147">Interchange Date Time</span></span>|<span data-ttu-id="ebe66-148">[以下]</span><span class="sxs-lookup"><span data-stu-id="ebe66-148">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="ebe66-149">[以上]</span><span class="sxs-lookup"><span data-stu-id="ebe66-149">Greater Than or Equals</span></span>|<span data-ttu-id="ebe66-150">特定の日時</span><span class="sxs-lookup"><span data-stu-id="ebe66-150">Specific Date Time</span></span><br /><br /> <span data-ttu-id="ebe66-151">[今日]</span><span class="sxs-lookup"><span data-stu-id="ebe66-151">Today</span></span><br /><br /> <span data-ttu-id="ebe66-152">昨日</span><span class="sxs-lookup"><span data-stu-id="ebe66-152">Today - 1</span></span>|<span data-ttu-id="ebe66-153">はい</span><span class="sxs-lookup"><span data-stu-id="ebe66-153">Yes</span></span><br /><br /> <span data-ttu-id="ebe66-154">メモ: クエリ式に 1 回以上含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-154">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="ebe66-155">[最大一致数]</span><span class="sxs-lookup"><span data-stu-id="ebe66-155">Maximum Matches</span></span>|<span data-ttu-id="ebe66-156">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ebe66-156">Equals</span></span>|<span data-ttu-id="ebe66-157">整数 (既定値 50)</span><span class="sxs-lookup"><span data-stu-id="ebe66-157">Integer (default of 50)</span></span>|<span data-ttu-id="ebe66-158">はい</span><span class="sxs-lookup"><span data-stu-id="ebe66-158">Yes</span></span>|  
|<span data-ttu-id="ebe66-159">制御 ID</span><span class="sxs-lookup"><span data-stu-id="ebe66-159">Control ID</span></span>|<span data-ttu-id="ebe66-160">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ebe66-160">Equals</span></span>|<span data-ttu-id="ebe66-161">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="ebe66-161">Interchange Control ID</span></span>|<span data-ttu-id="ebe66-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="ebe66-162">No</span></span>|  
|<span data-ttu-id="ebe66-163">Direction</span><span class="sxs-lookup"><span data-stu-id="ebe66-163">Direction</span></span>|<span data-ttu-id="ebe66-164">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ebe66-164">Equals</span></span>|<span data-ttu-id="ebe66-165">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="ebe66-165">All (default)</span></span><br /><br /> <span data-ttu-id="ebe66-166">Receive</span><span class="sxs-lookup"><span data-stu-id="ebe66-166">Receive</span></span><br /><br /> <span data-ttu-id="ebe66-167">Send</span><span class="sxs-lookup"><span data-stu-id="ebe66-167">Send</span></span>|<span data-ttu-id="ebe66-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="ebe66-168">No</span></span>|  
|<span data-ttu-id="ebe66-169">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="ebe66-169">Receiver Party</span></span>|<span data-ttu-id="ebe66-170">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ebe66-170">Equals</span></span>|<span data-ttu-id="ebe66-171">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="ebe66-171">All (default)</span></span><br /><br /> <span data-ttu-id="ebe66-172">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="ebe66-172">Specific party name</span></span>|<span data-ttu-id="ebe66-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="ebe66-173">No</span></span>|  
|<span data-ttu-id="ebe66-174">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="ebe66-174">Sender Party</span></span>|<span data-ttu-id="ebe66-175">[等しい]</span><span class="sxs-lookup"><span data-stu-id="ebe66-175">Equals</span></span>|<span data-ttu-id="ebe66-176">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="ebe66-176">All (default)</span></span><br /><br /> <span data-ttu-id="ebe66-177">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="ebe66-177">Specific party name</span></span>|<span data-ttu-id="ebe66-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="ebe66-178">No</span></span>|  
  
## <a name="status-definitions"></a><span data-ttu-id="ebe66-179">状態の定義</span><span class="sxs-lookup"><span data-stu-id="ebe66-179">Status Definitions</span></span>  
 <span data-ttu-id="ebe66-180">EDI 状態レポートに使用される状態値には、次の定義があります。</span><span class="sxs-lookup"><span data-stu-id="ebe66-180">The status values used in EDI status reports have the following definitions:</span></span>  
  
- <span data-ttu-id="ebe66-181">受理: 有効なインターチェンジ。</span><span class="sxs-lookup"><span data-stu-id="ebe66-181">Accepted: Valid interchange</span></span>  
  
- <span data-ttu-id="ebe66-182">受理 (ただしエラーが発生): セグメントにエラーが検出されました。</span><span class="sxs-lookup"><span data-stu-id="ebe66-182">Accepted with Errors: Errors were noted in segments</span></span>  
  
- <span data-ttu-id="ebe66-183">送信済み: インターチェンジの送信に成功しました。</span><span class="sxs-lookup"><span data-stu-id="ebe66-183">Sent: The interchange was sent successfully</span></span>  
  
- <span data-ttu-id="ebe66-184">すべて: 他のいずれかの値を持つメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="ebe66-184">All: Display a message with any of the other values</span></span>  
  
- <span data-ttu-id="ebe66-185">確認が必要</span><span class="sxs-lookup"><span data-stu-id="ebe66-185">Ack Expected</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ebe66-186">[インターチェンジの状態と確認の詳細] の状態レポートの "インターチェンジの状態" フィールドは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が技術確認を要求する場合は、送信メッセージが送信されるときに、そのメッセージについて [確認が必要] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-186">The Interchange Status field in the Interchange Status and ACK Details status report will be set to "Ack Expected" for an outbound message when the message is sent if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] expects a technical acknowledgment.</span></span> <span data-ttu-id="ebe66-187">これは、場合に発生、 **TA1 が必要**プロパティで設定されて**受信確認**一方向アグリーメント タブのページ。状態は、技術確認が受信および検証されると、[受理] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-187">This occurs if the **TA1 Expected** property is set in **Acknowledgements** page for the one-way agreement tab. The status will be changed to “Accepted” when the technical acknowledgment has been received and validated.</span></span> <span data-ttu-id="ebe66-188">この処理は、技術確認に対してだけ行われ、機能確認に対しては行われないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ebe66-188">Note that this only occurs for a technical acknowledgment, not a functional acknowledgment.</span></span>  
  
- <span data-ttu-id="ebe66-189">確認は不要</span><span class="sxs-lookup"><span data-stu-id="ebe66-189">Ack Not Expected</span></span>  
  
- <span data-ttu-id="ebe66-190">拒否: インターチェンジはエラーのため無効でした。</span><span class="sxs-lookup"><span data-stu-id="ebe66-190">Rejected: The interchange was invalid due to errors.</span></span>  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="ebe66-191">このレポートで表示されるその他のレポート</span><span class="sxs-lookup"><span data-stu-id="ebe66-191">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="ebe66-192">トランザクション セットの詳細レポートに表示されるトランザクション セットについて、次のその他の状態レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ebe66-192">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report.</span></span> <span data-ttu-id="ebe66-193">レポートにアクセスするには、[EDI インターチェンジと関連する ACK の状態] レポートに記載されたインターチェンジまたは確認を右クリックし、該当するコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ebe66-193">You access the reports by right-clicking an interchange or acknowledgment listed in the EDI Interchange and Correlated ACK Status report, and then clicking the appropriate command:</span></span>  
  
-   [<span data-ttu-id="ebe66-194">インターチェンジの状態と確認の詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="ebe66-194">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="ebe66-195">トランザクション セットの詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="ebe66-195">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a><span data-ttu-id="ebe66-196">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ebe66-196">Next steps</span></span>
  
-   [<span data-ttu-id="ebe66-197">インターチェンジの状態と確認の詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="ebe66-197">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="ebe66-198">トランザクション セットの詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="ebe66-198">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
-   [<span data-ttu-id="ebe66-199">EDI メッセージ コンテンツの状態レポート</span><span class="sxs-lookup"><span data-stu-id="ebe66-199">EDI Message Content Status Report</span></span>](../core/edi-message-content-status-report.md)  
  
