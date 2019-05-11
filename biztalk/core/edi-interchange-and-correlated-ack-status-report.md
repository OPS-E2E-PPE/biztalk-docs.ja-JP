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
ms.openlocfilehash: 1c7a1246da341cc984995b2222681cb8164919e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350622"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a><span data-ttu-id="9d850-102">EDI インターチェンジし、関連する ACK の状態レポート</span><span class="sxs-lookup"><span data-stu-id="9d850-102">EDI Interchange and Correlated ACK Status Report</span></span>
<span data-ttu-id="9d850-103">このレポートでは、それらのインターチェンジに関連した確認し、EDI で処理される EDI インターチェンジが送信および受信パイプラインをすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-103">This report shows all EDI interchanges that are processed by the EDI send and receive pipelines, and the acknowledgment correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="9d850-104">状態レポート内のフィールド</span><span class="sxs-lookup"><span data-stu-id="9d850-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="9d850-105">EDI インターチェンジと関連する ACK の状態レポートは、それらを受信または送信したインターチェンジと関連付けられる受信確認の次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-105">The EDI Interchange and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
- <span data-ttu-id="9d850-106">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="9d850-106">Sender Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9d850-107">送信者パーティように決定されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-107">The sender party will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="9d850-108">インターチェンジのパーティ名には、パーティの EDI のプロパティで構成されている名前が一致すると、構成されている名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-108">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="9d850-109">インターチェンジのパーティ名が一致しない構成済みの EDI のプロパティのいずれかの既存のパーティのインターチェンジに指定されたパーティ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-109">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="9d850-110">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="9d850-110">Receiver Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9d850-111">受信者パーティ名は、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-111">The receiver party name will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="9d850-112">インターチェンジのパーティ名には、パーティの EDI のプロパティで構成されている名前が一致すると、構成されている名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-112">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="9d850-113">インターチェンジのパーティ名が一致しない構成済みの EDI のプロパティのいずれかの既存のパーティのインターチェンジに指定されたパーティ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-113">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="9d850-114">制御 ID</span><span class="sxs-lookup"><span data-stu-id="9d850-114">Control ID</span></span>  
  
- <span data-ttu-id="9d850-115">Direction</span><span class="sxs-lookup"><span data-stu-id="9d850-115">Direction</span></span>  
  
- <span data-ttu-id="9d850-116">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="9d850-116">Interchange Date Time</span></span>  
  
- <span data-ttu-id="9d850-117">EDI エンコードの種類</span><span class="sxs-lookup"><span data-stu-id="9d850-117">EDI encoding type</span></span>  
  
- <span data-ttu-id="9d850-118">インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="9d850-118">Interchange Status</span></span>  
  
- <span data-ttu-id="9d850-119">グループ数</span><span class="sxs-lookup"><span data-stu-id="9d850-119">Group Count</span></span>  
  
- <span data-ttu-id="9d850-120">ポート ID</span><span class="sxs-lookup"><span data-stu-id="9d850-120">Port ID</span></span>  
  
- <span data-ttu-id="9d850-121">送信者パーティ エイリアス</span><span class="sxs-lookup"><span data-stu-id="9d850-121">Sender Party Alias</span></span>  
  
- <span data-ttu-id="9d850-122">受信者パーティ エイリアス</span><span class="sxs-lookup"><span data-stu-id="9d850-122">Receiver Party Alias</span></span>  
  
- <span data-ttu-id="9d850-123">トランザクション セット関連付け ID</span><span class="sxs-lookup"><span data-stu-id="9d850-123">Transaction Set Correlation ID</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="9d850-124">状態レポートのクエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="9d850-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="9d850-125">表示されるデータを指定するクエリ式のフィールドを変更することにより、EDI インターチェンジと関連する ACK の状態レポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9d850-125">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="9d850-126">使用できるフィールドは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9d850-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="9d850-127">クエリ式のフィールド</span><span class="sxs-lookup"><span data-stu-id="9d850-127">Query Expression Field</span></span>|<span data-ttu-id="9d850-128">有効な演算子</span><span class="sxs-lookup"><span data-stu-id="9d850-128">Potential Operators</span></span>|<span data-ttu-id="9d850-129">潜在的な値</span><span class="sxs-lookup"><span data-stu-id="9d850-129">Potential Values</span></span>|<span data-ttu-id="9d850-130">既定で含まれますか。</span><span class="sxs-lookup"><span data-stu-id="9d850-130">Included By Default?</span></span>|  
|<span data-ttu-id="9d850-131">検索</span><span class="sxs-lookup"><span data-stu-id="9d850-131">Search for</span></span>|<span data-ttu-id="9d850-132">[等しい]</span><span class="sxs-lookup"><span data-stu-id="9d850-132">Equals</span></span>|<span data-ttu-id="9d850-133">インターチェンジ/確認の状態</span><span class="sxs-lookup"><span data-stu-id="9d850-133">Interchange/ACK Status</span></span>|<span data-ttu-id="9d850-134">指定あり (必須)</span><span class="sxs-lookup"><span data-stu-id="9d850-134">Yes (required)</span></span>|  
|<span data-ttu-id="9d850-135">状態</span><span class="sxs-lookup"><span data-stu-id="9d850-135">Status</span></span>|<span data-ttu-id="9d850-136">[等しい]</span><span class="sxs-lookup"><span data-stu-id="9d850-136">Equals</span></span><br /><br /> <span data-ttu-id="9d850-137">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="9d850-137">Not Equals</span></span>|<span data-ttu-id="9d850-138">受理</span><span class="sxs-lookup"><span data-stu-id="9d850-138">Accepted</span></span><br /><br /> <span data-ttu-id="9d850-139">受理 (ただしエラーが発生)</span><span class="sxs-lookup"><span data-stu-id="9d850-139">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="9d850-140">送信済み</span><span class="sxs-lookup"><span data-stu-id="9d850-140">Sent</span></span><br /><br /> <span data-ttu-id="9d850-141">All</span><span class="sxs-lookup"><span data-stu-id="9d850-141">All</span></span><br /><br /> <span data-ttu-id="9d850-142">確認が必要</span><span class="sxs-lookup"><span data-stu-id="9d850-142">Ack Expected</span></span><br /><br /> <span data-ttu-id="9d850-143">確認は不要</span><span class="sxs-lookup"><span data-stu-id="9d850-143">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="9d850-144">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="9d850-144">Rejected</span></span><br /><br /> <span data-ttu-id="9d850-145">(これらの値は、以下に定義されます)。</span><span class="sxs-lookup"><span data-stu-id="9d850-145">(These values are defined below.)</span></span>|<span data-ttu-id="9d850-146">はい</span><span class="sxs-lookup"><span data-stu-id="9d850-146">Yes</span></span>|  
|<span data-ttu-id="9d850-147">インターチェンジの日時</span><span class="sxs-lookup"><span data-stu-id="9d850-147">Interchange Date Time</span></span>|<span data-ttu-id="9d850-148">[以下]</span><span class="sxs-lookup"><span data-stu-id="9d850-148">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="9d850-149">[以上]</span><span class="sxs-lookup"><span data-stu-id="9d850-149">Greater Than or Equals</span></span>|<span data-ttu-id="9d850-150">特定の日時</span><span class="sxs-lookup"><span data-stu-id="9d850-150">Specific Date Time</span></span><br /><br /> <span data-ttu-id="9d850-151">[今日]</span><span class="sxs-lookup"><span data-stu-id="9d850-151">Today</span></span><br /><br /> <span data-ttu-id="9d850-152">昨日</span><span class="sxs-lookup"><span data-stu-id="9d850-152">Today - 1</span></span>|<span data-ttu-id="9d850-153">はい</span><span class="sxs-lookup"><span data-stu-id="9d850-153">Yes</span></span><br /><br /> <span data-ttu-id="9d850-154">注:できますに含めることが 1 回以上のクエリ式です。</span><span class="sxs-lookup"><span data-stu-id="9d850-154">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="9d850-155">[最大一致数]</span><span class="sxs-lookup"><span data-stu-id="9d850-155">Maximum Matches</span></span>|<span data-ttu-id="9d850-156">[等しい]</span><span class="sxs-lookup"><span data-stu-id="9d850-156">Equals</span></span>|<span data-ttu-id="9d850-157">整数 (既定値 50)</span><span class="sxs-lookup"><span data-stu-id="9d850-157">Integer (default of 50)</span></span>|<span data-ttu-id="9d850-158">はい</span><span class="sxs-lookup"><span data-stu-id="9d850-158">Yes</span></span>|  
|<span data-ttu-id="9d850-159">制御 ID</span><span class="sxs-lookup"><span data-stu-id="9d850-159">Control ID</span></span>|<span data-ttu-id="9d850-160">[等しい]</span><span class="sxs-lookup"><span data-stu-id="9d850-160">Equals</span></span>|<span data-ttu-id="9d850-161">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="9d850-161">Interchange Control ID</span></span>|<span data-ttu-id="9d850-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="9d850-162">No</span></span>|  
|<span data-ttu-id="9d850-163">Direction</span><span class="sxs-lookup"><span data-stu-id="9d850-163">Direction</span></span>|<span data-ttu-id="9d850-164">[等しい]</span><span class="sxs-lookup"><span data-stu-id="9d850-164">Equals</span></span>|<span data-ttu-id="9d850-165">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="9d850-165">All (default)</span></span><br /><br /> <span data-ttu-id="9d850-166">Receive</span><span class="sxs-lookup"><span data-stu-id="9d850-166">Receive</span></span><br /><br /> <span data-ttu-id="9d850-167">Send</span><span class="sxs-lookup"><span data-stu-id="9d850-167">Send</span></span>|<span data-ttu-id="9d850-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="9d850-168">No</span></span>|  
|<span data-ttu-id="9d850-169">受信者パーティ</span><span class="sxs-lookup"><span data-stu-id="9d850-169">Receiver Party</span></span>|<span data-ttu-id="9d850-170">[等しい]</span><span class="sxs-lookup"><span data-stu-id="9d850-170">Equals</span></span>|<span data-ttu-id="9d850-171">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="9d850-171">All (default)</span></span><br /><br /> <span data-ttu-id="9d850-172">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="9d850-172">Specific party name</span></span>|<span data-ttu-id="9d850-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="9d850-173">No</span></span>|  
|<span data-ttu-id="9d850-174">送信者パーティ</span><span class="sxs-lookup"><span data-stu-id="9d850-174">Sender Party</span></span>|<span data-ttu-id="9d850-175">[等しい]</span><span class="sxs-lookup"><span data-stu-id="9d850-175">Equals</span></span>|<span data-ttu-id="9d850-176">すべて (既定)</span><span class="sxs-lookup"><span data-stu-id="9d850-176">All (default)</span></span><br /><br /> <span data-ttu-id="9d850-177">特定のパーティ名</span><span class="sxs-lookup"><span data-stu-id="9d850-177">Specific party name</span></span>|<span data-ttu-id="9d850-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="9d850-178">No</span></span>|  
  
## <a name="status-definitions"></a><span data-ttu-id="9d850-179">ステータスの定義</span><span class="sxs-lookup"><span data-stu-id="9d850-179">Status Definitions</span></span>  
 <span data-ttu-id="9d850-180">EDI 状態レポートで使用される状態値は、次の定義を持ちます。</span><span class="sxs-lookup"><span data-stu-id="9d850-180">The status values used in EDI status reports have the following definitions:</span></span>  
  
- <span data-ttu-id="9d850-181">使用できます。有効なインターチェンジ</span><span class="sxs-lookup"><span data-stu-id="9d850-181">Accepted: Valid interchange</span></span>  
  
- <span data-ttu-id="9d850-182">エラーありで受理します。セグメントにエラーが検出されました</span><span class="sxs-lookup"><span data-stu-id="9d850-182">Accepted with Errors: Errors were noted in segments</span></span>  
  
- <span data-ttu-id="9d850-183">送信。インターチェンジが正常に送信されました</span><span class="sxs-lookup"><span data-stu-id="9d850-183">Sent: The interchange was sent successfully</span></span>  
  
- <span data-ttu-id="9d850-184">すべての：その他の値のいずれかでメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="9d850-184">All: Display a message with any of the other values</span></span>  
  
- <span data-ttu-id="9d850-185">確認が必要</span><span class="sxs-lookup"><span data-stu-id="9d850-185">Ack Expected</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9d850-186">インターチェンジの状態と確認の詳細ステータス レポートの [インターチェンジの状態] フィールドに設定されます「確認が必要」は送信メッセージの場合、メッセージが送信されるときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]技術確認が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d850-186">The Interchange Status field in the Interchange Status and ACK Details status report will be set to "Ack Expected" for an outbound message when the message is sent if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] expects a technical acknowledgment.</span></span> <span data-ttu-id="9d850-187">これは、場合に発生、 **TA1 が必要**プロパティで設定されて**受信確認**一方向アグリーメント タブのページ。技術確認を受信し、検証、状態を「受理」に変更されます。</span><span class="sxs-lookup"><span data-stu-id="9d850-187">This occurs if the **TA1 Expected** property is set in **Acknowledgements** page for the one-way agreement tab. The status will be changed to “Accepted” when the technical acknowledgment has been received and validated.</span></span> <span data-ttu-id="9d850-188">これのみ、技術確認、機能確認ではないために起こることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9d850-188">Note that this only occurs for a technical acknowledgment, not a functional acknowledgment.</span></span>  
  
- <span data-ttu-id="9d850-189">確認は不要</span><span class="sxs-lookup"><span data-stu-id="9d850-189">Ack Not Expected</span></span>  
  
- <span data-ttu-id="9d850-190">拒否。インターチェンジはエラーのため無効です。</span><span class="sxs-lookup"><span data-stu-id="9d850-190">Rejected: The interchange was invalid due to errors.</span></span>  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="9d850-191">このレポートで表示されるその他のレポート</span><span class="sxs-lookup"><span data-stu-id="9d850-191">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="9d850-192">トランザクション セットのトランザクション セットの詳細レポートに表示されるは、次の追加のステータス レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9d850-192">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report.</span></span> <span data-ttu-id="9d850-193">インターチェンジまたは確認が EDI インターチェンジと関連する ACK の状態レポートに記載を右クリックし、適切なコマンドをクリックしてレポートにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9d850-193">You access the reports by right-clicking an interchange or acknowledgment listed in the EDI Interchange and Correlated ACK Status report, and then clicking the appropriate command:</span></span>  
  
-   [<span data-ttu-id="9d850-194">インターチェンジの状態と確認の詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="9d850-194">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="9d850-195">トランザクション セットの詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="9d850-195">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a><span data-ttu-id="9d850-196">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9d850-196">Next steps</span></span>
  
-   [<span data-ttu-id="9d850-197">インターチェンジの状態と確認の詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="9d850-197">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="9d850-198">トランザクション セットの詳細の状態レポート</span><span class="sxs-lookup"><span data-stu-id="9d850-198">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
-   [<span data-ttu-id="9d850-199">EDI メッセージ コンテンツの状態レポート</span><span class="sxs-lookup"><span data-stu-id="9d850-199">EDI Message Content Status Report</span></span>](../core/edi-message-content-status-report.md)  
  
