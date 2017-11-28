---
title: "メッセージング イベント ストリーム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dc56aff-c093-4c79-9cc7-f72079ee927f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d955dbc2b50d1d9c40b54736762fcbaa2bfe536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messaging-event-streams"></a><span data-ttu-id="6c9fa-102">メッセージング イベント ストリーム</span><span class="sxs-lookup"><span data-stu-id="6c9fa-102">Messaging Event Streams</span></span>
<span data-ttu-id="6c9fa-103">メッセージング イベント ストリーム (MES) は、BizTalk Server がインストールされているコンピューターでアプリケーションを実行し、BizTalk パイプライン トランザクションの一部である項目を追跡する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6c9fa-103">You use Messaging Event Streams (MES) when your application runs on a computer on which BizTalk Server is installed and you are you are tracking items that are part of BizTalk pipeline transactions.</span></span> <span data-ttu-id="6c9fa-104">MES を使用すると、BAM イベントの永続化と BizTalk パイプライン トランザクションとの同期を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="6c9fa-104">Using MES ensures that your BAM event persistence remains in sync with the BizTalk pipeline transactions.</span></span>  
  
 <span data-ttu-id="6c9fa-105">メッセージング イベント ストリームによって返される EventStream オブジェクトのインスタンスである、 [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="6c9fa-105">Messaging Event Streams are instances of EventStream objects returned by the [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx) method.</span></span>  
  
 <span data-ttu-id="6c9fa-106">メッセージング イベント ストリームは非同期であり、最初に追跡データを BizTalk メッセージ ボックス データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="6c9fa-106">Messaging Event Streams are asynchronous and store tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="6c9fa-107">このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c9fa-107">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="6c9fa-108">Ipipelinecontext は、 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)名前空間。</span><span class="sxs-lookup"><span data-stu-id="6c9fa-108">IPipelineContext is found in the [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx) namespace.</span></span> <span data-ttu-id="6c9fa-109">API を使用するには、Microsoft.BizTalk.Pipeline (microsoft.biztalk.pipeline.dll 内) をプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c9fa-109">To use the API you must add the Microsoft.BizTalk.Pipeline (in microsoft.biztalk.pipeline.dll) to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9fa-110">参照</span><span class="sxs-lookup"><span data-stu-id="6c9fa-110">See Also</span></span>  
 <span data-ttu-id="6c9fa-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span><span class="sxs-lookup"><span data-stu-id="6c9fa-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span></span>  
 <span data-ttu-id="6c9fa-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span><span class="sxs-lookup"><span data-stu-id="6c9fa-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span></span>  
 [<span data-ttu-id="6c9fa-113">Microsoft.BizTalk.Component.Interop</span><span class="sxs-lookup"><span data-stu-id="6c9fa-113">Microsoft.BizTalk.Component.Interop</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)