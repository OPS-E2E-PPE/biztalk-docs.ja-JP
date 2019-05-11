---
title: EDI または AS2 状態レポートの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60968c3d-6329-411f-9f10-1dd4a6cc9d79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 699218479eb0d8bb5a37eb21afc4eb814cf51233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389351"
---
# <a name="displaying-an-edi-or-as2-status-report"></a><span data-ttu-id="2bc2d-102">EDI または AS2 状態レポートの表示</span><span class="sxs-lookup"><span data-stu-id="2bc2d-102">Displaying an EDI or AS2 Status Report</span></span>
<span data-ttu-id="2bc2d-103">EDI および AS2 状態レポートを有効にすると、次の状態レポートへのアクセスが用意されます。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-103">When EDI and AS2 status reports are enabled, you will have access to the following status reports:</span></span>  
  
|<span data-ttu-id="2bc2d-104">レポートの種類</span><span class="sxs-lookup"><span data-stu-id="2bc2d-104">Type of Report</span></span>|<span data-ttu-id="2bc2d-105">上位レベルの状態レポート</span><span class="sxs-lookup"><span data-stu-id="2bc2d-105">Higher-level status report</span></span>|<span data-ttu-id="2bc2d-106">下位レベルの状態レポート</span><span class="sxs-lookup"><span data-stu-id="2bc2d-106">Lower-level status report</span></span>|  
|--------------------|---------------------------------|--------------------------------|  
|<span data-ttu-id="2bc2d-107">EDI </span><span class="sxs-lookup"><span data-stu-id="2bc2d-107">EDI</span></span>|<span data-ttu-id="2bc2d-108">EDI インターチェンジし、関連する ACK の状態</span><span class="sxs-lookup"><span data-stu-id="2bc2d-108">EDI Interchange and Correlated ACK Status</span></span>|<span data-ttu-id="2bc2d-109">-インターチェンジの状態と確認の詳細</span><span class="sxs-lookup"><span data-stu-id="2bc2d-109">- Interchange Status and ACK Details</span></span><br /><br /> <span data-ttu-id="2bc2d-110">トランザクション セットの詳細</span><span class="sxs-lookup"><span data-stu-id="2bc2d-110">- Transaction Set Details</span></span><br /><br /> <span data-ttu-id="2bc2d-111">EDI メッセージの内容</span><span class="sxs-lookup"><span data-stu-id="2bc2d-111">- EDI Message Content</span></span>|  
|<span data-ttu-id="2bc2d-112">EDI </span><span class="sxs-lookup"><span data-stu-id="2bc2d-112">EDI</span></span>|<span data-ttu-id="2bc2d-113">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="2bc2d-113">Batch Status</span></span>|-|  
|<span data-ttu-id="2bc2d-114">EDI </span><span class="sxs-lookup"><span data-stu-id="2bc2d-114">EDI</span></span>|<span data-ttu-id="2bc2d-115">インターチェンジの集計レポート</span><span class="sxs-lookup"><span data-stu-id="2bc2d-115">Interchange Aggregation Report</span></span>|-|  
|<span data-ttu-id="2bc2d-116">EDI </span><span class="sxs-lookup"><span data-stu-id="2bc2d-116">EDI</span></span>|<span data-ttu-id="2bc2d-117">トランザクション セットの集計レポート</span><span class="sxs-lookup"><span data-stu-id="2bc2d-117">Transaction Set Aggregation Report</span></span>|-|  
|<span data-ttu-id="2bc2d-118">AS2</span><span class="sxs-lookup"><span data-stu-id="2bc2d-118">AS2</span></span>|<span data-ttu-id="2bc2d-119">AS2 メッセージおよび関連する MDN の状態</span><span class="sxs-lookup"><span data-stu-id="2bc2d-119">AS2 Message and Correlated MDN Status</span></span>|<span data-ttu-id="2bc2d-120">AS2 メッセージの内容</span><span class="sxs-lookup"><span data-stu-id="2bc2d-120">AS2 Message Content</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="2bc2d-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="2bc2d-121">Prerequisites</span></span>  
 <span data-ttu-id="2bc2d-122">次に、このトピックの手順を実行するための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-122">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="2bc2d-123">メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループの状態レポートをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to customize any of the status reports.</span></span>  
  
- <span data-ttu-id="2bc2d-124">メンバーとしてログオンしている場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループ、読み取り専用の状態レポートを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-124">If you are logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, you can display read-only status reports.</span></span>  
  
## <a name="display-an-edi-or-as2-status-report"></a><span data-ttu-id="2bc2d-125">EDI または AS2 状態レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-125">Display an EDI or AS2 status report</span></span>  
  
1. <span data-ttu-id="2bc2d-126">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、 **BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node.</span></span>  
  
2. <span data-ttu-id="2bc2d-127">**グループ ハブ**のタブ、**グループの概要**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ページの下部に移動します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-127">In the **Group Hub** tab of the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, move to the bottom of the page.</span></span>  
  
3. <span data-ttu-id="2bc2d-128">表示する、 **EDI インターチェンジと関連する ACK の状態**レポート、次のように続行します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-128">To display the **EDI Interchange and Correlated ACK Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="2bc2d-129">クリックして**EDI インターチェンジと関連する ACK の状態**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-129">Click **EDI Interchange and Correlated ACK Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="2bc2d-130">インターチェンジおよびその関連確認の詳細を表示するには、クエリの結果のエントリを右クリックして、 **EDI インターチェンジと関連する ACK の状態**レポートとクリックして**インターチェンジの状態と確認詳細**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-130">To display details of an interchange and its correlated acknowledgments, right-click an entry in the query results of the **EDI Interchange and Correlated ACK Status** report, and then click **Interchange status and ack details**.</span></span>  
  
   3.  <span data-ttu-id="2bc2d-131">トランザクション セットの詳細を表示する、レポートを閉じインターチェンジ状態と確認の詳細を返す、 **EDI インターチェンジと関連する ACK の状態**詳細レポート。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-131">To display details of a transaction set, close the Interchange status and ack details report, returning to the **EDI Interchange and Correlated ACK Status** details report.</span></span> <span data-ttu-id="2bc2d-132">クエリの結果内のエントリを右クリックし、をクリックし、**トランザクション セットの詳細**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-132">Right-click an entry in the query results, and then click **Transaction Set Details**.</span></span>  
  
   4.  <span data-ttu-id="2bc2d-133">ヘッダーおよびトランザクション セットのペイロードに関する詳細を表示するには、内のエントリを右クリックし、**トランザクション セットの詳細**レポートとクリックして**トランザクション セット**。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-133">To display details about the headers and payload of a transaction set, right-click an entry in the **Transaction Set Details** report, and then click **View Transaction Set Content**.</span></span>  
  
   5.  <span data-ttu-id="2bc2d-134">トランザクション セットを含むインターチェンジに関するデータを表示するには、エントリを右クリックして、**トランザクション セットの詳細**レポートとクリックして**インターチェンジ/確認の状態**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-134">To display data about the interchange containing the transaction set, right-click an entry in the **Transaction Set Details** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="2bc2d-135">トランザクション セットを含むインターチェンジは、インターチェンジ/確認の状態レポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-135">The interchange containing the transaction set will be highlighted in the Interchange/ACK Status report.</span></span>  
  
4. <span data-ttu-id="2bc2d-136">表示する、**バッチの状態**レポート、次のように続行します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-136">To display the **Batch Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="2bc2d-137">をクリックして**バッチ ステータス**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-137">Click **Batch Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="2bc2d-138">内のバッチ エントリに関連付けられている完了したバッチを表示する、**バッチ ステータス**レポート、エントリを右クリックし、クリックして**完了済みのバッチ**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-138">To display the completed batches associated with a batch entry in the **Batch Status** report, right-click the entry and then click **Completed Batches**.</span></span>  
  
   3.  <span data-ttu-id="2bc2d-139">完了したバッチ インターチェンジに関するデータを表示するには、内のインターチェンジを右クリックし、**完了済みバッチ**レポートとクリックして**インターチェンジ/確認の状態**。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-139">To display data about a completed batched interchange, right-click the interchange in the **Completed Batch** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="2bc2d-140">バッチ インターチェンジのエントリは、インターチェンジ/確認の状態レポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-140">The entry for the batched interchange will be highlighted in the Interchange/ACK Status report.</span></span>  
  
5. <span data-ttu-id="2bc2d-141">表示する、**インターチェンジの集計レポート**、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-141">To display the **Interchange Aggregation Report**, proceed as follows:</span></span>  
  
   -   <span data-ttu-id="2bc2d-142">クリックして**インターチェンジの集計レポート**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-142">Click **Interchange Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
6. <span data-ttu-id="2bc2d-143">表示する、**トランザクション セットの集計レポート**、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-143">To display the **Transaction Set Aggregation Report**, proceed as follows:</span></span>  
  
   -   <span data-ttu-id="2bc2d-144">クリックして**トランザクション セットの集計レポート**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-144">Click **Transaction Set Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
7. <span data-ttu-id="2bc2d-145">表示する、 **AS2 メッセージおよび関連する MDN 状態**レポート、次のように続行します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-145">To display the **AS2 Message and Correlated MDN Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="2bc2d-146">クリックして**AS2 メッセージおよび関連する MDN 状態**で、 **EDIINT 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-146">Click **AS2 Message and Correlated MDN Status** in the **EDIINT Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="2bc2d-147">AS2 メッセージを EDI インターチェンジの状態を表示するには、エントリを右クリックして、 **AS2 メッセージおよび関連する MDN 状態**レポートとクリックして**インターチェンジ/確認の状態**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-147">To display the status of the EDI interchange in an AS2 message, right-click an entry in the **AS2 Message and Correlated MDN Status** report, and then click **Interchange/ACK Status**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="2bc2d-148">EDI 状態と AS2 状態の関連付けの方法の詳細については、の「の関連付け、AS2 メッセージと EDI ペイロードの」セクションを参照してください。 [AS2 メッセージおよび関連する MDN 状態レポート](../core/as2-message-and-correlated-mdn-status-report.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-148">For more information on how EDI status and AS2 status are correlated, see the "Correlating an AS2 Message with its EDI Payload" section of [AS2 Message and Correlated MDN Status Report](../core/as2-message-and-correlated-mdn-status-report.md).</span></span>  
  
   3.  <span data-ttu-id="2bc2d-149">AS2 メッセージをワイヤ形式で表示する、または MDN の AS2 状態レポート エントリを右クリックし、**メッセージのワイヤ形式**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-149">To display an AS2 message in wire format, right-click an entry in the AS2/MDN Status report, and then click **Message Wire Format**.</span></span>  
  
   4.  <span data-ttu-id="2bc2d-150">AS2 メッセージをデコードされた形式で表示する、または MDN の AS2 状態レポート エントリを右クリックし、順にクリックします**メッセージのデコードされた形式**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-150">To display an AS2 message in decoded format, right-click an entry in the AS2/MDN Status report, and then click **Message Decoded Format**.</span></span>  
  
   5.  <span data-ttu-id="2bc2d-151">MDN メッセージを表示する、または MDN の AS2 状態レポート エントリを右クリックし、順にクリックします**Mdn メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="2bc2d-151">To display an MDN message, right-click an entry in the AS2/MDN Status report, and then click **Mdn Message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc2d-152">参照</span><span class="sxs-lookup"><span data-stu-id="2bc2d-152">See Also</span></span>  
 <span data-ttu-id="2bc2d-153">[EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="2bc2d-153">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="2bc2d-154">[EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="2bc2d-154">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="2bc2d-155">[EDI および AS2 状態レポートを有効にします。](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="2bc2d-155">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="2bc2d-156">EDI および AS2 状態レポートの構成</span><span class="sxs-lookup"><span data-stu-id="2bc2d-156">Configuring an EDI and AS2 Status Report</span></span>](../core/configuring-an-edi-and-as2-status-report.md)