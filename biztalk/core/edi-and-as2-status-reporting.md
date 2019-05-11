---
title: EDI および AS2 状態レポート |Microsoft Docs
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
ms.openlocfilehash: 6bf0f3f5b5e6c50a02451215f56dbc3ec4c2939a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350580"
---
# <a name="edi-and-as2-status-reporting"></a><span data-ttu-id="195fb-102">EDI および AS2 状態レポート</span><span class="sxs-lookup"><span data-stu-id="195fb-102">EDI and AS2 Status Reporting</span></span>
<span data-ttu-id="195fb-103">EDI 状態レポートを有効に運用担当者の EDI および AS2 の送信の状態を追跡します。</span><span class="sxs-lookup"><span data-stu-id="195fb-103">EDI status reporting enables operations personnel to track the status of EDI and AS2 transmissions.</span></span> <span data-ttu-id="195fb-104">有効な場合、状態レポートは、インターチェンジには、インターチェンジに関連付けられたすべての確認など、ドキュメント交換トランザクションの包括的な状態を提供します。</span><span class="sxs-lookup"><span data-stu-id="195fb-104">If enabled, status reports provide comprehensive status of a document exchange transaction, including an interchange and any acknowledgments correlated to the interchange.</span></span> <span data-ttu-id="195fb-105">これらのレポートは、受信、検証、バッチ処理、および EDI および AS2 メッセージの受信確認処理でデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="195fb-105">These reports provide data on receipt, validation, batching, and acknowledgment processing of EDI and AS2 messages.</span></span>  
  
 <span data-ttu-id="195fb-106">これらのレポートを使用すると、保留中の状態と未確認のインターチェンジ、完全なインターチェンジ、エラーのシナリオまたはビジネス シナリオを取得します。</span><span class="sxs-lookup"><span data-stu-id="195fb-106">You can use these reports to get the status of pending and unacknowledged interchanges, complete interchanges, error scenarios, or business scenarios.</span></span> <span data-ttu-id="195fb-107">これらのレポートには、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="195fb-107">With these reports, you can do the following:</span></span>  
  
- <span data-ttu-id="195fb-108">インターチェンジの受信を確認します。</span><span class="sxs-lookup"><span data-stu-id="195fb-108">Confirm the receipt of interchanges</span></span>  
  
- <span data-ttu-id="195fb-109">送信インターチェンジ待機確認を一覧します。</span><span class="sxs-lookup"><span data-stu-id="195fb-109">List outgoing interchanges awaiting acknowledgment</span></span>  
  
- <span data-ttu-id="195fb-110">受信したすべての拒否されたインターチェンジを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="195fb-110">List all rejected interchanges received</span></span>  
  
- <span data-ttu-id="195fb-111">拒否された、または部分的に報告された送信インターチェンジの一覧が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="195fb-111">List outgoing interchanges that are reported as rejected or partially accepted.</span></span>  
  
  <span data-ttu-id="195fb-112">状態レポートに含まれるデータは、インターチェンジ制御セグメント ISA、TA1、GS、UNB、UNG など (機能確認状態) を除くから取得されます。</span><span class="sxs-lookup"><span data-stu-id="195fb-112">Data included in the status reports is obtained from interchange control segments, such as ISA, TA1, GS, UNB, and UNG (with the exception of the Functional ACK status).</span></span>  
  
  <span data-ttu-id="195fb-113">**状態レポートの UI**</span><span class="sxs-lookup"><span data-stu-id="195fb-113">**Status Reporting UI**</span></span>  
  
  <span data-ttu-id="195fb-114">EDI および AS2 状態レポートはから利用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="195fb-114">EDI and AS2 status reports are available from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="195fb-115">**グループ ハブ**のページ、 **BizTalk グループ**ノード、EDI インターチェンジと関連する受信確認状態、バッチの状態と AS2 メッセージおよび関連する MDN の状態へのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="195fb-115">From the **Group Hub** page of the **BizTalk Group** node, you have links to EDI interchange and correlated acknowledgment status, batch status, and AS2 message and correlated MDN status.</span></span> <span data-ttu-id="195fb-116">各レポートを含めるかが必要とする状態レポートを構築できるように、クエリ式から除外する状態パラメーターの範囲を提供します。</span><span class="sxs-lookup"><span data-stu-id="195fb-116">Each of these reports provides a range of status parameters that you can include or exclude from a query expression, enabling you to build the status report that they need.</span></span>  
  
  <span data-ttu-id="195fb-117">EDI インターチェンジの状態を表示することに加えて、インターチェンジのトランザクション セットを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="195fb-117">In addition to seeing the status of an EDI interchange, you can also view the transaction sets in an interchange.</span></span> <span data-ttu-id="195fb-118">追跡 (BizTalkDTADb) データベースの EDI テーブルにメッセージ ペイロードのストレージを有効にするとこれを行います。</span><span class="sxs-lookup"><span data-stu-id="195fb-118">You do so by enabling the storage of message payloads in the EDI tables of the tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="195fb-119">状態レポート UI の詳細を表示するコマンドを使用して、トランザクション セットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="195fb-119">You can view the transaction sets by using the view details command in the status reporting UI.</span></span>  
  
  <span data-ttu-id="195fb-120">否認不可データベースに受信または送信 AS2 メッセージまたは Mdn を格納することもできます。</span><span class="sxs-lookup"><span data-stu-id="195fb-120">You can also store inbound or outbound AS2 messages or MDNs in the non-repudiation database.</span></span> <span data-ttu-id="195fb-121">トランザクション セットまたは AS2 メッセージを表示するには、状態レポートにメッセージを右クリックし、適切なコマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="195fb-121">You can view the transaction sets or AS2 messages by right-clicking the message in the status report and selecting the appropriate command.</span></span>  
  
  <span data-ttu-id="195fb-122">**状態レポートのコンポーネント**</span><span class="sxs-lookup"><span data-stu-id="195fb-122">**Status Report Components**</span></span>  
  
  <span data-ttu-id="195fb-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状態レポートに関連するコンポーネントが次に示します。</span><span class="sxs-lookup"><span data-stu-id="195fb-123">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components involved in status reporting are the following:</span></span>  
  
- <span data-ttu-id="195fb-124">EDI 逆アセンブラーで EDI 受信パイプラインを作成し、受信したインターチェンジについて、データ ストアに状態エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="195fb-124">The EDI Disassembler in the EDI receive pipeline that creates and updates status entries in the data store for an incoming interchange</span></span>  
  
- <span data-ttu-id="195fb-125">EDI アセンブラーは EDI 送信パイプラインを作成して、送信インターチェンジのデータ ストアに状態エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="195fb-125">The EDI Assembler in the EDI send pipeline that creates and updates status entries in the data store for an outgoing interchange</span></span>  
  
- <span data-ttu-id="195fb-126">状態レポート エントリを格納するデータ ストア。</span><span class="sxs-lookup"><span data-stu-id="195fb-126">The data stores that store the status report entries.</span></span> <span data-ttu-id="195fb-127">これらは、データと EDI トランザクション セットおよび AS2 メッセージの内容を BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルを追跡するため、BAM プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="195fb-127">These are the BAM Primary Import database for tracking data and the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb) for EDI transaction sets and/or AS2 message contents</span></span>  
  
- <span data-ttu-id="195fb-128">状態レポート UI、**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、状態レポート データを表示するために使用</span><span class="sxs-lookup"><span data-stu-id="195fb-128">Status reporting UI on the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to display status reporting data</span></span>  
  
- <span data-ttu-id="195fb-129">アグリーメント プロパティ オプションおよびフォールバック アグリーメント プロパティ オプション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、有効にして、状態レポートを構成するために使用</span><span class="sxs-lookup"><span data-stu-id="195fb-129">Agreement property and fallback agreement property options in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to enable and configure status reporting</span></span>  
  
- <span data-ttu-id="195fb-130">BAM インフラストラクチャを利用する DTA および SQL 分析サーバー。</span><span class="sxs-lookup"><span data-stu-id="195fb-130">DTA and SQL Analysis Server that leverage the BAM infrastructure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="195fb-131">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="195fb-131">In This Section</span></span>  
  
-   [<span data-ttu-id="195fb-132">EDI および AS2 状態レポートの構成</span><span class="sxs-lookup"><span data-stu-id="195fb-132">Configuration of EDI and AS2 Status Reporting</span></span>](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [<span data-ttu-id="195fb-133">EDI および AS2 状態レポートの種類</span><span class="sxs-lookup"><span data-stu-id="195fb-133">Types of EDI and AS2 Status Reports</span></span>](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="195fb-134">EDI および AS2 状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="195fb-134">Data Stored for EDI and AS2 Status Reports</span></span>](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="195fb-135">EDI および AS2 状態レポートのデータ格納方法</span><span class="sxs-lookup"><span data-stu-id="195fb-135">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)