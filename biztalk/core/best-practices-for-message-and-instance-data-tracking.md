---
title: メッセージとインスタンス データ追跡のベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, best practices
- best practices, HAT
ms.assetid: 2ac5c87b-2059-4912-9cec-2ae4eaac56df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8415547ec5f4300a89d8a96ffc3ee78325c7c57d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358195"
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a><span data-ttu-id="8a9e9-102">メッセージとインスタンス データ追跡のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="8a9e9-102">Best Practices for Message and Instance Data Tracking</span></span>
<span data-ttu-id="8a9e9-103">履歴および追跡データを使用するための次のベスト プラクティスを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-103">Review the following best practices for using historical and tracked data.</span></span>  
  
-   <span data-ttu-id="8a9e9-104">**履歴および追跡データを使用するセキュリティの考慮事項を確認してください。**</span><span class="sxs-lookup"><span data-stu-id="8a9e9-104">**Review the security considerations for using historical and tracked data**</span></span>  
  
    -   <span data-ttu-id="8a9e9-105">履歴および追跡データのセキュリティに関する考慮事項の詳細については、次を参照してください。[メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-105">For more information about security considerations for historical and tracked data, see [Security Considerations for Message and Instance Data Tracking](../core/security-considerations-for-message-and-instance-data-tracking.md).</span></span>  
  
-   <span data-ttu-id="8a9e9-106">**すべてのメッセージ ボックス データベースで SQL Server エージェント サービスが実行されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="8a9e9-106">**Ensure that the SQL Server Agent service is running on all MessageBox databases**</span></span>  
  
    -   <span data-ttu-id="8a9e9-107">SQL Server エージェントでは、WMI、および履歴および追跡データに使用可能なメッセージ本文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-107">SQL Server Agent makes message bodies available to WMI, and historical and tracked data.</span></span> <span data-ttu-id="8a9e9-108">これにより、メッセージ ボックス データベースをクリーンアップするジョブを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-108">This enables you to run jobs to clean up the MessageBox databases.</span></span> <span data-ttu-id="8a9e9-109">SQL Server エージェントの詳細については、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-109">For more information about SQL Server Agent, see SQL Server Books Online.</span></span>  
  
-   <span data-ttu-id="8a9e9-110">**メッセージ本文の追跡を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="8a9e9-110">**Enable message body tracking**</span></span>  
  
    -   <span data-ttu-id="8a9e9-111">本文の追跡は、サービス インスタンスの処理後のメッセージを保存するために必要なメッセージが完了しました。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-111">Message body tracking is required to save messages after service instances processing is complete.</span></span>  
  
-   <span data-ttu-id="8a9e9-112">**お客様のビジネス ニーズに応じて追跡を構成します。**</span><span class="sxs-lookup"><span data-stu-id="8a9e9-112">**Configure tracking as appropriate for your business needs**</span></span>  
  
    -   <span data-ttu-id="8a9e9-113">履歴および追跡データを表示するには、最初、BizTalk Server 管理コンソールを使用して追跡を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-113">Before you can view historical and tracked data, you must first configure tracking using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="8a9e9-114">有効化または追跡オプションを無効にするときに考慮すべき事項は複数あります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-114">There are multiple considerations to keep in mind when enabling or disabling tracking options.</span></span> <span data-ttu-id="8a9e9-115">多くのデータを追跡する、高速、BizTalk 追跡 (BizTalkDTADb) データベース サイズが大きく、実行時のパフォーマンスに悪影響をします。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-115">The more data you track, the faster your BizTalk Tracking (BizTalkDTADb) database will grow in size, which can adversely affect your runtime performance.</span></span> <span data-ttu-id="8a9e9-116">詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用した追跡構成](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-116">For more information, see [Configuring Tracking Using the BizTalk Server Administration Console](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef).</span></span>  
  
-   <span data-ttu-id="8a9e9-117">**適切なトラブルシューティングのための追跡の種類を選択または監査**</span><span class="sxs-lookup"><span data-stu-id="8a9e9-117">**Select the appropriate type of tracking for troubleshooting or auditing**</span></span>  
  
    -   <span data-ttu-id="8a9e9-118">アイテム イベント、メッセージのプロパティ、メッセージ本文、およびオーケストレーション イベントの詳細が表示されるよう、開発環境またはステージング環境または運用環境でのいずれかをトラブルシューティングするには、すべての追跡オプションを有効する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-118">For troubleshooting either in a development environment, or in a staging or production environment, you should enable all tracking options so that you can see artifact events, message properties, message bodies and orchestration events in detail.</span></span> <span data-ttu-id="8a9e9-119">これは、システムのイベントのシーケンスを再作成し、アプリケーションのデバッグに使用できる追跡情報の豊富なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-119">This provides a rich set of tracked information that you can use to recreate the sequence of events in your system and debug your application.</span></span>  
  
    -   <span data-ttu-id="8a9e9-120">実稼働レベルの監査、監査イベントについてのみ追跡を有効にするイベントを慎重に選択します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-120">For production level auditing, carefully choose the events you want to audit and then enable tracking only for those events.</span></span> <span data-ttu-id="8a9e9-121">たとえば、多くの企業は、メッセージが入力して、システムを終了したことを証明することができるようにします。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-121">For example, many enterprises want to be able to prove that a message entered and exited the system.</span></span> <span data-ttu-id="8a9e9-122">これを実現する必要があります、受信の追跡を有効にする受信ポートと送信ポートを対応する送信メッセージの追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-122">To achieve this, you should enable inbound tracking on the corresponding receive port and enable outbound tracking on the corresponding send port.</span></span> <span data-ttu-id="8a9e9-123">必要に応じて、メッセージ プロパティとメッセージ本文の追跡を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-123">If necessary, you can add message property and message body tracking.</span></span>  
  
    -   <span data-ttu-id="8a9e9-124">ビジネス主要業績評価指標 (Kpi) または指定されたビジネス マイルス トーンの達成によって測定される進行状況を測定するためには、ビジネス アクティビティの監視 (BAM) のいずれも追跡を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-124">For measuring business Key Performance Indicators (KPIs) or progress as measured by the achievement of specified business milestones, you should use Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="8a9e9-125">BAM の追跡には、追跡、これは重要では、履歴および追跡データを BAM の追跡と組み合わせて使用する必要がありますは場合、本文のメッセージを格納する機能が制限されています。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-125">BAM tracking has limited abilities to track and store message bodies, so if this is important, you should use historical and tracked data  in conjunction with BAM tracking.</span></span> <span data-ttu-id="8a9e9-126">BAM の追跡の詳細については、次を参照してください。[ビジネス アクティビティの監視を使用して](../core/using-business-activity-monitoring.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-126">For more information about BAM tracking, see [Using Business Activity Monitoring](../core/using-business-activity-monitoring.md).</span></span>  
  
-   <span data-ttu-id="8a9e9-127">**アーカイブし、を定期的に BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除**</span><span class="sxs-lookup"><span data-stu-id="8a9e9-127">**Archive and purge data from the BizTalk Tracking (BizTalkDTADb) database on a regular basis**</span></span>  
  
    -   <span data-ttu-id="8a9e9-128">有効にした場合、追跡をアーカイブし、システム パフォーマンスが向上する適切なサイズ、データベースを保つために定期的に BizTalk 追跡データベースからデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-128">If you have enabled tracking, you should archive and purge data from the BizTalk Tracking database on a regular basis to help keep the database appropriately sized, which helps improve system performance.</span></span> <span data-ttu-id="8a9e9-129">詳細については、次を参照してください。[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a9e9-129">For more information, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a9e9-130">参照</span><span class="sxs-lookup"><span data-stu-id="8a9e9-130">See Also</span></span>  
 [<span data-ttu-id="8a9e9-131">追跡メッセージおよびインスタンス データの表示</span><span class="sxs-lookup"><span data-stu-id="8a9e9-131">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)