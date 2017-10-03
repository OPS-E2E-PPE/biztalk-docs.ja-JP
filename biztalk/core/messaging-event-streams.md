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
# <a name="messaging-event-streams"></a>メッセージング イベント ストリーム
メッセージング イベント ストリーム (MES) は、BizTalk Server がインストールされているコンピューターでアプリケーションを実行し、BizTalk パイプライン トランザクションの一部である項目を追跡する場合に使用します。 MES を使用すると、BAM イベントの永続化と BizTalk パイプライン トランザクションとの同期を維持することができます。  
  
 メッセージング イベント ストリームによって返される EventStream オブジェクトのインスタンスである、 [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)メソッドです。  
  
 メッセージング イベント ストリームは非同期であり、最初に追跡データを BizTalk メッセージ ボックス データベースに保存します。 このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。  
  
 Ipipelinecontext は、 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)名前空間。 API を使用するには、Microsoft.BizTalk.Pipeline (microsoft.biztalk.pipeline.dll 内) をプロジェクトに追加する必要があります。  
  
## <a name="see-also"></a>参照  
 [OrchestrationEventStream](../core/orchestrationeventstream.md)   
 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx)   
 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)