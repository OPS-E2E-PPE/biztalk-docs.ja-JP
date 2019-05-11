---
title: 送信 EDI メッセージのデータを格納する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6e576fc-37fd-417d-ae68-607a0a8bcc0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2678a8c81807e3d76ba54bae150342076589b618
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344113"
---
# <a name="how-data-is-stored-for-outbound-edi-messages"></a><span data-ttu-id="87bec-102">送信 EDI メッセージのデータを格納する方法</span><span class="sxs-lookup"><span data-stu-id="87bec-102">How Data Is Stored for Outbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="87bec-103">送信インターチェンジの状態レポート エントリを生成するには、次を行います。</span><span class="sxs-lookup"><span data-stu-id="87bec-103">does the following to generate a status report entry for an outbound interchange:</span></span>  
  
1.  <span data-ttu-id="87bec-104">XML が EDI に送信される出力方向のメッセージの送信パイプライン、送信パイプラインは、ステータス レポートの次の値を使用してデータ ストアにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="87bec-104">When outbound message XML is sent to the EDI send pipeline, the send pipeline creates an entry in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="87bec-105">インターチェンジ状態エントリが処理済み に設定します。</span><span class="sxs-lookup"><span data-stu-id="87bec-105">Interchange status entry is set to Processed</span></span>  
  
    -   <span data-ttu-id="87bec-106">インターチェンジ確認状態エントリ (インターチェンジごとに 1 つ) が必要 に設定します。</span><span class="sxs-lookup"><span data-stu-id="87bec-106">Interchange ACK status entry (one per interchange) is set to Expected</span></span>  
  
    -   <span data-ttu-id="87bec-107">機能の確認状態エントリ (X12、EDIFACT のすべてのグループに 1 つではグループごとに 1 つ) が必要 に設定します。</span><span class="sxs-lookup"><span data-stu-id="87bec-107">Functional ACK status entries (one per group in X12, one for all groups in EDIFACT) are set to Expected</span></span>  
  
2.  <span data-ttu-id="87bec-108">インターチェンジの状態、インターチェンジ確認状態、および、機能、EDI 受信確認の更新プログラムを受信するパイプラインを取引先に EDI メッセージが送信され、取引先から受信確認が返された後、必要に応じて確認状態エントリを受理/一部受理/拒否します。</span><span class="sxs-lookup"><span data-stu-id="87bec-108">After the EDI message has been sent to the trading partner, and the acknowledgment has been returned from the trading partner, the EDI receive pipeline that receives the acknowledgment updates the Interchange status, the Interchange ACK status, and the Functional ACK status entries to Accepted/Partially Accepted/Rejected, as appropriate.</span></span>  
  
## <a name="data-stored-by-the-send-pipeline-for-outbound-interchanges"></a><span data-ttu-id="87bec-109">送信インターチェンジの送信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-109">Data Stored by the Send Pipeline for Outbound Interchanges</span></span>  
 <span data-ttu-id="87bec-110">送信パイプラインは、送信する各インターチェンジの状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="87bec-110">The send pipeline creates a record in the status report data store for each interchange that it sends.</span></span> <span data-ttu-id="87bec-111">エントリに必要なほとんどのデータは、インターチェンジ ヘッダー/トレーラー セグメント (ISA/IEA または UNB/UNZ) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="87bec-111">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="87bec-112">その他のデータは、送信ポートのプロパティから入手できます。</span><span class="sxs-lookup"><span data-stu-id="87bec-112">Other data is available from send port properties.</span></span> <span data-ttu-id="87bec-113">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87bec-113">The data stored includes:</span></span>  
  
-   <span data-ttu-id="87bec-114">レコードの種類 = インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="87bec-114">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="87bec-115">インターチェンジ方向 = 更新データ = 送信</span><span class="sxs-lookup"><span data-stu-id="87bec-115">Interchange Direction = Update Data = Send</span></span>  
  
-   <span data-ttu-id="87bec-116">インターチェンジの受信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-116">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="87bec-117">インターチェンジの送信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-117">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="87bec-118">インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-118">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="87bec-119">インターチェンジ時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-119">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="87bec-120">インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-120">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="87bec-121">インターチェンジの状態。処理/送信されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-121">Interchange Status: Processed/Sent.</span></span> <span data-ttu-id="87bec-122">送信パイプラインのインターチェンジを処理および配信の送信アダプターに渡したが正常に処理済み 状態を示します。</span><span class="sxs-lookup"><span data-stu-id="87bec-122">A status of Processed indicates that the send pipeline has successfully processed the interchange and handed it over to the send adapter for delivery.</span></span>  
  
-   <span data-ttu-id="87bec-123">インターチェンジ制御カウント (X12 でのグループ/メッセージそれぞれ) データを =</span><span class="sxs-lookup"><span data-stu-id="87bec-123">Interchange Control Count (Groups/Messages in X12 respectively) = Data</span></span>  
  
-   <span data-ttu-id="87bec-124">インターチェンジの送信ポートの ID データを =</span><span class="sxs-lookup"><span data-stu-id="87bec-124">Interchange Send Port ID = Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="87bec-125">送信インターチェンジへの応答で受信した各技術確認の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-125">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="87bec-126">受信パイプラインは、受信した各技術確認の状態レポート データ ストアでレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="87bec-126">The receive pipeline creates a record in the status report data store for each technical acknowledgment that it receives.</span></span> <span data-ttu-id="87bec-127">受信パイプラインは、状態レポートのデータ ストアに受信した各インターチェンジのレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="87bec-127">The receive pipeline creates a record of each interchange received in the status report data store.</span></span> <span data-ttu-id="87bec-128">取引先パートナーに送信されたインターチェンジへの応答として受信した各技術確認用のデータ ストアに 1 つの技術確認の状態レポート エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="87bec-128">creates one technical acknowledgment status report entry in the data store for each technical ACK received as a response to an interchange sent to a trading partner.</span></span> <span data-ttu-id="87bec-129">技術確認は、EDIFACT の場合、UCI セグメントのみで、X12 と CONTRL メッセージに TA1 です。</span><span class="sxs-lookup"><span data-stu-id="87bec-129">The technical acknowledge is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="87bec-130">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87bec-130">The data stored includes:</span></span>  
  
- <span data-ttu-id="87bec-131">レコードの種類 = インターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="87bec-131">Record Type = Interchange ACK Status</span></span>  
  
- <span data-ttu-id="87bec-132">インターチェンジ確認方向 = 送信 – 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-132">Interchange ACK Direction = Send – Update Data</span></span>  
  
- <span data-ttu-id="87bec-133">インターチェンジの受信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="87bec-133">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="87bec-134">インターチェンジの送信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="87bec-134">Interchange Sender = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="87bec-135">インターチェンジ日付 = 更新データ (X12 に必要な相関関係)</span><span class="sxs-lookup"><span data-stu-id="87bec-135">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
- <span data-ttu-id="87bec-136">インターチェンジ制御 ID = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="87bec-136">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="87bec-137">インターチェンジ確認状態 = 生成または該当なし\<注 0 参照\>-データを更新</span><span class="sxs-lookup"><span data-stu-id="87bec-137">Interchange ACK Status = Generated or Not Applicable \<Refer Note 0\> - Update Data</span></span>  
  
- <span data-ttu-id="87bec-138">インターチェンジ確認制御 ID = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="87bec-138">Interchange ACK Control ID= Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="87bec-139">インターチェンジ確認日付 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="87bec-139">Interchange ACK Date = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="87bec-140">インターチェンジ確認時刻 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="87bec-140">Interchange ACK Time = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="87bec-141">確認/アクション コード = 更新データ\<注 1 を参照してください\>(X12 TA104 edifact-uci4 から) \*。</span><span class="sxs-lookup"><span data-stu-id="87bec-141">ACK/Action Code = Update Data  \<refer note 1\> (from X12-TA104 or EDIFACT-UCI4)\*</span></span>  
  
- <span data-ttu-id="87bec-142">確認通知コード = 更新データ\<注 2 を参照\>(X12-TA105、EDIFACT には該当しません) から \*</span><span class="sxs-lookup"><span data-stu-id="87bec-142">ACK Note Code = Update Data \<Refer Note 2\> (from X12-TA105, not applicable for EDIFACT)\*</span></span>  
  
  <span data-ttu-id="87bec-143">次の確認/アクション コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-143">The following ACK/Action Codes are used:</span></span>  
  
|<span data-ttu-id="87bec-144">確認/アクション コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-144">Data in ACK/Action Code</span></span>|<span data-ttu-id="87bec-145">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="87bec-145">Error description for Reporting</span></span>|<span data-ttu-id="87bec-146">コメント (適用性)</span><span class="sxs-lookup"><span data-stu-id="87bec-146">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="87bec-147">A</span><span class="sxs-lookup"><span data-stu-id="87bec-147">A</span></span>|<span data-ttu-id="87bec-148">受理</span><span class="sxs-lookup"><span data-stu-id="87bec-148">Accepted</span></span>|<span data-ttu-id="87bec-149">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-149">X12</span></span>|  
|<span data-ttu-id="87bec-150">E</span><span class="sxs-lookup"><span data-stu-id="87bec-150">E</span></span>|<span data-ttu-id="87bec-151">受理、エラー検出</span><span class="sxs-lookup"><span data-stu-id="87bec-151">Accepted, errors noted</span></span>|<span data-ttu-id="87bec-152">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-152">X12</span></span>|  
|<span data-ttu-id="87bec-153">P</span><span class="sxs-lookup"><span data-stu-id="87bec-153">P</span></span>|<span data-ttu-id="87bec-154">一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-154">Partially Accepted</span></span>|<span data-ttu-id="87bec-155">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-155">X12</span></span>|  
|<span data-ttu-id="87bec-156">R</span><span class="sxs-lookup"><span data-stu-id="87bec-156">R</span></span>|<span data-ttu-id="87bec-157">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-157">Rejected</span></span>|<span data-ttu-id="87bec-158">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-158">X12</span></span>|  
|<span data-ttu-id="87bec-159">4</span><span class="sxs-lookup"><span data-stu-id="87bec-159">4</span></span>|<span data-ttu-id="87bec-160">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-160">Rejected</span></span>|<span data-ttu-id="87bec-161">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-161">EDIFACT</span></span>|  
|<span data-ttu-id="87bec-162">8</span><span class="sxs-lookup"><span data-stu-id="87bec-162">8</span></span>|<span data-ttu-id="87bec-163">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-163">Accepted/Partially Accepted</span></span>|<span data-ttu-id="87bec-164">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-164">EDIFACT</span></span>|  
  
 <span data-ttu-id="87bec-165">次の確認通知コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-165">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="87bec-166">確認通知コード (X12) でのデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-166">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="87bec-167">説明</span><span class="sxs-lookup"><span data-stu-id="87bec-167">Description</span></span>|  
|--------------------------------------|-----------------|  
|<span data-ttu-id="87bec-168">000</span><span class="sxs-lookup"><span data-stu-id="87bec-168">000</span></span>|<span data-ttu-id="87bec-169">成功</span><span class="sxs-lookup"><span data-stu-id="87bec-169">Success</span></span>|  
|<span data-ttu-id="87bec-170">001</span><span class="sxs-lookup"><span data-stu-id="87bec-170">001</span></span>|<span data-ttu-id="87bec-171">インターチェンジ制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-171">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="87bec-172">002</span><span class="sxs-lookup"><span data-stu-id="87bec-172">002</span></span>|<span data-ttu-id="87bec-173">標準がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-173">Standard not supported</span></span>|  
|<span data-ttu-id="87bec-174">003</span><span class="sxs-lookup"><span data-stu-id="87bec-174">003</span></span>|<span data-ttu-id="87bec-175">バージョンのコントロールはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-175">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="87bec-176">004</span><span class="sxs-lookup"><span data-stu-id="87bec-176">004</span></span>|<span data-ttu-id="87bec-177">セグメント終端記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-177">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="87bec-178">005</span><span class="sxs-lookup"><span data-stu-id="87bec-178">005</span></span>|<span data-ttu-id="87bec-179">送信者の無効なインターチェンジ ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="87bec-179">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="87bec-180">006</span><span class="sxs-lookup"><span data-stu-id="87bec-180">006</span></span>|<span data-ttu-id="87bec-181">無効なインターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-181">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="87bec-182">007</span><span class="sxs-lookup"><span data-stu-id="87bec-182">007</span></span>|<span data-ttu-id="87bec-183">受信側の無効なインターチェンジ ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="87bec-183">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="87bec-184">008</span><span class="sxs-lookup"><span data-stu-id="87bec-184">008</span></span>|<span data-ttu-id="87bec-185">無効なインターチェンジ受信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-185">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="87bec-186">009</span><span class="sxs-lookup"><span data-stu-id="87bec-186">009</span></span>|<span data-ttu-id="87bec-187">不明なインターチェンジ受信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-187">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="87bec-188">010</span><span class="sxs-lookup"><span data-stu-id="87bec-188">010</span></span>|<span data-ttu-id="87bec-189">無効な認証情報修飾子の値</span><span class="sxs-lookup"><span data-stu-id="87bec-189">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="87bec-190">011</span><span class="sxs-lookup"><span data-stu-id="87bec-190">011</span></span>|<span data-ttu-id="87bec-191">無効な認証情報の値</span><span class="sxs-lookup"><span data-stu-id="87bec-191">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="87bec-192">012</span><span class="sxs-lookup"><span data-stu-id="87bec-192">012</span></span>|<span data-ttu-id="87bec-193">無効なセキュリティ情報修飾子の値</span><span class="sxs-lookup"><span data-stu-id="87bec-193">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="87bec-194">013</span><span class="sxs-lookup"><span data-stu-id="87bec-194">013</span></span>|<span data-ttu-id="87bec-195">無効なセキュリティ情報の値</span><span class="sxs-lookup"><span data-stu-id="87bec-195">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="87bec-196">014</span><span class="sxs-lookup"><span data-stu-id="87bec-196">014</span></span>|<span data-ttu-id="87bec-197">無効なインターチェンジ日付の値</span><span class="sxs-lookup"><span data-stu-id="87bec-197">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="87bec-198">015</span><span class="sxs-lookup"><span data-stu-id="87bec-198">015</span></span>|<span data-ttu-id="87bec-199">無効なインターチェンジ時刻の値</span><span class="sxs-lookup"><span data-stu-id="87bec-199">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="87bec-200">016</span><span class="sxs-lookup"><span data-stu-id="87bec-200">016</span></span>|<span data-ttu-id="87bec-201">無効なインターチェンジ標準識別子の値</span><span class="sxs-lookup"><span data-stu-id="87bec-201">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="87bec-202">017</span><span class="sxs-lookup"><span data-stu-id="87bec-202">017</span></span>|<span data-ttu-id="87bec-203">無効なインターチェンジ バージョン ID の値</span><span class="sxs-lookup"><span data-stu-id="87bec-203">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="87bec-204">018</span><span class="sxs-lookup"><span data-stu-id="87bec-204">018</span></span>|<span data-ttu-id="87bec-205">無効なインターチェンジ制御番号の値</span><span class="sxs-lookup"><span data-stu-id="87bec-205">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="87bec-206">019</span><span class="sxs-lookup"><span data-stu-id="87bec-206">019</span></span>|<span data-ttu-id="87bec-207">無効な確認要求の値</span><span class="sxs-lookup"><span data-stu-id="87bec-207">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="87bec-208">020</span><span class="sxs-lookup"><span data-stu-id="87bec-208">020</span></span>|<span data-ttu-id="87bec-209">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="87bec-209">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="87bec-210">021</span><span class="sxs-lookup"><span data-stu-id="87bec-210">021</span></span>|<span data-ttu-id="87bec-211">含まれているグループの値の数が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-211">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="87bec-212">022</span><span class="sxs-lookup"><span data-stu-id="87bec-212">022</span></span>|<span data-ttu-id="87bec-213">制御構造が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-213">Invalid Control Structure</span></span>|  
|<span data-ttu-id="87bec-214">023</span><span class="sxs-lookup"><span data-stu-id="87bec-214">023</span></span>|<span data-ttu-id="87bec-215">不適切な最後のファイル</span><span class="sxs-lookup"><span data-stu-id="87bec-215">Improper End-of-File</span></span>|  
|<span data-ttu-id="87bec-216">024</span><span class="sxs-lookup"><span data-stu-id="87bec-216">024</span></span>|<span data-ttu-id="87bec-217">インターチェンジの内容が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-217">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="87bec-218">025</span><span class="sxs-lookup"><span data-stu-id="87bec-218">025</span></span>|<span data-ttu-id="87bec-219">インターチェンジ制御番号が重複しています</span><span class="sxs-lookup"><span data-stu-id="87bec-219">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="87bec-220">026</span><span class="sxs-lookup"><span data-stu-id="87bec-220">026</span></span>|<span data-ttu-id="87bec-221">データ要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-221">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="87bec-222">027</span><span class="sxs-lookup"><span data-stu-id="87bec-222">027</span></span>|<span data-ttu-id="87bec-223">コンポーネント要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-223">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="87bec-224">028</span><span class="sxs-lookup"><span data-stu-id="87bec-224">028</span></span>|<span data-ttu-id="87bec-225">遅延配信要求の無効な配信日</span><span class="sxs-lookup"><span data-stu-id="87bec-225">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="87bec-226">029</span><span class="sxs-lookup"><span data-stu-id="87bec-226">029</span></span>|<span data-ttu-id="87bec-227">遅延配信要求の無効な配信時刻</span><span class="sxs-lookup"><span data-stu-id="87bec-227">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="87bec-228">030</span><span class="sxs-lookup"><span data-stu-id="87bec-228">030</span></span>|<span data-ttu-id="87bec-229">遅延配信要求に無効な配信時のコード</span><span class="sxs-lookup"><span data-stu-id="87bec-229">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="87bec-230">031</span><span class="sxs-lookup"><span data-stu-id="87bec-230">031</span></span>|<span data-ttu-id="87bec-231">サービスの評価が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-231">Invalid Grade of Service</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a><span data-ttu-id="87bec-232">送信インターチェンジへの応答で受信した各技術確認の受信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-232">Data Updated by the Receive Pipeline for Each Technical Acknowledgment Received in Response to an Outbound Interchange</span></span>  
 <span data-ttu-id="87bec-233">受信パイプラインが受信した各技術確認の関連する送信インターチェンジの状態レポート エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="87bec-233">For each technical acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="87bec-234">EDI 逆アセンブラーは UCI および TA1 セグメントに、受信確認の内のデータを次のように使用して、データ ストアでレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="87bec-234">The EDI Disassembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="87bec-235">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="87bec-235">Fields in ACK</span></span>|<span data-ttu-id="87bec-236">データ ストア内のフィールド</span><span class="sxs-lookup"><span data-stu-id="87bec-236">Fields in Data store</span></span>|<span data-ttu-id="87bec-237">解説</span><span class="sxs-lookup"><span data-stu-id="87bec-237">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="87bec-238">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-238">Interchange Sender ID</span></span>|<span data-ttu-id="87bec-239">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="87bec-239">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="87bec-240">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-240">Interchange Receiver ID</span></span>|<span data-ttu-id="87bec-241">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="87bec-241">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="87bec-242">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="87bec-242">Interchange Date</span></span>|-|  
|<span data-ttu-id="87bec-243">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="87bec-243">Interchange Control Number</span></span>|<span data-ttu-id="87bec-244">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-244">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="87bec-245">インターチェンジ方向 = 送信</span><span class="sxs-lookup"><span data-stu-id="87bec-245">Interchange Direction = Send</span></span>|<span data-ttu-id="87bec-246">保存されたバッチ シナリオの一意性に必要です。</span><span class="sxs-lookup"><span data-stu-id="87bec-246">Required in preserved batch scenario for uniqueness</span></span>|  
|<span data-ttu-id="87bec-247">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="87bec-247">Record Type</span></span>|<span data-ttu-id="87bec-248">インターチェンジの状態とインターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="87bec-248">Interchange Status and Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="87bec-249">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87bec-249">The data stored includes:</span></span>  
  
- <span data-ttu-id="87bec-250">インターチェンジ確認方向 = 受信 – 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-250">Interchange ACK Direction = Receive – Existing Data</span></span>  
  
- <span data-ttu-id="87bec-251">インターチェンジ確認状態 = 受信</span><span class="sxs-lookup"><span data-stu-id="87bec-251">Interchange ACK Status = Received</span></span>  
  
- <span data-ttu-id="87bec-252">インターチェンジの受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-252">Interchange Receiver = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-253">インターチェンジの送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-253">Interchange Sender = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-254">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-254">Interchange Date = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-255">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-255">Interchange Control ID = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-256">インターチェンジ確認制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-256">Interchange ACK Control ID= Update Data</span></span>  
  
- <span data-ttu-id="87bec-257">インターチェンジ確認日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-257">Interchange ACK Date = Update Data</span></span>  
  
- <span data-ttu-id="87bec-258">インターチェンジ確認時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-258">Interchange ACK Time = Update Data</span></span>  
  
- <span data-ttu-id="87bec-259">確認/アクション コード = 更新データ (X12 TA104 edifact-uci4 から) \*\<注 1 を参照してください。\></span><span class="sxs-lookup"><span data-stu-id="87bec-259">ACK/Action Code = Update Data (from X12-TA104 or EDIFACT-UCI4)\* \<Refer Note 1\></span></span>  
  
- <span data-ttu-id="87bec-260">確認通知コード 2 = 更新データ (X12 TA105 から edifact と) \*\<注 2 を参照\></span><span class="sxs-lookup"><span data-stu-id="87bec-260">ACK Note Code 2 = Update Data (from X12-TA105 and not valued for EDIFACT)\* \<Refer Note 2\></span></span>  
  
  <span data-ttu-id="87bec-261">X12 ACK からのデータ: TA1 104 または EDIFACT UCI4 は、次のようにマップするのには。</span><span class="sxs-lookup"><span data-stu-id="87bec-261">The data from the ACK X12:TA1-104 or EDIFACT UCI4 is to be mapped as follows:</span></span>  
  
|<span data-ttu-id="87bec-262">確認/アクション コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-262">Data in ACK/Action Code</span></span>|<span data-ttu-id="87bec-263">状態レポート用のマップ</span><span class="sxs-lookup"><span data-stu-id="87bec-263">Mapped for Status Reporting</span></span>|<span data-ttu-id="87bec-264">解説</span><span class="sxs-lookup"><span data-stu-id="87bec-264">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="87bec-265">A</span><span class="sxs-lookup"><span data-stu-id="87bec-265">A</span></span>|<span data-ttu-id="87bec-266">受理</span><span class="sxs-lookup"><span data-stu-id="87bec-266">Accepted</span></span>|<span data-ttu-id="87bec-267">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-267">X12</span></span>|  
|<span data-ttu-id="87bec-268">P</span><span class="sxs-lookup"><span data-stu-id="87bec-268">P</span></span>|<span data-ttu-id="87bec-269">一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-269">Partially Accepted</span></span>|<span data-ttu-id="87bec-270">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-270">X12</span></span>|  
|<span data-ttu-id="87bec-271">R、M、W、X</span><span class="sxs-lookup"><span data-stu-id="87bec-271">R, M, W, X</span></span>|<span data-ttu-id="87bec-272">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-272">Rejected</span></span>|<span data-ttu-id="87bec-273">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-273">X12</span></span>|  
|<span data-ttu-id="87bec-274">E</span><span class="sxs-lookup"><span data-stu-id="87bec-274">E</span></span>|<span data-ttu-id="87bec-275">エラーありで受理</span><span class="sxs-lookup"><span data-stu-id="87bec-275">Accepted with errors</span></span>|<span data-ttu-id="87bec-276">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-276">X12</span></span>|  
|<span data-ttu-id="87bec-277">4</span><span class="sxs-lookup"><span data-stu-id="87bec-277">4</span></span>|<span data-ttu-id="87bec-278">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-278">Rejected</span></span>|<span data-ttu-id="87bec-279">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-279">EDIFACT</span></span>|  
|<span data-ttu-id="87bec-280">7, 8</span><span class="sxs-lookup"><span data-stu-id="87bec-280">7, 8</span></span>|<span data-ttu-id="87bec-281">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-281">Accepted/Partially Accepted</span></span>|<span data-ttu-id="87bec-282">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-282">EDIFACT</span></span>|  
  
 <span data-ttu-id="87bec-283">次の確認通知コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-283">The following ACK Note Codes are used:</span></span>  
  
|<span data-ttu-id="87bec-284">確認通知コード (X12) でのデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-284">Data in ACK Note Code (in X12)</span></span>|<span data-ttu-id="87bec-285">状態レポート用のマップ</span><span class="sxs-lookup"><span data-stu-id="87bec-285">Mapped for Status Reporting</span></span>|  
|--------------------------------------|---------------------------------|  
|<span data-ttu-id="87bec-286">000</span><span class="sxs-lookup"><span data-stu-id="87bec-286">000</span></span>|<span data-ttu-id="87bec-287">成功</span><span class="sxs-lookup"><span data-stu-id="87bec-287">Success</span></span>|  
|<span data-ttu-id="87bec-288">001</span><span class="sxs-lookup"><span data-stu-id="87bec-288">001</span></span>|<span data-ttu-id="87bec-289">インターチェンジ制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-289">Interchange Control Number mismatch</span></span>|  
|<span data-ttu-id="87bec-290">002</span><span class="sxs-lookup"><span data-stu-id="87bec-290">002</span></span>|<span data-ttu-id="87bec-291">標準がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-291">Standard not supported</span></span>|  
|<span data-ttu-id="87bec-292">003</span><span class="sxs-lookup"><span data-stu-id="87bec-292">003</span></span>|<span data-ttu-id="87bec-293">バージョンのコントロールはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-293">Version of the Controls Not Supported</span></span>|  
|<span data-ttu-id="87bec-294">004</span><span class="sxs-lookup"><span data-stu-id="87bec-294">004</span></span>|<span data-ttu-id="87bec-295">セグメント終端記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-295">Segment Terminator is Invalid</span></span>|  
|<span data-ttu-id="87bec-296">005</span><span class="sxs-lookup"><span data-stu-id="87bec-296">005</span></span>|<span data-ttu-id="87bec-297">送信者の無効なインターチェンジ ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="87bec-297">Invalid Interchange ID Qualifier for Sender</span></span>|  
|<span data-ttu-id="87bec-298">006</span><span class="sxs-lookup"><span data-stu-id="87bec-298">006</span></span>|<span data-ttu-id="87bec-299">無効なインターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-299">Invalid Interchange Sender ID</span></span>|  
|<span data-ttu-id="87bec-300">007</span><span class="sxs-lookup"><span data-stu-id="87bec-300">007</span></span>|<span data-ttu-id="87bec-301">受信側の無効なインターチェンジ ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="87bec-301">Invalid Interchange ID Qualifier for Receiver</span></span>|  
|<span data-ttu-id="87bec-302">008</span><span class="sxs-lookup"><span data-stu-id="87bec-302">008</span></span>|<span data-ttu-id="87bec-303">無効なインターチェンジ受信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-303">Invalid Interchange Receiver ID</span></span>|  
|<span data-ttu-id="87bec-304">009</span><span class="sxs-lookup"><span data-stu-id="87bec-304">009</span></span>|<span data-ttu-id="87bec-305">不明なインターチェンジ受信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-305">Unknown Interchange Receiver ID</span></span>|  
|<span data-ttu-id="87bec-306">010</span><span class="sxs-lookup"><span data-stu-id="87bec-306">010</span></span>|<span data-ttu-id="87bec-307">無効な認証情報修飾子の値</span><span class="sxs-lookup"><span data-stu-id="87bec-307">Invalid Authorization Information Qualifier Value</span></span>|  
|<span data-ttu-id="87bec-308">011</span><span class="sxs-lookup"><span data-stu-id="87bec-308">011</span></span>|<span data-ttu-id="87bec-309">無効な認証情報の値</span><span class="sxs-lookup"><span data-stu-id="87bec-309">Invalid Authorization Information Value</span></span>|  
|<span data-ttu-id="87bec-310">012</span><span class="sxs-lookup"><span data-stu-id="87bec-310">012</span></span>|<span data-ttu-id="87bec-311">無効なセキュリティ情報修飾子の値</span><span class="sxs-lookup"><span data-stu-id="87bec-311">Invalid Security Information Qualifier Value</span></span>|  
|<span data-ttu-id="87bec-312">013</span><span class="sxs-lookup"><span data-stu-id="87bec-312">013</span></span>|<span data-ttu-id="87bec-313">無効なセキュリティ情報の値</span><span class="sxs-lookup"><span data-stu-id="87bec-313">Invalid Security Information Value</span></span>|  
|<span data-ttu-id="87bec-314">014</span><span class="sxs-lookup"><span data-stu-id="87bec-314">014</span></span>|<span data-ttu-id="87bec-315">無効なインターチェンジ日付の値</span><span class="sxs-lookup"><span data-stu-id="87bec-315">Invalid Interchange Date Value</span></span>|  
|<span data-ttu-id="87bec-316">015</span><span class="sxs-lookup"><span data-stu-id="87bec-316">015</span></span>|<span data-ttu-id="87bec-317">無効なインターチェンジ時刻の値</span><span class="sxs-lookup"><span data-stu-id="87bec-317">Invalid Interchange Time Value</span></span>|  
|<span data-ttu-id="87bec-318">016</span><span class="sxs-lookup"><span data-stu-id="87bec-318">016</span></span>|<span data-ttu-id="87bec-319">無効なインターチェンジ標準識別子の値</span><span class="sxs-lookup"><span data-stu-id="87bec-319">Invalid Interchange Standards Identifier Value</span></span>|  
|<span data-ttu-id="87bec-320">017</span><span class="sxs-lookup"><span data-stu-id="87bec-320">017</span></span>|<span data-ttu-id="87bec-321">無効なインターチェンジ バージョン ID の値</span><span class="sxs-lookup"><span data-stu-id="87bec-321">Invalid Interchange Version ID Value</span></span>|  
|<span data-ttu-id="87bec-322">018</span><span class="sxs-lookup"><span data-stu-id="87bec-322">018</span></span>|<span data-ttu-id="87bec-323">無効なインターチェンジ制御番号の値</span><span class="sxs-lookup"><span data-stu-id="87bec-323">Invalid Interchange Control Number Value</span></span>|  
|<span data-ttu-id="87bec-324">019</span><span class="sxs-lookup"><span data-stu-id="87bec-324">019</span></span>|<span data-ttu-id="87bec-325">無効な確認要求の値</span><span class="sxs-lookup"><span data-stu-id="87bec-325">Invalid Acknowledgment Requested Value</span></span>|  
|<span data-ttu-id="87bec-326">020</span><span class="sxs-lookup"><span data-stu-id="87bec-326">020</span></span>|<span data-ttu-id="87bec-327">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="87bec-327">Invalid Test Indicator Value</span></span>|  
|<span data-ttu-id="87bec-328">021</span><span class="sxs-lookup"><span data-stu-id="87bec-328">021</span></span>|<span data-ttu-id="87bec-329">含まれているグループの値の数が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-329">Invalid Number of Included Groups Value</span></span>|  
|<span data-ttu-id="87bec-330">022</span><span class="sxs-lookup"><span data-stu-id="87bec-330">022</span></span>|<span data-ttu-id="87bec-331">制御構造が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-331">Invalid Control Structure</span></span>|  
|<span data-ttu-id="87bec-332">023</span><span class="sxs-lookup"><span data-stu-id="87bec-332">023</span></span>|<span data-ttu-id="87bec-333">不適切な最後のファイル</span><span class="sxs-lookup"><span data-stu-id="87bec-333">Improper End-of-File</span></span>|  
|<span data-ttu-id="87bec-334">024</span><span class="sxs-lookup"><span data-stu-id="87bec-334">024</span></span>|<span data-ttu-id="87bec-335">インターチェンジの内容が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-335">Invalid Interchange Content</span></span>|  
|<span data-ttu-id="87bec-336">025</span><span class="sxs-lookup"><span data-stu-id="87bec-336">025</span></span>|<span data-ttu-id="87bec-337">インターチェンジ制御番号が重複しています</span><span class="sxs-lookup"><span data-stu-id="87bec-337">Duplicate Interchange Control Number</span></span>|  
|<span data-ttu-id="87bec-338">026</span><span class="sxs-lookup"><span data-stu-id="87bec-338">026</span></span>|<span data-ttu-id="87bec-339">データ要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-339">Invalid Data Element Separator</span></span>|  
|<span data-ttu-id="87bec-340">027</span><span class="sxs-lookup"><span data-stu-id="87bec-340">027</span></span>|<span data-ttu-id="87bec-341">コンポーネント要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-341">Invalid Component Element Separator</span></span>|  
|<span data-ttu-id="87bec-342">028</span><span class="sxs-lookup"><span data-stu-id="87bec-342">028</span></span>|<span data-ttu-id="87bec-343">遅延配信要求の無効な配信日</span><span class="sxs-lookup"><span data-stu-id="87bec-343">Invalid Delivery Date in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="87bec-344">029</span><span class="sxs-lookup"><span data-stu-id="87bec-344">029</span></span>|<span data-ttu-id="87bec-345">遅延配信要求の無効な配信時刻</span><span class="sxs-lookup"><span data-stu-id="87bec-345">Invalid Delivery Time in Deferred Delivery Request</span></span>|  
|<span data-ttu-id="87bec-346">030</span><span class="sxs-lookup"><span data-stu-id="87bec-346">030</span></span>|<span data-ttu-id="87bec-347">遅延配信要求に無効な配信時のコード</span><span class="sxs-lookup"><span data-stu-id="87bec-347">Invalid Delivery Time Code in Deferred Delivery  Request</span></span>|  
|<span data-ttu-id="87bec-348">031</span><span class="sxs-lookup"><span data-stu-id="87bec-348">031</span></span>|<span data-ttu-id="87bec-349">サービスの評価が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-349">Invalid Grade of Service</span></span>|  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outbound-interchanges"></a><span data-ttu-id="87bec-350">送信インターチェンジへの応答で受信した各機能確認の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-350">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outbound Interchanges</span></span>  
 <span data-ttu-id="87bec-351">受信パイプラインは、受信した各機能確認の状態レポート データ ストアでレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="87bec-351">The receive pipeline creates a record in the status report data store for each functional acknowledgment that it receives.</span></span>  <span data-ttu-id="87bec-352">技術確認は、997 のメッセージを X12 と完全な CONTRL EDIFACT です。</span><span class="sxs-lookup"><span data-stu-id="87bec-352">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="87bec-353">グループごとに 1 つのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-353">One entry per group will to be created.</span></span> <span data-ttu-id="87bec-354">インターチェンジとグループ ヘッダーからのデータは、このエントリの作成中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-354">Data from the interchange and group headers is used while making this entry.</span></span> <span data-ttu-id="87bec-355">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87bec-355">The data stored includes:</span></span>  
  
- <span data-ttu-id="87bec-356">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="87bec-356">Record Type = Functional ACK Status</span></span>  
  
- <span data-ttu-id="87bec-357">機能確認方向 = 送信</span><span class="sxs-lookup"><span data-stu-id="87bec-357">Functional ACK Direction = Send</span></span>  
  
- <span data-ttu-id="87bec-358">機能確認状態 = \<Generated または該当なし、注 1 を参照してください。\></span><span class="sxs-lookup"><span data-stu-id="87bec-358">Functional ACK Status = \<Generated or Not Applicable, refer note 1\></span></span>  
  
- <span data-ttu-id="87bec-359">インターチェンジの受信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="87bec-359">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="87bec-360">インターチェンジの送信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="87bec-360">Interchange Sender = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="87bec-361">インターチェンジ日付 = 更新データ (X12 に必要な相関関係)</span><span class="sxs-lookup"><span data-stu-id="87bec-361">Interchange Date = Update Data (required for X12 correlation)</span></span>  
  
- <span data-ttu-id="87bec-362">インターチェンジ制御 ID = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="87bec-362">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
- <span data-ttu-id="87bec-363">グループ制御番号 = 更新データ (EDIFACT はオプション' と x12 の場合に必要な相関関係)</span><span class="sxs-lookup"><span data-stu-id="87bec-363">Group Control Number = Update Data (‘optional for EDIFACT’ and required for X12 correlation)</span></span>  
  
- <span data-ttu-id="87bec-364">機能 ID コード = 更新データ (gs01/ung01)</span><span class="sxs-lookup"><span data-stu-id="87bec-364">Functional ID Code = Update Data (GS01/UNG01)</span></span>  
  
- <span data-ttu-id="87bec-365">トランザクション セットの数 = 更新データ (une1/unz1)</span><span class="sxs-lookup"><span data-stu-id="87bec-365">Count of Transaction Sets = Update Data (UNE1/UNZ1)</span></span>  
  
- <span data-ttu-id="87bec-366">機能確認インターチェンジ制御 ID = 値なし – 送信側によって適用されます</span><span class="sxs-lookup"><span data-stu-id="87bec-366">Functional ACK Interchange Control ID= Not value – will be applied by send side</span></span>  
  
- <span data-ttu-id="87bec-367">機能確認インターチェンジ日付 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="87bec-367">Functional ACK Interchange Date = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="87bec-368">機能確認インターチェンジ時刻 = 値なし – 送信側によって適用</span><span class="sxs-lookup"><span data-stu-id="87bec-368">Functional ACK Interchange Time = Not valued – will be applied by send side</span></span>  
  
- <span data-ttu-id="87bec-369">数のトランザクション セット受信 = 更新データ (X12 AK903 および EDIFACT エンコードのエンジンで計算)</span><span class="sxs-lookup"><span data-stu-id="87bec-369">Count of Transaction Sets Received = Update Data (X12-AK903 and computed by Engine for EDIFACT encoding)</span></span>  
  
- <span data-ttu-id="87bec-370">カウントの受理されたトランザクション セット = 更新データ (X12 AK904 および EDIFACT のエンジンのエンジンで計算)</span><span class="sxs-lookup"><span data-stu-id="87bec-370">Count of Transaction Sets Accepted = Update Data (X12-AK904 and computed by Engine for EDIFACT engine)</span></span>  
  
- <span data-ttu-id="87bec-371">確認/アクション コード = 更新データ\<注 2 を参照してください\>(X12 AK901 edifact-uci4 から) \*。</span><span class="sxs-lookup"><span data-stu-id="87bec-371">ACK/Action Code = Update Data  \<refer note 2\> (from X12-AK901 or EDIFACT-UCI4)\*</span></span>  
  
- <span data-ttu-id="87bec-372">エラー/構文エラー コード = 更新データ (X12-AK905、EDIFACT UCI5) 注 3</span><span class="sxs-lookup"><span data-stu-id="87bec-372">Error/Syntax Error Code  = Update Data (X12-AK905, EDIFACT UCI5) Note 3</span></span>  
  
- <span data-ttu-id="87bec-373">追加の X12 確認エラー コード 2 = 更新データ (X12 AK906)</span><span class="sxs-lookup"><span data-stu-id="87bec-373">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
- <span data-ttu-id="87bec-374">追加の X12 確認エラー コード 3 = 更新データ (X12 AK907)</span><span class="sxs-lookup"><span data-stu-id="87bec-374">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
- <span data-ttu-id="87bec-375">追加の X12 確認エラー コード 4 = 更新データ (X12 AK908)</span><span class="sxs-lookup"><span data-stu-id="87bec-375">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
- <span data-ttu-id="87bec-376">追加の X12 確認エラー コード 5 = 更新データ (X12 AK909)</span><span class="sxs-lookup"><span data-stu-id="87bec-376">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
  <span data-ttu-id="87bec-377">次の確認/アクション コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-377">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="87bec-378">確認/アクション コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-378">Data in ACK/Action Code</span></span>|<span data-ttu-id="87bec-379">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="87bec-379">Error description for Reporting</span></span>|<span data-ttu-id="87bec-380">コメント (適用性)</span><span class="sxs-lookup"><span data-stu-id="87bec-380">Comment (applicability)</span></span>|  
|------------------------------|-------------------------------------|-------------------------------|  
|<span data-ttu-id="87bec-381">A</span><span class="sxs-lookup"><span data-stu-id="87bec-381">A</span></span>|<span data-ttu-id="87bec-382">受理</span><span class="sxs-lookup"><span data-stu-id="87bec-382">Accepted</span></span>|<span data-ttu-id="87bec-383">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-383">X12</span></span>|  
|<span data-ttu-id="87bec-384">E</span><span class="sxs-lookup"><span data-stu-id="87bec-384">E</span></span>|<span data-ttu-id="87bec-385">エラーありで受理</span><span class="sxs-lookup"><span data-stu-id="87bec-385">Accepted  with errors</span></span>|<span data-ttu-id="87bec-386">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-386">X12</span></span>|  
|<span data-ttu-id="87bec-387">P</span><span class="sxs-lookup"><span data-stu-id="87bec-387">P</span></span>|<span data-ttu-id="87bec-388">一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-388">Partially Accepted</span></span>|<span data-ttu-id="87bec-389">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-389">X12</span></span>|  
|<span data-ttu-id="87bec-390">R</span><span class="sxs-lookup"><span data-stu-id="87bec-390">R</span></span>|<span data-ttu-id="87bec-391">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-391">Rejected</span></span>|<span data-ttu-id="87bec-392">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-392">X12</span></span>|  
|<span data-ttu-id="87bec-393">4</span><span class="sxs-lookup"><span data-stu-id="87bec-393">4</span></span>|<span data-ttu-id="87bec-394">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-394">Rejected</span></span>|<span data-ttu-id="87bec-395">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-395">EDIFACT</span></span>|  
|<span data-ttu-id="87bec-396">7</span><span class="sxs-lookup"><span data-stu-id="87bec-396">7</span></span>|<span data-ttu-id="87bec-397">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-397">Accepted/Partially Accepted</span></span>|<span data-ttu-id="87bec-398">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-398">EDIFACT</span></span>|  
  
 <span data-ttu-id="87bec-399">次のエラー/構文エラー コードは、EDIFACT のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-399">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="87bec-400">エラー/構文エラー コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-400">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="87bec-401">(EDIFACT に適用)</span><span class="sxs-lookup"><span data-stu-id="87bec-401">(applicable to EDIFACT)</span></span>|<span data-ttu-id="87bec-402">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="87bec-402">Error Description for reporting</span></span>|  
|--------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="87bec-403">2</span><span class="sxs-lookup"><span data-stu-id="87bec-403">2</span></span>|<span data-ttu-id="87bec-404">構文のバージョンまたはレベル サポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-404">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="87bec-405">7</span><span class="sxs-lookup"><span data-stu-id="87bec-405">7</span></span>|<span data-ttu-id="87bec-406">インターチェンジの受信者の実際の受信者</span><span class="sxs-lookup"><span data-stu-id="87bec-406">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="87bec-407">12</span><span class="sxs-lookup"><span data-stu-id="87bec-407">12</span></span>|<span data-ttu-id="87bec-408">値が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-408">Invalid value</span></span>|  
|<span data-ttu-id="87bec-409">13</span><span class="sxs-lookup"><span data-stu-id="87bec-409">13</span></span>|<span data-ttu-id="87bec-410">Missing</span><span class="sxs-lookup"><span data-stu-id="87bec-410">Missing</span></span>|  
|<span data-ttu-id="87bec-411">14</span><span class="sxs-lookup"><span data-stu-id="87bec-411">14</span></span>|<span data-ttu-id="87bec-412">値がこの位置でサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-412">Value not supported in this position</span></span>|  
|<span data-ttu-id="87bec-413">15</span><span class="sxs-lookup"><span data-stu-id="87bec-413">15</span></span>|<span data-ttu-id="87bec-414">この位置でサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-414">Not supported in this position</span></span>|  
|<span data-ttu-id="87bec-415">16</span><span class="sxs-lookup"><span data-stu-id="87bec-415">16</span></span>|<span data-ttu-id="87bec-416">構成要素が多すぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-416">Too many constituents</span></span>|  
|<span data-ttu-id="87bec-417">17</span><span class="sxs-lookup"><span data-stu-id="87bec-417">17</span></span>|<span data-ttu-id="87bec-418">契約</span><span class="sxs-lookup"><span data-stu-id="87bec-418">No agreement</span></span>|  
|<span data-ttu-id="87bec-419">18</span><span class="sxs-lookup"><span data-stu-id="87bec-419">18</span></span>|<span data-ttu-id="87bec-420">特定できないエラー</span><span class="sxs-lookup"><span data-stu-id="87bec-420">Unspecified error</span></span>|  
|<span data-ttu-id="87bec-421">19</span><span class="sxs-lookup"><span data-stu-id="87bec-421">19</span></span>|<span data-ttu-id="87bec-422">無効な 10 進表記</span><span class="sxs-lookup"><span data-stu-id="87bec-422">Invalid decimal notation</span></span>|  
|<span data-ttu-id="87bec-423">20</span><span class="sxs-lookup"><span data-stu-id="87bec-423">20</span></span>|<span data-ttu-id="87bec-424">サービス文字として無効な文字</span><span class="sxs-lookup"><span data-stu-id="87bec-424">Character invalid as service character</span></span>|  
|<span data-ttu-id="87bec-425">21</span><span class="sxs-lookup"><span data-stu-id="87bec-425">21</span></span>|<span data-ttu-id="87bec-426">無効な文字</span><span class="sxs-lookup"><span data-stu-id="87bec-426">Invalid character(s)</span></span>|  
|<span data-ttu-id="87bec-427">22</span><span class="sxs-lookup"><span data-stu-id="87bec-427">22</span></span>|<span data-ttu-id="87bec-428">サービスの無効な文字</span><span class="sxs-lookup"><span data-stu-id="87bec-428">Invalid service character(s)</span></span>|  
|<span data-ttu-id="87bec-429">23</span><span class="sxs-lookup"><span data-stu-id="87bec-429">23</span></span>|<span data-ttu-id="87bec-430">不明なインターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="87bec-430">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="87bec-431">24</span><span class="sxs-lookup"><span data-stu-id="87bec-431">24</span></span>|<span data-ttu-id="87bec-432">古すぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-432">Too old</span></span>|  
|<span data-ttu-id="87bec-433">25</span><span class="sxs-lookup"><span data-stu-id="87bec-433">25</span></span>|<span data-ttu-id="87bec-434">テスト インジケーターがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-434">Test indicator not supported</span></span>|  
|<span data-ttu-id="87bec-435">26</span><span class="sxs-lookup"><span data-stu-id="87bec-435">26</span></span>|<span data-ttu-id="87bec-436">重複が検出されました</span><span class="sxs-lookup"><span data-stu-id="87bec-436">Duplicate detected</span></span>|  
|<span data-ttu-id="87bec-437">27</span><span class="sxs-lookup"><span data-stu-id="87bec-437">27</span></span>|<span data-ttu-id="87bec-438">セキュリティ関数がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-438">Security function not supported</span></span>|  
|<span data-ttu-id="87bec-439">28</span><span class="sxs-lookup"><span data-stu-id="87bec-439">28</span></span>|<span data-ttu-id="87bec-440">参照が一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-440">References do not match</span></span>|  
|<span data-ttu-id="87bec-441">29</span><span class="sxs-lookup"><span data-stu-id="87bec-441">29</span></span>|<span data-ttu-id="87bec-442">コントロールの数が、受信したインスタンスの数と一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-442">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="87bec-443">30</span><span class="sxs-lookup"><span data-stu-id="87bec-443">30</span></span>|<span data-ttu-id="87bec-444">グループとメッセージ/パッケージの混在</span><span class="sxs-lookup"><span data-stu-id="87bec-444">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="87bec-445">31</span><span class="sxs-lookup"><span data-stu-id="87bec-445">31</span></span>|<span data-ttu-id="87bec-446">グループ内の 1 つ以上のメッセージ型</span><span class="sxs-lookup"><span data-stu-id="87bec-446">More than one message type in group</span></span>|  
|<span data-ttu-id="87bec-447">32</span><span class="sxs-lookup"><span data-stu-id="87bec-447">32</span></span>|<span data-ttu-id="87bec-448">下位レベルが空</span><span class="sxs-lookup"><span data-stu-id="87bec-448">Lower level empty</span></span>|  
|<span data-ttu-id="87bec-449">33</span><span class="sxs-lookup"><span data-stu-id="87bec-449">33</span></span>|<span data-ttu-id="87bec-450">メッセージ、パッケージ、またはグループの外側に無効な項目</span><span class="sxs-lookup"><span data-stu-id="87bec-450">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="87bec-451">34</span><span class="sxs-lookup"><span data-stu-id="87bec-451">34</span></span>|<span data-ttu-id="87bec-452">入れ子にインジケーターが許可されていません</span><span class="sxs-lookup"><span data-stu-id="87bec-452">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="87bec-453">35</span><span class="sxs-lookup"><span data-stu-id="87bec-453">35</span></span>|<span data-ttu-id="87bec-454">多くのデータ要素またはセグメントの繰り返し</span><span class="sxs-lookup"><span data-stu-id="87bec-454">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="87bec-455">36</span><span class="sxs-lookup"><span data-stu-id="87bec-455">36</span></span>|<span data-ttu-id="87bec-456">セグメント グループの繰り返しが多すぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-456">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="87bec-457">37</span><span class="sxs-lookup"><span data-stu-id="87bec-457">37</span></span>|<span data-ttu-id="87bec-458">文字の型が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-458">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="87bec-459">38</span><span class="sxs-lookup"><span data-stu-id="87bec-459">38</span></span>|<span data-ttu-id="87bec-460">桁区切り記号の前に数値がありません。</span><span class="sxs-lookup"><span data-stu-id="87bec-460">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="87bec-461">39</span><span class="sxs-lookup"><span data-stu-id="87bec-461">39</span></span>|<span data-ttu-id="87bec-462">データ要素が長すぎます。</span><span class="sxs-lookup"><span data-stu-id="87bec-462">Data element too long</span></span>|  
|<span data-ttu-id="87bec-463">40</span><span class="sxs-lookup"><span data-stu-id="87bec-463">40</span></span>|<span data-ttu-id="87bec-464">データ要素が短すぎます。</span><span class="sxs-lookup"><span data-stu-id="87bec-464">Data element too short</span></span>|  
|<span data-ttu-id="87bec-465">41</span><span class="sxs-lookup"><span data-stu-id="87bec-465">41</span></span>|<span data-ttu-id="87bec-466">永続的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="87bec-466">Permanent communication network error</span></span>|  
|<span data-ttu-id="87bec-467">42</span><span class="sxs-lookup"><span data-stu-id="87bec-467">42</span></span>|<span data-ttu-id="87bec-468">一時的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="87bec-468">Temporary communication network error</span></span>|  
|<span data-ttu-id="87bec-469">43</span><span class="sxs-lookup"><span data-stu-id="87bec-469">43</span></span>|<span data-ttu-id="87bec-470">不明なインターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="87bec-470">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="87bec-471">45</span><span class="sxs-lookup"><span data-stu-id="87bec-471">45</span></span>|<span data-ttu-id="87bec-472">末尾の区切り記号</span><span class="sxs-lookup"><span data-stu-id="87bec-472">Trailing separator</span></span>|  
|<span data-ttu-id="87bec-473">46</span><span class="sxs-lookup"><span data-stu-id="87bec-473">46</span></span>|<span data-ttu-id="87bec-474">サポートされている設定されていない文字</span><span class="sxs-lookup"><span data-stu-id="87bec-474">Character set not supported</span></span>|  
|<span data-ttu-id="87bec-475">47</span><span class="sxs-lookup"><span data-stu-id="87bec-475">47</span></span>|<span data-ttu-id="87bec-476">エンベロープ機能がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-476">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="87bec-477">48</span><span class="sxs-lookup"><span data-stu-id="87bec-477">48</span></span>|<span data-ttu-id="87bec-478">依存関係の条件に違反しました</span><span class="sxs-lookup"><span data-stu-id="87bec-478">Dependency condition violated</span></span>|  
|<span data-ttu-id="87bec-479">70</span><span class="sxs-lookup"><span data-stu-id="87bec-479">70</span></span>|<span data-ttu-id="87bec-480">トランザクション セットが存在しないか、無効なトランザクション セットの識別子</span><span class="sxs-lookup"><span data-stu-id="87bec-480">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="87bec-481">71</span><span class="sxs-lookup"><span data-stu-id="87bec-481">71</span></span>|<span data-ttu-id="87bec-482">トランザクション セットまたはグループ制御番号の不一致</span><span class="sxs-lookup"><span data-stu-id="87bec-482">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="87bec-483">72</span><span class="sxs-lookup"><span data-stu-id="87bec-483">72</span></span>|<span data-ttu-id="87bec-484">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="87bec-484">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="87bec-485">73</span><span class="sxs-lookup"><span data-stu-id="87bec-485">73</span></span>|<span data-ttu-id="87bec-486">適切な位置ではなく XML</span><span class="sxs-lookup"><span data-stu-id="87bec-486">XML not at correct position</span></span>|  
|<span data-ttu-id="87bec-487">74</span><span class="sxs-lookup"><span data-stu-id="87bec-487">74</span></span>|<span data-ttu-id="87bec-488">セグメント グループの繰り返しが少なすぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-488">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="87bec-489">75</span><span class="sxs-lookup"><span data-stu-id="87bec-489">75</span></span>|<span data-ttu-id="87bec-490">セグメントの繰り返しが少なすぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-490">Too few segment repetitions</span></span>|  
|<span data-ttu-id="87bec-491">76</span><span class="sxs-lookup"><span data-stu-id="87bec-491">76</span></span>|<span data-ttu-id="87bec-492">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-492">Too few data elements found</span></span>|  
  
 <span data-ttu-id="87bec-493">次のエラー/構文エラー コードは、X12 のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-493">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="87bec-494">エラー/構文エラー コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-494">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="87bec-495">(X12 に適用)</span><span class="sxs-lookup"><span data-stu-id="87bec-495">(applicable to X12)</span></span>|<span data-ttu-id="87bec-496">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="87bec-496">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="87bec-497">1</span><span class="sxs-lookup"><span data-stu-id="87bec-497">1</span></span>|<span data-ttu-id="87bec-498">機能グループがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-498">Functional group not supported</span></span>|  
|<span data-ttu-id="87bec-499">2</span><span class="sxs-lookup"><span data-stu-id="87bec-499">2</span></span>|<span data-ttu-id="87bec-500">機能グループのバージョンがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-500">Functional group version not supported</span></span>|  
|<span data-ttu-id="87bec-501">3</span><span class="sxs-lookup"><span data-stu-id="87bec-501">3</span></span>|<span data-ttu-id="87bec-502">機能グループ トレーラーがありません。</span><span class="sxs-lookup"><span data-stu-id="87bec-502">Functional group trailer missing</span></span>|  
|<span data-ttu-id="87bec-503">4</span><span class="sxs-lookup"><span data-stu-id="87bec-503">4</span></span>|<span data-ttu-id="87bec-504">機能グループ ヘッダーとトレーラーのグループ制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-504">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="87bec-505">5</span><span class="sxs-lookup"><span data-stu-id="87bec-505">5</span></span>|<span data-ttu-id="87bec-506">含まれているトランザクション セットの数が、実際の数と一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-506">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="87bec-507">6-26</span><span class="sxs-lookup"><span data-stu-id="87bec-507">6-26</span></span>|<span data-ttu-id="87bec-508">その他のサポートされていない検証エラー</span><span class="sxs-lookup"><span data-stu-id="87bec-508">Other unsupported validation errors</span></span>|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outgoing-interchanges"></a><span data-ttu-id="87bec-509">送信インターチェンジへの応答で受信した各機能確認の受信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-509">Data Updated by the Receive Pipeline for Each Functional Acknowledgment Received in Response to Outgoing Interchanges</span></span>  
 <span data-ttu-id="87bec-510">受信パイプラインが受信した各機能確認、用、関連する送信インターチェンジの状態レポート エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="87bec-510">For each functional acknowledgment that the receive pipeline receives, it updates the status report entry for the correlated sent interchange.</span></span>  
  
 <span data-ttu-id="87bec-511">EDI 逆アセンブラはインターチェンジおよび受信の確認のグループ ヘッダー セグメント内のデータを次のように使用して、データ ストアでレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="87bec-511">The EDI Disassembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="87bec-512">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="87bec-512">Fields in ACK</span></span>|<span data-ttu-id="87bec-513">データ ストア内のフィールド</span><span class="sxs-lookup"><span data-stu-id="87bec-513">Fields in Data store</span></span>|<span data-ttu-id="87bec-514">解説</span><span class="sxs-lookup"><span data-stu-id="87bec-514">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="87bec-515">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-515">Interchange Sender ID</span></span>|<span data-ttu-id="87bec-516">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="87bec-516">Interchange Receiver</span></span>|<span data-ttu-id="87bec-517">X12 と EDIFACT の両方に適用できます。</span><span class="sxs-lookup"><span data-stu-id="87bec-517">Applicable to both X12 and EDIFACT</span></span>|  
|<span data-ttu-id="87bec-518">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-518">Interchange Receiver ID</span></span>|<span data-ttu-id="87bec-519">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="87bec-519">Interchange Sender</span></span>|<span data-ttu-id="87bec-520">X12 と EDIFACT の両方に適用できます。</span><span class="sxs-lookup"><span data-stu-id="87bec-520">Applicable to both X12 and EDIFACT</span></span>|  
|-|<span data-ttu-id="87bec-521">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="87bec-521">Interchange Date</span></span>|-|  
|<span data-ttu-id="87bec-522">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="87bec-522">Interchange Control Number</span></span>|<span data-ttu-id="87bec-523">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="87bec-523">Interchange Control ID</span></span>|<span data-ttu-id="87bec-524">EDIFACT のみに適用可能</span><span class="sxs-lookup"><span data-stu-id="87bec-524">Applicable only to EDIFACT</span></span>|  
|<span data-ttu-id="87bec-525">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="87bec-525">Group Control Number</span></span>|<span data-ttu-id="87bec-526">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="87bec-526">Group Control Number</span></span>|<span data-ttu-id="87bec-527">X12 のみに適用可能</span><span class="sxs-lookup"><span data-stu-id="87bec-527">Applicable only to X12</span></span>|  
|-|<span data-ttu-id="87bec-528">インターチェンジ方向 = 送信</span><span class="sxs-lookup"><span data-stu-id="87bec-528">Interchange Direction = Send</span></span>|<span data-ttu-id="87bec-529">一意性のため BIBO シナリオで必要な</span><span class="sxs-lookup"><span data-stu-id="87bec-529">Required since in BIBO Scenario for uniqueness</span></span>|  
|<span data-ttu-id="87bec-530">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="87bec-530">Record Type</span></span>|<span data-ttu-id="87bec-531">機能確認状態</span><span class="sxs-lookup"><span data-stu-id="87bec-531">Functional ACK Status</span></span>|<span data-ttu-id="87bec-532">X12 と EDIFACT の両方に適用できます。</span><span class="sxs-lookup"><span data-stu-id="87bec-532">Applicable to both X12 and EDIFACT</span></span>|  
  
 <span data-ttu-id="87bec-533">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87bec-533">The data stored includes:</span></span>  
  
- <span data-ttu-id="87bec-534">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="87bec-534">Record Type = Functional ACK Status</span></span>  
  
- <span data-ttu-id="87bec-535">機能確認方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="87bec-535">Functional ACK Direction = Receive</span></span>  
  
- <span data-ttu-id="87bec-536">機能確認状態 = 更新データを受信</span><span class="sxs-lookup"><span data-stu-id="87bec-536">Functional ACK Status =Update Data as Received</span></span>  
  
- <span data-ttu-id="87bec-537">インターチェンジの受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-537">Interchange Receiver = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-538">インターチェンジの送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-538">Interchange Sender = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-539">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-539">Interchange Date = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-540">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-540">Interchange Control ID = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-541">グループ制御番号 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-541">Group Control Number = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-542">機能 ID コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-542">Functional ID Code = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-543">トランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="87bec-543">Count of Transaction Sets = Existing Data</span></span>  
  
- <span data-ttu-id="87bec-544">機能確認インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-544">Functional ACK Interchange Control ID= Update Data</span></span>  
  
- <span data-ttu-id="87bec-545">機能確認インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-545">Functional ACK Interchange Date = Update Data</span></span>  
  
- <span data-ttu-id="87bec-546">機能確認インターチェンジ時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="87bec-546">Functional ACK Interchange Time = Update Data</span></span>  
  
- <span data-ttu-id="87bec-547">カウントの配信されたトランザクション セット = 更新データ (X12-AK903 および EDIFACT には該当しません)</span><span class="sxs-lookup"><span data-stu-id="87bec-547">Count of Transaction Sets Delivered = Update Data (X12 AK903 and not applicable for EDIFACT)</span></span>  
  
- <span data-ttu-id="87bec-548">カウントの受理されたトランザクション セット = 更新データ (X12-AK904 および EDIFACT には該当しません)</span><span class="sxs-lookup"><span data-stu-id="87bec-548">Count of Transaction Sets Accepted = Update Data (X12 AK904 and not applicable for EDIFACT)</span></span>  
  
- <span data-ttu-id="87bec-549">確認/アクション コード = 更新データ (X 12 AK901 および UCI4) 注 1 を参照してください</span><span class="sxs-lookup"><span data-stu-id="87bec-549">ACK/Action Code = Update Data (X12 AK901 and UCI4) Refer Note 1</span></span>  
  
- <span data-ttu-id="87bec-550">エラー/構文エラー コード = (X 12 AK905 および UCI5) 注 2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87bec-550">Error/Syntax Error Code  = (X12 AK905 and UCI5) Refer Note 2</span></span>  
  
- <span data-ttu-id="87bec-551">追加の X12 確認エラー コード 2 = 更新データ (X12 AK906)</span><span class="sxs-lookup"><span data-stu-id="87bec-551">Additional X12 ACK Error Code 2 = Update Data (X12-AK906)</span></span>  
  
- <span data-ttu-id="87bec-552">追加の X12 確認エラー コード 3 = 更新データ (X12 AK907)</span><span class="sxs-lookup"><span data-stu-id="87bec-552">Additional X12 ACK Error Code 3 = Update Data (X12-AK907)</span></span>  
  
- <span data-ttu-id="87bec-553">追加の X12 確認エラー コード 4 = 更新データ (X12 AK908)</span><span class="sxs-lookup"><span data-stu-id="87bec-553">Additional X12 ACK Error Code 4 = Update Data (X12-AK908)</span></span>  
  
- <span data-ttu-id="87bec-554">追加の X12 確認エラー コード 5 = 更新データ (X12 AK909)</span><span class="sxs-lookup"><span data-stu-id="87bec-554">Additional X12 ACK Error Code 5 = Update Data (X12-AK909)</span></span>  
  
  <span data-ttu-id="87bec-555">次の確認/アクション コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-555">The following ACK/Action Codes will be used:</span></span>  
  
|<span data-ttu-id="87bec-556">確認/アクション コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-556">Data in ACK/Action Code</span></span>|<span data-ttu-id="87bec-557">状態レポート用のマップ</span><span class="sxs-lookup"><span data-stu-id="87bec-557">Mapped for Status Reporting</span></span>|<span data-ttu-id="87bec-558">解説</span><span class="sxs-lookup"><span data-stu-id="87bec-558">Comment</span></span>|  
|------------------------------|---------------------------------|-------------|  
|<span data-ttu-id="87bec-559">A</span><span class="sxs-lookup"><span data-stu-id="87bec-559">A</span></span>|<span data-ttu-id="87bec-560">受理</span><span class="sxs-lookup"><span data-stu-id="87bec-560">Accepted</span></span>|<span data-ttu-id="87bec-561">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-561">X12</span></span>|  
|<span data-ttu-id="87bec-562">P</span><span class="sxs-lookup"><span data-stu-id="87bec-562">P</span></span>|<span data-ttu-id="87bec-563">一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-563">Partially Accepted</span></span>|<span data-ttu-id="87bec-564">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-564">X12</span></span>|  
|<span data-ttu-id="87bec-565">R、M、W、X</span><span class="sxs-lookup"><span data-stu-id="87bec-565">R, M, W, X</span></span>|<span data-ttu-id="87bec-566">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-566">Rejected</span></span>|<span data-ttu-id="87bec-567">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-567">X12</span></span>|  
|<span data-ttu-id="87bec-568">E</span><span class="sxs-lookup"><span data-stu-id="87bec-568">E</span></span>|<span data-ttu-id="87bec-569">エラーありで受理</span><span class="sxs-lookup"><span data-stu-id="87bec-569">Accepted with errors</span></span>|<span data-ttu-id="87bec-570">X12</span><span class="sxs-lookup"><span data-stu-id="87bec-570">X12</span></span>|  
|<span data-ttu-id="87bec-571">4</span><span class="sxs-lookup"><span data-stu-id="87bec-571">4</span></span>|<span data-ttu-id="87bec-572">拒否されました。</span><span class="sxs-lookup"><span data-stu-id="87bec-572">Rejected</span></span>|<span data-ttu-id="87bec-573">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-573">EDIFACT</span></span>|  
|<span data-ttu-id="87bec-574">7, 8</span><span class="sxs-lookup"><span data-stu-id="87bec-574">7, 8</span></span>|<span data-ttu-id="87bec-575">受理/一部受理</span><span class="sxs-lookup"><span data-stu-id="87bec-575">Accepted/Partially Accepted</span></span>|<span data-ttu-id="87bec-576">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="87bec-576">EDIFACT</span></span>|  
  
 <span data-ttu-id="87bec-577">次のエラー/構文エラー コードは、EDIFACT のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-577">The following Error/Syntax Error Codes will be used for EDIFACT:</span></span>  
  
|<span data-ttu-id="87bec-578">エラー/構文エラー コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-578">Data in Error/Syntax Error Cod</span></span><br /><br /> <span data-ttu-id="87bec-579">(EDIFACT に適用)</span><span class="sxs-lookup"><span data-stu-id="87bec-579">(applicable to EDIFACT)</span></span>|<span data-ttu-id="87bec-580">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="87bec-580">Error Description for reporting</span></span>|  
|-------------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="87bec-581">2</span><span class="sxs-lookup"><span data-stu-id="87bec-581">2</span></span>|<span data-ttu-id="87bec-582">構文のバージョンまたはレベル サポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-582">Syntax version or level not supported</span></span>|  
|<span data-ttu-id="87bec-583">7</span><span class="sxs-lookup"><span data-stu-id="87bec-583">7</span></span>|<span data-ttu-id="87bec-584">インターチェンジの受信者の実際の受信者</span><span class="sxs-lookup"><span data-stu-id="87bec-584">Interchange recipient not actual recipient</span></span>|  
|<span data-ttu-id="87bec-585">12</span><span class="sxs-lookup"><span data-stu-id="87bec-585">12</span></span>|<span data-ttu-id="87bec-586">値が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-586">Invalid value</span></span>|  
|<span data-ttu-id="87bec-587">13</span><span class="sxs-lookup"><span data-stu-id="87bec-587">13</span></span>|<span data-ttu-id="87bec-588">Missing</span><span class="sxs-lookup"><span data-stu-id="87bec-588">Missing</span></span>|  
|<span data-ttu-id="87bec-589">14</span><span class="sxs-lookup"><span data-stu-id="87bec-589">14</span></span>|<span data-ttu-id="87bec-590">値がこの位置でサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-590">Value not supported in this position</span></span>|  
|<span data-ttu-id="87bec-591">15</span><span class="sxs-lookup"><span data-stu-id="87bec-591">15</span></span>|<span data-ttu-id="87bec-592">この位置でサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-592">Not supported in this position</span></span>|  
|<span data-ttu-id="87bec-593">16</span><span class="sxs-lookup"><span data-stu-id="87bec-593">16</span></span>|<span data-ttu-id="87bec-594">構成要素が多すぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-594">Too many constituents</span></span>|  
|<span data-ttu-id="87bec-595">17</span><span class="sxs-lookup"><span data-stu-id="87bec-595">17</span></span>|<span data-ttu-id="87bec-596">契約</span><span class="sxs-lookup"><span data-stu-id="87bec-596">No agreement</span></span>|  
|<span data-ttu-id="87bec-597">18</span><span class="sxs-lookup"><span data-stu-id="87bec-597">18</span></span>|<span data-ttu-id="87bec-598">特定できないエラー</span><span class="sxs-lookup"><span data-stu-id="87bec-598">Unspecified error</span></span>|  
|<span data-ttu-id="87bec-599">19</span><span class="sxs-lookup"><span data-stu-id="87bec-599">19</span></span>|<span data-ttu-id="87bec-600">無効な 10 進表記</span><span class="sxs-lookup"><span data-stu-id="87bec-600">Invalid decimal notation</span></span>|  
|<span data-ttu-id="87bec-601">20</span><span class="sxs-lookup"><span data-stu-id="87bec-601">20</span></span>|<span data-ttu-id="87bec-602">サービス文字として無効な文字</span><span class="sxs-lookup"><span data-stu-id="87bec-602">Character invalid as service character</span></span>|  
|<span data-ttu-id="87bec-603">21</span><span class="sxs-lookup"><span data-stu-id="87bec-603">21</span></span>|<span data-ttu-id="87bec-604">無効な文字</span><span class="sxs-lookup"><span data-stu-id="87bec-604">Invalid character(s)</span></span>|  
|<span data-ttu-id="87bec-605">22</span><span class="sxs-lookup"><span data-stu-id="87bec-605">22</span></span>|<span data-ttu-id="87bec-606">サービスの無効な文字</span><span class="sxs-lookup"><span data-stu-id="87bec-606">Invalid service character(s)</span></span>|  
|<span data-ttu-id="87bec-607">23</span><span class="sxs-lookup"><span data-stu-id="87bec-607">23</span></span>|<span data-ttu-id="87bec-608">不明なインターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="87bec-608">Unknown Interchange sender</span></span>|  
|<span data-ttu-id="87bec-609">24</span><span class="sxs-lookup"><span data-stu-id="87bec-609">24</span></span>|<span data-ttu-id="87bec-610">古すぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-610">Too old</span></span>|  
|<span data-ttu-id="87bec-611">25</span><span class="sxs-lookup"><span data-stu-id="87bec-611">25</span></span>|<span data-ttu-id="87bec-612">テスト インジケーターがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-612">Test indicator not supported</span></span>|  
|<span data-ttu-id="87bec-613">26</span><span class="sxs-lookup"><span data-stu-id="87bec-613">26</span></span>|<span data-ttu-id="87bec-614">重複が検出されました</span><span class="sxs-lookup"><span data-stu-id="87bec-614">Duplicate detected</span></span>|  
|<span data-ttu-id="87bec-615">27</span><span class="sxs-lookup"><span data-stu-id="87bec-615">27</span></span>|<span data-ttu-id="87bec-616">セキュリティ関数がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-616">Security function not supported</span></span>|  
|<span data-ttu-id="87bec-617">28</span><span class="sxs-lookup"><span data-stu-id="87bec-617">28</span></span>|<span data-ttu-id="87bec-618">参照が一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-618">References do not match</span></span>|  
|<span data-ttu-id="87bec-619">29</span><span class="sxs-lookup"><span data-stu-id="87bec-619">29</span></span>|<span data-ttu-id="87bec-620">コントロールの数が、受信したインスタンスの数と一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-620">Control count does not match number of instances received</span></span>|  
|<span data-ttu-id="87bec-621">30</span><span class="sxs-lookup"><span data-stu-id="87bec-621">30</span></span>|<span data-ttu-id="87bec-622">グループとメッセージ/パッケージの混在</span><span class="sxs-lookup"><span data-stu-id="87bec-622">Groups and messages/packages mixed</span></span>|  
|<span data-ttu-id="87bec-623">31</span><span class="sxs-lookup"><span data-stu-id="87bec-623">31</span></span>|<span data-ttu-id="87bec-624">グループ内の 1 つ以上のメッセージ型</span><span class="sxs-lookup"><span data-stu-id="87bec-624">More than one message type in group</span></span>|  
|<span data-ttu-id="87bec-625">32</span><span class="sxs-lookup"><span data-stu-id="87bec-625">32</span></span>|<span data-ttu-id="87bec-626">下位レベルが空</span><span class="sxs-lookup"><span data-stu-id="87bec-626">Lower level empty</span></span>|  
|<span data-ttu-id="87bec-627">33</span><span class="sxs-lookup"><span data-stu-id="87bec-627">33</span></span>|<span data-ttu-id="87bec-628">メッセージ、パッケージ、またはグループの外側に無効な項目</span><span class="sxs-lookup"><span data-stu-id="87bec-628">Invalid occurrence outside message, package, or group</span></span>|  
|<span data-ttu-id="87bec-629">34</span><span class="sxs-lookup"><span data-stu-id="87bec-629">34</span></span>|<span data-ttu-id="87bec-630">入れ子にインジケーターが許可されていません</span><span class="sxs-lookup"><span data-stu-id="87bec-630">Nesting indicator not allowed</span></span>|  
|<span data-ttu-id="87bec-631">35</span><span class="sxs-lookup"><span data-stu-id="87bec-631">35</span></span>|<span data-ttu-id="87bec-632">多くのデータ要素またはセグメントの繰り返し</span><span class="sxs-lookup"><span data-stu-id="87bec-632">Too many data element or segment repetitions</span></span>|  
|<span data-ttu-id="87bec-633">36</span><span class="sxs-lookup"><span data-stu-id="87bec-633">36</span></span>|<span data-ttu-id="87bec-634">セグメント グループの繰り返しが多すぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-634">Too many segment group repetitions</span></span>|  
|<span data-ttu-id="87bec-635">37</span><span class="sxs-lookup"><span data-stu-id="87bec-635">37</span></span>|<span data-ttu-id="87bec-636">文字の型が無効です。</span><span class="sxs-lookup"><span data-stu-id="87bec-636">Invalid type of character(s)</span></span>|  
|<span data-ttu-id="87bec-637">38</span><span class="sxs-lookup"><span data-stu-id="87bec-637">38</span></span>|<span data-ttu-id="87bec-638">桁区切り記号の前に数値がありません。</span><span class="sxs-lookup"><span data-stu-id="87bec-638">Missing digit in front of decimal sign</span></span>|  
|<span data-ttu-id="87bec-639">39</span><span class="sxs-lookup"><span data-stu-id="87bec-639">39</span></span>|<span data-ttu-id="87bec-640">データ要素が長すぎます。</span><span class="sxs-lookup"><span data-stu-id="87bec-640">Data element too long</span></span>|  
|<span data-ttu-id="87bec-641">40</span><span class="sxs-lookup"><span data-stu-id="87bec-641">40</span></span>|<span data-ttu-id="87bec-642">データ要素が短すぎます。</span><span class="sxs-lookup"><span data-stu-id="87bec-642">Data element too short</span></span>|  
|<span data-ttu-id="87bec-643">41</span><span class="sxs-lookup"><span data-stu-id="87bec-643">41</span></span>|<span data-ttu-id="87bec-644">永続的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="87bec-644">Permanent communication network error</span></span>|  
|<span data-ttu-id="87bec-645">42</span><span class="sxs-lookup"><span data-stu-id="87bec-645">42</span></span>|<span data-ttu-id="87bec-646">一時的な通信ネットワーク エラー</span><span class="sxs-lookup"><span data-stu-id="87bec-646">Temporary communication network error</span></span>|  
|<span data-ttu-id="87bec-647">43</span><span class="sxs-lookup"><span data-stu-id="87bec-647">43</span></span>|<span data-ttu-id="87bec-648">不明なインターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="87bec-648">Unknown interchange recipient</span></span>|  
|<span data-ttu-id="87bec-649">45</span><span class="sxs-lookup"><span data-stu-id="87bec-649">45</span></span>|<span data-ttu-id="87bec-650">末尾の区切り記号</span><span class="sxs-lookup"><span data-stu-id="87bec-650">Trailing separator</span></span>|  
|<span data-ttu-id="87bec-651">46</span><span class="sxs-lookup"><span data-stu-id="87bec-651">46</span></span>|<span data-ttu-id="87bec-652">サポートされている設定されていない文字</span><span class="sxs-lookup"><span data-stu-id="87bec-652">Character set not supported</span></span>|  
|<span data-ttu-id="87bec-653">47</span><span class="sxs-lookup"><span data-stu-id="87bec-653">47</span></span>|<span data-ttu-id="87bec-654">エンベロープ機能がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-654">Envelope functionality not supported</span></span>|  
|<span data-ttu-id="87bec-655">48</span><span class="sxs-lookup"><span data-stu-id="87bec-655">48</span></span>|<span data-ttu-id="87bec-656">依存関係の条件に違反しました</span><span class="sxs-lookup"><span data-stu-id="87bec-656">Dependency condition violated</span></span>|  
|<span data-ttu-id="87bec-657">70</span><span class="sxs-lookup"><span data-stu-id="87bec-657">70</span></span>|<span data-ttu-id="87bec-658">トランザクション セットが存在しないか、無効なトランザクション セットの識別子</span><span class="sxs-lookup"><span data-stu-id="87bec-658">Transaction set is missing or invalid transaction set Identifier</span></span>|  
|<span data-ttu-id="87bec-659">71</span><span class="sxs-lookup"><span data-stu-id="87bec-659">71</span></span>|<span data-ttu-id="87bec-660">トランザクション セットまたはグループ制御番号の不一致</span><span class="sxs-lookup"><span data-stu-id="87bec-660">Transaction set or group control number mismatch</span></span>|  
|<span data-ttu-id="87bec-661">72</span><span class="sxs-lookup"><span data-stu-id="87bec-661">72</span></span>|<span data-ttu-id="87bec-662">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="87bec-662">Unrecognized segment ID</span></span>|  
|<span data-ttu-id="87bec-663">73</span><span class="sxs-lookup"><span data-stu-id="87bec-663">73</span></span>|<span data-ttu-id="87bec-664">適切な位置ではなく XML</span><span class="sxs-lookup"><span data-stu-id="87bec-664">XML not at correct position</span></span>|  
|<span data-ttu-id="87bec-665">74</span><span class="sxs-lookup"><span data-stu-id="87bec-665">74</span></span>|<span data-ttu-id="87bec-666">セグメント グループの繰り返しが少なすぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-666">Too few segment group repetitions</span></span>|  
|<span data-ttu-id="87bec-667">75</span><span class="sxs-lookup"><span data-stu-id="87bec-667">75</span></span>|<span data-ttu-id="87bec-668">セグメントの繰り返しが少なすぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-668">Too few segment repetitions</span></span>|  
|<span data-ttu-id="87bec-669">76</span><span class="sxs-lookup"><span data-stu-id="87bec-669">76</span></span>|<span data-ttu-id="87bec-670">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="87bec-670">Too few data elements found</span></span>|  
  
 <span data-ttu-id="87bec-671">次のエラー/構文エラー コードは、X12 のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87bec-671">The following Error/Syntax Error Codes will be used for X12:</span></span>  
  
|<span data-ttu-id="87bec-672">エラー/構文エラー コード内のデータ</span><span class="sxs-lookup"><span data-stu-id="87bec-672">Data in Error/Syntax Error Code</span></span><br /><br /> <span data-ttu-id="87bec-673">(X12 に適用)</span><span class="sxs-lookup"><span data-stu-id="87bec-673">(applicable to X12)</span></span>|<span data-ttu-id="87bec-674">レポートのエラーの説明</span><span class="sxs-lookup"><span data-stu-id="87bec-674">Error Description for reporting</span></span>|  
|----------------------------------------------------------------|-------------------------------------|  
|<span data-ttu-id="87bec-675">1</span><span class="sxs-lookup"><span data-stu-id="87bec-675">1</span></span>|<span data-ttu-id="87bec-676">機能グループがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-676">Functional group not supported</span></span>|  
|<span data-ttu-id="87bec-677">2</span><span class="sxs-lookup"><span data-stu-id="87bec-677">2</span></span>|<span data-ttu-id="87bec-678">機能グループのバージョンがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="87bec-678">Functional group version not supported</span></span>|  
|<span data-ttu-id="87bec-679">3</span><span class="sxs-lookup"><span data-stu-id="87bec-679">3</span></span>|<span data-ttu-id="87bec-680">機能グループ トレーラーがありません。</span><span class="sxs-lookup"><span data-stu-id="87bec-680">Functional group trailer missing</span></span>|  
|<span data-ttu-id="87bec-681">4</span><span class="sxs-lookup"><span data-stu-id="87bec-681">4</span></span>|<span data-ttu-id="87bec-682">機能グループ ヘッダーとトレーラーのグループ制御番号が一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-682">Group control number in the functional group header and trailer do not agree</span></span>|  
|<span data-ttu-id="87bec-683">5</span><span class="sxs-lookup"><span data-stu-id="87bec-683">5</span></span>|<span data-ttu-id="87bec-684">含まれているトランザクション セットの数が、実際の数と一致しません</span><span class="sxs-lookup"><span data-stu-id="87bec-684">Number of included transaction sets does not match actual count</span></span>|  
|<span data-ttu-id="87bec-685">6-26</span><span class="sxs-lookup"><span data-stu-id="87bec-685">6-26</span></span>|<span data-ttu-id="87bec-686">その他のサポートされていない検証エラー</span><span class="sxs-lookup"><span data-stu-id="87bec-686">Other unsupported validation errors</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87bec-687">参照</span><span class="sxs-lookup"><span data-stu-id="87bec-687">See Also</span></span>  
 <span data-ttu-id="87bec-688">[EDI および AS2 状態レポートのデータを格納する方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="87bec-688">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="87bec-689">受信 EDI メッセージのデータ格納方法</span><span class="sxs-lookup"><span data-stu-id="87bec-689">How Data Is Stored for Inbound EDI Messages</span></span>](../core/how-data-is-stored-for-inbound-edi-messages.md)