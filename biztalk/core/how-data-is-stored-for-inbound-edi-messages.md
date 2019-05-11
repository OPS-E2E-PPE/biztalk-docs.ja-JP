---
title: 受信 EDI メッセージのデータを格納する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a117bb89989977ab0050d0d6b4704002f316315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387471"
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a><span data-ttu-id="f1e10-102">受信 EDI メッセージのデータを格納する方法</span><span class="sxs-lookup"><span data-stu-id="f1e10-102">How Data Is Stored for Inbound EDI Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f1e10-103">受信インターチェンジとそれに対する応答として送信、受信確認の状態レポート エントリを生成するには、次を行います。</span><span class="sxs-lookup"><span data-stu-id="f1e10-103">does the following to generate a status report entry for an inbound interchange and the acknowledgment sent in response to it:</span></span>  
  
1.  <span data-ttu-id="f1e10-104">受信メッセージ XML は、EDI 受信パイプラインによって送信されるメッセージ ボックスに、受信パイプラインは、レポートの次の値を持つデータ ストアの状態で、次のエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-104">When inbound message XML is sent by the EDI receive pipeline to the MessageBox, the receive pipeline creates the following entries in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="f1e10-105">受信した状態に受理/一部受理]/[拒否の設定の各インターチェンジの 1 つの状態レポート エントリ</span><span class="sxs-lookup"><span data-stu-id="f1e10-105">One status report entry for each interchange received, with Status set to Accepted/Partially Accepted/Rejected</span></span>  
  
    -   <span data-ttu-id="f1e10-106">各技術 (インターチェンジ) 確認の 1 つの状態レポート エントリを状態で、インターチェンジごとに 1 つ、生成されたに設定</span><span class="sxs-lookup"><span data-stu-id="f1e10-106">One status report entry for each technical (interchange) acknowledgment, one per interchange, with Status set to Generated</span></span>  
  
    -   <span data-ttu-id="f1e10-107">各機能確認の 1 つの状態レポート エントリを生成する X12 と EDIFACT では、状態のすべてのグループに 1 つのグループごとに 1 つ設定します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-107">One status report entry for each functional acknowledgment, one per group in X12 and one for all groups in EDIFACT, with Status set to Generated.</span></span>  
  
2.  <span data-ttu-id="f1e10-108">送信パイプラインが送信された後に取引先のパートナーでは、EDI 受信確認更新を送信パイプライン、インターチェンジ確認状態と機能確認状態エントリ、適切な。</span><span class="sxs-lookup"><span data-stu-id="f1e10-108">After the send pipeline has sent the acknowledgments to the trading partner, the EDI send pipeline updates the Interchange ACK status and Functional ACK status entries to Sent, as appropriate.</span></span> <span data-ttu-id="f1e10-109">インターチェンジ状態エントリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="f1e10-109">No changes are made to the Interchange status entry.</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a><span data-ttu-id="f1e10-110">受信インターチェンジの受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="f1e10-110">Data Stored by the Receive Pipeline for Inbound Interchanges</span></span>  
 <span data-ttu-id="f1e10-111">受信パイプラインは、受信する各インターチェンジの状態レポート データ ストアにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-111">The receive pipeline creates a record in the status report data store for each interchange that it receives.</span></span> <span data-ttu-id="f1e10-112">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1e10-112">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f1e10-113">レコードの種類 = インターチェンジの状態</span><span class="sxs-lookup"><span data-stu-id="f1e10-113">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="f1e10-114">インターチェンジ方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="f1e10-114">Interchange Direction = Receive</span></span>  
  
-   <span data-ttu-id="f1e10-115">インターチェンジの受信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-115">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-116">インターチェンジの送信者 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-116">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-117">インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-117">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-118">インターチェンジ時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-118">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-119">インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-119">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-120">インターチェンジの状態。更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-120">Interchange Status: Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-121">インターチェンジ内のグループ数 = 更新データ (EDIFACT ではグループは省略可能と適用しない ' として値を指定しない場合)</span><span class="sxs-lookup"><span data-stu-id="f1e10-121">Count of Groups in Interchange = Update Data (In EDIFACT Groups are optional and if not present, valued as ‘Not Applicable’)</span></span>  
  
-   <span data-ttu-id="f1e10-122">インターチェンジの受信ポート ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-122">Interchange Receive Port ID = Update Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="f1e10-123">受信インターチェンジへの応答で生成された各技術確認の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="f1e10-123">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="f1e10-124">送信パイプラインは、送信した各技術確認の状態レポート データ ストアでレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-124">The send pipeline creates a record in the status report data store for each technical acknowledgment that it sends.</span></span> <span data-ttu-id="f1e10-125">技術確認は、EDIFACT の場合、UCI セグメントのみで、X12 と CONTRL メッセージに TA1 です。</span><span class="sxs-lookup"><span data-stu-id="f1e10-125">The technical acknowledgement is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="f1e10-126">エントリに必要なほとんどのデータは、インターチェンジ ヘッダー/トレーラー セグメント (ISA/IEA または UNB/UNZ) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="f1e10-126">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="f1e10-127">その他のデータは、送信ポートのプロパティから入手できます。</span><span class="sxs-lookup"><span data-stu-id="f1e10-127">Other data is available from send port properties.</span></span> <span data-ttu-id="f1e10-128">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1e10-128">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f1e10-129">レコードの種類 = インターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="f1e10-129">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="f1e10-130">インターチェンジ確認方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="f1e10-130">Interchange ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="f1e10-131">インターチェンジの受信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="f1e10-131">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f1e10-132">インターチェンジの送信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="f1e10-132">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f1e10-133">インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-133">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-134">インターチェンジ制御 ID = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="f1e10-134">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f1e10-135">インターチェンジ確認状態 =\<想定または該当なし\>します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-135">Interchange ACK Status = \< Expected or Not Applicable\>.</span></span> <span data-ttu-id="f1e10-136">技術確認が構成されて、受信インターチェンジの状態の値または = が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1e10-136">If the technical ACK is configured or valued in the incoming interchange, status = Expected.</span></span> <span data-ttu-id="f1e10-137">それ以外の場合、状態 = 該当なし。</span><span class="sxs-lookup"><span data-stu-id="f1e10-137">Otherwise, status = Not Applicable.</span></span>  
  
-   <span data-ttu-id="f1e10-138">インターチェンジ確認制御 ID =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-138">Interchange ACK Control ID= \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-139">インターチェンジ確認日付 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-139">Interchange ACK Date = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-140">インターチェンジ確認時刻 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-140">Interchange ACK Time = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-141">確認/アクション コード =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-141">ACK/Action Code = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-142">確認通知コード =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-142">ACK Note Code = \<not valued\></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="f1e10-143">受信インターチェンジへの応答で生成された各技術確認の送信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="f1e10-143">Data Updated by the Send Pipeline for Each Technical Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="f1e10-144">送信パイプラインで送信する各技術確認用に、関連する受信インターチェンジの状態レポート エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-144">For each technical acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="f1e10-145">データのソースは、送信パイプラインによって作成されたインターチェンジのエンベロープになります。</span><span class="sxs-lookup"><span data-stu-id="f1e10-145">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="f1e10-146">EDI アセンブラーは、UCI および TA1 セグメントに、受信確認の内のデータを次のように使用して、データ ストアでレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-146">The EDI Assembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="f1e10-147">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="f1e10-147">Fields in ACK</span></span>|<span data-ttu-id="f1e10-148">データ ストア内のフィールド</span><span class="sxs-lookup"><span data-stu-id="f1e10-148">Fields in Data store</span></span>|<span data-ttu-id="f1e10-149">解説</span><span class="sxs-lookup"><span data-stu-id="f1e10-149">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="f1e10-150">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="f1e10-150">Interchange Sender ID</span></span>|<span data-ttu-id="f1e10-151">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="f1e10-151">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="f1e10-152">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="f1e10-152">Interchange Receiver ID</span></span>|<span data-ttu-id="f1e10-153">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="f1e10-153">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="f1e10-154">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="f1e10-154">Interchange Date</span></span>|-|  
|<span data-ttu-id="f1e10-155">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="f1e10-155">Interchange Control Number</span></span>|<span data-ttu-id="f1e10-156">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="f1e10-156">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="f1e10-157">インターチェンジ方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="f1e10-157">Interchange Direction = Receive</span></span>|<span data-ttu-id="f1e10-158">保存されたインターチェンジ シナリオの一意性に必要です。</span><span class="sxs-lookup"><span data-stu-id="f1e10-158">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="f1e10-159">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="f1e10-159">Record Type</span></span>|<span data-ttu-id="f1e10-160">インターチェンジ確認の状態</span><span class="sxs-lookup"><span data-stu-id="f1e10-160">Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="f1e10-161">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1e10-161">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f1e10-162">レコードの種類 = インターチェンジ確認状態</span><span class="sxs-lookup"><span data-stu-id="f1e10-162">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="f1e10-163">インターチェンジ確認方向 = 送信 - 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-163">Interchange ACK Direction = Send- Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-164">インターチェンジ確認状態 = 処理済みまたは送信 – 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-164">Interchange ACK Status = Processed or Sent – Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-165">インターチェンジの受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-165">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-166">インターチェンジの送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-166">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-167">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-167">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-168">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-168">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-169">インターチェンジ確認制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-169">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-170">インターチェンジ確認日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-170">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-171">インターチェンジ確認時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-171">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-172">確認/アクション コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-172">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-173">確認通知コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-173">ACK Note Code = Existing Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="f1e10-174">受信インターチェンジへの応答で生成された各機能確認の受信パイプラインによって格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="f1e10-174">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="f1e10-175">送信パイプラインは、送信した各機能確認の状態レポート データ ストアでレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-175">The send pipeline creates a record in the status report data store for each functional acknowledgment that it sends.</span></span> <span data-ttu-id="f1e10-176">送信パイプラインは、状態レポートのデータ ストアに (受信したインターチェンジへの応答) で送信される各機能確認のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-176">The send pipeline creates a record of each functional acknowledgment sent (in response to an interchange received) in the status report data store.</span></span> <span data-ttu-id="f1e10-177">EDIFACT に存在するグループがない場合は、1 つの機能確認は作成されます。</span><span class="sxs-lookup"><span data-stu-id="f1e10-177">If no group is present in EDIFACT, one functional ACK will still be created.</span></span> <span data-ttu-id="f1e10-178">機能確認状態レポート エントリは、機能グループ ヘッダーおよびトレーラ (GS/GE または UNG/UNE) から作成されます。</span><span class="sxs-lookup"><span data-stu-id="f1e10-178">The functional ACK status report entry will be populated from the functional group header/trailer (GS/GE or UNG/UNE).</span></span> <span data-ttu-id="f1e10-179">技術確認は、997 のメッセージを X12 と完全な CONTRL EDIFACT です。</span><span class="sxs-lookup"><span data-stu-id="f1e10-179">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="f1e10-180">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1e10-180">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f1e10-181">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="f1e10-181">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="f1e10-182">機能確認方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="f1e10-182">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="f1e10-183">機能確認状態 =\<想定または該当なし\>します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-183">Functional ACK Status = \< Expected or Not Applicable\>.</span></span> <span data-ttu-id="f1e10-184">PAM で機能確認のタブが選択されている場合、状態が予期されるに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f1e10-184">If the functional acknowledgment tab in PAM is selected, status will set to Expected.</span></span> <span data-ttu-id="f1e10-185">それ以外の場合、状態は、該当なし に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f1e10-185">Otherwise, status will be set to Not Applicable.</span></span>  
  
-   <span data-ttu-id="f1e10-186">インターチェンジの受信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="f1e10-186">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f1e10-187">インターチェンジの送信者 = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="f1e10-187">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f1e10-188">インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-188">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-189">インターチェンジ制御 ID = 更新データ (関連付けのために必要)</span><span class="sxs-lookup"><span data-stu-id="f1e10-189">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f1e10-190">グループ制御番号 = 更新データ (相関関係に必要です。</span><span class="sxs-lookup"><span data-stu-id="f1e10-190">Group Control Number = Update Data (required for correlation.</span></span> <span data-ttu-id="f1e10-191">EDIFACT のグループのセグメントにはこのフィールドが存在しない場合は unh.1)</span><span class="sxs-lookup"><span data-stu-id="f1e10-191">In EDIFACT if no group segments present this field is valued using UNH.1)</span></span>  
  
-   <span data-ttu-id="f1e10-192">機能 ID コード = 更新データが (しない値を持つ EDIFACT のグループが存在しない場合)</span><span class="sxs-lookup"><span data-stu-id="f1e10-192">Functional ID Code = Update Data (not valued in EDIFACT if group is not present)</span></span>  
  
-   <span data-ttu-id="f1e10-193">トランザクション セットの数 (グループ セグメントが存在しない場合に UNE.1 UNG/UNE が存在するときに、または UNZ.1 にマップされますこの EDIFACT) でデータを =</span><span class="sxs-lookup"><span data-stu-id="f1e10-193">Count of Transaction Sets = Data (in EDIFACT this is mapped to UNE.1 while UNG/UNE are present or UNZ.1 if no group segments are present)</span></span>  
  
-   <span data-ttu-id="f1e10-194">機能確認インターチェンジ制御 ID =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-194">Functional ACK Interchange Control ID= \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-195">機能確認インターチェンジ日付 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-195">Functional ACK Interchange Date = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-196">機能確認インターチェンジ時刻 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-196">Functional ACK Interchange Time = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-197">カウントの配信されたトランザクション セット =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-197">Count of Transaction Sets Delivered = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-198">カウントの受理されたトランザクション セット =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-198">Count of Transaction Sets Accepted = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-199">確認/アクション コード =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-199">ACK/Action Code = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-200">エラー/構文エラー コード =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-200">Error/Syntax Error Code  = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-201">追加の X12 確認エラー コード 2 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-201">Additional X12 ACK Error Code 2 = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-202">追加の X12 確認エラー コード 3 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-202">Additional X12 ACK Error Code 3 = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-203">追加の X12 確認エラー コード 4 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-203">Additional X12 ACK Error Code 4 = \<not valued\></span></span>  
  
-   <span data-ttu-id="f1e10-204">追加の X12 確認エラー コード 5 =\<値ではありません\></span><span class="sxs-lookup"><span data-stu-id="f1e10-204">Additional X12 ACK Error Code 5 = \<not valued\></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="f1e10-205">受信インターチェンジへの応答で生成された各機能確認の送信パイプラインによって更新されるデータ</span><span class="sxs-lookup"><span data-stu-id="f1e10-205">Data Updated by the Send Pipeline for Each Functional Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="f1e10-206">送信パイプラインで送信する各機能確認用に、関連する受信インターチェンジの状態レポート エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-206">For each functional acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="f1e10-207">データのソースは、送信パイプラインによって作成されたインターチェンジのエンベロープになります。</span><span class="sxs-lookup"><span data-stu-id="f1e10-207">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="f1e10-208">EDI アセンブラーはインターチェンジおよび受信の確認のグループ ヘッダー セグメント内のデータを次のように使用して、データ ストアでレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="f1e10-208">The EDI Assembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="f1e10-209">確認のフィールド</span><span class="sxs-lookup"><span data-stu-id="f1e10-209">Fields in ACK</span></span>|<span data-ttu-id="f1e10-210">データ ストア内のフィールド</span><span class="sxs-lookup"><span data-stu-id="f1e10-210">Fields in Data store</span></span>|<span data-ttu-id="f1e10-211">解説</span><span class="sxs-lookup"><span data-stu-id="f1e10-211">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="f1e10-212">インターチェンジの送信者 ID</span><span class="sxs-lookup"><span data-stu-id="f1e10-212">Interchange Sender ID</span></span>|<span data-ttu-id="f1e10-213">インターチェンジの受信者</span><span class="sxs-lookup"><span data-stu-id="f1e10-213">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="f1e10-214">インターチェンジの受信者 ID</span><span class="sxs-lookup"><span data-stu-id="f1e10-214">Interchange Receiver ID</span></span>|<span data-ttu-id="f1e10-215">インターチェンジの送信者</span><span class="sxs-lookup"><span data-stu-id="f1e10-215">Interchange Sender</span></span>|-|  
|<span data-ttu-id="f1e10-216">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="f1e10-216">Interchange Date</span></span>|<span data-ttu-id="f1e10-217">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="f1e10-217">Interchange Date</span></span>|-|  
|<span data-ttu-id="f1e10-218">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="f1e10-218">Interchange Control Number</span></span>|<span data-ttu-id="f1e10-219">インターチェンジ制御 ID</span><span class="sxs-lookup"><span data-stu-id="f1e10-219">Interchange Control ID</span></span>|-|  
|<span data-ttu-id="f1e10-220">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="f1e10-220">Group Control Number</span></span>|<span data-ttu-id="f1e10-221">グループ制御番号</span><span class="sxs-lookup"><span data-stu-id="f1e10-221">Group Control Number</span></span>|<span data-ttu-id="f1e10-222">EDIFACT では省略可能</span><span class="sxs-lookup"><span data-stu-id="f1e10-222">Optional in EDIFACT</span></span>|  
|-|<span data-ttu-id="f1e10-223">インターチェンジ方向 = 受信</span><span class="sxs-lookup"><span data-stu-id="f1e10-223">Interchange Direction = Receive</span></span>|<span data-ttu-id="f1e10-224">保存されたインターチェンジ シナリオの一意性に必要です。</span><span class="sxs-lookup"><span data-stu-id="f1e10-224">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="f1e10-225">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="f1e10-225">Record Type</span></span>|<span data-ttu-id="f1e10-226">機能確認状態</span><span class="sxs-lookup"><span data-stu-id="f1e10-226">Functional ACK Status</span></span>|-|  
  
 <span data-ttu-id="f1e10-227">格納されているデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1e10-227">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f1e10-228">レコードの種類 = 機能確認状態</span><span class="sxs-lookup"><span data-stu-id="f1e10-228">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="f1e10-229">機能確認方向 = 送信 – 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-229">Functional ACK Direction = Send – Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-230">機能確認状態 = 送信/処理済み-更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-230">Functional ACK Status = Sent/Processed – Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-231">インターチェンジの受信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-231">Interchange Receiver =  Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-232">インターチェンジの送信者 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-232">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-233">インターチェンジ日付 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-233">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-234">インターチェンジ制御 ID = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-234">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-235">グループ制御番号 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-235">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-236">機能 ID コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-236">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-237">トランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-237">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-238">機能確認インターチェンジ制御 ID = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-238">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-239">機能確認インターチェンジ日付 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-239">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-240">機能確認インターチェンジ時刻 = 更新データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-240">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="f1e10-241">受信したトランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-241">Count of Transaction Sets Received = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-242">受理トランザクション セットの数 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-242">Count of Transaction Sets Accepted = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-243">確認/アクション コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-243">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-244">エラー/構文エラー コード = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-244">Error/Syntax Error Code  = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-245">追加の X12 確認エラー コード 2 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-245">Additional X12 ACK Error Code 2 = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-246">追加の X12 確認エラー コード 3 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-246">Additional X12 ACK Error Code 3 = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-247">追加の X12 確認エラー コード 4 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-247">Additional X12 ACK Error Code 4 = Existing Data</span></span>  
  
-   <span data-ttu-id="f1e10-248">追加の X12 確認エラー コード 5 = 既存データ</span><span class="sxs-lookup"><span data-stu-id="f1e10-248">Additional X12 ACK Error Code 5 = Existing Data</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e10-249">参照</span><span class="sxs-lookup"><span data-stu-id="f1e10-249">See Also</span></span>  
 <span data-ttu-id="f1e10-250">[EDI および AS2 状態レポートのデータを格納する方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="f1e10-250">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="f1e10-251">送信 EDI メッセージのデータ格納方法</span><span class="sxs-lookup"><span data-stu-id="f1e10-251">How Data Is Stored for Outbound EDI Messages</span></span>](../core/how-data-is-stored-for-outbound-edi-messages.md)