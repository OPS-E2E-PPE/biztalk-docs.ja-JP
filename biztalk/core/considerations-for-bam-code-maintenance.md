---
title: "コードの保守の BAM に関する考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, code maintenance
- BAMInterceptor class
ms.assetid: e1f1d8e0-207c-47e1-b9bd-a473c86922ce
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f7cfdb75a32c23ef5c8dedec3b6a4c783bf089a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-for-bam-code-maintenance"></a>BAM コードの管理に関する考慮事項
BAM を使用するアプリケーションのインストルメント化の方法を決定する場合は、要件が変更になる可能性を考慮する必要があります。 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) クラスの 1 つでメソッドを呼び出して監視対象データを書き込む場合、基本的には、アプリケーションに観測モデルをハードコーディングします。 監視対象データを変更する必要がある場合は、アプリケーションをオフラインにして、コードを変更し、アプリケーションを再コンパイルして、更新したアプリケーションを再展開する必要があります。  
  
 または、 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) クラスでメソッドを呼び出すと、アプリケーションをインストルメント化できます。 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) クラスは構成ファイルを参照し、監視対象のイベントとデータを決定します。 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) クラスを使用すると、コードを一度インストルメント化すれば、メタデータを更新することによって監視対象データを変更できるので、アプリケーションをオフラインにする必要はありません。  
  
## <a name="instrumenting-your-application-by-using-the-eventstream-object"></a>EventStream オブジェクトを使用したアプリケーションのインストルメント化  
 この方法はより簡単で、特定の監視要件がよくわかっている専用アプリケーションをビルドする場合に適しています。 この方法を使用する場合は、次の点を明確にしておく必要があります。  
  
-   BAM のマイルストーンは何か、コードのどこで発生するのか。  
  
-   監視するデータは何か、コードのどこで、いつ、そのデータを使用できるのか。  
  
 いずれかの質問に対する回答が変更になる可能性がある場合は、この方法ではなく、 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)オブジェクトを使用したアプリケーションのインストルメント化を検討してください。  
  
 このハードコーディングの方法では、必要に応じて単純に、 [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)、 [Microsoft.BizTalk.Bam.EventObservation.BufferedEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.bufferedeventstream.aspx)、 **MessagingEventStream** クラスで (パイプライン実装から) メソッドを呼び出すか、または **OrchestrationEventStream** クラスで (オーケストレーション実装から) メソッドを呼び出します。  
  
## <a name="instrumenting-your-application-by-using-the-baminterceptor-object"></a>BAMInterceptor オブジェクトを使用したアプリケーションのインストルメント化  
 この方法は、次の場合にお勧めします。  
  
-   データの可視性とアプリケーションのパフォーマンスとのバランスを調整する必要があり、実行時に監視対象データを制御したい。  
  
-   アプリケーションで大容量の XML メッセージを処理し、その中のデータが最終的に監視に重要になる可能性がある。  
  
-   別のデータを監視するために、アプリケーションを停止してコードを変更する余裕がない。  
  
 この方法では、 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)クラスのメソッドを使用して、一般的な方法でアプリケーションをインストルメント化します。 さまざまな構成をインターセプターに渡すことによって、BAM が監視するデータを変更できます。  
  
 追跡プロファイル エディター (TPE) を使用すると、BAM が BizTalk オーケストレーションから収集するデータを変更できます。  
  
## <a name="see-also"></a>参照  
 [アクティビティを使用](../core/using-an-activity.md)   
 [BAM インターセプタとは何ですか。](../core/what-is-the-bam-interceptor.md)   
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)