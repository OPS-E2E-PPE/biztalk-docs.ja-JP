---
title: グループ ハブ ページを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50693ccc-a3b2-4ad0-9a05-d60dab404a07
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f705305422f47cbf5510823a82356c9781d82aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396018"
---
# <a name="using-the-group-hub-page"></a><span data-ttu-id="13ece-102">グループ ハブ ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="13ece-102">Using the Group Hub Page</span></span>
<span data-ttu-id="13ece-103">選択すると、 **BizTalk グループ**BizTalk Server 管理コンソール内のノードには、詳細ウィンドウで、BizTalk Server グループ ハブ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13ece-103">Selecting the **BizTalk Group** node in the BizTalk Server Administration Console, displays the BizTalk Server Group Hub page in the details pane.</span></span> <span data-ttu-id="13ece-104">BizTalk Server グループ ハブ ページは、BizTalk Server システムの正常性の全体像を提供する 3 つのセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="13ece-104">The BizTalk Server Group Hub page is divided into three sections that provide an overall view of the health of your BizTalk Server system:</span></span>  
  
-   <span data-ttu-id="13ece-105">**構成の概要** セクションで、グループ ハブ ページの上部にあるは、アプリケーション、ホストのインスタンスの状態を表示することで、BizTalk グループの全体的な正常性を示しで構成されているアダプター ハンドラーこのグループです。</span><span class="sxs-lookup"><span data-stu-id="13ece-105">The **Configuration Overview** section, located in the upper part of the Group Hub page, indicates the overall health of the BizTalk group by displaying the state of the applications, host instances, and adapter handlers configured in this group.</span></span>  
  
-   <span data-ttu-id="13ece-106">**進行中の作業**と**中断状態のアイテム**のセクションでは、[グループ ハブ] ページの中央にあります。</span><span class="sxs-lookup"><span data-stu-id="13ece-106">The **Work in Progress**  and **Suspended Items** sections are located in the middle of the Group Hub page.</span></span>  
  
    -   <span data-ttu-id="13ece-107">**進行中の作業**セクションが表示のサービス インスタンス、退避されたオーケストレーション、再試行中およびアイドル状態のポート、準備がサービス インスタンス、およびスケジュールされたサービス インスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="13ece-107">The **Work in Progress** section displays running service instances, dehydrated orchestrations, retrying and idle ports, ready service instances, and scheduled service instances.</span></span>  
  
    -   <span data-ttu-id="13ece-108">**中断状態のアイテム**セクションには、中断されたサービス インスタンス、および再開可能なおよび再開不可のインスタンスの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13ece-108">The **Suspended Items** section displays the number of suspended service instances, and resumable and non-resumable instances.</span></span>  
  
-   <span data-ttu-id="13ece-109">**中断サービス インスタンスのグループ化**セクションには、アプリケーション、サービス名、エラー コード、および URI によってグループ化、中断されたサービス インスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13ece-109">The **Grouped Suspended Service Instances** section displays suspended service instances grouped by application, service name, error code, and URI.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13ece-110">グループ ハブ ページに記載されている数値は、おおよその数だけです。</span><span class="sxs-lookup"><span data-stu-id="13ece-110">The numbers listed on the Group Hub page are approximate counts only.</span></span> <span data-ttu-id="13ece-111">下に表示される番号など、**サービス インスタンスを実行している**または**中断されたサービス インスタンス**サービス インスタンスまたは中断されたサービス インスタンスの実行の合計数が等しくない場合があります[ハブ] ページのさまざまな統計情報の生成中に、システムの状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="13ece-111">For example, the numbers displayed under **Running service instances** or **Suspended service instances** might not equal the total number of running service instances or suspended service instances because the state of the system could change while the various statistics on the Hub page are being generated.</span></span>  
  
-   <span data-ttu-id="13ece-112">**追跡サービス インスタンス**と**追跡メッセージ イベント**のセクションでは、メッセージ イベントおよび最大 match を使用したサービス インスタンスの状態でクエリを実行 = 50。</span><span class="sxs-lookup"><span data-stu-id="13ece-112">The **Tracked Service Instances** and **Tracked Message Events** sections execute queries on message events and the state of service instances with a maximum match = 50.</span></span>  
  
    -   <span data-ttu-id="13ece-113">**追跡サービス インスタンス**追跡サービス インスタンスの検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="13ece-113">**Tracked service instances** query searches for tracked service instances.</span></span>  
  
    -   <span data-ttu-id="13ece-114">**完了したインスタンス**クエリが完了済み状態で追跡対象のサービス インスタンスで検索します。</span><span class="sxs-lookup"><span data-stu-id="13ece-114">**Completed instances** query searches for tracked service instances with state equal to completed.</span></span>  
  
    -   <span data-ttu-id="13ece-115">**終了されたインスタンス**状態が終了すると、追跡サービス インスタンスの検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="13ece-115">**Terminated instances** query searches for tracked service instances with state equal to terminated.</span></span>  
  
    -   <span data-ttu-id="13ece-116">**追跡メッセージ イベント**追跡メッセージ イベントの検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="13ece-116">**Tracked message events** query searches for tracked message events.</span></span>  
  
    -   <span data-ttu-id="13ece-117">**送信エラー イベント**追跡メッセージ イベントの送信エラー イベントの種類の検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="13ece-117">**Transmission failure events** query searches for tracked message events with an event type of transmission failure.</span></span>  
  
-   <span data-ttu-id="13ece-118">**EDI 状態レポート**と**EDIINT 状態レポート**グループ ハブ ページの下部にあるのセクションでは、EDI インターチェンジに関する 4 つのレポートと AS2 インターチェンジに関する 1 つが表示されます: EDI インターチェンジ関連する ACK の状態レポート、バッチ状態レポート、インターチェンジの集計レポート、トランザクション セットの集計レポートと AS2 メッセージおよび関連する MDN 状態レポート。</span><span class="sxs-lookup"><span data-stu-id="13ece-118">The **EDI Status Reports** and **EDIINT Status Reports** sections, located at the bottom of the Group Hub page, displays four reports about EDI interchanges and one about AS2 interchanges: the EDI Interchange and Correlated ACK Status reports, the Batch Status report, the Interchange Aggregation Report, the Transaction Set Aggregation Report, and the AS2 Message and Correlated MDN Status report.</span></span> <span data-ttu-id="13ece-119">これらのレポートの詳細については、次を参照してください。 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)します。</span><span class="sxs-lookup"><span data-stu-id="13ece-119">For more information about these reports, see [EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13ece-120">EDI および EDIINT 状態レポートのセクションでは、この BizTalk グループの EDI および AS2 機能が構成されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="13ece-120">The EDI and EDIINT Status Report sections will only be displayed if the EDI/AS2 features are configured for this BizTalk group.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13ece-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="13ece-121">In This Section</span></span>  
  
-   [<span data-ttu-id="13ece-122">サービス インスタンスの状態</span><span class="sxs-lookup"><span data-stu-id="13ece-122">Service Instance States</span></span>](../core/service-instance-states.md)  
  
-   [<span data-ttu-id="13ece-123">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="13ece-123">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)  
  
-   <span data-ttu-id="13ece-124">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="13ece-124">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>  
  
-   [<span data-ttu-id="13ece-125">追跡メッセージおよびインスタンス データの表示</span><span class="sxs-lookup"><span data-stu-id="13ece-125">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [<span data-ttu-id="13ece-126">状態と動作状況の追跡</span><span class="sxs-lookup"><span data-stu-id="13ece-126">Health and Activity Tracking</span></span>](../core/health-and-activity-tracking.md)