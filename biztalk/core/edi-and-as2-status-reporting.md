---
title: EDI および AS2 状態レポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9e58b29-9be0-41d6-ad35-1aae28e1a784
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31b08fd8222cee0cb0f04750eedcb32d06c28820
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241386"
---
# <a name="edi-and-as2-status-reporting"></a><span data-ttu-id="8a829-102">EDI および AS2 状態レポート</span><span class="sxs-lookup"><span data-stu-id="8a829-102">EDI and AS2 Status Reporting</span></span>
<span data-ttu-id="8a829-103">EDI 状態レポートを使用すると、運用担当者は EDI および AS2 送信の状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-103">EDI status reporting enables operations personnel to track the status of EDI and AS2 transmissions.</span></span> <span data-ttu-id="8a829-104">状態レポートを有効にすると、インターチェンジおよび、それに関連付けられた受信確認を含むドキュメント交換トランザクションの総合的な状態が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8a829-104">If enabled, status reports provide comprehensive status of a document exchange transaction, including an interchange and any acknowledgments correlated to the interchange.</span></span> <span data-ttu-id="8a829-105">このレポートでは、EDI および AS2 メッセージの受信、検証、バッチ処理、受信確認処理に関するデータが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8a829-105">These reports provide data on receipt, validation, batching, and acknowledgment processing of EDI and AS2 messages.</span></span>  
  
 <span data-ttu-id="8a829-106">このレポートを使用して、保留および未確認のインターチェンジ、完全なインターチェンジ、エラー シナリオ、またはビジネス シナリオの状態を取得できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-106">You can use these reports to get the status of pending and unacknowledged interchanges, complete interchanges, error scenarios, or business scenarios.</span></span> <span data-ttu-id="8a829-107">このレポートを使用して、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-107">With these reports, you can do the following:</span></span>  
  
-   <span data-ttu-id="8a829-108">インターチェンジの受信の確認</span><span class="sxs-lookup"><span data-stu-id="8a829-108">Confirm the receipt of interchanges</span></span>  
  
-   <span data-ttu-id="8a829-109">送信インターチェンジ待機確認の一覧表示</span><span class="sxs-lookup"><span data-stu-id="8a829-109">List outgoing interchanges awaiting acknowledgment</span></span>  
  
-   <span data-ttu-id="8a829-110">受信したすべての拒否インターチェンジの一覧表示</span><span class="sxs-lookup"><span data-stu-id="8a829-110">List all rejected interchanges received</span></span>  
  
-   <span data-ttu-id="8a829-111">拒否または一部受理としてレポートされた送信インターチェンジの一覧表示</span><span class="sxs-lookup"><span data-stu-id="8a829-111">List outgoing interchanges that are reported as rejected or partially accepted.</span></span>  
  
 <span data-ttu-id="8a829-112">状態レポートに含まれるデータは、ISA、TA1、GS、UNB、UNG (機能確認状態を除く) などのインターチェンジ制御セグメントから取得できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-112">Data included in the status reports is obtained from interchange control segments, such as ISA, TA1, GS, UNB, and UNG (with the exception of the Functional ACK status).</span></span>  
  
 <span data-ttu-id="8a829-113">**状態レポートの UI**</span><span class="sxs-lookup"><span data-stu-id="8a829-113">**Status Reporting UI**</span></span>  
  
 <span data-ttu-id="8a829-114">EDI および AS2 状態レポートは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-114">EDI and AS2 status reports are available from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="8a829-115">**グループ ハブ**のページ、 **BizTalk グループ**ノード、EDI インターチェンジと関連する受信確認状態、バッチ状態、および AS2 メッセージおよび関連する MDN の状態へのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="8a829-115">From the **Group Hub** page of the **BizTalk Group** node, you have links to EDI interchange and correlated acknowledgment status, batch status, and AS2 message and correlated MDN status.</span></span> <span data-ttu-id="8a829-116">これらのレポートはそれぞれ、クエリ式に含める、またはクエリ式から除外する状態パラメーターの範囲を提供し、必要な状態レポートの構築を可能にします。</span><span class="sxs-lookup"><span data-stu-id="8a829-116">Each of these reports provides a range of status parameters that you can include or exclude from a query expression, enabling you to build the status report that they need.</span></span>  
  
 <span data-ttu-id="8a829-117">EDI インターチェンジの状態を表示するだけでなく、インターチェンジのトランザクション セットも表示できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-117">In addition to seeing the status of an EDI interchange, you can also view the transaction sets in an interchange.</span></span> <span data-ttu-id="8a829-118">これは、追跡 (BizTalkDTADb) データベースの EDI テーブルへのメッセージ ペイロードの格納を有効にすることによって実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-118">You do so by enabling the storage of message payloads in the EDI tables of the tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="8a829-119">状態レポート UI の詳細表示コマンドを使用して、トランザクション セットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-119">You can view the transaction sets by using the view details command in the status reporting UI.</span></span>  
  
 <span data-ttu-id="8a829-120">受信または送信 AS2 メッセージ、または MDN を否認不可データベースに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a829-120">You can also store inbound or outbound AS2 messages or MDNs in the non-repudiation database.</span></span> <span data-ttu-id="8a829-121">状態レポートのメッセージを右クリックし、適切なコマンドを選択することにより、トランザクション セットまたは AS2 メッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8a829-121">You can view the transaction sets or AS2 messages by right-clicking the message in the status report and selecting the appropriate command.</span></span>  
  
 <span data-ttu-id="8a829-122">**状態レポートのコンポーネント**</span><span class="sxs-lookup"><span data-stu-id="8a829-122">**Status Report Components**</span></span>  
  
 <span data-ttu-id="8a829-123">状態レポートに関連する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a829-123">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components involved in status reporting are the following:</span></span>  
  
-   <span data-ttu-id="8a829-124">受信インターチェンジのデータ ストアに状態エントリを作成および更新する EDI 受信パイプラインの EDI 逆アセンブラー。</span><span class="sxs-lookup"><span data-stu-id="8a829-124">The EDI Disassembler in the EDI receive pipeline that creates and updates status entries in the data store for an incoming interchange</span></span>  
  
-   <span data-ttu-id="8a829-125">送信インターチェンジのデータ ストアに状態エントリを作成および更新する EDI 送信パイプラインの EDI アセンブラー。</span><span class="sxs-lookup"><span data-stu-id="8a829-125">The EDI Assembler in the EDI send pipeline that creates and updates status entries in the data store for an outgoing interchange</span></span>  
  
-   <span data-ttu-id="8a829-126">状態レポート エントリを格納するデータ ストア。</span><span class="sxs-lookup"><span data-stu-id="8a829-126">The data stores that store the status report entries.</span></span> <span data-ttu-id="8a829-127">これは、データ追跡用の BAM プライマリ インポート データベースと、EDI トランザクション セットおよび AS2 メッセージ コンテンツ用の BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="8a829-127">These are the BAM Primary Import database for tracking data and the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb) for EDI transaction sets and/or AS2 message contents</span></span>  
  
-   <span data-ttu-id="8a829-128">状態レポートの UI、**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、状態レポート データを表示するために使用</span><span class="sxs-lookup"><span data-stu-id="8a829-128">Status reporting UI on the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to display status reporting data</span></span>  
  
-   <span data-ttu-id="8a829-129">状態レポートの有効化および構成に使用される [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのアグリーメント プロパティ オプションおよびフォールバック アグリーメント プロパティ オプション。</span><span class="sxs-lookup"><span data-stu-id="8a829-129">Agreement property and fallback agreement property options in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to enable and configure status reporting</span></span>  
  
-   <span data-ttu-id="8a829-130">BAM インフラストラクチャを利用する DTA および SQL 分析サーバー。</span><span class="sxs-lookup"><span data-stu-id="8a829-130">DTA and SQL Analysis Server that leverage the BAM infrastructure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a829-131">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8a829-131">In This Section</span></span>  
  
-   [<span data-ttu-id="8a829-132">構成の EDI および AS2 状態レポート</span><span class="sxs-lookup"><span data-stu-id="8a829-132">Configuration of EDI and AS2 Status Reporting</span></span>](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [<span data-ttu-id="8a829-133">EDI および AS2 状態レポートの種類</span><span class="sxs-lookup"><span data-stu-id="8a829-133">Types of EDI and AS2 Status Reports</span></span>](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="8a829-134">格納されている EDI および AS2 状態レポートのデータ</span><span class="sxs-lookup"><span data-stu-id="8a829-134">Data Stored for EDI and AS2 Status Reports</span></span>](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="8a829-135">EDI および AS2 状態レポートのデータを格納する方法</span><span class="sxs-lookup"><span data-stu-id="8a829-135">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)