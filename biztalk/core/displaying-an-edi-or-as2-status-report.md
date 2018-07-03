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
ms.openlocfilehash: a729e089c3d833d7bf8d8b87ebabeec0743b358a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018636"
---
# <a name="displaying-an-edi-or-as2-status-report"></a><span data-ttu-id="eb492-102">EDI または AS2 状態レポートの表示</span><span class="sxs-lookup"><span data-stu-id="eb492-102">Displaying an EDI or AS2 Status Report</span></span>
<span data-ttu-id="eb492-103">EDI 状態レポートおよび AS2 状態レポートが有効になっている場合は、次の状態レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eb492-103">When EDI and AS2 status reports are enabled, you will have access to the following status reports:</span></span>  
  
|<span data-ttu-id="eb492-104">レポートの種類</span><span class="sxs-lookup"><span data-stu-id="eb492-104">Type of Report</span></span>|<span data-ttu-id="eb492-105">上位レベルの状態レポート</span><span class="sxs-lookup"><span data-stu-id="eb492-105">Higher-level status report</span></span>|<span data-ttu-id="eb492-106">下位レベルの状態レポート</span><span class="sxs-lookup"><span data-stu-id="eb492-106">Lower-level status report</span></span>|  
|--------------------|---------------------------------|--------------------------------|  
|<span data-ttu-id="eb492-107">EDI </span><span class="sxs-lookup"><span data-stu-id="eb492-107">EDI</span></span>|<span data-ttu-id="eb492-108">EDI インターチェンジと関連する ACK の状態</span><span class="sxs-lookup"><span data-stu-id="eb492-108">EDI Interchange and Correlated ACK Status</span></span>|<span data-ttu-id="eb492-109">-インターチェンジの状態と確認の詳細</span><span class="sxs-lookup"><span data-stu-id="eb492-109">- Interchange Status and ACK Details</span></span><br /><br /> <span data-ttu-id="eb492-110">トランザクション セットの詳細</span><span class="sxs-lookup"><span data-stu-id="eb492-110">- Transaction Set Details</span></span><br /><br /> <span data-ttu-id="eb492-111">EDI メッセージの内容</span><span class="sxs-lookup"><span data-stu-id="eb492-111">- EDI Message Content</span></span>|  
|<span data-ttu-id="eb492-112">EDI </span><span class="sxs-lookup"><span data-stu-id="eb492-112">EDI</span></span>|<span data-ttu-id="eb492-113">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="eb492-113">Batch Status</span></span>|-|  
|<span data-ttu-id="eb492-114">EDI </span><span class="sxs-lookup"><span data-stu-id="eb492-114">EDI</span></span>|<span data-ttu-id="eb492-115">インターチェンジの集計レポート</span><span class="sxs-lookup"><span data-stu-id="eb492-115">Interchange Aggregation Report</span></span>|-|  
|<span data-ttu-id="eb492-116">EDI </span><span class="sxs-lookup"><span data-stu-id="eb492-116">EDI</span></span>|<span data-ttu-id="eb492-117">トランザクション セットの集計レポート</span><span class="sxs-lookup"><span data-stu-id="eb492-117">Transaction Set Aggregation Report</span></span>|-|  
|<span data-ttu-id="eb492-118">AS2</span><span class="sxs-lookup"><span data-stu-id="eb492-118">AS2</span></span>|<span data-ttu-id="eb492-119">AS2 メッセージおよび関連する MDN の状態</span><span class="sxs-lookup"><span data-stu-id="eb492-119">AS2 Message and Correlated MDN Status</span></span>|<span data-ttu-id="eb492-120">AS2 メッセージ コンテンツ</span><span class="sxs-lookup"><span data-stu-id="eb492-120">AS2 Message Content</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="eb492-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="eb492-121">Prerequisites</span></span>  
 <span data-ttu-id="eb492-122">次に、このトピックの手順を実行するための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="eb492-122">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="eb492-123">状態レポートをカスタマイズするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb492-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to customize any of the status reports.</span></span>  
  
- <span data-ttu-id="eb492-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンすると、読み取り専用の状態レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="eb492-124">If you are logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, you can display read-only status reports.</span></span>  
  
## <a name="display-an-edi-or-as2-status-report"></a><span data-ttu-id="eb492-125">EDI または AS2 状態レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="eb492-125">Display an EDI or AS2 status report</span></span>  
  
1. <span data-ttu-id="eb492-126">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、 **BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb492-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node.</span></span>  
  
2. <span data-ttu-id="eb492-127">**グループ ハブ**のタブ、**グループの概要**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ページの下部に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb492-127">In the **Group Hub** tab of the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, move to the bottom of the page.</span></span>  
  
3. <span data-ttu-id="eb492-128">表示する、 **EDI インターチェンジと関連する ACK の状態**レポート、次のように続行します。</span><span class="sxs-lookup"><span data-stu-id="eb492-128">To display the **EDI Interchange and Correlated ACK Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="eb492-129">クリックして**EDI インターチェンジと関連する ACK の状態**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="eb492-129">Click **EDI Interchange and Correlated ACK Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="eb492-130">インターチェンジおよびその関連確認の詳細を表示するには、クエリの結果のエントリを右クリックして、 **EDI インターチェンジと関連する ACK の状態**レポートとクリックして**インターチェンジの状態と確認詳細**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-130">To display details of an interchange and its correlated acknowledgments, right-click an entry in the query results of the **EDI Interchange and Correlated ACK Status** report, and then click **Interchange status and ack details**.</span></span>  
  
   3.  <span data-ttu-id="eb492-131">トランザクション セットの詳細を表示する、レポートを閉じインターチェンジ状態と確認の詳細を返す、 **EDI インターチェンジと関連する ACK の状態**詳細レポート。</span><span class="sxs-lookup"><span data-stu-id="eb492-131">To display details of a transaction set, close the Interchange status and ack details report, returning to the **EDI Interchange and Correlated ACK Status** details report.</span></span> <span data-ttu-id="eb492-132">クエリの結果内のエントリを右クリックし、をクリックし、**トランザクション セットの詳細**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-132">Right-click an entry in the query results, and then click **Transaction Set Details**.</span></span>  
  
   4.  <span data-ttu-id="eb492-133">ヘッダーおよびトランザクション セットのペイロードに関する詳細を表示するには、内のエントリを右クリックし、**トランザクション セットの詳細**レポートとクリックして**トランザクション セット**。</span><span class="sxs-lookup"><span data-stu-id="eb492-133">To display details about the headers and payload of a transaction set, right-click an entry in the **Transaction Set Details** report, and then click **View Transaction Set Content**.</span></span>  
  
   5.  <span data-ttu-id="eb492-134">トランザクション セットを含むインターチェンジに関するデータを表示するには、エントリを右クリックして、**トランザクション セットの詳細**レポートとクリックして**インターチェンジ/確認の状態**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-134">To display data about the interchange containing the transaction set, right-click an entry in the **Transaction Set Details** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="eb492-135">トランザクション セットを含むインターチェンジが、インターチェンジ/確認の状態レポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb492-135">The interchange containing the transaction set will be highlighted in the Interchange/ACK Status report.</span></span>  
  
4. <span data-ttu-id="eb492-136">表示する、**バッチの状態**レポート、次のように続行します。</span><span class="sxs-lookup"><span data-stu-id="eb492-136">To display the **Batch Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="eb492-137">をクリックして**バッチ ステータス**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="eb492-137">Click **Batch Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="eb492-138">内のバッチ エントリに関連付けられている完了したバッチを表示する、**バッチ ステータス**レポート、エントリを右クリックし、クリックして**完了済みのバッチ**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-138">To display the completed batches associated with a batch entry in the **Batch Status** report, right-click the entry and then click **Completed Batches**.</span></span>  
  
   3.  <span data-ttu-id="eb492-139">完了したバッチ インターチェンジに関するデータを表示するには、内のインターチェンジを右クリックし、**完了済みバッチ**レポートとクリックして**インターチェンジ/確認の状態**。</span><span class="sxs-lookup"><span data-stu-id="eb492-139">To display data about a completed batched interchange, right-click the interchange in the **Completed Batch** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="eb492-140">バッチ インターチェンジに関するエントリが、インターチェンジ/確認の状態レポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb492-140">The entry for the batched interchange will be highlighted in the Interchange/ACK Status report.</span></span>  
  
5. <span data-ttu-id="eb492-141">表示する、**インターチェンジの集計レポート**、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="eb492-141">To display the **Interchange Aggregation Report**, proceed as follows:</span></span>  
  
   -   <span data-ttu-id="eb492-142">クリックして**インターチェンジの集計レポート**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="eb492-142">Click **Interchange Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
6. <span data-ttu-id="eb492-143">表示する、**トランザクション セットの集計レポート**、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="eb492-143">To display the **Transaction Set Aggregation Report**, proceed as follows:</span></span>  
  
   -   <span data-ttu-id="eb492-144">クリックして**トランザクション セットの集計レポート**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="eb492-144">Click **Transaction Set Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
7. <span data-ttu-id="eb492-145">表示する、 **AS2 メッセージおよび関連する MDN 状態**レポート、次のように続行します。</span><span class="sxs-lookup"><span data-stu-id="eb492-145">To display the **AS2 Message and Correlated MDN Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="eb492-146">クリックして**AS2 メッセージおよび関連する MDN 状態**で、 **EDIINT 状態レポート**の領域、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="eb492-146">Click **AS2 Message and Correlated MDN Status** in the **EDIINT Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="eb492-147">AS2 メッセージを EDI インターチェンジの状態を表示するには、エントリを右クリックして、 **AS2 メッセージおよび関連する MDN 状態**レポートとクリックして**インターチェンジ/確認の状態**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-147">To display the status of the EDI interchange in an AS2 message, right-click an entry in the **AS2 Message and Correlated MDN Status** report, and then click **Interchange/ACK Status**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="eb492-148">EDI 状態と AS2 状態の関連付けの方法の詳細については、の「の関連付け、AS2 メッセージと EDI ペイロードの」セクションを参照してください。 [AS2 メッセージおよび関連する MDN 状態レポート](../core/as2-message-and-correlated-mdn-status-report.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb492-148">For more information on how EDI status and AS2 status are correlated, see the "Correlating an AS2 Message with its EDI Payload" section of [AS2 Message and Correlated MDN Status Report](../core/as2-message-and-correlated-mdn-status-report.md).</span></span>  
  
   3.  <span data-ttu-id="eb492-149">AS2 メッセージをワイヤ形式で表示する、または MDN の AS2 状態レポート エントリを右クリックし、**メッセージのワイヤ形式**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-149">To display an AS2 message in wire format, right-click an entry in the AS2/MDN Status report, and then click **Message Wire Format**.</span></span>  
  
   4.  <span data-ttu-id="eb492-150">AS2 メッセージをデコードされた形式で表示する、または MDN の AS2 状態レポート エントリを右クリックし、順にクリックします**メッセージのデコードされた形式**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-150">To display an AS2 message in decoded format, right-click an entry in the AS2/MDN Status report, and then click **Message Decoded Format**.</span></span>  
  
   5.  <span data-ttu-id="eb492-151">MDN メッセージを表示する、または MDN の AS2 状態レポート エントリを右クリックし、順にクリックします**Mdn メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="eb492-151">To display an MDN message, right-click an entry in the AS2/MDN Status report, and then click **Mdn Message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb492-152">参照</span><span class="sxs-lookup"><span data-stu-id="eb492-152">See Also</span></span>  
 <span data-ttu-id="eb492-153">[EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="eb492-153">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="eb492-154">[EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="eb492-154">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="eb492-155">[EDI および AS2 状態レポートを有効にします。](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="eb492-155">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="eb492-156">EDI および AS2 状態レポートの構成</span><span class="sxs-lookup"><span data-stu-id="eb492-156">Configuring an EDI and AS2 Status Report</span></span>](../core/configuring-an-edi-and-as2-status-report.md)