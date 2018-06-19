---
title: EDI 状態レポートに格納されているデータ |Microsoft ドキュメント
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
ms.openlocfilehash: 9395cb3895675e586576088f3d257dbf4115948f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970624"
---
# <a name="data-stored-for-edi-status-reports"></a><span data-ttu-id="a2147-102">EDI 状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="a2147-102">Data Stored for EDI Status Reports</span></span>
<span data-ttu-id="a2147-103">2 つのレベルのレポートを EDI 状態レポートで利用可能: 最初の場合、**レポートをオンに**アグリーメント、および 2 番目の場合は、プロパティが選択されている、**ストア トランザクション セット/ペイロードを reporting**アグリーメントのプロパティが選択されます。</span><span class="sxs-lookup"><span data-stu-id="a2147-103">Two levels of reporting are available in EDI status reporting: the first if the **Turn ON Reporting** property is selected for an agreement, and the second if the **Store transaction set/payload reporting** property is selected for an agreement.</span></span> <span data-ttu-id="a2147-104">これらのプロパティで使用可能な**全般プロパティ**のページ、**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a2147-104">These properties are available in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span>  
  
## <a name="data-stored-if-edi-reporting-is-activated"></a><span data-ttu-id="a2147-105">EDI レポートがアクティブになっている場合に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="a2147-105">Data Stored If EDI Reporting Is Activated</span></span>  
 <span data-ttu-id="a2147-106">場合、**レポートをオンに**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての送信または受信したインターチェンジ、技術確認、および機能確認のレコードが保持されます。</span><span class="sxs-lookup"><span data-stu-id="a2147-106">If the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will keep a record of all sent or received interchanges, technical acknowledgments, and functional acknowledgments.</span></span>  
  
 <span data-ttu-id="a2147-107">受信したインターチェンジについて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="a2147-107">For a received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
-   <span data-ttu-id="a2147-108">受信したすべてのインターチェンジのレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-108">A record of all received interchanges.</span></span> <span data-ttu-id="a2147-109">EDI の状態レポートの UI に表示される最初の情報です。</span><span class="sxs-lookup"><span data-stu-id="a2147-109">This is the first information displayed in the status reporting UI for EDI.</span></span>  
  
-   <span data-ttu-id="a2147-110">インターチェンジに含まれているすべてのトランザクション セットのレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-110">A record of all transaction sets contained in the interchange.</span></span> <span data-ttu-id="a2147-111">ここには、トランザクション セットの格納が有効になっている場合に格納される詳細は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a2147-111">This does not include all the details that are stored when transaction-set storage is enabled.</span></span>  
  
-   <span data-ttu-id="a2147-112">受信したインターチェンジにあるすべての技術確認のレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-112">A record of all Technical acknowledgments present in the received interchange</span></span>  
  
-   <span data-ttu-id="a2147-113">受信したインターチェンジにあるすべての機能確認のレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-113">A record of all Functional acknowledgments present in the received interchange</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2147-114">インターチェンジに複数の機能グループが存在する場合、状態レポートの UI には複数の機能確認が格納されます。</span><span class="sxs-lookup"><span data-stu-id="a2147-114">If an interchange has multiple functional groups, multiple functional acknowledgments will be stored in the status reporting UI.</span></span> <span data-ttu-id="a2147-115">ただし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が 1 つのグループに対して重複する機能確認を受信した場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は状態レポートの UI に最後の機能確認だけを格納します。</span><span class="sxs-lookup"><span data-stu-id="a2147-115">However, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives duplicate functional acknowledgments for a group, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store only the last functional acknowledgment in the status reporting UI.</span></span>  
  
-   <span data-ttu-id="a2147-116">受信したインターチェンジに対して技術確認を生成する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a2147-116">Whether a technical acknowledgment needs to be generated for the received interchange</span></span>  
  
-   <span data-ttu-id="a2147-117">受信したトランザクション セットに対して機能確認を生成する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a2147-117">Whether functional acknowledgments need to be generated for the received transaction sets</span></span>  
  
 <span data-ttu-id="a2147-118">送信したインターチェンジについて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="a2147-118">For a sent interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
-   <span data-ttu-id="a2147-119">送信インターチェンジのレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-119">A record of the sent interchange</span></span>  
  
-   <span data-ttu-id="a2147-120">インターチェンジに含まれるすべてのトランザクション セットのレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-120">A record of all transaction sets contained in the interchange</span></span>  
  
-   <span data-ttu-id="a2147-121">送信したインターチェンジにあるすべての技術確認のレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-121">A record of all Technical acknowledgments present in the sent interchange</span></span>  
  
-   <span data-ttu-id="a2147-122">送信したインターチェンジにあるすべての機能確認のレコード。</span><span class="sxs-lookup"><span data-stu-id="a2147-122">A record of all Functional acknowledgments present in the sent interchange</span></span>  
  
 <span data-ttu-id="a2147-123">EDI 状態レポートの UI は、これらのレコードを関連付けて完全な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2147-123">EDI status reporting UI correlates these records to display complete information.</span></span> <span data-ttu-id="a2147-124">たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインターチェンジを受信し、元のメッセージの送信者に対して技術確認と機能確認を送信する必要がある場合、この情報を状態レポートの UI で簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a2147-124">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an interchange, and a technical acknowledgment and a functional acknowledgment need to be sent to the sender of the original message, you can easily find this information in the status reporting UI.</span></span>  
  
## <a name="data-stored-if-transaction-set-storage-is-enabled"></a><span data-ttu-id="a2147-125">トランザクション セットの格納が有効になっている場合に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="a2147-125">Data Stored If Transaction Set Storage Is Enabled</span></span>  
 <span data-ttu-id="a2147-126">場合、 **reporting 用メッセージ ペイロードを格納**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は送信または受信したインターチェンジに含まれるすべてのトランザクション セットの詳細を格納します。</span><span class="sxs-lookup"><span data-stu-id="a2147-126">If the **Store message payload for reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store details of all transaction sets found in a sent or received interchange.</span></span> <span data-ttu-id="a2147-127">このレベルの状態レポートには、EDI レポートがアクティブになっている場合に作成される第 1 レベル レポートのすべての情報に加えて、トランザクション セットに固有の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2147-127">This level of status reporting implements all of the first-level reporting performed if EDI reporting is activated, plus transaction-set specific information.</span></span> <span data-ttu-id="a2147-128">EDI 受信パイプラインと、BAM データベースに着信および発信グループ/トランザクション セットごとのパイプラインの作成のエントリを送信 (中に、"**ストア メッセージ ペイロード reporting**プロパティが選択されている)。</span><span class="sxs-lookup"><span data-stu-id="a2147-128">The EDI receive pipeline and send pipeline make entries in the BAM database for each incoming and outgoing Group/Transaction Set (while the "**Store message payload reporting** property is selected).</span></span> <span data-ttu-id="a2147-129">インターチェンジが拒否される場合は、エントリは作成されません。</span><span class="sxs-lookup"><span data-stu-id="a2147-129">If the interchange is rejected, no entry is made.</span></span>  
  
 <span data-ttu-id="a2147-130">送信または受信したインターチェンジについて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="a2147-130">For a sent or received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
-   <span data-ttu-id="a2147-131">トランザクション セットのコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="a2147-131">The transaction set content.</span></span> <span data-ttu-id="a2147-132">状態レポート UI でインターチェンジに含まれるトランザクション セットを参照し、実際のトランザクション セットのコンテンツを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a2147-132">In the status reporting UI, you can look at the transaction sets contained in an interchange, and then view the actual transaction set content.</span></span>  
  
-   <span data-ttu-id="a2147-133">トランザクション セットの詳細情報には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2147-133">More detailed information about a transaction set, including the following:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2147-134">情報</span><span class="sxs-lookup"><span data-stu-id="a2147-134">Information</span></span>|<span data-ttu-id="a2147-135">フィールドまたは値</span><span class="sxs-lookup"><span data-stu-id="a2147-135">Field or Value</span></span>|  
|<span data-ttu-id="a2147-136">ApplicationSender</span><span class="sxs-lookup"><span data-stu-id="a2147-136">ApplicationSender</span></span>|<span data-ttu-id="a2147-137">(GS02 または\<UNG2.1(UNG2.2)\></span><span class="sxs-lookup"><span data-stu-id="a2147-137">(GS02 or \<UNG2.1(UNG2.2)\></span></span>|  
|<span data-ttu-id="a2147-138">ApplicationReceiver</span><span class="sxs-lookup"><span data-stu-id="a2147-138">ApplicationReceiver</span></span>|<span data-ttu-id="a2147-139">GS03 または\<UNG3.1(UNG3.2)\></span><span class="sxs-lookup"><span data-stu-id="a2147-139">GS03 or \<UNG3.1(UNG3.2)\></span></span>|  
|<span data-ttu-id="a2147-140">GroupDate</span><span class="sxs-lookup"><span data-stu-id="a2147-140">GroupDate</span></span>|<span data-ttu-id="a2147-141">GS04 または UNG2.4</span><span class="sxs-lookup"><span data-stu-id="a2147-141">GS04 or UNG2.4</span></span>|  
|<span data-ttu-id="a2147-142">GroupTime</span><span class="sxs-lookup"><span data-stu-id="a2147-142">GroupTime</span></span>|<span data-ttu-id="a2147-143">GS05 または UNG2.5</span><span class="sxs-lookup"><span data-stu-id="a2147-143">GS05 or UNG2.5</span></span>|  
|<span data-ttu-id="a2147-144">TransactionSetId</span><span class="sxs-lookup"><span data-stu-id="a2147-144">TransactionSetId</span></span>|<span data-ttu-id="a2147-145">ST01 または UNH2.1 (AN 文字列)</span><span class="sxs-lookup"><span data-stu-id="a2147-145">ST01 or  UNH2.1 (AN string)</span></span>|  
|<span data-ttu-id="a2147-146">InterchangeControlNo</span><span class="sxs-lookup"><span data-stu-id="a2147-146">InterchangeControlNo</span></span>|<span data-ttu-id="a2147-147">ISA13</span><span class="sxs-lookup"><span data-stu-id="a2147-147">ISA13</span></span>|  
|<span data-ttu-id="a2147-148">GroupControlNo</span><span class="sxs-lookup"><span data-stu-id="a2147-148">GroupControlNo</span></span>|<span data-ttu-id="a2147-149">GS06</span><span class="sxs-lookup"><span data-stu-id="a2147-149">GS06</span></span>|  
|<span data-ttu-id="a2147-150">BtsDocType</span><span class="sxs-lookup"><span data-stu-id="a2147-150">BtsDocType</span></span>|<span data-ttu-id="a2147-151">NameSpace + ルート ノード名</span><span class="sxs-lookup"><span data-stu-id="a2147-151">NameSpace + Root node name</span></span>|  
|<span data-ttu-id="a2147-152">TransactionSetControlID</span><span class="sxs-lookup"><span data-stu-id="a2147-152">TransactionSetControlID</span></span>|<span data-ttu-id="a2147-153">ST02 または UNH1</span><span class="sxs-lookup"><span data-stu-id="a2147-153">ST02 or UNH1</span></span>|  
|<span data-ttu-id="a2147-154">TransactionSetStatus</span><span class="sxs-lookup"><span data-stu-id="a2147-154">TransactionSetStatus</span></span>|<span data-ttu-id="a2147-155">Accepted、AcceptedWithError、または Rejected</span><span class="sxs-lookup"><span data-stu-id="a2147-155">Accepted, AcceptedWithError, or Rejected</span></span>|  
|<span data-ttu-id="a2147-156">Direction</span><span class="sxs-lookup"><span data-stu-id="a2147-156">Direction</span></span>|<span data-ttu-id="a2147-157">Send または Receive</span><span class="sxs-lookup"><span data-stu-id="a2147-157">Send or Receive</span></span>|  
|<span data-ttu-id="a2147-158">BtsProcessingTime</span><span class="sxs-lookup"><span data-stu-id="a2147-158">BtsProcessingTime</span></span>|<span data-ttu-id="a2147-159">受信側: BTSReceiveTime (ローカル時刻) (パイプラインで設定された時刻)</span><span class="sxs-lookup"><span data-stu-id="a2147-159">On receive side: BTSReceiveTime (local time) as stamped in the Pipeline</span></span><br /><br /> <span data-ttu-id="a2147-160">送信側: BTSSendTime (ローカル時刻) (ASM コンポーネントによってエンベロープに設定された時刻)</span><span class="sxs-lookup"><span data-stu-id="a2147-160">On send side: BTSSendTime as (local time) stamped on the envelope by the ASM component</span></span>|  
|<span data-ttu-id="a2147-161">BTS.MessageId</span><span class="sxs-lookup"><span data-stu-id="a2147-161">BTS.MessageId</span></span>|<span data-ttu-id="a2147-162">受信側: メッセージ プロパティの BTSMessageId</span><span class="sxs-lookup"><span data-stu-id="a2147-162">On receive side: BTSMessageId from message properties</span></span><br /><br /> <span data-ttu-id="a2147-163">送信側 : </span><span class="sxs-lookup"><span data-stu-id="a2147-163">On send side:</span></span><br /><br /> <span data-ttu-id="a2147-164">単一のトランザクション セットの場合: BTSMessageId</span><span class="sxs-lookup"><span data-stu-id="a2147-164">For single Transaction Set: BTSMessageId</span></span><br /><br /> <span data-ttu-id="a2147-165">送信バッチの: (バッチ メッセージの BTSMessageId でなく) のバッチで各メッセージの TransactionSet BTSMessageId**注:** 記憶域のみ – はない UI に表示します。</span><span class="sxs-lookup"><span data-stu-id="a2147-165">For outbound batch: TransactionSet BTSMessageId for each individual message in batch (not the BTSMessageId for the batch message) **Note:**  Storage only – will not be displayed in UI.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2147-166">参照</span><span class="sxs-lookup"><span data-stu-id="a2147-166">See Also</span></span>  
 <span data-ttu-id="a2147-167">[格納されている EDI および AS2 状態レポートのデータ](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="a2147-167">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="a2147-168">[格納されているバッチの状態レポートのデータ](../core/data-stored-for-batching-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="a2147-168">[Data Stored for Batching Status Reports](../core/data-stored-for-batching-status-reports.md) </span></span>  
 [<span data-ttu-id="a2147-169">AS2 状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="a2147-169">Data Stored for AS2 Status Reports</span></span>](../core/data-stored-for-as2-status-reports.md)