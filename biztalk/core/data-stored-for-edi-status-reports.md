---
title: EDI 状態レポート用に格納されているデータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec66e4d7-2694-499f-a60c-2f80fe643e12
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 498af225f64d58cdff962b34f276814f55f4498e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389790"
---
# <a name="data-stored-for-edi-status-reports"></a><span data-ttu-id="37e01-102">EDI 状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="37e01-102">Data Stored for EDI Status Reports</span></span>
<span data-ttu-id="37e01-103">レポートの 2 つのレベルが EDI 状態レポートで使用可能: 最初の場合、**レポートを有効にする**アグリーメント、および 2 番目の場合は、プロパティが選択されている、**ストア トランザクション セット/ペイロードを reporting**アグリーメントのプロパティが選択されます。</span><span class="sxs-lookup"><span data-stu-id="37e01-103">Two levels of reporting are available in EDI status reporting: the first if the **Turn ON Reporting** property is selected for an agreement, and the second if the **Store transaction set/payload reporting** property is selected for an agreement.</span></span> <span data-ttu-id="37e01-104">これらのプロパティは、**全般プロパティ**のページ、**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="37e01-104">These properties are available in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span>  
  
## <a name="data-stored-if-edi-reporting-is-activated"></a><span data-ttu-id="37e01-105">EDI レポートが有効な場合に格納されているデータ</span><span class="sxs-lookup"><span data-stu-id="37e01-105">Data Stored If EDI Reporting Is Activated</span></span>  
 <span data-ttu-id="37e01-106">場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての送信または受信したインターチェンジ、技術確認、および機能確認のレコードが保持されます。</span><span class="sxs-lookup"><span data-stu-id="37e01-106">If the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will keep a record of all sent or received interchanges, technical acknowledgments, and functional acknowledgments.</span></span>  
  
 <span data-ttu-id="37e01-107">受信したインターチェンジの場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="37e01-107">For a received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
- <span data-ttu-id="37e01-108">インターチェンジを受信したすべての記録します。</span><span class="sxs-lookup"><span data-stu-id="37e01-108">A record of all received interchanges.</span></span> <span data-ttu-id="37e01-109">これは、最初に状態レポートの EDI の UI に表示される情報です。</span><span class="sxs-lookup"><span data-stu-id="37e01-109">This is the first information displayed in the status reporting UI for EDI.</span></span>  
  
- <span data-ttu-id="37e01-110">インターチェンジに含まれているすべてのトランザクション セットのレコード。</span><span class="sxs-lookup"><span data-stu-id="37e01-110">A record of all transaction sets contained in the interchange.</span></span> <span data-ttu-id="37e01-111">これは、トランザクション セットの格納が有効な場合に格納されているすべての詳細には含まれません。</span><span class="sxs-lookup"><span data-stu-id="37e01-111">This does not include all the details that are stored when transaction-set storage is enabled.</span></span>  
  
- <span data-ttu-id="37e01-112">受信したインターチェンジにあるすべての技術確認のレコード</span><span class="sxs-lookup"><span data-stu-id="37e01-112">A record of all Technical acknowledgments present in the received interchange</span></span>  
  
- <span data-ttu-id="37e01-113">受信したインターチェンジにあるすべての機能確認のレコード</span><span class="sxs-lookup"><span data-stu-id="37e01-113">A record of all Functional acknowledgments present in the received interchange</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="37e01-114">インターチェンジに複数の機能グループがある場合は、複数の機能確認は状態レポート UI に格納されます。</span><span class="sxs-lookup"><span data-stu-id="37e01-114">If an interchange has multiple functional groups, multiple functional acknowledgments will be stored in the status reporting UI.</span></span> <span data-ttu-id="37e01-115">ただし場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、重複する機能確認を受け取る[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状態レポート UI に、最後の機能確認だけを格納します。</span><span class="sxs-lookup"><span data-stu-id="37e01-115">However, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives duplicate functional acknowledgments for a group, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store only the last functional acknowledgment in the status reporting UI.</span></span>  
  
- <span data-ttu-id="37e01-116">技術確認を受信したインターチェンジに対して生成される必要があるかどうか</span><span class="sxs-lookup"><span data-stu-id="37e01-116">Whether a technical acknowledgment needs to be generated for the received interchange</span></span>  
  
- <span data-ttu-id="37e01-117">機能確認を受信したトランザクション セットに対して生成される必要があるかどうか</span><span class="sxs-lookup"><span data-stu-id="37e01-117">Whether functional acknowledgments need to be generated for the received transaction sets</span></span>  
  
  <span data-ttu-id="37e01-118">送信インターチェンジの場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="37e01-118">For a sent interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
- <span data-ttu-id="37e01-119">送信インターチェンジのレコード</span><span class="sxs-lookup"><span data-stu-id="37e01-119">A record of the sent interchange</span></span>  
  
- <span data-ttu-id="37e01-120">インターチェンジに含まれているすべてのトランザクション セットのレコード</span><span class="sxs-lookup"><span data-stu-id="37e01-120">A record of all transaction sets contained in the interchange</span></span>  
  
- <span data-ttu-id="37e01-121">送信インターチェンジにあるすべての技術確認のレコード</span><span class="sxs-lookup"><span data-stu-id="37e01-121">A record of all Technical acknowledgments present in the sent interchange</span></span>  
  
- <span data-ttu-id="37e01-122">送信インターチェンジにあるすべての機能確認のレコード</span><span class="sxs-lookup"><span data-stu-id="37e01-122">A record of all Functional acknowledgments present in the sent interchange</span></span>  
  
  <span data-ttu-id="37e01-123">EDI 状態レポート UI には、完全な情報を表示するこれらのレコードがによって関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="37e01-123">EDI status reporting UI correlates these records to display complete information.</span></span> <span data-ttu-id="37e01-124">たとえば場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信インターチェンジ、技術確認と状態レポート UI に、この情報を簡単に見つけることができます、元のメッセージの送信者に送信する機能確認が必要です。</span><span class="sxs-lookup"><span data-stu-id="37e01-124">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an interchange, and a technical acknowledgment and a functional acknowledgment need to be sent to the sender of the original message, you can easily find this information in the status reporting UI.</span></span>  
  
## <a name="data-stored-if-transaction-set-storage-is-enabled"></a><span data-ttu-id="37e01-125">トランザクション セットの格納が有効になっている場合に格納されているデータ</span><span class="sxs-lookup"><span data-stu-id="37e01-125">Data Stored If Transaction Set Storage Is Enabled</span></span>  
 <span data-ttu-id="37e01-126">場合、**メッセージ ペイロードを格納するレポートの**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は送信または受信したインターチェンジにあるすべてのトランザクション セットの詳細を格納します。</span><span class="sxs-lookup"><span data-stu-id="37e01-126">If the **Store message payload for reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store details of all transaction sets found in a sent or received interchange.</span></span> <span data-ttu-id="37e01-127">このレベルの状態レポートでは、すべての EDI レポートがアクティブの場合に実行される、レポートの最初のレベルとトランザクション セット固有の情報を実装します。</span><span class="sxs-lookup"><span data-stu-id="37e01-127">This level of status reporting implements all of the first-level reporting performed if EDI reporting is activated, plus transaction-set specific information.</span></span> <span data-ttu-id="37e01-128">EDI 受信パイプラインとパイプライン作成のエントリを BAM データベースに受信および送信グループ/トランザクション セットごとの送信 (中に、"**ストア メッセージ ペイロード reporting**プロパティが選択されている)。</span><span class="sxs-lookup"><span data-stu-id="37e01-128">The EDI receive pipeline and send pipeline make entries in the BAM database for each incoming and outgoing Group/Transaction Set (while the "**Store message payload reporting** property is selected).</span></span> <span data-ttu-id="37e01-129">インターチェンジが拒否された場合、エントリは行われません。</span><span class="sxs-lookup"><span data-stu-id="37e01-129">If the interchange is rejected, no entry is made.</span></span>  
  
 <span data-ttu-id="37e01-130">送信または受信したインターチェンジの場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="37e01-130">For a sent or received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
-   <span data-ttu-id="37e01-131">トランザクション セットのコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="37e01-131">The transaction set content.</span></span> <span data-ttu-id="37e01-132">レポートの UI 状態で、インターチェンジに含まれるトランザクション セットを見てし、実際のトランザクション セットのコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="37e01-132">In the status reporting UI, you can look at the transaction sets contained in an interchange, and then view the actual transaction set content.</span></span>  
  
-   <span data-ttu-id="37e01-133">については、次を含む、トランザクション セットの詳細。</span><span class="sxs-lookup"><span data-stu-id="37e01-133">More detailed information about a transaction set, including the following:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37e01-134">[情報]</span><span class="sxs-lookup"><span data-stu-id="37e01-134">Information</span></span>|<span data-ttu-id="37e01-135">フィールドまたは値</span><span class="sxs-lookup"><span data-stu-id="37e01-135">Field or Value</span></span>|  
|<span data-ttu-id="37e01-136">ApplicationSender</span><span class="sxs-lookup"><span data-stu-id="37e01-136">ApplicationSender</span></span>|<span data-ttu-id="37e01-137">(GS02 または\<UNG2.1(UNG2.2)\></span><span class="sxs-lookup"><span data-stu-id="37e01-137">(GS02 or \<UNG2.1(UNG2.2)\></span></span>|  
|<span data-ttu-id="37e01-138">ApplicationReceiver</span><span class="sxs-lookup"><span data-stu-id="37e01-138">ApplicationReceiver</span></span>|<span data-ttu-id="37e01-139">GS03 または\<UNG3.1(UNG3.2)\></span><span class="sxs-lookup"><span data-stu-id="37e01-139">GS03 or \<UNG3.1(UNG3.2)\></span></span>|  
|<span data-ttu-id="37e01-140">GroupDate</span><span class="sxs-lookup"><span data-stu-id="37e01-140">GroupDate</span></span>|<span data-ttu-id="37e01-141">GS04 または UNG2.4</span><span class="sxs-lookup"><span data-stu-id="37e01-141">GS04 or UNG2.4</span></span>|  
|<span data-ttu-id="37e01-142">GroupTime</span><span class="sxs-lookup"><span data-stu-id="37e01-142">GroupTime</span></span>|<span data-ttu-id="37e01-143">GS05 または UNG2.5</span><span class="sxs-lookup"><span data-stu-id="37e01-143">GS05 or UNG2.5</span></span>|  
|<span data-ttu-id="37e01-144">TransactionSetId</span><span class="sxs-lookup"><span data-stu-id="37e01-144">TransactionSetId</span></span>|<span data-ttu-id="37e01-145">ST01 または UNH2.1 (AN 文字列)</span><span class="sxs-lookup"><span data-stu-id="37e01-145">ST01 or  UNH2.1 (AN string)</span></span>|  
|<span data-ttu-id="37e01-146">InterchangeControlNo</span><span class="sxs-lookup"><span data-stu-id="37e01-146">InterchangeControlNo</span></span>|<span data-ttu-id="37e01-147">ISA13</span><span class="sxs-lookup"><span data-stu-id="37e01-147">ISA13</span></span>|  
|<span data-ttu-id="37e01-148">GroupControlNo</span><span class="sxs-lookup"><span data-stu-id="37e01-148">GroupControlNo</span></span>|<span data-ttu-id="37e01-149">GS06</span><span class="sxs-lookup"><span data-stu-id="37e01-149">GS06</span></span>|  
|<span data-ttu-id="37e01-150">BtsDocType</span><span class="sxs-lookup"><span data-stu-id="37e01-150">BtsDocType</span></span>|<span data-ttu-id="37e01-151">NameSpace + ルート ノード名</span><span class="sxs-lookup"><span data-stu-id="37e01-151">NameSpace + Root node name</span></span>|  
|<span data-ttu-id="37e01-152">TransactionSetControlID</span><span class="sxs-lookup"><span data-stu-id="37e01-152">TransactionSetControlID</span></span>|<span data-ttu-id="37e01-153">ST02 または UNH1</span><span class="sxs-lookup"><span data-stu-id="37e01-153">ST02 or UNH1</span></span>|  
|<span data-ttu-id="37e01-154">TransactionSetStatus</span><span class="sxs-lookup"><span data-stu-id="37e01-154">TransactionSetStatus</span></span>|<span data-ttu-id="37e01-155">Accepted、AcceptedWithError、または拒否</span><span class="sxs-lookup"><span data-stu-id="37e01-155">Accepted, AcceptedWithError, or Rejected</span></span>|  
|<span data-ttu-id="37e01-156">Direction</span><span class="sxs-lookup"><span data-stu-id="37e01-156">Direction</span></span>|<span data-ttu-id="37e01-157">送信または受信</span><span class="sxs-lookup"><span data-stu-id="37e01-157">Send or Receive</span></span>|  
|<span data-ttu-id="37e01-158">BtsProcessingTime</span><span class="sxs-lookup"><span data-stu-id="37e01-158">BtsProcessingTime</span></span>|<span data-ttu-id="37e01-159">受信側。Btsreceivetime (ローカル時刻)、パイプラインで設定された時刻</span><span class="sxs-lookup"><span data-stu-id="37e01-159">On receive side: BTSReceiveTime (local time) as stamped in the Pipeline</span></span><br /><br /> <span data-ttu-id="37e01-160">送信側。ASM コンポーネントによってエンベロープに設定 (ローカル時刻) BTSSendTime</span><span class="sxs-lookup"><span data-stu-id="37e01-160">On send side: BTSSendTime as (local time) stamped on the envelope by the ASM component</span></span>|  
|<span data-ttu-id="37e01-161">BTS.MessageId</span><span class="sxs-lookup"><span data-stu-id="37e01-161">BTS.MessageId</span></span>|<span data-ttu-id="37e01-162">受信側。メッセージ プロパティの BTSMessageId</span><span class="sxs-lookup"><span data-stu-id="37e01-162">On receive side: BTSMessageId from message properties</span></span><br /><br /> <span data-ttu-id="37e01-163">送信側。</span><span class="sxs-lookup"><span data-stu-id="37e01-163">On send side:</span></span><br /><br /> <span data-ttu-id="37e01-164">トランザクションの 1 つの設定。BTSMessageId</span><span class="sxs-lookup"><span data-stu-id="37e01-164">For single Transaction Set: BTSMessageId</span></span><br /><br /> <span data-ttu-id="37e01-165">送信バッチの場合。バッチ (バッチ メッセージの BTSMessageId でなく) で各メッセージの TransactionSet BTSMessageId**に注意してください。** 記憶域のみ – はない UI に表示します。</span><span class="sxs-lookup"><span data-stu-id="37e01-165">For outbound batch: TransactionSet BTSMessageId for each individual message in batch (not the BTSMessageId for the batch message) **Note:**  Storage only – will not be displayed in UI.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37e01-166">参照</span><span class="sxs-lookup"><span data-stu-id="37e01-166">See Also</span></span>  
 <span data-ttu-id="37e01-167">[EDI および AS2 状態レポートの格納データ](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="37e01-167">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="37e01-168">[バッチの状態レポートの格納されているデータ](../core/data-stored-for-batching-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="37e01-168">[Data Stored for Batching Status Reports](../core/data-stored-for-batching-status-reports.md) </span></span>  
 [<span data-ttu-id="37e01-169">AS2 状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="37e01-169">Data Stored for AS2 Status Reports</span></span>](../core/data-stored-for-as2-status-reports.md)