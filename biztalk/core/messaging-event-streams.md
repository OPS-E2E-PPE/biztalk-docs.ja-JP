---
title: メッセージング イベント ストリーム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dc56aff-c093-4c79-9cc7-f72079ee927f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae51bce79ca06edc8874100648b1b3002f917f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324969"
---
# <a name="messaging-event-streams"></a><span data-ttu-id="87d2e-102">メッセージング イベント ストリーム</span><span class="sxs-lookup"><span data-stu-id="87d2e-102">Messaging Event Streams</span></span>
<span data-ttu-id="87d2e-103">BizTalk Server がインストールされているし、するが、コンピューター、アプリケーションの実行は BizTalk パイプライン トランザクションの一部である項目を追跡する場合は、メッセージング イベント ストリーム (MES) を使用します。</span><span class="sxs-lookup"><span data-stu-id="87d2e-103">You use Messaging Event Streams (MES) when your application runs on a computer on which BizTalk Server is installed and you are you are tracking items that are part of BizTalk pipeline transactions.</span></span> <span data-ttu-id="87d2e-104">MES を使用すると、BAM イベントの永続化非 BizTalk パイプライン トランザクションとの同期にならないように。</span><span class="sxs-lookup"><span data-stu-id="87d2e-104">Using MES ensures that your BAM event persistence remains in sync with the BizTalk pipeline transactions.</span></span>  
  
 <span data-ttu-id="87d2e-105">メッセージング イベント ストリームによって返される EventStream オブジェクトのインスタンスである、 [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)メソッド。</span><span class="sxs-lookup"><span data-stu-id="87d2e-105">Messaging Event Streams are instances of EventStream objects returned by the [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx) method.</span></span>  
  
 <span data-ttu-id="87d2e-106">メッセージング イベント ストリームは非同期であり、BizTalk メッセージ ボックス データベースで最初に追跡データを保存します。</span><span class="sxs-lookup"><span data-stu-id="87d2e-106">Messaging Event Streams are asynchronous and store tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="87d2e-107">このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="87d2e-107">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="87d2e-108">Ipipelinecontext は、 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)名前空間。</span><span class="sxs-lookup"><span data-stu-id="87d2e-108">IPipelineContext is found in the [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx) namespace.</span></span> <span data-ttu-id="87d2e-109">API を使用して、プロジェクトに、Microsoft.BizTalk.Pipeline (microsoft.biztalk.pipeline.dll 内) を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87d2e-109">To use the API you must add the Microsoft.BizTalk.Pipeline (in microsoft.biztalk.pipeline.dll) to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d2e-110">参照</span><span class="sxs-lookup"><span data-stu-id="87d2e-110">See Also</span></span>  
 <span data-ttu-id="87d2e-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span><span class="sxs-lookup"><span data-stu-id="87d2e-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span></span>  
 <span data-ttu-id="87d2e-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span><span class="sxs-lookup"><span data-stu-id="87d2e-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span></span>  
 [<span data-ttu-id="87d2e-113">Microsoft.BizTalk.Component.Interop</span><span class="sxs-lookup"><span data-stu-id="87d2e-113">Microsoft.BizTalk.Component.Interop</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)