---
title: "EDI または AS2 状態レポートの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60968c3d-6329-411f-9f10-1dd4a6cc9d79
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0564a5c5d904a217ac406befebd3d7c742dc00c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="displaying-an-edi-or-as2-status-report"></a><span data-ttu-id="3fcad-102">EDI または AS2 状態レポートの表示</span><span class="sxs-lookup"><span data-stu-id="3fcad-102">Displaying an EDI or AS2 Status Report</span></span>
<span data-ttu-id="3fcad-103">EDI 状態レポートおよび AS2 状態レポートが有効になっている場合は、次の状態レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3fcad-103">When EDI and AS2 status reports are enabled, you will have access to the following status reports:</span></span>  
  
|<span data-ttu-id="3fcad-104">レポートの種類</span><span class="sxs-lookup"><span data-stu-id="3fcad-104">Type of Report</span></span>|<span data-ttu-id="3fcad-105">上位レベルの状態レポート</span><span class="sxs-lookup"><span data-stu-id="3fcad-105">Higher-level status report</span></span>|<span data-ttu-id="3fcad-106">下位レベルの状態レポート</span><span class="sxs-lookup"><span data-stu-id="3fcad-106">Lower-level status report</span></span>|  
|--------------------|---------------------------------|--------------------------------|  
|<span data-ttu-id="3fcad-107">EDI </span><span class="sxs-lookup"><span data-stu-id="3fcad-107">EDI</span></span>|<span data-ttu-id="3fcad-108">EDI インターチェンジと関連する ACK の状態</span><span class="sxs-lookup"><span data-stu-id="3fcad-108">EDI Interchange and Correlated ACK Status</span></span>|<span data-ttu-id="3fcad-109">-インターチェンジの状態と確認の詳細</span><span class="sxs-lookup"><span data-stu-id="3fcad-109">- Interchange Status and ACK Details</span></span><br /><br /> <span data-ttu-id="3fcad-110">トランザクション セットの詳細</span><span class="sxs-lookup"><span data-stu-id="3fcad-110">- Transaction Set Details</span></span><br /><br /> <span data-ttu-id="3fcad-111">EDI メッセージの内容</span><span class="sxs-lookup"><span data-stu-id="3fcad-111">- EDI Message Content</span></span>|  
|<span data-ttu-id="3fcad-112">EDI </span><span class="sxs-lookup"><span data-stu-id="3fcad-112">EDI</span></span>|<span data-ttu-id="3fcad-113">バッチの状態</span><span class="sxs-lookup"><span data-stu-id="3fcad-113">Batch Status</span></span>|-|  
|<span data-ttu-id="3fcad-114">EDI </span><span class="sxs-lookup"><span data-stu-id="3fcad-114">EDI</span></span>|<span data-ttu-id="3fcad-115">インターチェンジの集計レポート</span><span class="sxs-lookup"><span data-stu-id="3fcad-115">Interchange Aggregation Report</span></span>|-|  
|<span data-ttu-id="3fcad-116">EDI </span><span class="sxs-lookup"><span data-stu-id="3fcad-116">EDI</span></span>|<span data-ttu-id="3fcad-117">トランザクション セットの集計レポート</span><span class="sxs-lookup"><span data-stu-id="3fcad-117">Transaction Set Aggregation Report</span></span>|-|  
|<span data-ttu-id="3fcad-118">AS2</span><span class="sxs-lookup"><span data-stu-id="3fcad-118">AS2</span></span>|<span data-ttu-id="3fcad-119">AS2 メッセージおよび関連する MDN の状態</span><span class="sxs-lookup"><span data-stu-id="3fcad-119">AS2 Message and Correlated MDN Status</span></span>|<span data-ttu-id="3fcad-120">AS2 メッセージ コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3fcad-120">AS2 Message Content</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="3fcad-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="3fcad-121">Prerequisites</span></span>  
 <span data-ttu-id="3fcad-122">このトピックの手順を実行するための前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-122">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="3fcad-123">状態レポートをカスタマイズするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fcad-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to customize any of the status reports.</span></span>  
  
-   <span data-ttu-id="3fcad-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンすると、読み取り専用の状態レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3fcad-124">If you are logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, you can display read-only status reports.</span></span>  
  
## <a name="display-an-edi-or-as2-status-report"></a><span data-ttu-id="3fcad-125">EDI または AS2 状態レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-125">Display an EDI or AS2 status report</span></span>  
  
1.  <span data-ttu-id="3fcad-126">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、 **BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="3fcad-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node.</span></span>  
  
2.  <span data-ttu-id="3fcad-127">**グループ ハブ**のタブ、**グループの概要**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ページの下部に移動します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-127">In the **Group Hub** tab of the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, move to the bottom of the page.</span></span>  
  
3.  <span data-ttu-id="3fcad-128">表示する、 **EDI インターチェンジと関連する ACK の状態**レポートを次の手順します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-128">To display the **EDI Interchange and Correlated ACK Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="3fcad-129">をクリックして**EDI インターチェンジと関連する ACK の状態**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブです。</span><span class="sxs-lookup"><span data-stu-id="3fcad-129">Click **EDI Interchange and Correlated ACK Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="3fcad-130">インターチェンジおよびその関連確認の詳細を表示するには、クエリ結果内のエントリを右クリックし、 **EDI インターチェンジと関連する ACK の状態**レポートには、クリックして**インターチェンジの状態と確認詳細**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-130">To display details of an interchange and its correlated acknowledgments, right-click an entry in the query results of the **EDI Interchange and Correlated ACK Status** report, and then click **Interchange status and ack details**.</span></span>  
  
    3.  <span data-ttu-id="3fcad-131">トランザクション セットの詳細を表示するには、インターチェンジ状態と確認の詳細レポートに戻るを閉じる、 **EDI インターチェンジと関連する ACK の状態**レポートについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-131">To display details of a transaction set, close the Interchange status and ack details report, returning to the **EDI Interchange and Correlated ACK Status** details report.</span></span> <span data-ttu-id="3fcad-132">クエリ結果内のエントリを右クリックし、をクリックして**トランザクション セットの詳細**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-132">Right-click an entry in the query results, and then click **Transaction Set Details**.</span></span>  
  
    4.  <span data-ttu-id="3fcad-133">ヘッダーおよびトランザクション セットのペイロードに関する詳細を表示するには、内のエントリを右クリックし、**トランザクション セットの詳細**レポートには、クリックして**トランザクション セットのコンテンツ**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-133">To display details about the headers and payload of a transaction set, right-click an entry in the **Transaction Set Details** report, and then click **View Transaction Set Content**.</span></span>  
  
    5.  <span data-ttu-id="3fcad-134">表示するには、トランザクション セットを含むインターチェンジに関するデータ内のエントリを右クリックし、**トランザクション セットの詳細**レポートには、クリックして**インターチェンジ/確認の状態**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-134">To display data about the interchange containing the transaction set, right-click an entry in the **Transaction Set Details** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="3fcad-135">トランザクション セットを含むインターチェンジが、インターチェンジ/確認の状態レポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fcad-135">The interchange containing the transaction set will be highlighted in the Interchange/ACK Status report.</span></span>  
  
4.  <span data-ttu-id="3fcad-136">表示する、**バッチ ステータス**レポートを次の手順します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-136">To display the **Batch Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="3fcad-137">をクリックして**バッチ ステータス**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブです。</span><span class="sxs-lookup"><span data-stu-id="3fcad-137">Click **Batch Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="3fcad-138">内のバッチ エントリに関連付けられている完了したバッチを表示する、**バッチ ステータス**レポートをエントリを右クリックし、をクリックして**完了済みのバッチ**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-138">To display the completed batches associated with a batch entry in the **Batch Status** report, right-click the entry and then click **Completed Batches**.</span></span>  
  
    3.  <span data-ttu-id="3fcad-139">完了したバッチ インターチェンジに関するデータを表示するのには、内のインターチェンジを右クリックし、**完了済みバッチ**レポートには、クリックして**インターチェンジ/確認の状態**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-139">To display data about a completed batched interchange, right-click the interchange in the **Completed Batch** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="3fcad-140">バッチ インターチェンジに関するエントリが、インターチェンジ/確認の状態レポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fcad-140">The entry for the batched interchange will be highlighted in the Interchange/ACK Status report.</span></span>  
  
5.  <span data-ttu-id="3fcad-141">表示する、**インターチェンジの集計レポート**、次の手順します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-141">To display the **Interchange Aggregation Report**, proceed as follows:</span></span>  
  
    -   <span data-ttu-id="3fcad-142">をクリックして**インターチェンジの集計レポート**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブです。</span><span class="sxs-lookup"><span data-stu-id="3fcad-142">Click **Interchange Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
6.  <span data-ttu-id="3fcad-143">表示する、**トランザクション セットの集計レポート**、次の手順します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-143">To display the **Transaction Set Aggregation Report**, proceed as follows:</span></span>  
  
    -   <span data-ttu-id="3fcad-144">をクリックして**トランザクション セットの集計レポート**で、 **EDI 状態レポート**の領域、**グループ ハブ**タブです。</span><span class="sxs-lookup"><span data-stu-id="3fcad-144">Click **Transaction Set Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
7.  <span data-ttu-id="3fcad-145">表示する、 **AS2 メッセージおよび関連する MDN 状態**レポートを次の手順します。</span><span class="sxs-lookup"><span data-stu-id="3fcad-145">To display the **AS2 Message and Correlated MDN Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="3fcad-146">をクリックして**AS2 メッセージおよび関連する MDN 状態**で、 **EDIINT 状態レポート**の領域、**グループ ハブ**タブです。</span><span class="sxs-lookup"><span data-stu-id="3fcad-146">Click **AS2 Message and Correlated MDN Status** in the **EDIINT Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="3fcad-147">AS2 メッセージに EDI インターチェンジの状態を表示するには、内のエントリを右クリックし、 **AS2 メッセージおよび関連する MDN 状態**レポートには、クリックして**インターチェンジ/確認の状態**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-147">To display the status of the EDI interchange in an AS2 message, right-click an entry in the **AS2 Message and Correlated MDN Status** report, and then click **Interchange/ACK Status**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3fcad-148">EDI 状態と AS2 状態の関連付けの方法の詳細についてを参照してください「の関連付け、AS2 メッセージと EDI ペイロードの」の[AS2 メッセージおよび関連する MDN 状態レポート](../core/as2-message-and-correlated-mdn-status-report.md)です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-148">For more information on how EDI status and AS2 status are correlated, see the "Correlating an AS2 Message with its EDI Payload" section of [AS2 Message and Correlated MDN Status Report](../core/as2-message-and-correlated-mdn-status-report.md).</span></span>  
  
    3.  <span data-ttu-id="3fcad-149">表示するには、AS2 メッセージのワイヤ形式で AS2/MDN の状態レポート内のエントリを右クリックし、をクリックして**メッセージのワイヤ形式**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-149">To display an AS2 message in wire format, right-click an entry in the AS2/MDN Status report, and then click **Message Wire Format**.</span></span>  
  
    4.  <span data-ttu-id="3fcad-150">デコードされた形式で AS2 メッセージを表示するに AS2/MDN の状態レポート内のエントリを右クリックし、をクリックして**メッセージのデコードされた形式**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-150">To display an AS2 message in decoded format, right-click an entry in the AS2/MDN Status report, and then click **Message Decoded Format**.</span></span>  
  
    5.  <span data-ttu-id="3fcad-151">MDN メッセージを表示するには、AS2/MDN の状態レポート内のエントリを右クリックし、をクリックして**Mdn メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="3fcad-151">To display an MDN message, right-click an entry in the AS2/MDN Status report, and then click **Mdn Message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fcad-152">参照</span><span class="sxs-lookup"><span data-stu-id="3fcad-152">See Also</span></span>  
 <span data-ttu-id="3fcad-153">[EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="3fcad-153">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="3fcad-154">[EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="3fcad-154">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="3fcad-155">[EDI および AS2 状態レポートを有効にします。](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="3fcad-155">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="3fcad-156">EDI および AS2 状態レポートの構成</span><span class="sxs-lookup"><span data-stu-id="3fcad-156">Configuring an EDI and AS2 Status Report</span></span>](../core/configuring-an-edi-and-as2-status-report.md)