---
title: "受信 EDI メッセージのデータを格納する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60cc8743cd945ad231f3a42f9cbd4f0e76b418d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a><span data-ttu-id="3f51f-102">受信 EDI メッセージのデータ格納方法</span><span class="sxs-lookup"><span data-stu-id="3f51f-102">How Data Is Stored for Inbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3f51f-103"> は次の操作を実行して、受信インターチェンジと、そのインターチェンジに対する応答として送信される受信確認の状態レポート エントリを生成します。</span><span class="sxs-lookup"><span data-stu-id="3f51f-103"> does the following to generate a status report entry for an inbound interchange and the acknowledgment sent in response to it:</span></span>  
  
1.  <span data-ttu-id="3f51f-104">受信メッセージ XML が EDI 受信パイプラインによってメッセージ ボックスに送信されると、受信パイプラインは状態レポートのデータ ストアに次のエントリを作成します。エントリには、次に示す値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-104">When inbound message XML is sent by the EDI receive pipeline to the MessageBox, the receive pipeline creates the following entries in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="3f51f-105">受信したインターチェンジごとに 1 つの状態レポート エントリが作成されます。[状態] には [受理]、[一部受理]、[拒否] のいずれかが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-105">One status report entry for each interchange received, with Status set to Accepted/Partially Accepted/Rejected</span></span>  
  
    -   <span data-ttu-id="3f51f-106">技術 (インターチェンジ) 確認ごとに 1 つの状態レポート エントリが作成されます。[状態] には [作成] が設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-106">One status report entry for each technical (interchange) acknowledgment, one per interchange, with Status set to Generated</span></span>  
  
    -   <span data-ttu-id="3f51f-107">機能確認 (X12 では 1 グループに 1 つ、EDIFACT ではすべてのグループに 1 つ) ごとに 1 つの状態レポート エントリが作成されます。[状態] には [作成] が設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-107">One status report entry for each functional acknowledgment, one per group in X12 and one for all groups in EDIFACT, with Status set to Generated.</span></span>  
  
2.  <span data-ttu-id="3f51f-108">送信パイプラインが取引先に受信確認を送信すると、必要に応じて、EDI 送信パイプラインによりインターチェンジ確認状態エントリと機能確認状態エントリが [送信済み] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-108">After the send pipeline has sent the acknowledgments to the trading partner, the EDI send pipeline updates the Interchange ACK status and Functional ACK status entries to Sent, as appropriate.</span></span> <span data-ttu-id="3f51f-109">インターチェンジ状態エントリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="3f51f-109">No changes are made to the Interchange status entry.</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a><span data-ttu-id="3f51f-110">受信インターチェンジの受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="3f51f-110">Data Stored by the Receive Pipeline for Inbound Interchanges</span></span>  
 <span data-ttu-id="3f51f-111">受信パイプラインは、受信する各インターチェンジの状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f51f-111">The receive pipeline creates a record in the status report data store for each interchange that it receives.</span></span> <span data-ttu-id="3f51f-112">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f51f-112">The data stored includes:</span></span>  
  
-   <span data-ttu-id="3f51f-113">レコードの種類 = インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="3f51f-113">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="3f51f-114">インターチェンジ方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="3f51f-114">Interchange Direction = Receive</span></span>  
  
-   <span data-ttu-id="3f51f-115">インターチェンジの受信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-115">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-116">インターチェンジの送信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-116">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-117">インターチェンジの日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-117">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-118">インターチェンジの時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-118">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-119">インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-119">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-120">インターチェンジの状態 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-120">Interchange Status: Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-121">インターチェンジ内のグループ数 = 更新データ (EDIFACT ではグループは省略可能です。存在しない場合は値に "適用できません" が設定されます)</span><span class="sxs-lookup"><span data-stu-id="3f51f-121">Count of Groups in Interchange = Update Data (In EDIFACT Groups are optional and if not present, valued as ‘Not Applicable’)</span></span>  
  
-   <span data-ttu-id="3f51f-122">インターチェンジの受信ポート ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-122">Interchange Receive Port ID = Update Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="3f51f-123">受信インターチェンジへの応答として生成された各技術確認用の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="3f51f-123">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="3f51f-124">送信パイプラインは、送信した各技術確認用の状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f51f-124">The send pipeline creates a record in the status report data store for each technical acknowledgment that it sends.</span></span> <span data-ttu-id="3f51f-125">技術確認は、EDIFACT の場合、UCI セグメントのみで、X12 と CONTRL メッセージに対する TA1 です。</span><span class="sxs-lookup"><span data-stu-id="3f51f-125">The technical acknowledgement is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="3f51f-126">エントリに必要なほとんどのデータは、インターチェンジのヘッダー/トレーラー セグメント (ISA/IEA または UNB/UNZ) から使用可能です。</span><span class="sxs-lookup"><span data-stu-id="3f51f-126">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="3f51f-127">他のデータは、送信ポートのプロパティから使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-127">Other data is available from send port properties.</span></span> <span data-ttu-id="3f51f-128">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f51f-128">The data stored includes:</span></span>  
  
-   <span data-ttu-id="3f51f-129">レコードの種類 = インターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="3f51f-129">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="3f51f-130">インターチェンジ確認方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="3f51f-130">Interchange ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="3f51f-131">インターチェンジの受信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="3f51f-131">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="3f51f-132">インターチェンジの送信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="3f51f-132">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="3f51f-133">インターチェンジの日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-133">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-134">インターチェンジ制御 ID = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="3f51f-134">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="3f51f-135">インターチェンジ確認状態 =\<想定または該当なし > です。</span><span class="sxs-lookup"><span data-stu-id="3f51f-135">Interchange ACK Status = \< Expected or Not Applicable>.</span></span> <span data-ttu-id="3f51f-136">(技術確認が受信インターチェンジで構成されているか、または値が設定されている場合は、状態は "必要" になります。</span><span class="sxs-lookup"><span data-stu-id="3f51f-136">If the technical ACK is configured or valued in the incoming interchange, status = Expected.</span></span> <span data-ttu-id="3f51f-137">それ以外の場合、状態には "適用されません" が設定されます)</span><span class="sxs-lookup"><span data-stu-id="3f51f-137">Otherwise, status = Not Applicable.</span></span>  
  
-   <span data-ttu-id="3f51f-138">インターチェンジ確認制御 ID =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-138">Interchange ACK Control ID= \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-139">インターチェンジ確認日付 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-139">Interchange ACK Date = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-140">インターチェンジ確認時刻 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-140">Interchange ACK Time = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-141">確認/アクション コード =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-141">ACK/Action Code = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-142">確認通知コード =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-142">ACK Note Code = \<not valued></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="3f51f-143">受信インターチェンジへの応答として生成された各技術確認用の送信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="3f51f-143">Data Updated by the Send Pipeline for Each Technical Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="3f51f-144">送信パイプラインが送信した各技術確認用に、関連する受信インターチェンジの状態レポート エントリが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-144">For each technical acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="3f51f-145">送信パイプラインによって作成されたインターチェンジ エンベロープがデータのソースになります。</span><span class="sxs-lookup"><span data-stu-id="3f51f-145">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="3f51f-146">EDI アセンブラーは、次のように受信確認の UCI および TA1 セグメントのデータを使用して、データ ストア内でレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="3f51f-146">The EDI Assembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="3f51f-147">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="3f51f-147">Fields in ACK</span></span>|<span data-ttu-id="3f51f-148">データ ストアのフィールド</span><span class="sxs-lookup"><span data-stu-id="3f51f-148">Fields in Data store</span></span>|<span data-ttu-id="3f51f-149">解説</span><span class="sxs-lookup"><span data-stu-id="3f51f-149">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="3f51f-150">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="3f51f-150">Interchange Sender ID</span></span>|<span data-ttu-id="3f51f-151">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="3f51f-151">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="3f51f-152">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="3f51f-152">Interchange Receiver ID</span></span>|<span data-ttu-id="3f51f-153">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="3f51f-153">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="3f51f-154">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="3f51f-154">Interchange Date</span></span>|-|  
|<span data-ttu-id="3f51f-155">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="3f51f-155">Interchange Control Number</span></span>|<span data-ttu-id="3f51f-156">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="3f51f-156">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="3f51f-157">インターチェンジ方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="3f51f-157">Interchange Direction = Receive</span></span>|<span data-ttu-id="3f51f-158">保存されたインターチェンジ シナリオの一意性に必要</span><span class="sxs-lookup"><span data-stu-id="3f51f-158">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="3f51f-159">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="3f51f-159">Record Type</span></span>|<span data-ttu-id="3f51f-160">インターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="3f51f-160">Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="3f51f-161">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f51f-161">The data stored includes:</span></span>  
  
-   <span data-ttu-id="3f51f-162">レコードの種類 = インターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="3f51f-162">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="3f51f-163">インターチェンジ確認方向 = 送信 - 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-163">Interchange ACK Direction = Send- Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-164">インターチェンジ確認の状態 = 処理済みまたは送信 - 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-164">Interchange ACK Status = Processed or Sent – Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-165">インターチェンジ受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-165">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-166">インターチェンジ送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-166">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-167">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-167">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-168">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-168">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-169">インターチェンジ確認制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-169">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-170">インターチェンジ確認日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-170">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-171">インターチェンジ確認時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-171">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-172">確認/アクション コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-172">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-173">確認通知コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-173">ACK Note Code = Existing Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="3f51f-174">受信インターチェンジへの応答として生成された各機能確認用の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="3f51f-174">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="3f51f-175">送信パイプラインは、送信した各機能確認用の状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f51f-175">The send pipeline creates a record in the status report data store for each functional acknowledgment that it sends.</span></span> <span data-ttu-id="3f51f-176">送信パイプラインは、(受信したインターチェンジへの応答として) 送信した各機能確認のレコードを状態レポート データ ストアに作成します。</span><span class="sxs-lookup"><span data-stu-id="3f51f-176">The send pipeline creates a record of each functional acknowledgment sent (in response to an interchange received) in the status report data store.</span></span> <span data-ttu-id="3f51f-177">EDIFACT では、グループが存在しない場合でも機能確認は 1 つは作成されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-177">If no group is present in EDIFACT, one functional ACK will still be created.</span></span> <span data-ttu-id="3f51f-178">機能確認用の状態レポート エントリは、機能グループのヘッダーとトレーラー (GS/GE または UNG/UNE) に基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-178">The functional ACK status report entry will be populated from the functional group header/trailer (GS/GE or UNG/UNE).</span></span> <span data-ttu-id="3f51f-179">技術確認は、X12 では 997 で、EDIFACT では CONTRL メッセージの全文です。</span><span class="sxs-lookup"><span data-stu-id="3f51f-179">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="3f51f-180">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f51f-180">The data stored includes:</span></span>  
  
-   <span data-ttu-id="3f51f-181">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="3f51f-181">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="3f51f-182">機能確認方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="3f51f-182">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="3f51f-183">機能確認状態 =\<想定または該当なし > です。</span><span class="sxs-lookup"><span data-stu-id="3f51f-183">Functional ACK Status = \< Expected or Not Applicable>.</span></span> <span data-ttu-id="3f51f-184">(PAM で機能確認のタブが選択されている場合、状態は "必要" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-184">If the functional acknowledgment tab in PAM is selected, status will set to Expected.</span></span> <span data-ttu-id="3f51f-185">それ以外の場合、状態は、該当なし に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-185">Otherwise, status will be set to Not Applicable.</span></span>  
  
-   <span data-ttu-id="3f51f-186">インターチェンジの受信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="3f51f-186">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="3f51f-187">インターチェンジの送信者 = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="3f51f-187">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="3f51f-188">インターチェンジの日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-188">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-189">インターチェンジ制御 ID = 更新データ (関連付けに必要)</span><span class="sxs-lookup"><span data-stu-id="3f51f-189">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="3f51f-190">グループ制御番号 = 更新データ (関連付けに必要。</span><span class="sxs-lookup"><span data-stu-id="3f51f-190">Group Control Number = Update Data (required for correlation.</span></span> <span data-ttu-id="3f51f-191">EDIFACT では、グループ セグメントが存在しない場合、このフィールドには UNH.1 が設定されます)</span><span class="sxs-lookup"><span data-stu-id="3f51f-191">In EDIFACT if no group segments present this field is valued using UNH.1)</span></span>  
  
-   <span data-ttu-id="3f51f-192">機能 ID コード = 更新データ (EDIFACT では、グループ セグメントが存在しない場合、"値なし" に設定されます)</span><span class="sxs-lookup"><span data-stu-id="3f51f-192">Functional ID Code = Update Data (not valued in EDIFACT if group is not present)</span></span>  
  
-   <span data-ttu-id="3f51f-193">トランザクション セットの数 = データ (EDIFACT では、UNG/UNE が存在する場合は UNE.1、グループ セグメントが存在しない場合は UNZ.1 にマップされます)</span><span class="sxs-lookup"><span data-stu-id="3f51f-193">Count of Transaction Sets = Data (in EDIFACT this is mapped to UNE.1 while UNG/UNE are present or UNZ.1 if no group segments are present)</span></span>  
  
-   <span data-ttu-id="3f51f-194">機能確認インターチェンジ制御 ID =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-194">Functional ACK Interchange Control ID= \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-195">機能確認インターチェンジ日付 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-195">Functional ACK Interchange Date = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-196">機能確認インターチェンジ時刻 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-196">Functional ACK Interchange Time = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-197">カウントの配信されたトランザクション セット =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-197">Count of Transaction Sets Delivered = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-198">カウントの受理されたトランザクション セット =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-198">Count of Transaction Sets Accepted = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-199">確認/アクション コード =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-199">ACK/Action Code = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-200">エラー/構文エラー コード =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-200">Error/Syntax Error Code  = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-201">追加の X12 確認エラー コード 2 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-201">Additional X12 ACK Error Code 2 = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-202">追加の X12 確認エラー コード 3 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-202">Additional X12 ACK Error Code 3 = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-203">追加の X12 確認エラー コード 4 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-203">Additional X12 ACK Error Code 4 = \<not valued></span></span>  
  
-   <span data-ttu-id="3f51f-204">追加の X12 確認エラー コード 5 =\<値なし ></span><span class="sxs-lookup"><span data-stu-id="3f51f-204">Additional X12 ACK Error Code 5 = \<not valued></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="3f51f-205">受信インターチェンジへの応答として生成された各機能確認用の送信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="3f51f-205">Data Updated by the Send Pipeline for Each Functional Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="3f51f-206">送信パイプラインが送信した各機能確認用に、関連する受信インターチェンジの状態レポート エントリが更新されます。</span><span class="sxs-lookup"><span data-stu-id="3f51f-206">For each functional acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="3f51f-207">送信パイプラインによって作成されたインターチェンジ エンベロープがデータのソースになります。</span><span class="sxs-lookup"><span data-stu-id="3f51f-207">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="3f51f-208">EDI アセンブラーは、次のように、インターチェンジとグループ ヘッダー セグメントに、受信確認の内のデータを使用してデータ ストア内のレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="3f51f-208">The EDI Assembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="3f51f-209">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="3f51f-209">Fields in ACK</span></span>|<span data-ttu-id="3f51f-210">データ ストアのフィールド</span><span class="sxs-lookup"><span data-stu-id="3f51f-210">Fields in Data store</span></span>|<span data-ttu-id="3f51f-211">解説</span><span class="sxs-lookup"><span data-stu-id="3f51f-211">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="3f51f-212">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="3f51f-212">Interchange Sender ID</span></span>|<span data-ttu-id="3f51f-213">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="3f51f-213">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="3f51f-214">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="3f51f-214">Interchange Receiver ID</span></span>|<span data-ttu-id="3f51f-215">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="3f51f-215">Interchange Sender</span></span>|-|  
|<span data-ttu-id="3f51f-216">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="3f51f-216">Interchange Date</span></span>|<span data-ttu-id="3f51f-217">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="3f51f-217">Interchange Date</span></span>|-|  
|<span data-ttu-id="3f51f-218">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="3f51f-218">Interchange Control Number</span></span>|<span data-ttu-id="3f51f-219">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="3f51f-219">Interchange Control ID</span></span>|-|  
|<span data-ttu-id="3f51f-220">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="3f51f-220">Group Control Number</span></span>|<span data-ttu-id="3f51f-221">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="3f51f-221">Group Control Number</span></span>|<span data-ttu-id="3f51f-222">EDIFACT では省略可能</span><span class="sxs-lookup"><span data-stu-id="3f51f-222">Optional in EDIFACT</span></span>|  
|-|<span data-ttu-id="3f51f-223">インターチェンジ方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="3f51f-223">Interchange Direction = Receive</span></span>|<span data-ttu-id="3f51f-224">保存されたインターチェンジ シナリオの一意性に必要</span><span class="sxs-lookup"><span data-stu-id="3f51f-224">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="3f51f-225">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="3f51f-225">Record Type</span></span>|<span data-ttu-id="3f51f-226">機能確認状態</span><span class="sxs-lookup"><span data-stu-id="3f51f-226">Functional ACK Status</span></span>|-|  
  
 <span data-ttu-id="3f51f-227">格納されるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f51f-227">The data stored includes:</span></span>  
  
-   <span data-ttu-id="3f51f-228">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="3f51f-228">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="3f51f-229">機能確認方向 = 受信 - 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-229">Functional ACK Direction = Send – Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-230">機能確認状態 = 送信/処理済み - 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-230">Functional ACK Status = Sent/Processed – Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-231">インターチェンジの受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-231">Interchange Receiver =  Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-232">インターチェンジ送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-232">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-233">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-233">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-234">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-234">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-235">グループ制御番号 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-235">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-236">機能 ID コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-236">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-237">トランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-237">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-238">機能確認インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-238">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-239">機能確認インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-239">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-240">機能確認インターチェンジ時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-240">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="3f51f-241">受信したトランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-241">Count of Transaction Sets Received = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-242">受理したトランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-242">Count of Transaction Sets Accepted = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-243">確認/アクション コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-243">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-244">エラー/構文エラー コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-244">Error/Syntax Error Code  = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-245">追加の X12 確認エラー コード 2 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-245">Additional X12 ACK Error Code 2 = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-246">追加の X12 確認エラー コード 3 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-246">Additional X12 ACK Error Code 3 = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-247">追加の X12 確認エラー コード 4 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-247">Additional X12 ACK Error Code 4 = Existing Data</span></span>  
  
-   <span data-ttu-id="3f51f-248">追加の X12 確認エラー コード 5 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="3f51f-248">Additional X12 ACK Error Code 5 = Existing Data</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f51f-249">参照</span><span class="sxs-lookup"><span data-stu-id="3f51f-249">See Also</span></span>  
 <span data-ttu-id="3f51f-250">[EDI および AS2 状態レポートのデータを格納する方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="3f51f-250">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="3f51f-251">送信 EDI メッセージのデータを格納する方法</span><span class="sxs-lookup"><span data-stu-id="3f51f-251">How Data Is Stored for Outbound EDI Messages</span></span>](../core/how-data-is-stored-for-outbound-edi-messages.md)