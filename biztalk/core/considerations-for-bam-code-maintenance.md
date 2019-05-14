---
title: BAM に関する考慮事項はコードのメンテナンス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, code maintenance
- BAMInterceptor class
ms.assetid: e1f1d8e0-207c-47e1-b9bd-a473c86922ce
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8a5b305fbd72861383444836808e765e8313e90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390408"
---
# <a name="considerations-for-bam-code-maintenance"></a><span data-ttu-id="4d083-102">BAM コードの管理に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4d083-102">Considerations for BAM Code Maintenance</span></span>
<span data-ttu-id="4d083-103">BAM を使用するアプリケーションのインストルメント化の方法を決定する場合は、要件が変更になる可能性を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d083-103">When you decide how to instrument your application to use BAM, you should consider the likelihood that requirements will change.</span></span> <span data-ttu-id="4d083-104">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) クラスの 1 つでメソッドを呼び出して監視対象データを書き込む場合、基本的には、アプリケーションに観測モデルをハードコーディングします。</span><span class="sxs-lookup"><span data-stu-id="4d083-104">If you call methods on one of the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) classes to write the data that is being monitored, you are essentially “hard-coding” the observation model into the application.</span></span> <span data-ttu-id="4d083-105">監視対象データを変更する必要がある場合は、アプリケーションをオフラインにして、コードを変更し、アプリケーションを再コンパイルして、更新したアプリケーションを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d083-105">If you need to change which data is being monitored, you will have to take the application offline, change the code, recompile the application, and then redeploy the updated application.</span></span>  
  
 <span data-ttu-id="4d083-106">または、 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) クラスでメソッドを呼び出すと、アプリケーションをインストルメント化できます。</span><span class="sxs-lookup"><span data-stu-id="4d083-106">Alternatively, you can instrument your application by calling methods on the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) class.</span></span> <span data-ttu-id="4d083-107">[Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) クラスは構成ファイルを参照し、監視対象のイベントとデータを決定します。</span><span class="sxs-lookup"><span data-stu-id="4d083-107">The [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) class refers to a configuration file to determine which events and data to monitor.</span></span> <span data-ttu-id="4d083-108"> [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) クラスを使用すると、コードを一度インストルメント化すれば、メタデータを更新することによって監視対象データを変更できるので、アプリケーションをオフラインにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4d083-108">By using the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) class, you can instrument your code once, and then change the data that is being monitored by updating the metadata, without having to take the application offline.</span></span>  
  
## <a name="instrumenting-your-application-by-using-the-eventstream-object"></a><span data-ttu-id="4d083-109">EventStream オブジェクトを使用したアプリケーションのインストルメント化</span><span class="sxs-lookup"><span data-stu-id="4d083-109">Instrumenting Your Application by Using the EventStream Object</span></span>  
 <span data-ttu-id="4d083-110">この方法はより簡単で、特定の監視要件がよくわかっている専用アプリケーションをビルドする場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="4d083-110">This approach is simpler and applies when you are building a dedicated application with specific, well-known monitoring requirements.</span></span> <span data-ttu-id="4d083-111">この方法を使用する場合は、次の点を明確にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d083-111">Before deciding to use this approach, you need to know the answers to the following questions:</span></span>  
  
- <span data-ttu-id="4d083-112">BAM のマイルストーンは何か、コードのどこで発生するのか。</span><span class="sxs-lookup"><span data-stu-id="4d083-112">What are the BAM milestones, and where in the code do they occur?</span></span>  
  
- <span data-ttu-id="4d083-113">監視するデータは何か、コードのどこで、いつ、そのデータを使用できるのか。</span><span class="sxs-lookup"><span data-stu-id="4d083-113">What data will be monitored, and when and where in the code is that data available?</span></span>  
  
  <span data-ttu-id="4d083-114">いずれかの質問に対する回答が変更になる可能性がある場合は、この方法ではなく、 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)オブジェクトを使用したアプリケーションのインストルメント化を検討してください。</span><span class="sxs-lookup"><span data-stu-id="4d083-114">If the answer to either of these questions is likely to change, you should consider instrumenting your application by using the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)object instead.</span></span>  
  
  <span data-ttu-id="4d083-115">このハードコーディングの方法では、必要に応じて単純に、 [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)、 [Microsoft.BizTalk.Bam.EventObservation.BufferedEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.bufferedeventstream.aspx)、 **MessagingEventStream** クラスで (パイプライン実装から) メソッドを呼び出すか、または **OrchestrationEventStream** クラスで (オーケストレーション実装から) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4d083-115">When you follow this “hard-coded” approach, you simply call methods on the [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx), [Microsoft.BizTalk.Bam.EventObservation.BufferedEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.bufferedeventstream.aspx), **MessagingEventStream** (from pipeline implementations) or **OrchestrationEventStream** (from orchestration implementations) class, depending on your requirements.</span></span>  
  
## <a name="instrumenting-your-application-by-using-the-baminterceptor-object"></a><span data-ttu-id="4d083-116">BAMInterceptor オブジェクトを使用したアプリケーションのインストルメント化</span><span class="sxs-lookup"><span data-stu-id="4d083-116">Instrumenting Your Application by Using the BAMInterceptor Object</span></span>  
 <span data-ttu-id="4d083-117">この方法は、次の場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4d083-117">This approach is better when:</span></span>  
  
- <span data-ttu-id="4d083-118">データの可視性とアプリケーションのパフォーマンスとのバランスを調整する必要があり、実行時に監視対象データを制御したい。</span><span class="sxs-lookup"><span data-stu-id="4d083-118">You need to balance visibility of data with performance of the application, and you want to be able to control the data that is monitored at run time.</span></span>  
  
- <span data-ttu-id="4d083-119">アプリケーションで大容量の XML メッセージを処理し、その中のデータが最終的に監視に重要になる可能性がある。</span><span class="sxs-lookup"><span data-stu-id="4d083-119">The application processes large XML messages, in which any data may eventually become important for monitoring.</span></span>  
  
- <span data-ttu-id="4d083-120">別のデータを監視するために、アプリケーションを停止してコードを変更する余裕がない。</span><span class="sxs-lookup"><span data-stu-id="4d083-120">It is unacceptable to stop the application and change the code to monitor different data.</span></span>  
  
  <span data-ttu-id="4d083-121">この方法では、 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)クラスのメソッドを使用して、一般的な方法でアプリケーションをインストルメント化します。</span><span class="sxs-lookup"><span data-stu-id="4d083-121">In this approach, you instrument the application in a generic way by using the methods of the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)class.</span></span> <span data-ttu-id="4d083-122">さまざまな構成をインターセプターに渡すことによって、BAM が監視するデータを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d083-122">By passing different configurations to the interceptor, you can change the data that BAM monitors.</span></span>  
  
  <span data-ttu-id="4d083-123">追跡プロファイル エディター (TPE) を使用すると、BAM が BizTalk オーケストレーションから収集するデータを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d083-123">You can use the Tracking Profile Editor (TPE) to change the data that BAM collects from a BizTalk orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d083-124">参照</span><span class="sxs-lookup"><span data-stu-id="4d083-124">See Also</span></span>  
 <span data-ttu-id="4d083-125">[アクティビティを使用](../core/using-an-activity.md) </span><span class="sxs-lookup"><span data-stu-id="4d083-125">[Using an Activity](../core/using-an-activity.md) </span></span>  
 <span data-ttu-id="4d083-126">[BAM インターセプターは何ですか。](../core/what-is-the-bam-interceptor.md) </span><span class="sxs-lookup"><span data-stu-id="4d083-126">[What Is the BAM Interceptor?](../core/what-is-the-bam-interceptor.md) </span></span>  
 [<span data-ttu-id="4d083-127">BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="4d083-127">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)