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
# <a name="monitoring-the-service-oriented-solution-with-bam"></a>BAM によるソリューションを指向サービスを監視します。
ソリューション内のすべてのバージョンのアクティビティの監視、 **CustomerService**ビジネス アクティビティ監視 (BAM) API を使用してオーケストレーションします。 新しいより具体的には、 **OrchestrationEventStream**オブジェクト。  
  
## <a name="what-is-the-orchestrationeventstream-object"></a>OrchestrationEventStream オブジェクトとは何ですか。  
 新しい**OrchestrationEventStream**追跡とのオーケストレーションから監視オブジェクトを使用できます。 キャプチャされた情報は、オーケストレーションの状態の一貫性。 たとえば、オーケストレーションの実行中のオーケストレーションのホスト インスタンスを再起動する場合、インスタンスの最後の永続性ポイントからオーケストレーション インスタンスを再起動します。 **OrchestrationEventStream**クラスは、キャプチャされたデータは、オーケストレーション インスタンスの最後の永続化ポイントとトランザクション上一貫性のあることを保証します。 すべての**OrchestrationEventStream**すると、オーケストレーションは、そのインスタンスを作成する必要はありません、メソッドは静的です。  
  
> [!NOTE]
>  使用する、 **OrchestrationEventStream**オブジェクトへの参照を追加する必要がある、 **Microsoft.BizTalk.Bam.XLANGs**と**Microsoft.BizTalk.Bam.EventObservation**アセンブリ。 ただし、 **OrchestrationEventStream**オブジェクトは、 **Microsoft.BizTalk.Bam.EventObservation**名前空間に存在する、 **Microsoft.BizTalk.Bam.XLANGs**アセンブリ。  
  
 追跡プロファイル エディター (TPE) では、BAM を使用することをお勧めが、TPE にオーケストレーション変数の値をキャプチャできませんも、カスタム オブジェクトを処理することができます。 ソリューションでは、これらの制限を克服するために、BAM API を使用します。  
  
 BAM の詳細については、次を参照してください。[ビジネス アクティビティの監視を使用して](../core/using-business-activity-monitoring.md)します。 追跡プロファイル エディター (TPE) についての情報を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)します。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>OrchestrationEventStream オブジェクトのラップ  
 サービス指向ソリューションのラップ、 **OrchestrationEventStream**クラス、 **ServiceLevelTracking**クラス。 **ServiceLevelTracking**クラスは、アプリケーション固有のマイルス トーン メソッドを提供し、いくつかの使用方法の詳細を非表示に**OrchestrationEventStream**します。  
  
 うに**OrchestrationEventStream**のすべてのメソッド**ServiceLevelTracking**は静的です。 したがって、オーケストレーションまたはカスタム コンポーネントは、そのインスタンスを作成する必要ありません。 アクティビティの追跡を開始するメソッドで**TrackingBeginRequest**、一意のアクティビティ インスタンスの ID を返します。 以降の追跡イベントをすべて関連付ける必要があるこのアクティビティ インスタンス ID サービス レベルのデータを正常にキャプチャするにはのインスタンスに一意であるため、 **CustomerService**オーケストレーションします。  
  
## <a name="see-also"></a>参照  
 [開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md)   
 [サービス指向ソリューションの実装の重要なポイント](../core/implementation-highlights-of-the-service-oriented-solution.md)