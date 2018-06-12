---
title: メッセージとインスタンス データ追跡のベスト プラクティス |Microsoft ドキュメント
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
ms.openlocfilehash: 680958d2950edffeaa56c7c3b8d7f8da40967173
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34849018"
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a><span data-ttu-id="31700-102">メッセージとインスタンス データ追跡のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="31700-102">Best Practices for Message and Instance Data Tracking</span></span>
<span data-ttu-id="31700-103">履歴および追跡データを使用するためのベスト プラクティスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="31700-103">Review the following best practices for using historical and tracked data.</span></span>  
  
-   <span data-ttu-id="31700-104">**履歴および追跡データを使用するセキュリティの考慮事項を確認します。**</span><span class="sxs-lookup"><span data-stu-id="31700-104">**Review the security considerations for using historical and tracked data**</span></span>  
  
    -   <span data-ttu-id="31700-105">履歴および追跡データのセキュリティに関する考慮事項の詳細については、次を参照してください。[メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)です。</span><span class="sxs-lookup"><span data-stu-id="31700-105">For more information about security considerations for historical and tracked data, see [Security Considerations for Message and Instance Data Tracking](../core/security-considerations-for-message-and-instance-data-tracking.md).</span></span>  
  
-   <span data-ttu-id="31700-106">**すべてのメッセージ ボックス データベースで SQL Server エージェント サービスが実行されていることを確認してください。**</span><span class="sxs-lookup"><span data-stu-id="31700-106">**Ensure that the SQL Server Agent service is running on all MessageBox databases**</span></span>  
  
    -   <span data-ttu-id="31700-107">SQL Server エージェントは、メッセージ本文を WMI、および履歴データや追跡データで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="31700-107">SQL Server Agent makes message bodies available to WMI, and historical and tracked data.</span></span> <span data-ttu-id="31700-108">これにより、ジョブを実行してメッセージ ボックス データベースをクリーンアップできます。</span><span class="sxs-lookup"><span data-stu-id="31700-108">This enables you to run jobs to clean up the MessageBox databases.</span></span> <span data-ttu-id="31700-109">SQL Server エージェントの詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31700-109">For more information about SQL Server Agent, see SQL Server Books Online.</span></span>  
  
-   <span data-ttu-id="31700-110">**メッセージ本文の追跡を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="31700-110">**Enable message body tracking**</span></span>  
  
    -   <span data-ttu-id="31700-111">サービス インスタンスの処理が完了した後にメッセージを保存するには、メッセージ本文の追跡が必要です。</span><span class="sxs-lookup"><span data-stu-id="31700-111">Message body tracking is required to save messages after service instances processing is complete.</span></span>  
  
-   <span data-ttu-id="31700-112">**必要に応じて、ビジネス ニーズに追跡を構成します。**</span><span class="sxs-lookup"><span data-stu-id="31700-112">**Configure tracking as appropriate for your business needs**</span></span>  
  
    -   <span data-ttu-id="31700-113">履歴データおよび追跡データを表示するためには、BizTalk Server 管理コンソールを使用して追跡を構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="31700-113">Before you can view historical and tracked data, you must first configure tracking using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="31700-114">追跡オプションを有効または無効にする場合は、いくつかの注意事項があります。</span><span class="sxs-lookup"><span data-stu-id="31700-114">There are multiple considerations to keep in mind when enabling or disabling tracking options.</span></span> <span data-ttu-id="31700-115">追跡するデータが多いと、それだけ早く、BizTalk 追跡 (BizTalkDTADb) データベースのサイズが肥大化し、実行時のパフォーマンスに悪影響が生じます。</span><span class="sxs-lookup"><span data-stu-id="31700-115">The more data you track, the faster your BizTalk Tracking (BizTalkDTADb) database will grow in size, which can adversely affect your runtime performance.</span></span> <span data-ttu-id="31700-116">詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用した追跡構成](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)です。</span><span class="sxs-lookup"><span data-stu-id="31700-116">For more information, see [Configuring Tracking Using the BizTalk Server Administration Console](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef).</span></span>  
  
-   <span data-ttu-id="31700-117">**適切なトラブルシューティングのための追跡の種類を選択または監査**</span><span class="sxs-lookup"><span data-stu-id="31700-117">**Select the appropriate type of tracking for troubleshooting or auditing**</span></span>  
  
    -   <span data-ttu-id="31700-118">開発環境またはステージング/実稼働環境でトラブルシューティングを行う場合は、アイテム イベント、メッセージのプロパティ、メッセージ本文、オーケストレーションのイベントを詳細に確認できるよう、追跡オプションをすべて有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31700-118">For troubleshooting either in a development environment, or in a staging or production environment, you should enable all tracking options so that you can see artifact events, message properties, message bodies and orchestration events in detail.</span></span> <span data-ttu-id="31700-119">これにより、システムの一連のイベントを作成し直したり、アプリケーションをデバッグできるだけの十分な追跡情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="31700-119">This provides a rich set of tracked information that you can use to recreate the sequence of events in your system and debug your application.</span></span>  
  
    -   <span data-ttu-id="31700-120">実稼働レベルの監査を行う場合は、監査対象のイベントを慎重に選びながら、本当に必要なイベントについてのみ追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="31700-120">For production level auditing, carefully choose the events you want to audit and then enable tracking only for those events.</span></span> <span data-ttu-id="31700-121">たとえば、多くの企業は、メッセージが入力し、システムを終了したことを証明するためにできるようにします。</span><span class="sxs-lookup"><span data-stu-id="31700-121">For example, many enterprises want to be able to prove that a message entered and exited the system.</span></span> <span data-ttu-id="31700-122">そのためには、受信ポートと送信ポートで、それぞれ対応する受信メッセージと送信メッセージの追跡を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31700-122">To achieve this, you should enable inbound tracking on the corresponding receive port and enable outbound tracking on the corresponding send port.</span></span> <span data-ttu-id="31700-123">必要であれば、メッセージ プロパティやメッセージ本文を追跡することもできます。</span><span class="sxs-lookup"><span data-stu-id="31700-123">If necessary, you can add message property and message body tracking.</span></span>  
  
    -   <span data-ttu-id="31700-124">主要業績評価指標 (KPI) を評価したり、特定のビジネス マイルストーンの達成度に基づいて進捗状況を評価したりする場合は、ビジネス アクティビティ監視 (BAM) 追跡を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31700-124">For measuring business Key Performance Indicators (KPIs) or progress as measured by the achievement of specified business milestones, you should use Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="31700-125">BAM 追跡ではメッセージ本文を追跡する機能が限られているため、BAM 追跡が必要な場合は、履歴データと追跡データを組み合わせて使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31700-125">BAM tracking has limited abilities to track and store message bodies, so if this is important, you should use historical and tracked data  in conjunction with BAM tracking.</span></span> <span data-ttu-id="31700-126">BAM 追跡の詳細については、次を参照してください。[を使用したビジネス アクティビティ監視](../core/using-business-activity-monitoring.md)です。</span><span class="sxs-lookup"><span data-stu-id="31700-126">For more information about BAM tracking, see [Using Business Activity Monitoring](../core/using-business-activity-monitoring.md).</span></span>  
  
-   <span data-ttu-id="31700-127">**アーカイブおよびを定期的に BizTalk 追跡 (BizTalkDTADb) データベースからデータを消去**</span><span class="sxs-lookup"><span data-stu-id="31700-127">**Archive and purge data from the BizTalk Tracking (BizTalkDTADb) database on a regular basis**</span></span>  
  
    -   <span data-ttu-id="31700-128">追跡を有効にする場合は、データベースのサイズが大きくなりすぎないように、BizTalk 追跡データベースのデータを定期的にアーカイブ/削除する必要があります。これにより、システムのパフォーマンスを最適な状態に維持することができます。</span><span class="sxs-lookup"><span data-stu-id="31700-128">If you have enabled tracking, you should archive and purge data from the BizTalk Tracking database on a regular basis to help keep the database appropriately sized, which helps improve system performance.</span></span> <span data-ttu-id="31700-129">詳細については、次を参照してください。[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="31700-129">For more information, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31700-130">参照</span><span class="sxs-lookup"><span data-stu-id="31700-130">See Also</span></span>  
 [<span data-ttu-id="31700-131">追跡メッセージおよびインスタンス データの表示</span><span class="sxs-lookup"><span data-stu-id="31700-131">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)