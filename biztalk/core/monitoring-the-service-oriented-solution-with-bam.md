---
title: BAM によるソリューションを指向、サービスの監視 |Microsoft Docs
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
ms.openlocfilehash: 489e1b8c19f10831e1e75115a41ac32660dfe99a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264501"
---
# <a name="monitoring-the-service-oriented-solution-with-bam"></a><span data-ttu-id="5c193-102">BAM によるソリューションを指向サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="5c193-102">Monitoring the Service Oriented Solution with BAM</span></span>
<span data-ttu-id="5c193-103">ソリューション内のすべてのバージョンのアクティビティの監視、 **CustomerService**ビジネス アクティビティ監視 (BAM) API を使用してオーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5c193-103">The solution monitors activity in all versions of the **CustomerService** orchestration using the Business Activity Monitoring (BAM) API.</span></span> <span data-ttu-id="5c193-104">新しいより具体的には、 **OrchestrationEventStream**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5c193-104">More specifically, it uses the new **OrchestrationEventStream** object.</span></span>  
  
## <a name="what-is-the-orchestrationeventstream-object"></a><span data-ttu-id="5c193-105">OrchestrationEventStream オブジェクトとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5c193-105">What is the OrchestrationEventStream Object?</span></span>  
 <span data-ttu-id="5c193-106">新しい**OrchestrationEventStream**追跡とのオーケストレーションから監視オブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c193-106">The new **OrchestrationEventStream** object enables tracking and monitoring from orchestrations.</span></span> <span data-ttu-id="5c193-107">キャプチャされた情報は、オーケストレーションの状態の一貫性。</span><span class="sxs-lookup"><span data-stu-id="5c193-107">The information captured is transactionally consistent with the orchestration state.</span></span> <span data-ttu-id="5c193-108">たとえば、オーケストレーションの実行中のオーケストレーションのホスト インスタンスを再起動する場合、インスタンスの最後の永続性ポイントからオーケストレーション インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5c193-108">For example, if the orchestration host instance restarts in the middle of executing the orchestration, the orchestration instance restarts from the last persistence point of the instance.</span></span> <span data-ttu-id="5c193-109">**OrchestrationEventStream**クラスは、キャプチャされたデータは、オーケストレーション インスタンスの最後の永続化ポイントとトランザクション上一貫性のあることを保証します。</span><span class="sxs-lookup"><span data-stu-id="5c193-109">The **OrchestrationEventStream** class ensures that the captured data is transactionally consistent with the orchestration instance's last persistence point.</span></span> <span data-ttu-id="5c193-110">すべての**OrchestrationEventStream**すると、オーケストレーションは、そのインスタンスを作成する必要はありません、メソッドは静的です。</span><span class="sxs-lookup"><span data-stu-id="5c193-110">All of the **OrchestrationEventStream** methods are static so that your orchestration does not need to create an instance of it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c193-111">使用する、 **OrchestrationEventStream**オブジェクトへの参照を追加する必要がある、 **Microsoft.BizTalk.Bam.XLANGs**と**Microsoft.BizTalk.Bam.EventObservation**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="5c193-111">To use the **OrchestrationEventStream** object, you need to add references to the **Microsoft.BizTalk.Bam.XLANGs** and **Microsoft.BizTalk.Bam.EventObservation** assemblies.</span></span> <span data-ttu-id="5c193-112">ただし、 **OrchestrationEventStream**オブジェクトは、 **Microsoft.BizTalk.Bam.EventObservation**名前空間に存在する、 **Microsoft.BizTalk.Bam.XLANGs**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="5c193-112">Although the **OrchestrationEventStream** object is in the **Microsoft.BizTalk.Bam.EventObservation** namespace, it resides in the **Microsoft.BizTalk.Bam.XLANGs** assembly.</span></span>  
  
 <span data-ttu-id="5c193-113">追跡プロファイル エディター (TPE) では、BAM を使用することをお勧めが、TPE にオーケストレーション変数の値をキャプチャできませんも、カスタム オブジェクトを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="5c193-113">Although the Tracking Profile Editor (TPE) is the preferred way of using BAM, TPE cannot capture the orchestration variable values, nor can it handle custom objects.</span></span> <span data-ttu-id="5c193-114">ソリューションでは、これらの制限を克服するために、BAM API を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c193-114">The solution uses the BAM API to overcome these limitations.</span></span>  
  
 <span data-ttu-id="5c193-115">BAM の詳細については、次を参照してください。[ビジネス アクティビティの監視を使用して](../core/using-business-activity-monitoring.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c193-115">For general information about BAM, see [Using Business Activity Monitoring](../core/using-business-activity-monitoring.md).</span></span> <span data-ttu-id="5c193-116">追跡プロファイル エディター (TPE) についての情報を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c193-116">For information about the Tracking Profile Editor (TPE), see [Tracking Profile Editor](../core/tracking-profile-editor.md).</span></span>  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a><span data-ttu-id="5c193-117">OrchestrationEventStream オブジェクトのラップ</span><span class="sxs-lookup"><span data-stu-id="5c193-117">Wrapping the OrchestrationEventStream Object</span></span>  
 <span data-ttu-id="5c193-118">サービス指向ソリューションのラップ、 **OrchestrationEventStream**クラス、 **ServiceLevelTracking**クラス。</span><span class="sxs-lookup"><span data-stu-id="5c193-118">The service oriented solution wraps the **OrchestrationEventStream** class with the **ServiceLevelTracking** class.</span></span> <span data-ttu-id="5c193-119">**ServiceLevelTracking**クラスは、アプリケーション固有のマイルス トーン メソッドを提供し、いくつかの使用方法の詳細を非表示に**OrchestrationEventStream**します。</span><span class="sxs-lookup"><span data-stu-id="5c193-119">The **ServiceLevelTracking** class provides application-specific milestone methods and hides some of the details of using **OrchestrationEventStream**.</span></span>  
  
 <span data-ttu-id="5c193-120">うに**OrchestrationEventStream**のすべてのメソッド**ServiceLevelTracking**は静的です。</span><span class="sxs-lookup"><span data-stu-id="5c193-120">As in **OrchestrationEventStream**, all the methods of **ServiceLevelTracking** are static.</span></span> <span data-ttu-id="5c193-121">したがって、オーケストレーションまたはカスタム コンポーネントは、そのインスタンスを作成する必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5c193-121">Thus, the orchestration or custom component does not need to create an instance of it.</span></span> <span data-ttu-id="5c193-122">アクティビティの追跡を開始するメソッドで**TrackingBeginRequest**、一意のアクティビティ インスタンスの ID を返します。</span><span class="sxs-lookup"><span data-stu-id="5c193-122">The method that begins tracking an activity, **TrackingBeginRequest**, returns a unique activity instance ID.</span></span> <span data-ttu-id="5c193-123">以降の追跡イベントをすべて関連付ける必要があるこのアクティビティ インスタンス ID サービス レベルのデータを正常にキャプチャするにはのインスタンスに一意であるため、 **CustomerService**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5c193-123">All subsequent tracking events must be associated with this activity instance ID in order to capture the service level data correctly, because it is unique to the instance of the **CustomerService** orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c193-124">参照</span><span class="sxs-lookup"><span data-stu-id="5c193-124">See Also</span></span>  
 <span data-ttu-id="5c193-125">[開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="5c193-125">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="5c193-126">サービス指向ソリューションの実装の重要なポイント</span><span class="sxs-lookup"><span data-stu-id="5c193-126">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)