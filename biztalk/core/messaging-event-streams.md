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
# <a name="messaging-event-streams"></a>メッセージング イベント ストリーム
BizTalk Server がインストールされているし、するが、コンピューター、アプリケーションの実行は BizTalk パイプライン トランザクションの一部である項目を追跡する場合は、メッセージング イベント ストリーム (MES) を使用します。 MES を使用すると、BAM イベントの永続化非 BizTalk パイプライン トランザクションとの同期にならないように。  
  
 メッセージング イベント ストリームによって返される EventStream オブジェクトのインスタンスである、 [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx)メソッド。  
  
 メッセージング イベント ストリームは非同期であり、BizTalk メッセージ ボックス データベースで最初に追跡データを保存します。 このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。  
  
 Ipipelinecontext は、 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)名前空間。 API を使用して、プロジェクトに、Microsoft.BizTalk.Pipeline (microsoft.biztalk.pipeline.dll 内) を追加する必要があります。  
  
## <a name="see-also"></a>参照  
 [OrchestrationEventStream](../core/orchestrationeventstream.md)   
 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx)   
 [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)