---
title: BAM によるソリューションを指向サービスを監視する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, service solutions
- service solution tutorial, monitoring
- OrchestrationEventStream object
ms.assetid: 9b251580-9371-490e-9218-0ce3f6b00fa6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1aeaec2513ebe3c6d7fe62ef542b6f044bca56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264114"
---
# <a name="monitoring-the-service-oriented-solution-with-bam"></a><span data-ttu-id="49051-102">BAM によるソリューションを指向サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="49051-102">Monitoring the Service Oriented Solution with BAM</span></span>
<span data-ttu-id="49051-103">ソリューション内のすべてのバージョンのアクティビティの監視、 **CustomerService**ビジネス アクティビティ監視 (BAM) API を使用してオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="49051-103">The solution monitors activity in all versions of the **CustomerService** orchestration using the Business Activity Monitoring (BAM) API.</span></span> <span data-ttu-id="49051-104">具体的には、使用して、新しい**OrchestrationEventStream**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="49051-104">More specifically, it uses the new **OrchestrationEventStream** object.</span></span>  
  
## <a name="what-is-the-orchestrationeventstream-object"></a><span data-ttu-id="49051-105">OrchestrationEventStream オブジェクトについて</span><span class="sxs-lookup"><span data-stu-id="49051-105">What is the OrchestrationEventStream Object?</span></span>  
 <span data-ttu-id="49051-106">新しい**OrchestrationEventStream**オブジェクトは、オーケストレーションから監視と追跡ができるようにします。</span><span class="sxs-lookup"><span data-stu-id="49051-106">The new **OrchestrationEventStream** object enables tracking and monitoring from orchestrations.</span></span> <span data-ttu-id="49051-107">取得された情報とオーケストレーションの状態には、トランザクション上の一貫性があります。</span><span class="sxs-lookup"><span data-stu-id="49051-107">The information captured is transactionally consistent with the orchestration state.</span></span> <span data-ttu-id="49051-108">たとえば、オーケストレーションの実行中にオーケストレーションのホスト インスタンスを再起動すると、オーケストレーション インスタンスはインスタンスの最後の永続化ポイントから再起動されます。</span><span class="sxs-lookup"><span data-stu-id="49051-108">For example, if the orchestration host instance restarts in the middle of executing the orchestration, the orchestration instance restarts from the last persistence point of the instance.</span></span> <span data-ttu-id="49051-109">**OrchestrationEventStream**クラス キャプチャされたデータが、オーケストレーション インスタンスの最後の永続性ポイントに一貫性があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="49051-109">The **OrchestrationEventStream** class ensures that the captured data is transactionally consistent with the orchestration instance's last persistence point.</span></span> <span data-ttu-id="49051-110">すべての**OrchestrationEventStream**すると、オーケストレーションは、そのインスタンスを作成する必要はありません、メソッドは静的です。</span><span class="sxs-lookup"><span data-stu-id="49051-110">All of the **OrchestrationEventStream** methods are static so that your orchestration does not need to create an instance of it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49051-111">使用する、 **OrchestrationEventStream**オブジェクトへの参照を追加する必要があります、 **Microsoft.BizTalk.Bam.XLANGs**と**Microsoft.BizTalk.Bam.EventObservation**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="49051-111">To use the **OrchestrationEventStream** object, you need to add references to the **Microsoft.BizTalk.Bam.XLANGs** and **Microsoft.BizTalk.Bam.EventObservation** assemblies.</span></span> <span data-ttu-id="49051-112">ただし、 **OrchestrationEventStream**オブジェクトは、 **Microsoft.BizTalk.Bam.EventObservation**名前空間に存在する、 **Microsoft.BizTalk.Bam.XLANGs**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="49051-112">Although the **OrchestrationEventStream** object is in the **Microsoft.BizTalk.Bam.EventObservation** namespace, it resides in the **Microsoft.BizTalk.Bam.XLANGs** assembly.</span></span>  
  
 <span data-ttu-id="49051-113">BAM を使用する場合には追跡プロファイル エディタ (TPE) が推奨されていますが、TPE ではオーケストレーション変数値を取得できず、カスタム オブジェクトも処理できません。</span><span class="sxs-lookup"><span data-stu-id="49051-113">Although the Tracking Profile Editor (TPE) is the preferred way of using BAM, TPE cannot capture the orchestration variable values, nor can it handle custom objects.</span></span> <span data-ttu-id="49051-114">ソリューションでは、BAM API を使用してこれらの制限を回避します。</span><span class="sxs-lookup"><span data-stu-id="49051-114">The solution uses the BAM API to overcome these limitations.</span></span>  
  
 <span data-ttu-id="49051-115">BAM の詳細については、次を参照してください。[を使用したビジネス アクティビティ監視](../core/using-business-activity-monitoring.md)です。</span><span class="sxs-lookup"><span data-stu-id="49051-115">For general information about BAM, see [Using Business Activity Monitoring](../core/using-business-activity-monitoring.md).</span></span> <span data-ttu-id="49051-116">追跡プロファイル エディター (TPE) についての詳細について、次を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)です。</span><span class="sxs-lookup"><span data-stu-id="49051-116">For information about the Tracking Profile Editor (TPE), see [Tracking Profile Editor](../core/tracking-profile-editor.md).</span></span>  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a><span data-ttu-id="49051-117">OrchestrationEventStream オブジェクトのラップ処理</span><span class="sxs-lookup"><span data-stu-id="49051-117">Wrapping the OrchestrationEventStream Object</span></span>  
 <span data-ttu-id="49051-118">サービス指向ソリューションのラップ、 **OrchestrationEventStream**クラス、 **ServiceLevelTracking**クラスです。</span><span class="sxs-lookup"><span data-stu-id="49051-118">The service oriented solution wraps the **OrchestrationEventStream** class with the **ServiceLevelTracking** class.</span></span> <span data-ttu-id="49051-119">**ServiceLevelTracking**クラスは、アプリケーション固有のマイルス トーン メソッドを提供し、いくつかの使用方法の詳細の表示と非**OrchestrationEventStream**です。</span><span class="sxs-lookup"><span data-stu-id="49051-119">The **ServiceLevelTracking** class provides application-specific milestone methods and hides some of the details of using **OrchestrationEventStream**.</span></span>  
  
 <span data-ttu-id="49051-120">として**OrchestrationEventStream**のすべてのメソッド**ServiceLevelTracking**は静的です。</span><span class="sxs-lookup"><span data-stu-id="49051-120">As in **OrchestrationEventStream**, all the methods of **ServiceLevelTracking** are static.</span></span> <span data-ttu-id="49051-121">したがって、オーケストレーションまたはカスタム コンポーネントのインスタンスを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49051-121">Thus, the orchestration or custom component does not need to create an instance of it.</span></span> <span data-ttu-id="49051-122">アクティビティの追跡を開始するメソッド**TrackingBeginRequest**、一意のアクティビティ インスタンス ID を返します。</span><span class="sxs-lookup"><span data-stu-id="49051-122">The method that begins tracking an activity, **TrackingBeginRequest**, returns a unique activity instance ID.</span></span> <span data-ttu-id="49051-123">すべての後続の追跡イベントに関連付ける必要がこのアクティビティ インスタンス ID 正しく、サービス レベルのデータを取得するためのインスタンスを一意になっているため、 **CustomerService**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="49051-123">All subsequent tracking events must be associated with this activity instance ID in order to capture the service level data correctly, because it is unique to the instance of the **CustomerService** orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49051-124">参照</span><span class="sxs-lookup"><span data-stu-id="49051-124">See Also</span></span>  
 <span data-ttu-id="49051-125">[指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="49051-125">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="49051-126">指向ソリューションのサービスの実装の要点</span><span class="sxs-lookup"><span data-stu-id="49051-126">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)