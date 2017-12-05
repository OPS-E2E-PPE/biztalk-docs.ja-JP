---
title: "送信 EDI メッセージのデータを格納する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6e576fc-37fd-417d-ae68-607a0a8bcc0a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98d5113c63e29f3f4b85834b7ca1aa0836d0a5d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-data-is-stored-for-outbound-edi-messages"></a><span data-ttu-id="f67fe-102">送信 EDI メッセージのデータ格納方法</span><span class="sxs-lookup"><span data-stu-id="f67fe-102">How Data Is Stored for Outbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f67fe-103"> は次の操作を実行して、送信インターチェンジの状態レポート エントリを生成します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-103"> does the following to generate a status report entry for an outbound interchange:</span></span>  
  
1.  <span data-ttu-id="f67fe-104">送信メッセージ XML が EDI 送信パイプラインに送信されると、送信パイプラインは状態レポートのデータ ストアに次の値のエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-104">When outbound message XML is sent to the EDI send pipeline, the send pipeline creates an entry in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="f67fe-105">インターチェンジ状態エントリは [処理済み] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-105">Interchange status entry is set to Processed</span></span>  
  
    -   <span data-ttu-id="f67fe-106">インターチェンジ確認状態エントリ (インターチェンジごとに 1 つ) は、[必要] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-106">Interchange ACK status entry (one per interchange) is set to Expected</span></span>  
  
    -   <span data-ttu-id="f67fe-107">機能確認状態エントリ (X12 ではグループごとに 1 つ、EDIFACT ではすべてのグループに 1 つ) は、[必要] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-107">Functional ACK status entries (one per group in X12, one for all groups in EDIFACT) are set to Expected</span></span>  
  
2.  <span data-ttu-id="f67fe-108">EDI メッセージが取引先に送信され、取引先から受信確認が返された後に、受信確認を受信する EDI 受信パイプラインは、インターチェンジ状態、インターチェンジ確認状態、および機能確認状態エントリを、必要に応じて [受理] / [一部受理] / [拒否] に更新します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-108">After the EDI message has been sent to the trading partner, and the acknowledgment has been returned from the trading partner, the EDI receive pipeline that receives the acknowledgment updates the Interchange status, the Interchange ACK status, and the Functional ACK status entries to Accepted/Partially Accepted/Rejected, as appropriate.</span></span>  
  
## <a name="data-stored-by-the-send-pipeline-for-outbound-interchanges"></a><span data-ttu-id="f67fe-109">送信インターチェンジの送信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-109">Data Stored by the Send Pipeline for Outbound Interchanges</span></span>  
 <span data-ttu-id="f67fe-110">送信パイプラインは、送信する各インターチェンジの状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-110">The send pipeline creates a record in the status report data store for each interchange that it sends.</span></span> <span data-ttu-id="f67fe-111">エントリに必要なほとんどのデータは、インターチェンジのヘッダー/トレーラー セグメント (ISA/IEA または UNB/UNZ) から使用可能です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-111">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="f67fe-112">他のデータは、送信ポートのプロパティから使用できます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-112">Other data is available from send port properties.</span></span> <span data-ttu-id="f67fe-113">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f67fe-113">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f67fe-114">レコードの種類 = インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="f67fe-114">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="f67fe-115">インターチェンジの方向 = 更新データ = 送信</span><span class="sxs-lookup"><span data-stu-id="f67fe-115">Interchange Direction = Update Data = Send</span></span>  
  
-   <span data-ttu-id="f67fe-116">インターチェンジの受信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-116">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-117">インターチェンジの送信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-117">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-118">インターチェンジの日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-118">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-119">インターチェンジの時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-119">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-120">インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-120">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-121">インターチェンジ状態: 処理済み/送信済み。</span><span class="sxs-lookup"><span data-stu-id="f67fe-121">Interchange Status: Processed/Sent.</span></span> <span data-ttu-id="f67fe-122">[処理済み] 状態は、送信パイプラインが正常にインターチェンジを処理し、配信用に送信アダプターに渡したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-122">A status of Processed indicates that the send pipeline has successfully processed the interchange and handed it over to the send adapter for delivery.</span></span>  
  
-   <span data-ttu-id="f67fe-123">インターチェンジ制御カウント (X12 でのグループ/メッセージ) = データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-123">Interchange Control Count (Groups/Messages in X12 respectively) = Data</span></span>  
  
-   <span data-ttu-id="f67fe-124">インターチェンジ送信ポート ID = データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-124">Interchange Send Port ID = Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="f67fe-125">送信インターチェンジへの応答として受信した各技術確認用の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-125">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="f67fe-126">受信パイプラインは、受信した各技術確認用の状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-126">The receive pipeline creates a record in the status report data store for each technical acknowledgment that it receives.</span></span> <span data-ttu-id="f67fe-127">受信パイプラインでは、状態レポート データ ストアで受信した各インターチェンジのレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-127">The receive pipeline creates a record of each interchange received in the status report data store.</span></span> <span data-ttu-id="f67fe-128">取引先に送信されたインターチェンジへの応答として受信した各技術確認用のデータ ストアに 1 つの技術確認の状態レポート エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-128">creates one technical acknowledgment status report entry in the data store for each technical ACK received as a response to an interchange sent to a trading partner.</span></span> <span data-ttu-id="f67fe-129">技術確認は、X12 では TA1 で、EDIFACT では UCI セグメントのみを持つ CONTRL メッセージです。</span><span class="sxs-lookup"><span data-stu-id="f67fe-129">The technical acknowledge is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="f67fe-130">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f67fe-130">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f67fe-131">レコードの種類 = インターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="f67fe-131">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="f67fe-132">インターチェンジ確認方向 = 送信 – 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-132">Interchange ACK Direction = Send – Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-133">インターチェンジの受信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-133">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-134">インターチェンジの送信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-134">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-135">インターチェンジの日付 = 更新データ (X12 関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-135">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-136">インターチェンジ制御 ID = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-136">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-137">インターチェンジ確認状態 = 生成または該当なし\<注 0 参照\>-データを更新</span><span class="sxs-lookup"><span data-stu-id="f67fe-137">Interchange ACK Status = Generated or Not Applicable \<Refer Note 0\> - Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-138">インターチェンジ確認制御 ID= 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="f67fe-138">Interchange ACK Control ID= Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="f67fe-139">インターチェンジ確認日付 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="f67fe-139">Interchange ACK Date = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="f67fe-140">インターチェンジ確認時刻 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="f67fe-140">Interchange ACK Time = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="f67fe-141">確認/アクション コード = 更新データ\<注 1 を参照してください\>(TA104 X12 または EDIFACT UCI4) から *</span><span class="sxs-lookup"><span data-stu-id="f67fe-141">ACK/Action Code = Update Data  \<refer note 1\> (from X12-TA104 or EDIFACT-UCI4)*</span></span>  
  
-   <span data-ttu-id="f67fe-142">確認通知コード = 更新データ\<注 2 を参照\>(から X12-TA105、EDIFACT には適用不可) *</span><span class="sxs-lookup"><span data-stu-id="f67fe-142">ACK Note Code = Update Data \<Refer Note 2\> (from X12-TA105, not applicable for EDIFACT)*</span></span>  
  
 <span data-ttu-id="f67fe-143">次の確認/アクション コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-143">The following ACK/Action Codes are used:</span></span>  
  
|<span data-ttu-id="f67fe-144">確認/アクション コードのデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-144">Data in ACK/Action Code</span></span>|<span data-ttu-id="f67fe-145">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="f67fe-145">Error description for Reporting</span></span>|<span data-ttu-id="f67fe-146">コメント (適用範囲)</span><span class="sxs-lookup"><span data-stu-id="f67fe-146">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="f67fe-147">A</span><span class="sxs-lookup"><span data-stu-id="f67fe-147">A</span></span>|<span data-ttu-id="f67fe-148">受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-148">Accepted</span></span>|<span data-ttu-id="f67fe-149">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-149">X12</span></span>|  
|<span data-ttu-id="f67fe-150">E</span><span class="sxs-lookup"><span data-stu-id="f67fe-150">E</span></span>|<span data-ttu-id="f67fe-151">受理、エラー検出</span><span class="sxs-lookup"><span data-stu-id="f67fe-151">Accepted, errors noted</span></span>|<span data-ttu-id="f67fe-152">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-152">X12</span></span>|  
|<span data-ttu-id="f67fe-153">P</span><span class="sxs-lookup"><span data-stu-id="f67fe-153">P</span></span>|<span data-ttu-id="f67fe-154">一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-154">Partially Accepted</span></span>|<span data-ttu-id="f67fe-155">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-155">X12</span></span>|  
|<span data-ttu-id="f67fe-156">R</span><span class="sxs-lookup"><span data-stu-id="f67fe-156">R</span></span>|<span data-ttu-id="f67fe-157">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-157">Rejected</span></span>|<span data-ttu-id="f67fe-158">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-158">X12</span></span>|  
|<span data-ttu-id="f67fe-159">4</span><span class="sxs-lookup"><span data-stu-id="f67fe-159">4</span></span>|<span data-ttu-id="f67fe-160">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-160">Rejected</span></span>|<span data-ttu-id="f67fe-161">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-161">EDIFACT</span></span>|  
|<span data-ttu-id="f67fe-162">8</span><span class="sxs-lookup"><span data-stu-id="f67fe-162">8</span></span>|<span data-ttu-id="f67fe-163">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-163">Accepted/Partially Accepted</span></span>|<span data-ttu-id="f67fe-164">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-164">EDIFACT</span></span>|  
  
 <span data-ttu-id="f67fe-165">次の確認通知コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-165">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="f67fe-166">確認通知コードのデータ (X12)</span><span class="sxs-lookup"><span data-stu-id="f67fe-166">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="f67fe-167">Description</span><span class="sxs-lookup"><span data-stu-id="f67fe-167">Description</span></span>|  
|--------------------------------------|-----------------|  
|<span data-ttu-id="f67fe-168">000</span><span class="sxs-lookup"><span data-stu-id="f67fe-168">000</span></span>|<span data-ttu-id="f67fe-169">Success</span><span class="sxs-lookup"><span data-stu-id="f67fe-169">Success</span></span>|  
|<span data-ttu-id="f67fe-170">001</span><span class="sxs-lookup"><span data-stu-id="f67fe-170">001</span></span>|<span data-ttu-id="f67fe-171">インターチェンジ制御番号が一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-171">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="f67fe-172">002</span><span class="sxs-lookup"><span data-stu-id="f67fe-172">002</span></span>|<span data-ttu-id="f67fe-173">標準がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-173">Standard not supported</span></span>|  
|<span data-ttu-id="f67fe-174">003</span><span class="sxs-lookup"><span data-stu-id="f67fe-174">003</span></span>|<span data-ttu-id="f67fe-175">バージョンのコントロールはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f67fe-175">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="f67fe-176">004</span><span class="sxs-lookup"><span data-stu-id="f67fe-176">004</span></span>|<span data-ttu-id="f67fe-177">セグメント終端記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-177">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="f67fe-178">005</span><span class="sxs-lookup"><span data-stu-id="f67fe-178">005</span></span>|<span data-ttu-id="f67fe-179">送信者のインターチェンジ ID 修飾子が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-179">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="f67fe-180">006</span><span class="sxs-lookup"><span data-stu-id="f67fe-180">006</span></span>|<span data-ttu-id="f67fe-181">インターチェンジ送信者 ID が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-181">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="f67fe-182">007</span><span class="sxs-lookup"><span data-stu-id="f67fe-182">007</span></span>|<span data-ttu-id="f67fe-183">受信者のインターチェンジ ID 修飾子が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-183">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="f67fe-184">008</span><span class="sxs-lookup"><span data-stu-id="f67fe-184">008</span></span>|<span data-ttu-id="f67fe-185">インターチェンジ受信者 ID が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-185">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="f67fe-186">009</span><span class="sxs-lookup"><span data-stu-id="f67fe-186">009</span></span>|<span data-ttu-id="f67fe-187">インターチェンジ受信者 ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-187">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="f67fe-188">010</span><span class="sxs-lookup"><span data-stu-id="f67fe-188">010</span></span>|<span data-ttu-id="f67fe-189">認証情報修飾子の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-189">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="f67fe-190">011</span><span class="sxs-lookup"><span data-stu-id="f67fe-190">011</span></span>|<span data-ttu-id="f67fe-191">認証情報の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-191">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="f67fe-192">012</span><span class="sxs-lookup"><span data-stu-id="f67fe-192">012</span></span>|<span data-ttu-id="f67fe-193">無効なセキュリティ情報修飾子の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-193">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="f67fe-194">013</span><span class="sxs-lookup"><span data-stu-id="f67fe-194">013</span></span>|<span data-ttu-id="f67fe-195">セキュリティ情報の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-195">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="f67fe-196">014</span><span class="sxs-lookup"><span data-stu-id="f67fe-196">014</span></span>|<span data-ttu-id="f67fe-197">無効なインターチェンジ日付の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-197">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="f67fe-198">015</span><span class="sxs-lookup"><span data-stu-id="f67fe-198">015</span></span>|<span data-ttu-id="f67fe-199">無効なインターチェンジ時刻の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-199">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="f67fe-200">016</span><span class="sxs-lookup"><span data-stu-id="f67fe-200">016</span></span>|<span data-ttu-id="f67fe-201">無効なインターチェンジ標準識別子の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-201">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="f67fe-202">017</span><span class="sxs-lookup"><span data-stu-id="f67fe-202">017</span></span>|<span data-ttu-id="f67fe-203">インターチェンジ バージョン ID の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-203">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="f67fe-204">018</span><span class="sxs-lookup"><span data-stu-id="f67fe-204">018</span></span>|<span data-ttu-id="f67fe-205">無効なインターチェンジ制御番号の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-205">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="f67fe-206">019</span><span class="sxs-lookup"><span data-stu-id="f67fe-206">019</span></span>|<span data-ttu-id="f67fe-207">確認要求の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-207">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="f67fe-208">020</span><span class="sxs-lookup"><span data-stu-id="f67fe-208">020</span></span>|<span data-ttu-id="f67fe-209">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="f67fe-209">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="f67fe-210">021</span><span class="sxs-lookup"><span data-stu-id="f67fe-210">021</span></span>|<span data-ttu-id="f67fe-211">含まれているグループの数の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-211">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="f67fe-212">022</span><span class="sxs-lookup"><span data-stu-id="f67fe-212">022</span></span>|<span data-ttu-id="f67fe-213">制御構造が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-213">Invalid Control Structure</span></span>|  
|<span data-ttu-id="f67fe-214">023</span><span class="sxs-lookup"><span data-stu-id="f67fe-214">023</span></span>|<span data-ttu-id="f67fe-215">ファイルの終わりが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-215">Improper End-of-File</span></span>|  
|<span data-ttu-id="f67fe-216">024</span><span class="sxs-lookup"><span data-stu-id="f67fe-216">024</span></span>|<span data-ttu-id="f67fe-217">インターチェンジの内容が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-217">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="f67fe-218">025</span><span class="sxs-lookup"><span data-stu-id="f67fe-218">025</span></span>|<span data-ttu-id="f67fe-219">インターチェンジ制御番号が重複しています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-219">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="f67fe-220">026</span><span class="sxs-lookup"><span data-stu-id="f67fe-220">026</span></span>|<span data-ttu-id="f67fe-221">データ要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-221">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="f67fe-222">027</span><span class="sxs-lookup"><span data-stu-id="f67fe-222">027</span></span>|<span data-ttu-id="f67fe-223">コンポーネント要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-223">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="f67fe-224">028</span><span class="sxs-lookup"><span data-stu-id="f67fe-224">028</span></span>|<span data-ttu-id="f67fe-225">遅延配信要求の配信日が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-225">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="f67fe-226">029</span><span class="sxs-lookup"><span data-stu-id="f67fe-226">029</span></span>|<span data-ttu-id="f67fe-227">遅延配信要求の配信時刻が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-227">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="f67fe-228">030</span><span class="sxs-lookup"><span data-stu-id="f67fe-228">030</span></span>|<span data-ttu-id="f67fe-229">遅延配信要求に無効な配信時のコード</span><span class="sxs-lookup"><span data-stu-id="f67fe-229">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="f67fe-230">031</span><span class="sxs-lookup"><span data-stu-id="f67fe-230">031</span></span>|<span data-ttu-id="f67fe-231">サービスの評価が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-231">Invalid Grade of Service</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="f67fe-232">送信インターチェンジへの応答として受信した各技術確認用の受信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-232">Data Updated by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="f67fe-233">受信パイプラインが受信した各技術確認用に、関連する送信インターチェンジの状態レポート エントリが更新されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-233">For each technical acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="f67fe-234">EDI 逆アセンブラーは、次のように受信確認の UCI および TA1 セグメントのデータを使用して、データ ストア内でレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-234">The EDI Disassembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="f67fe-235">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="f67fe-235">Fields in ACK</span></span>|<span data-ttu-id="f67fe-236">データ ストアのフィールド</span><span class="sxs-lookup"><span data-stu-id="f67fe-236">Fields in Data store</span></span>|<span data-ttu-id="f67fe-237">解説</span><span class="sxs-lookup"><span data-stu-id="f67fe-237">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="f67fe-238">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="f67fe-238">Interchange Sender ID</span></span>|<span data-ttu-id="f67fe-239">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="f67fe-239">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="f67fe-240">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="f67fe-240">Interchange Receiver ID</span></span>|<span data-ttu-id="f67fe-241">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="f67fe-241">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="f67fe-242">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="f67fe-242">Interchange Date</span></span>|-|  
|<span data-ttu-id="f67fe-243">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="f67fe-243">Interchange Control Number</span></span>|<span data-ttu-id="f67fe-244">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="f67fe-244">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="f67fe-245">インターチェンジ方向 = 送信</span><span class="sxs-lookup"><span data-stu-id="f67fe-245">Interchange Direction = Send</span></span>|<span data-ttu-id="f67fe-246">保存されたバッチ シナリオの一意性に必要</span><span class="sxs-lookup"><span data-stu-id="f67fe-246">Required in preserved batch scenario for uniqueness</span></span>|  
|<span data-ttu-id="f67fe-247">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="f67fe-247">Record Type</span></span>|<span data-ttu-id="f67fe-248">インターチェンジ状態とインターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="f67fe-248">Interchange Status and Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="f67fe-249">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f67fe-249">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f67fe-250">インターチェンジ確認方向 = 受信 – 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-250">Interchange ACK Direction = Receive – Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-251">インターチェンジ確認状態 = 受信</span><span class="sxs-lookup"><span data-stu-id="f67fe-251">Interchange ACK Status = Received</span></span>  
  
-   <span data-ttu-id="f67fe-252">インターチェンジ受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-252">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-253">インターチェンジ送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-253">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-254">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-254">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-255">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-255">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-256">インターチェンジ確認制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-256">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-257">インターチェンジ確認日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-257">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-258">インターチェンジ確認時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-258">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-259">確認/アクション コード = 更新データ (TA104 X12 または EDIFACT UCI4) から *\<注 1 を参照してください。\></span><span class="sxs-lookup"><span data-stu-id="f67fe-259">ACK/Action Code = Update Data (from X12-TA104 or EDIFACT-UCI4)* \<Refer Note 1\></span></span>  
  
-   <span data-ttu-id="f67fe-260">確認通知コード 2 = 更新データ (X12 TA105 から edifact と) *\<注 2 を参照してください\></span><span class="sxs-lookup"><span data-stu-id="f67fe-260">ACK Note Code 2 = Update Data (from X12-TA105 and not valued for EDIFACT)* \<Refer Note 2\></span></span>  
  
 <span data-ttu-id="f67fe-261">ACK X12:TA1-104 または EDIFACT UCI4 からのデータは、次のようにマップされます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-261">The data from the ACK X12:TA1-104 or EDIFACT UCI4 is to be mapped as follows:</span></span>  
  
|<span data-ttu-id="f67fe-262">確認/アクション コードのデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-262">Data in ACK/Action Code</span></span>|<span data-ttu-id="f67fe-263">状態レポートでのマップ</span><span class="sxs-lookup"><span data-stu-id="f67fe-263">Mapped for Status Reporting</span></span>|<span data-ttu-id="f67fe-264">解説</span><span class="sxs-lookup"><span data-stu-id="f67fe-264">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="f67fe-265">A</span><span class="sxs-lookup"><span data-stu-id="f67fe-265">A</span></span>|<span data-ttu-id="f67fe-266">受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-266">Accepted</span></span>|<span data-ttu-id="f67fe-267">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-267">X12</span></span>|  
|<span data-ttu-id="f67fe-268">P</span><span class="sxs-lookup"><span data-stu-id="f67fe-268">P</span></span>|<span data-ttu-id="f67fe-269">一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-269">Partially Accepted</span></span>|<span data-ttu-id="f67fe-270">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-270">X12</span></span>|  
|<span data-ttu-id="f67fe-271">R、M、W、X</span><span class="sxs-lookup"><span data-stu-id="f67fe-271">R, M, W, X</span></span>|<span data-ttu-id="f67fe-272">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-272">Rejected</span></span>|<span data-ttu-id="f67fe-273">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-273">X12</span></span>|  
|<span data-ttu-id="f67fe-274">E</span><span class="sxs-lookup"><span data-stu-id="f67fe-274">E</span></span>|<span data-ttu-id="f67fe-275">エラーを伴って承諾済み</span><span class="sxs-lookup"><span data-stu-id="f67fe-275">Accepted with errors</span></span>|<span data-ttu-id="f67fe-276">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-276">X12</span></span>|  
|<span data-ttu-id="f67fe-277">4</span><span class="sxs-lookup"><span data-stu-id="f67fe-277">4</span></span>|<span data-ttu-id="f67fe-278">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-278">Rejected</span></span>|<span data-ttu-id="f67fe-279">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-279">EDIFACT</span></span>|  
|<span data-ttu-id="f67fe-280">7、8</span><span class="sxs-lookup"><span data-stu-id="f67fe-280">7, 8</span></span>|<span data-ttu-id="f67fe-281">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-281">Accepted/Partially Accepted</span></span>|<span data-ttu-id="f67fe-282">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-282">EDIFACT</span></span>|  
  
 <span data-ttu-id="f67fe-283">次の確認通知コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-283">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="f67fe-284">確認通知コードのデータ (X12)</span><span class="sxs-lookup"><span data-stu-id="f67fe-284">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="f67fe-285">状態レポートでのマップ</span><span class="sxs-lookup"><span data-stu-id="f67fe-285">Mapped for Status Reporting</span></span>|  
|--------------------------------------|---------------------------------|  
|<span data-ttu-id="f67fe-286">000</span><span class="sxs-lookup"><span data-stu-id="f67fe-286">000</span></span>|<span data-ttu-id="f67fe-287">Success</span><span class="sxs-lookup"><span data-stu-id="f67fe-287">Success</span></span>|  
|<span data-ttu-id="f67fe-288">001</span><span class="sxs-lookup"><span data-stu-id="f67fe-288">001</span></span>|<span data-ttu-id="f67fe-289">インターチェンジ制御番号が一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-289">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="f67fe-290">002</span><span class="sxs-lookup"><span data-stu-id="f67fe-290">002</span></span>|<span data-ttu-id="f67fe-291">標準がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-291">Standard not supported</span></span>|  
|<span data-ttu-id="f67fe-292">003</span><span class="sxs-lookup"><span data-stu-id="f67fe-292">003</span></span>|<span data-ttu-id="f67fe-293">バージョンのコントロールはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f67fe-293">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="f67fe-294">004</span><span class="sxs-lookup"><span data-stu-id="f67fe-294">004</span></span>|<span data-ttu-id="f67fe-295">セグメント終端記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-295">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="f67fe-296">005</span><span class="sxs-lookup"><span data-stu-id="f67fe-296">005</span></span>|<span data-ttu-id="f67fe-297">送信者のインターチェンジ ID 修飾子が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-297">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="f67fe-298">006</span><span class="sxs-lookup"><span data-stu-id="f67fe-298">006</span></span>|<span data-ttu-id="f67fe-299">インターチェンジ送信者 ID が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-299">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="f67fe-300">007</span><span class="sxs-lookup"><span data-stu-id="f67fe-300">007</span></span>|<span data-ttu-id="f67fe-301">受信者のインターチェンジ ID 修飾子が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-301">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="f67fe-302">008</span><span class="sxs-lookup"><span data-stu-id="f67fe-302">008</span></span>|<span data-ttu-id="f67fe-303">インターチェンジ受信者 ID が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-303">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="f67fe-304">009</span><span class="sxs-lookup"><span data-stu-id="f67fe-304">009</span></span>|<span data-ttu-id="f67fe-305">インターチェンジ受信者 ID が不明です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-305">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="f67fe-306">010</span><span class="sxs-lookup"><span data-stu-id="f67fe-306">010</span></span>|<span data-ttu-id="f67fe-307">認証情報修飾子の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-307">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="f67fe-308">011</span><span class="sxs-lookup"><span data-stu-id="f67fe-308">011</span></span>|<span data-ttu-id="f67fe-309">認証情報の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-309">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="f67fe-310">012</span><span class="sxs-lookup"><span data-stu-id="f67fe-310">012</span></span>|<span data-ttu-id="f67fe-311">無効なセキュリティ情報修飾子の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-311">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="f67fe-312">013</span><span class="sxs-lookup"><span data-stu-id="f67fe-312">013</span></span>|<span data-ttu-id="f67fe-313">セキュリティ情報の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-313">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="f67fe-314">014</span><span class="sxs-lookup"><span data-stu-id="f67fe-314">014</span></span>|<span data-ttu-id="f67fe-315">無効なインターチェンジ日付の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-315">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="f67fe-316">015</span><span class="sxs-lookup"><span data-stu-id="f67fe-316">015</span></span>|<span data-ttu-id="f67fe-317">無効なインターチェンジ時刻の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-317">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="f67fe-318">016</span><span class="sxs-lookup"><span data-stu-id="f67fe-318">016</span></span>|<span data-ttu-id="f67fe-319">無効なインターチェンジ標準識別子の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-319">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="f67fe-320">017</span><span class="sxs-lookup"><span data-stu-id="f67fe-320">017</span></span>|<span data-ttu-id="f67fe-321">インターチェンジ バージョン ID の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-321">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="f67fe-322">018</span><span class="sxs-lookup"><span data-stu-id="f67fe-322">018</span></span>|<span data-ttu-id="f67fe-323">無効なインターチェンジ制御番号の値</span><span class="sxs-lookup"><span data-stu-id="f67fe-323">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="f67fe-324">019</span><span class="sxs-lookup"><span data-stu-id="f67fe-324">019</span></span>|<span data-ttu-id="f67fe-325">確認要求の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-325">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="f67fe-326">020</span><span class="sxs-lookup"><span data-stu-id="f67fe-326">020</span></span>|<span data-ttu-id="f67fe-327">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="f67fe-327">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="f67fe-328">021</span><span class="sxs-lookup"><span data-stu-id="f67fe-328">021</span></span>|<span data-ttu-id="f67fe-329">含まれているグループの数の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-329">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="f67fe-330">022</span><span class="sxs-lookup"><span data-stu-id="f67fe-330">022</span></span>|<span data-ttu-id="f67fe-331">制御構造が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-331">Invalid Control Structure</span></span>|  
|<span data-ttu-id="f67fe-332">023</span><span class="sxs-lookup"><span data-stu-id="f67fe-332">023</span></span>|<span data-ttu-id="f67fe-333">ファイルの終わりが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-333">Improper End-of-File</span></span>|  
|<span data-ttu-id="f67fe-334">024</span><span class="sxs-lookup"><span data-stu-id="f67fe-334">024</span></span>|<span data-ttu-id="f67fe-335">インターチェンジの内容が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-335">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="f67fe-336">025</span><span class="sxs-lookup"><span data-stu-id="f67fe-336">025</span></span>|<span data-ttu-id="f67fe-337">インターチェンジ制御番号が重複しています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-337">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="f67fe-338">026</span><span class="sxs-lookup"><span data-stu-id="f67fe-338">026</span></span>|<span data-ttu-id="f67fe-339">データ要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-339">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="f67fe-340">027</span><span class="sxs-lookup"><span data-stu-id="f67fe-340">027</span></span>|<span data-ttu-id="f67fe-341">コンポーネント要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-341">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="f67fe-342">028</span><span class="sxs-lookup"><span data-stu-id="f67fe-342">028</span></span>|<span data-ttu-id="f67fe-343">遅延配信要求の配信日が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-343">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="f67fe-344">029</span><span class="sxs-lookup"><span data-stu-id="f67fe-344">029</span></span>|<span data-ttu-id="f67fe-345">遅延配信要求の配信時刻が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-345">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="f67fe-346">030</span><span class="sxs-lookup"><span data-stu-id="f67fe-346">030</span></span>|<span data-ttu-id="f67fe-347">遅延配信要求に無効な配信時のコード</span><span class="sxs-lookup"><span data-stu-id="f67fe-347">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="f67fe-348">031</span><span class="sxs-lookup"><span data-stu-id="f67fe-348">031</span></span>|<span data-ttu-id="f67fe-349">サービスの評価が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-349">Invalid Grade of Service</span></span>|  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outbound-interchanges"></a><span data-ttu-id="f67fe-350">送信インターチェンジへの応答として受信した各機能確認用の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-350">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outbound Interchanges</span></span>  
 <span data-ttu-id="f67fe-351">受信パイプラインは、受信した各機能確認用の状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-351">The receive pipeline creates a record in the status report data store for each functional acknowledgment that it receives.</span></span>  <span data-ttu-id="f67fe-352">技術確認は、X12 では 997 で、EDIFACT では CONTRL メッセージの全文です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-352">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="f67fe-353">グループごとに 1 つのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-353">One entry per group will to be created.</span></span> <span data-ttu-id="f67fe-354">インターチェンジおよびグループ ヘッダーからのデータは、このエントリの作成中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-354">Data from the interchange and group headers is used while making this entry.</span></span> <span data-ttu-id="f67fe-355">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f67fe-355">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f67fe-356">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="f67fe-356">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="f67fe-357">機能確認方向 = 送信</span><span class="sxs-lookup"><span data-stu-id="f67fe-357">Functional ACK Direction = Send</span></span>  
  
-   <span data-ttu-id="f67fe-358">機能確認状態 =\<生成された、または該当なし、注 1 を参照してください。\></span><span class="sxs-lookup"><span data-stu-id="f67fe-358">Functional ACK Status = \<Generated or Not Applicable, refer note 1\></span></span>  
  
-   <span data-ttu-id="f67fe-359">インターチェンジの受信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-359">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-360">インターチェンジの送信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-360">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-361">インターチェンジの日付 = 更新データ (X12 関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-361">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-362">インターチェンジ制御 ID = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-362">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-363">グループ制御番号 = 更新データ (EDIFACT ではオプション、X12 関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="f67fe-363">Group Control Number = Update Data (‘optional for EDIFACT’ and required for X12 correlation)</span></span>  
  
-   <span data-ttu-id="f67fe-364">機能 ID コード = 更新データ (GS01/UNG01)</span><span class="sxs-lookup"><span data-stu-id="f67fe-364">Functional ID Code = Update Data (GS01/UNG01)</span></span>  
  
-   <span data-ttu-id="f67fe-365">トランザクション セットの数 = 更新データ (UNE1/UNZ1)</span><span class="sxs-lookup"><span data-stu-id="f67fe-365">Count of Transaction Sets = Update Data (UNE1/UNZ1)</span></span>  
  
-   <span data-ttu-id="f67fe-366">機能確認インターチェンジ制御 ID = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="f67fe-366">Functional ACK Interchange Control ID= Not value – will be applied by send side</span></span>  
  
-   <span data-ttu-id="f67fe-367">機能確認インターチェンジ日付 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="f67fe-367">Functional ACK Interchange Date = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="f67fe-368">機能確認インターチェンジ時刻 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="f67fe-368">Functional ACK Interchange Time = Not valued – will be applied by send side</span></span>  
  
-   <span data-ttu-id="f67fe-369">受信したトランザクション セットの数 = 更新データ (X12-AK903 および EDIFACT エンコード用にエンジンで計算)</span><span class="sxs-lookup"><span data-stu-id="f67fe-369">Count of Transaction Sets Received = Update Data (X12-AK903 and computed by Engine for EDIFACT encoding)</span></span>  
  
-   <span data-ttu-id="f67fe-370">受理したトランザクション セットの数 = 更新データ (X12-AK904 および EDIFACT エンコード用にエンジンで計算)</span><span class="sxs-lookup"><span data-stu-id="f67fe-370">Count of Transaction Sets Accepted = Update Data (X12-AK904 and computed by Engine for EDIFACT engine)</span></span>  
  
-   <span data-ttu-id="f67fe-371">確認/アクション コード = 更新データ\<注 2 を参照してください\>(X12 AK901 edifact-uci4 から) *</span><span class="sxs-lookup"><span data-stu-id="f67fe-371">ACK/Action Code = Update Data  \<refer note 2\> (from X12-AK901 or EDIFACT-UCI4)*</span></span>  
  
-   <span data-ttu-id="f67fe-372">エラー/構文エラー コード  = 更新データ (X12-AK905、EDIFACT UCI5) 注 3</span><span class="sxs-lookup"><span data-stu-id="f67fe-372">Error/Syntax Error Code  = Update Data (X12-AK905, EDIFACT UCI5) Note 3</span></span>  
  
-   <span data-ttu-id="f67fe-373">追加の X12 確認エラー コード 2 = 更新データ (X12-AK906)</span><span class="sxs-lookup"><span data-stu-id="f67fe-373">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
-   <span data-ttu-id="f67fe-374">追加の X12 確認エラー コード 3 = 更新データ (X12-AK907)</span><span class="sxs-lookup"><span data-stu-id="f67fe-374">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
-   <span data-ttu-id="f67fe-375">追加の X12 確認エラー コード 4 = 更新データ (X12-AK908)</span><span class="sxs-lookup"><span data-stu-id="f67fe-375">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
-   <span data-ttu-id="f67fe-376">追加の X12 確認エラー コード 5 = 更新データ (X12-AK909)</span><span class="sxs-lookup"><span data-stu-id="f67fe-376">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
 <span data-ttu-id="f67fe-377">次の確認/アクション コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-377">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="f67fe-378">確認/アクション コードのデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-378">Data in ACK/Action Code</span></span>|<span data-ttu-id="f67fe-379">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="f67fe-379">Error description for Reporting</span></span>|<span data-ttu-id="f67fe-380">コメント (適用範囲)</span><span class="sxs-lookup"><span data-stu-id="f67fe-380">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="f67fe-381">A</span><span class="sxs-lookup"><span data-stu-id="f67fe-381">A</span></span>|<span data-ttu-id="f67fe-382">受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-382">Accepted</span></span>|<span data-ttu-id="f67fe-383">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-383">X12</span></span>|  
|<span data-ttu-id="f67fe-384">E</span><span class="sxs-lookup"><span data-stu-id="f67fe-384">E</span></span>|<span data-ttu-id="f67fe-385">エラーを伴って承諾済み</span><span class="sxs-lookup"><span data-stu-id="f67fe-385">Accepted  with errors</span></span>|<span data-ttu-id="f67fe-386">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-386">X12</span></span>|  
|<span data-ttu-id="f67fe-387">P</span><span class="sxs-lookup"><span data-stu-id="f67fe-387">P</span></span>|<span data-ttu-id="f67fe-388">一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-388">Partially Accepted</span></span>|<span data-ttu-id="f67fe-389">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-389">X12</span></span>|  
|<span data-ttu-id="f67fe-390">R</span><span class="sxs-lookup"><span data-stu-id="f67fe-390">R</span></span>|<span data-ttu-id="f67fe-391">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-391">Rejected</span></span>|<span data-ttu-id="f67fe-392">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-392">X12</span></span>|  
|<span data-ttu-id="f67fe-393">4</span><span class="sxs-lookup"><span data-stu-id="f67fe-393">4</span></span>|<span data-ttu-id="f67fe-394">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-394">Rejected</span></span>|<span data-ttu-id="f67fe-395">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-395">EDIFACT</span></span>|  
|<span data-ttu-id="f67fe-396">7</span><span class="sxs-lookup"><span data-stu-id="f67fe-396">7</span></span>|<span data-ttu-id="f67fe-397">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-397">Accepted/Partially Accepted</span></span>|<span data-ttu-id="f67fe-398">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-398">EDIFACT</span></span>|  
  
 <span data-ttu-id="f67fe-399">次のエラー/構文エラー コードが EDIFACT に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-399">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="f67fe-400">エラー/構文エラー コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-400">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="f67fe-401">(EDIFACT に適用可能)</span><span class="sxs-lookup"><span data-stu-id="f67fe-401">(applicable to EDIFACT)</span></span>|<span data-ttu-id="f67fe-402">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="f67fe-402">Error Description for reporting</span></span>|  
|--------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="f67fe-403">2</span><span class="sxs-lookup"><span data-stu-id="f67fe-403">2</span></span>|<span data-ttu-id="f67fe-404">構文のバージョンまたはレベルがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-404">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="f67fe-405">7</span><span class="sxs-lookup"><span data-stu-id="f67fe-405">7</span></span>|<span data-ttu-id="f67fe-406">インターチェンジの受信者が実際の受信者ではありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-406">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="f67fe-407">12</span><span class="sxs-lookup"><span data-stu-id="f67fe-407">12</span></span>|<span data-ttu-id="f67fe-408">値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-408">Invalid value</span></span>|  
|<span data-ttu-id="f67fe-409">13</span><span class="sxs-lookup"><span data-stu-id="f67fe-409">13</span></span>|<span data-ttu-id="f67fe-410">Missing</span><span class="sxs-lookup"><span data-stu-id="f67fe-410">Missing</span></span>|  
|<span data-ttu-id="f67fe-411">14</span><span class="sxs-lookup"><span data-stu-id="f67fe-411">14</span></span>|<span data-ttu-id="f67fe-412">この位置ではサポートされていない値です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-412">Value not supported in this position</span></span>|  
|<span data-ttu-id="f67fe-413">15</span><span class="sxs-lookup"><span data-stu-id="f67fe-413">15</span></span>|<span data-ttu-id="f67fe-414">サポートされていない位置です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-414">Not supported in this position</span></span>|  
|<span data-ttu-id="f67fe-415">16</span><span class="sxs-lookup"><span data-stu-id="f67fe-415">16</span></span>|<span data-ttu-id="f67fe-416">含まれている要素が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-416">Too many constituents</span></span>|  
|<span data-ttu-id="f67fe-417">17</span><span class="sxs-lookup"><span data-stu-id="f67fe-417">17</span></span>|<span data-ttu-id="f67fe-418">アグリーメントがありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-418">No agreement</span></span>|  
|<span data-ttu-id="f67fe-419">18</span><span class="sxs-lookup"><span data-stu-id="f67fe-419">18</span></span>|<span data-ttu-id="f67fe-420">不特定のエラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-420">Unspecified error</span></span>|  
|<span data-ttu-id="f67fe-421">19</span><span class="sxs-lookup"><span data-stu-id="f67fe-421">19</span></span>|<span data-ttu-id="f67fe-422">無効な小数点表記です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-422">Invalid decimal notation</span></span>|  
|<span data-ttu-id="f67fe-423">20</span><span class="sxs-lookup"><span data-stu-id="f67fe-423">20</span></span>|<span data-ttu-id="f67fe-424">サービス文字として無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-424">Character invalid as service character</span></span>|  
|<span data-ttu-id="f67fe-425">21</span><span class="sxs-lookup"><span data-stu-id="f67fe-425">21</span></span>|<span data-ttu-id="f67fe-426">無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-426">Invalid character(s)</span></span>|  
|<span data-ttu-id="f67fe-427">22</span><span class="sxs-lookup"><span data-stu-id="f67fe-427">22</span></span>|<span data-ttu-id="f67fe-428">サービス文字が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-428">Invalid service character(s)</span></span>|  
|<span data-ttu-id="f67fe-429">23</span><span class="sxs-lookup"><span data-stu-id="f67fe-429">23</span></span>|<span data-ttu-id="f67fe-430">インターチェンジの送信者が不明です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-430">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="f67fe-431">24</span><span class="sxs-lookup"><span data-stu-id="f67fe-431">24</span></span>|<span data-ttu-id="f67fe-432">古すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-432">Too old</span></span>|  
|<span data-ttu-id="f67fe-433">25</span><span class="sxs-lookup"><span data-stu-id="f67fe-433">25</span></span>|<span data-ttu-id="f67fe-434">テスト インジケーターがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-434">Test indicator not supported</span></span>|  
|<span data-ttu-id="f67fe-435">26</span><span class="sxs-lookup"><span data-stu-id="f67fe-435">26</span></span>|<span data-ttu-id="f67fe-436">重複が検出されました。</span><span class="sxs-lookup"><span data-stu-id="f67fe-436">Duplicate detected</span></span>|  
|<span data-ttu-id="f67fe-437">27</span><span class="sxs-lookup"><span data-stu-id="f67fe-437">27</span></span>|<span data-ttu-id="f67fe-438">セキュリティ機能がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-438">Security function not supported</span></span>|  
|<span data-ttu-id="f67fe-439">28</span><span class="sxs-lookup"><span data-stu-id="f67fe-439">28</span></span>|<span data-ttu-id="f67fe-440">参照が一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-440">References do not match</span></span>|  
|<span data-ttu-id="f67fe-441">29</span><span class="sxs-lookup"><span data-stu-id="f67fe-441">29</span></span>|<span data-ttu-id="f67fe-442">制御数が受信したインターチェンジの数と一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-442">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="f67fe-443">30</span><span class="sxs-lookup"><span data-stu-id="f67fe-443">30</span></span>|<span data-ttu-id="f67fe-444">グループとメッセージ/パッケージが混在しています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-444">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="f67fe-445">31</span><span class="sxs-lookup"><span data-stu-id="f67fe-445">31</span></span>|<span data-ttu-id="f67fe-446">グループ内に複数のメッセージの種類があります。</span><span class="sxs-lookup"><span data-stu-id="f67fe-446">More than one message type in group</span></span>|  
|<span data-ttu-id="f67fe-447">32</span><span class="sxs-lookup"><span data-stu-id="f67fe-447">32</span></span>|<span data-ttu-id="f67fe-448">下位レベルが空です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-448">Lower level empty</span></span>|  
|<span data-ttu-id="f67fe-449">33</span><span class="sxs-lookup"><span data-stu-id="f67fe-449">33</span></span>|<span data-ttu-id="f67fe-450">メッセージ、パッケージ、またはグループの外側に無効な項目があります。</span><span class="sxs-lookup"><span data-stu-id="f67fe-450">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="f67fe-451">34</span><span class="sxs-lookup"><span data-stu-id="f67fe-451">34</span></span>|<span data-ttu-id="f67fe-452">インジケーターの入れ子は認められていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-452">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="f67fe-453">35</span><span class="sxs-lookup"><span data-stu-id="f67fe-453">35</span></span>|<span data-ttu-id="f67fe-454">データ要素またはセグメントの繰り返しが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-454">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="f67fe-455">36</span><span class="sxs-lookup"><span data-stu-id="f67fe-455">36</span></span>|<span data-ttu-id="f67fe-456">セグメント グループの繰り返しが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-456">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="f67fe-457">37</span><span class="sxs-lookup"><span data-stu-id="f67fe-457">37</span></span>|<span data-ttu-id="f67fe-458">文字の種類が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-458">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="f67fe-459">38</span><span class="sxs-lookup"><span data-stu-id="f67fe-459">38</span></span>|<span data-ttu-id="f67fe-460">小数点の記号の前に数値がありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-460">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="f67fe-461">39</span><span class="sxs-lookup"><span data-stu-id="f67fe-461">39</span></span>|<span data-ttu-id="f67fe-462">データ要素が長すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-462">Data element too long</span></span>|  
|<span data-ttu-id="f67fe-463">40</span><span class="sxs-lookup"><span data-stu-id="f67fe-463">40</span></span>|<span data-ttu-id="f67fe-464">データ要素が短すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-464">Data element too short</span></span>|  
|<span data-ttu-id="f67fe-465">41</span><span class="sxs-lookup"><span data-stu-id="f67fe-465">41</span></span>|<span data-ttu-id="f67fe-466">永続的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-466">Permanent communication network error</span></span>|  
|<span data-ttu-id="f67fe-467">42</span><span class="sxs-lookup"><span data-stu-id="f67fe-467">42</span></span>|<span data-ttu-id="f67fe-468">一時的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-468">Temporary communication network error</span></span>|  
|<span data-ttu-id="f67fe-469">43</span><span class="sxs-lookup"><span data-stu-id="f67fe-469">43</span></span>|<span data-ttu-id="f67fe-470">インターチェンジの受信者が不明です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-470">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="f67fe-471">45</span><span class="sxs-lookup"><span data-stu-id="f67fe-471">45</span></span>|<span data-ttu-id="f67fe-472">末尾の区切り記号が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="f67fe-472">Trailing separator</span></span>|  
|<span data-ttu-id="f67fe-473">46</span><span class="sxs-lookup"><span data-stu-id="f67fe-473">46</span></span>|<span data-ttu-id="f67fe-474">文字セットがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f67fe-474">Character set not supported</span></span>|  
|<span data-ttu-id="f67fe-475">47</span><span class="sxs-lookup"><span data-stu-id="f67fe-475">47</span></span>|<span data-ttu-id="f67fe-476">エンベロープ機能はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-476">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="f67fe-477">48</span><span class="sxs-lookup"><span data-stu-id="f67fe-477">48</span></span>|<span data-ttu-id="f67fe-478">依存状態が違反しています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-478">Dependency condition violated</span></span>|  
|<span data-ttu-id="f67fe-479">70</span><span class="sxs-lookup"><span data-stu-id="f67fe-479">70</span></span>|<span data-ttu-id="f67fe-480">トランザクション セットがないか、トランザクション セットの識別子が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-480">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="f67fe-481">71</span><span class="sxs-lookup"><span data-stu-id="f67fe-481">71</span></span>|<span data-ttu-id="f67fe-482">トランザクション セット制御番号またはグループ制御番号が一致していません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-482">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="f67fe-483">72</span><span class="sxs-lookup"><span data-stu-id="f67fe-483">72</span></span>|<span data-ttu-id="f67fe-484">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="f67fe-484">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="f67fe-485">73</span><span class="sxs-lookup"><span data-stu-id="f67fe-485">73</span></span>|<span data-ttu-id="f67fe-486">XML の位置が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-486">XML not at correct position</span></span>|  
|<span data-ttu-id="f67fe-487">74</span><span class="sxs-lookup"><span data-stu-id="f67fe-487">74</span></span>|<span data-ttu-id="f67fe-488">セグメント グループの繰り返しが少なすぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-488">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="f67fe-489">75</span><span class="sxs-lookup"><span data-stu-id="f67fe-489">75</span></span>|<span data-ttu-id="f67fe-490">セグメントの繰り返しが少なすぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-490">Too few segment repetitions</span></span>|  
|<span data-ttu-id="f67fe-491">76</span><span class="sxs-lookup"><span data-stu-id="f67fe-491">76</span></span>|<span data-ttu-id="f67fe-492">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="f67fe-492">Too few data elements found</span></span>|  
  
 <span data-ttu-id="f67fe-493">次のエラー/構文エラー コードが X12 で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-493">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="f67fe-494">エラー/構文エラー コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-494">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="f67fe-495">(X12 に適用可能)</span><span class="sxs-lookup"><span data-stu-id="f67fe-495">(applicable to X12)</span></span>|<span data-ttu-id="f67fe-496">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="f67fe-496">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="f67fe-497">1</span><span class="sxs-lookup"><span data-stu-id="f67fe-497">1</span></span>|<span data-ttu-id="f67fe-498">機能グループがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-498">Functional group not supported</span></span>|  
|<span data-ttu-id="f67fe-499">2</span><span class="sxs-lookup"><span data-stu-id="f67fe-499">2</span></span>|<span data-ttu-id="f67fe-500">機能グループのバージョンがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-500">Functional group version not supported</span></span>|  
|<span data-ttu-id="f67fe-501">3</span><span class="sxs-lookup"><span data-stu-id="f67fe-501">3</span></span>|<span data-ttu-id="f67fe-502">機能グループ トレーラーがありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-502">Functional group trailer missing</span></span>|  
|<span data-ttu-id="f67fe-503">4</span><span class="sxs-lookup"><span data-stu-id="f67fe-503">4</span></span>|<span data-ttu-id="f67fe-504">機能グループ ヘッダーとトレーラーのグループ制御番号が一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-504">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="f67fe-505">5</span><span class="sxs-lookup"><span data-stu-id="f67fe-505">5</span></span>|<span data-ttu-id="f67fe-506">含まれているトランザクション セットの数が実際の数と一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-506">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="f67fe-507">6-26</span><span class="sxs-lookup"><span data-stu-id="f67fe-507">6-26</span></span>|<span data-ttu-id="f67fe-508">その他のサポートされていない検証エラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-508">Other unsupported validation errors</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outgoing-interchanges"></a><span data-ttu-id="f67fe-509">送信インターチェンジへの応答として受信した各機能確認用の受信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-509">Data Updated by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outgoing Interchanges</span></span>  
 <span data-ttu-id="f67fe-510">受信パイプラインが受信した各機能を確認するたびに、関連する送信インターチェンジの状態レポート エントリが更新されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-510">For each functional acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="f67fe-511">EDI 逆アセンブラーは、次のように受信確認のインターチェンジおよびグループ ヘッダー セグメントのデータを使用して、データ ストア内でレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="f67fe-511">The EDI Disassembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="f67fe-512">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="f67fe-512">Fields in ACK</span></span>|<span data-ttu-id="f67fe-513">データ ストアのフィールド</span><span class="sxs-lookup"><span data-stu-id="f67fe-513">Fields in Data store</span></span>|<span data-ttu-id="f67fe-514">解説</span><span class="sxs-lookup"><span data-stu-id="f67fe-514">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="f67fe-515">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="f67fe-515">Interchange Sender ID</span></span>|<span data-ttu-id="f67fe-516">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="f67fe-516">Interchange Receiver</span></span>|<span data-ttu-id="f67fe-517">X12 および EDIFACT に適用可能</span><span class="sxs-lookup"><span data-stu-id="f67fe-517">Applicable to both X12 and EDIFACT</span></span>|  
|<span data-ttu-id="f67fe-518">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="f67fe-518">Interchange Receiver ID</span></span>|<span data-ttu-id="f67fe-519">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="f67fe-519">Interchange Sender</span></span>|<span data-ttu-id="f67fe-520">X12 および EDIFACT に適用可能</span><span class="sxs-lookup"><span data-stu-id="f67fe-520">Applicable to both X12 and EDIFACT</span></span>|  
|-|<span data-ttu-id="f67fe-521">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="f67fe-521">Interchange Date</span></span>|-|  
|<span data-ttu-id="f67fe-522">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="f67fe-522">Interchange Control Number</span></span>|<span data-ttu-id="f67fe-523">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="f67fe-523">Interchange Control ID</span></span>|<span data-ttu-id="f67fe-524">EDIFACT のみに適用可能</span><span class="sxs-lookup"><span data-stu-id="f67fe-524">Applicable only to EDIFACT</span></span>|  
|<span data-ttu-id="f67fe-525">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="f67fe-525">Group Control Number</span></span>|<span data-ttu-id="f67fe-526">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="f67fe-526">Group Control Number</span></span>|<span data-ttu-id="f67fe-527">X12 のみに適用可能</span><span class="sxs-lookup"><span data-stu-id="f67fe-527">Applicable only to X12</span></span>|  
|-|<span data-ttu-id="f67fe-528">インターチェンジ方向 = 送信</span><span class="sxs-lookup"><span data-stu-id="f67fe-528">Interchange Direction = Send</span></span>|<span data-ttu-id="f67fe-529">BIBO シナリオ以降の一意性に必要</span><span class="sxs-lookup"><span data-stu-id="f67fe-529">Required since in BIBO Scenario for uniqueness</span></span>|  
|<span data-ttu-id="f67fe-530">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="f67fe-530">Record Type</span></span>|<span data-ttu-id="f67fe-531">機能確認状態</span><span class="sxs-lookup"><span data-stu-id="f67fe-531">Functional ACK Status</span></span>|<span data-ttu-id="f67fe-532">X12 および EDIFACT に適用可能</span><span class="sxs-lookup"><span data-stu-id="f67fe-532">Applicable to both X12 and EDIFACT</span></span>|  
  
 <span data-ttu-id="f67fe-533">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f67fe-533">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f67fe-534">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="f67fe-534">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="f67fe-535">機能確認方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="f67fe-535">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="f67fe-536">機能確認状態 = 受信したとおりの更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-536">Functional ACK Status =Update Data as Received</span></span>  
  
-   <span data-ttu-id="f67fe-537">インターチェンジ受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-537">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-538">インターチェンジ送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-538">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-539">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-539">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-540">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-540">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-541">グループ制御番号 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-541">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-542">機能 ID コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-542">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-543">トランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-543">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="f67fe-544">機能確認インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-544">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-545">機能確認インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-545">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-546">機能確認インターチェンジ時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f67fe-546">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="f67fe-547">配信されたトランザクション セットの数 = 更新データ (X12-AK903、EDIFACT には適用不可)</span><span class="sxs-lookup"><span data-stu-id="f67fe-547">Count of Transaction Sets Delivered = Update Data (X12 AK903 and not applicable for EDIFACT)</span></span>  
  
-   <span data-ttu-id="f67fe-548">受理されたトランザクション セットの数 = 更新データ (X12-AK904、EDIFACT には適用不可)</span><span class="sxs-lookup"><span data-stu-id="f67fe-548">Count of Transaction Sets Accepted = Update Data (X12 AK904 and not applicable for EDIFACT)</span></span>  
  
-   <span data-ttu-id="f67fe-549">確認/アクション コード = 更新データ (X12 AK901 および UCI4) 注 1 を参照</span><span class="sxs-lookup"><span data-stu-id="f67fe-549">ACK/Action Code = Update Data (X12 AK901 and UCI4) Refer Note 1</span></span>  
  
-   <span data-ttu-id="f67fe-550">エラー/構文エラー コード  = (X12 AK905 および UCI5) 注 2 を参照</span><span class="sxs-lookup"><span data-stu-id="f67fe-550">Error/Syntax Error Code  = (X12 AK905 and UCI5) Refer Note 2</span></span>  
  
-   <span data-ttu-id="f67fe-551">追加の X12 確認エラー コード 2 = 更新データ (X12-AK906)</span><span class="sxs-lookup"><span data-stu-id="f67fe-551">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
-   <span data-ttu-id="f67fe-552">追加の X12 確認エラー コード 3 = 更新データ (X12-AK907)</span><span class="sxs-lookup"><span data-stu-id="f67fe-552">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
-   <span data-ttu-id="f67fe-553">追加の X12 確認エラー コード 4 = 更新データ (X12-AK908)</span><span class="sxs-lookup"><span data-stu-id="f67fe-553">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
-   <span data-ttu-id="f67fe-554">追加の X12 確認エラー コード 5 = 更新データ (X12-AK909)</span><span class="sxs-lookup"><span data-stu-id="f67fe-554">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
 <span data-ttu-id="f67fe-555">次の確認/アクション コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-555">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="f67fe-556">確認/アクション コードのデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-556">Data in ACK/Action Code</span></span>|<span data-ttu-id="f67fe-557">状態レポートでのマップ</span><span class="sxs-lookup"><span data-stu-id="f67fe-557">Mapped for Status Reporting</span></span>|<span data-ttu-id="f67fe-558">解説</span><span class="sxs-lookup"><span data-stu-id="f67fe-558">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="f67fe-559">A</span><span class="sxs-lookup"><span data-stu-id="f67fe-559">A</span></span>|<span data-ttu-id="f67fe-560">受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-560">Accepted</span></span>|<span data-ttu-id="f67fe-561">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-561">X12</span></span>|  
|<span data-ttu-id="f67fe-562">P</span><span class="sxs-lookup"><span data-stu-id="f67fe-562">P</span></span>|<span data-ttu-id="f67fe-563">一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-563">Partially Accepted</span></span>|<span data-ttu-id="f67fe-564">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-564">X12</span></span>|  
|<span data-ttu-id="f67fe-565">R、M、W、X</span><span class="sxs-lookup"><span data-stu-id="f67fe-565">R, M, W, X</span></span>|<span data-ttu-id="f67fe-566">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-566">Rejected</span></span>|<span data-ttu-id="f67fe-567">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-567">X12</span></span>|  
|<span data-ttu-id="f67fe-568">E</span><span class="sxs-lookup"><span data-stu-id="f67fe-568">E</span></span>|<span data-ttu-id="f67fe-569">エラーを伴って承諾済み</span><span class="sxs-lookup"><span data-stu-id="f67fe-569">Accepted with errors</span></span>|<span data-ttu-id="f67fe-570">X12</span><span class="sxs-lookup"><span data-stu-id="f67fe-570">X12</span></span>|  
|<span data-ttu-id="f67fe-571">4</span><span class="sxs-lookup"><span data-stu-id="f67fe-571">4</span></span>|<span data-ttu-id="f67fe-572">拒否しました</span><span class="sxs-lookup"><span data-stu-id="f67fe-572">Rejected</span></span>|<span data-ttu-id="f67fe-573">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-573">EDIFACT</span></span>|  
|<span data-ttu-id="f67fe-574">7、8</span><span class="sxs-lookup"><span data-stu-id="f67fe-574">7, 8</span></span>|<span data-ttu-id="f67fe-575">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="f67fe-575">Accepted/Partially Accepted</span></span>|<span data-ttu-id="f67fe-576">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f67fe-576">EDIFACT</span></span>|  
  
 <span data-ttu-id="f67fe-577">次のエラー/構文エラー コードが EDIFACT に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-577">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="f67fe-578">エラー/構文エラー コードのデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-578">Data in Error/Syntax Error Cod</span></span><br /><br /> <span data-ttu-id="f67fe-579">(EDIFACT に適用可能)</span><span class="sxs-lookup"><span data-stu-id="f67fe-579">(applicable to EDIFACT)</span></span>|<span data-ttu-id="f67fe-580">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="f67fe-580">Error Description for reporting</span></span>|  
|-------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="f67fe-581">2</span><span class="sxs-lookup"><span data-stu-id="f67fe-581">2</span></span>|<span data-ttu-id="f67fe-582">構文のバージョンまたはレベルがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-582">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="f67fe-583">7</span><span class="sxs-lookup"><span data-stu-id="f67fe-583">7</span></span>|<span data-ttu-id="f67fe-584">インターチェンジの受信者が実際の受信者ではありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-584">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="f67fe-585">12</span><span class="sxs-lookup"><span data-stu-id="f67fe-585">12</span></span>|<span data-ttu-id="f67fe-586">値が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-586">Invalid value</span></span>|  
|<span data-ttu-id="f67fe-587">13</span><span class="sxs-lookup"><span data-stu-id="f67fe-587">13</span></span>|<span data-ttu-id="f67fe-588">Missing</span><span class="sxs-lookup"><span data-stu-id="f67fe-588">Missing</span></span>|  
|<span data-ttu-id="f67fe-589">14</span><span class="sxs-lookup"><span data-stu-id="f67fe-589">14</span></span>|<span data-ttu-id="f67fe-590">この位置ではサポートされていない値です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-590">Value not supported in this position</span></span>|  
|<span data-ttu-id="f67fe-591">15</span><span class="sxs-lookup"><span data-stu-id="f67fe-591">15</span></span>|<span data-ttu-id="f67fe-592">サポートされていない位置です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-592">Not supported in this position</span></span>|  
|<span data-ttu-id="f67fe-593">16</span><span class="sxs-lookup"><span data-stu-id="f67fe-593">16</span></span>|<span data-ttu-id="f67fe-594">含まれている要素が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-594">Too many constituents</span></span>|  
|<span data-ttu-id="f67fe-595">17</span><span class="sxs-lookup"><span data-stu-id="f67fe-595">17</span></span>|<span data-ttu-id="f67fe-596">アグリーメントがありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-596">No agreement</span></span>|  
|<span data-ttu-id="f67fe-597">18</span><span class="sxs-lookup"><span data-stu-id="f67fe-597">18</span></span>|<span data-ttu-id="f67fe-598">不特定のエラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-598">Unspecified error</span></span>|  
|<span data-ttu-id="f67fe-599">19</span><span class="sxs-lookup"><span data-stu-id="f67fe-599">19</span></span>|<span data-ttu-id="f67fe-600">無効な小数点表記です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-600">Invalid decimal notation</span></span>|  
|<span data-ttu-id="f67fe-601">20</span><span class="sxs-lookup"><span data-stu-id="f67fe-601">20</span></span>|<span data-ttu-id="f67fe-602">サービス文字として無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-602">Character invalid as service character</span></span>|  
|<span data-ttu-id="f67fe-603">21</span><span class="sxs-lookup"><span data-stu-id="f67fe-603">21</span></span>|<span data-ttu-id="f67fe-604">無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-604">Invalid character(s)</span></span>|  
|<span data-ttu-id="f67fe-605">22</span><span class="sxs-lookup"><span data-stu-id="f67fe-605">22</span></span>|<span data-ttu-id="f67fe-606">サービス文字が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-606">Invalid service character(s)</span></span>|  
|<span data-ttu-id="f67fe-607">23</span><span class="sxs-lookup"><span data-stu-id="f67fe-607">23</span></span>|<span data-ttu-id="f67fe-608">インターチェンジの送信者が不明です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-608">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="f67fe-609">24</span><span class="sxs-lookup"><span data-stu-id="f67fe-609">24</span></span>|<span data-ttu-id="f67fe-610">古すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-610">Too old</span></span>|  
|<span data-ttu-id="f67fe-611">25</span><span class="sxs-lookup"><span data-stu-id="f67fe-611">25</span></span>|<span data-ttu-id="f67fe-612">テスト インジケーターがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-612">Test indicator not supported</span></span>|  
|<span data-ttu-id="f67fe-613">26</span><span class="sxs-lookup"><span data-stu-id="f67fe-613">26</span></span>|<span data-ttu-id="f67fe-614">重複が検出されました。</span><span class="sxs-lookup"><span data-stu-id="f67fe-614">Duplicate detected</span></span>|  
|<span data-ttu-id="f67fe-615">27</span><span class="sxs-lookup"><span data-stu-id="f67fe-615">27</span></span>|<span data-ttu-id="f67fe-616">セキュリティ機能がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-616">Security function not supported</span></span>|  
|<span data-ttu-id="f67fe-617">28</span><span class="sxs-lookup"><span data-stu-id="f67fe-617">28</span></span>|<span data-ttu-id="f67fe-618">参照が一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-618">References do not match</span></span>|  
|<span data-ttu-id="f67fe-619">29</span><span class="sxs-lookup"><span data-stu-id="f67fe-619">29</span></span>|<span data-ttu-id="f67fe-620">制御数が受信したインターチェンジの数と一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-620">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="f67fe-621">30</span><span class="sxs-lookup"><span data-stu-id="f67fe-621">30</span></span>|<span data-ttu-id="f67fe-622">グループとメッセージ/パッケージが混在しています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-622">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="f67fe-623">31</span><span class="sxs-lookup"><span data-stu-id="f67fe-623">31</span></span>|<span data-ttu-id="f67fe-624">グループ内に複数のメッセージの種類があります。</span><span class="sxs-lookup"><span data-stu-id="f67fe-624">More than one message type in group</span></span>|  
|<span data-ttu-id="f67fe-625">32</span><span class="sxs-lookup"><span data-stu-id="f67fe-625">32</span></span>|<span data-ttu-id="f67fe-626">下位レベルが空です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-626">Lower level empty</span></span>|  
|<span data-ttu-id="f67fe-627">33</span><span class="sxs-lookup"><span data-stu-id="f67fe-627">33</span></span>|<span data-ttu-id="f67fe-628">メッセージ、パッケージ、またはグループの外側に無効な項目があります。</span><span class="sxs-lookup"><span data-stu-id="f67fe-628">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="f67fe-629">34</span><span class="sxs-lookup"><span data-stu-id="f67fe-629">34</span></span>|<span data-ttu-id="f67fe-630">インジケーターの入れ子は認められていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-630">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="f67fe-631">35</span><span class="sxs-lookup"><span data-stu-id="f67fe-631">35</span></span>|<span data-ttu-id="f67fe-632">データ要素またはセグメントの繰り返しが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-632">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="f67fe-633">36</span><span class="sxs-lookup"><span data-stu-id="f67fe-633">36</span></span>|<span data-ttu-id="f67fe-634">セグメント グループの繰り返しが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-634">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="f67fe-635">37</span><span class="sxs-lookup"><span data-stu-id="f67fe-635">37</span></span>|<span data-ttu-id="f67fe-636">文字の種類が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-636">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="f67fe-637">38</span><span class="sxs-lookup"><span data-stu-id="f67fe-637">38</span></span>|<span data-ttu-id="f67fe-638">小数点の記号の前に数値がありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-638">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="f67fe-639">39</span><span class="sxs-lookup"><span data-stu-id="f67fe-639">39</span></span>|<span data-ttu-id="f67fe-640">データ要素が長すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-640">Data element too long</span></span>|  
|<span data-ttu-id="f67fe-641">40</span><span class="sxs-lookup"><span data-stu-id="f67fe-641">40</span></span>|<span data-ttu-id="f67fe-642">データ要素が短すぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-642">Data element too short</span></span>|  
|<span data-ttu-id="f67fe-643">41</span><span class="sxs-lookup"><span data-stu-id="f67fe-643">41</span></span>|<span data-ttu-id="f67fe-644">永続的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-644">Permanent communication network error</span></span>|  
|<span data-ttu-id="f67fe-645">42</span><span class="sxs-lookup"><span data-stu-id="f67fe-645">42</span></span>|<span data-ttu-id="f67fe-646">一時的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-646">Temporary communication network error</span></span>|  
|<span data-ttu-id="f67fe-647">43</span><span class="sxs-lookup"><span data-stu-id="f67fe-647">43</span></span>|<span data-ttu-id="f67fe-648">インターチェンジの受信者が不明です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-648">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="f67fe-649">45</span><span class="sxs-lookup"><span data-stu-id="f67fe-649">45</span></span>|<span data-ttu-id="f67fe-650">末尾の区切り記号が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="f67fe-650">Trailing separator</span></span>|  
|<span data-ttu-id="f67fe-651">46</span><span class="sxs-lookup"><span data-stu-id="f67fe-651">46</span></span>|<span data-ttu-id="f67fe-652">文字セットがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f67fe-652">Character set not supported</span></span>|  
|<span data-ttu-id="f67fe-653">47</span><span class="sxs-lookup"><span data-stu-id="f67fe-653">47</span></span>|<span data-ttu-id="f67fe-654">エンベロープ機能はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-654">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="f67fe-655">48</span><span class="sxs-lookup"><span data-stu-id="f67fe-655">48</span></span>|<span data-ttu-id="f67fe-656">依存状態が違反しています。</span><span class="sxs-lookup"><span data-stu-id="f67fe-656">Dependency condition violated</span></span>|  
|<span data-ttu-id="f67fe-657">70</span><span class="sxs-lookup"><span data-stu-id="f67fe-657">70</span></span>|<span data-ttu-id="f67fe-658">トランザクション セットがないか、トランザクション セットの識別子が無効です。</span><span class="sxs-lookup"><span data-stu-id="f67fe-658">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="f67fe-659">71</span><span class="sxs-lookup"><span data-stu-id="f67fe-659">71</span></span>|<span data-ttu-id="f67fe-660">トランザクション セット制御番号またはグループ制御番号が一致していません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-660">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="f67fe-661">72</span><span class="sxs-lookup"><span data-stu-id="f67fe-661">72</span></span>|<span data-ttu-id="f67fe-662">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="f67fe-662">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="f67fe-663">73</span><span class="sxs-lookup"><span data-stu-id="f67fe-663">73</span></span>|<span data-ttu-id="f67fe-664">XML の位置が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-664">XML not at correct position</span></span>|  
|<span data-ttu-id="f67fe-665">74</span><span class="sxs-lookup"><span data-stu-id="f67fe-665">74</span></span>|<span data-ttu-id="f67fe-666">セグメント グループの繰り返しが少なすぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-666">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="f67fe-667">75</span><span class="sxs-lookup"><span data-stu-id="f67fe-667">75</span></span>|<span data-ttu-id="f67fe-668">セグメントの繰り返しが少なすぎます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-668">Too few segment repetitions</span></span>|  
|<span data-ttu-id="f67fe-669">76</span><span class="sxs-lookup"><span data-stu-id="f67fe-669">76</span></span>|<span data-ttu-id="f67fe-670">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="f67fe-670">Too few data elements found</span></span>|  
  
 <span data-ttu-id="f67fe-671">次のエラー/構文エラー コードが X12 で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f67fe-671">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="f67fe-672">エラー/構文エラー コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="f67fe-672">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="f67fe-673">(X12 に適用可能)</span><span class="sxs-lookup"><span data-stu-id="f67fe-673">(applicable to X12)</span></span>|<span data-ttu-id="f67fe-674">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="f67fe-674">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="f67fe-675">1</span><span class="sxs-lookup"><span data-stu-id="f67fe-675">1</span></span>|<span data-ttu-id="f67fe-676">機能グループがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-676">Functional group not supported</span></span>|  
|<span data-ttu-id="f67fe-677">2</span><span class="sxs-lookup"><span data-stu-id="f67fe-677">2</span></span>|<span data-ttu-id="f67fe-678">機能グループのバージョンがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-678">Functional group version not supported</span></span>|  
|<span data-ttu-id="f67fe-679">3</span><span class="sxs-lookup"><span data-stu-id="f67fe-679">3</span></span>|<span data-ttu-id="f67fe-680">機能グループ トレーラーがありません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-680">Functional group trailer missing</span></span>|  
|<span data-ttu-id="f67fe-681">4</span><span class="sxs-lookup"><span data-stu-id="f67fe-681">4</span></span>|<span data-ttu-id="f67fe-682">機能グループ ヘッダーとトレーラーのグループ制御番号が一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-682">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="f67fe-683">5</span><span class="sxs-lookup"><span data-stu-id="f67fe-683">5</span></span>|<span data-ttu-id="f67fe-684">含まれているトランザクション セットの数が実際の数と一致しません。</span><span class="sxs-lookup"><span data-stu-id="f67fe-684">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="f67fe-685">6-26</span><span class="sxs-lookup"><span data-stu-id="f67fe-685">6-26</span></span>|<span data-ttu-id="f67fe-686">その他のサポートされていない検証エラー</span><span class="sxs-lookup"><span data-stu-id="f67fe-686">Other unsupported validation errors</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f67fe-687">参照</span><span class="sxs-lookup"><span data-stu-id="f67fe-687">See Also</span></span>  
 <span data-ttu-id="f67fe-688">[EDI および AS2 状態レポートのデータを格納する方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="f67fe-688">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="f67fe-689">受信 EDI メッセージのデータ格納方法</span><span class="sxs-lookup"><span data-stu-id="f67fe-689">How Data Is Stored for Inbound EDI Messages</span></span>](../core/how-data-is-stored-for-inbound-edi-messages.md)