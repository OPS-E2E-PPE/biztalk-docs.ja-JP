---
title: "BAM によるソリューションを指向サービスを監視する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring, service solutions
- service solution tutorial, monitoring
- OrchestrationEventStream object
ms.assetid: 9b251580-9371-490e-9218-0ce3f6b00fa6
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1aeaec2513ebe3c6d7fe62ef542b6f044bca56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-service-oriented-solution-with-bam"></a>BAM によるソリューションを指向サービスを監視します。
ソリューション内のすべてのバージョンのアクティビティの監視、 **CustomerService**ビジネス アクティビティ監視 (BAM) API を使用してオーケストレーションです。 具体的には、使用して、新しい**OrchestrationEventStream**オブジェクト。  
  
## <a name="what-is-the-orchestrationeventstream-object"></a>OrchestrationEventStream オブジェクトについて  
 新しい**OrchestrationEventStream**オブジェクトは、オーケストレーションから監視と追跡ができるようにします。 取得された情報とオーケストレーションの状態には、トランザクション上の一貫性があります。 たとえば、オーケストレーションの実行中にオーケストレーションのホスト インスタンスを再起動すると、オーケストレーション インスタンスはインスタンスの最後の永続化ポイントから再起動されます。 **OrchestrationEventStream**クラス キャプチャされたデータが、オーケストレーション インスタンスの最後の永続性ポイントに一貫性があることを確認します。 すべての**OrchestrationEventStream**すると、オーケストレーションは、そのインスタンスを作成する必要はありません、メソッドは静的です。  
  
> [!NOTE]
>  使用する、 **OrchestrationEventStream**オブジェクトへの参照を追加する必要があります、 **Microsoft.BizTalk.Bam.XLANGs**と**Microsoft.BizTalk.Bam.EventObservation**アセンブリ。 ただし、 **OrchestrationEventStream**オブジェクトは、 **Microsoft.BizTalk.Bam.EventObservation**名前空間に存在する、 **Microsoft.BizTalk.Bam.XLANGs**アセンブリ。  
  
 BAM を使用する場合には追跡プロファイル エディタ (TPE) が推奨されていますが、TPE ではオーケストレーション変数値を取得できず、カスタム オブジェクトも処理できません。 ソリューションでは、BAM API を使用してこれらの制限を回避します。  
  
 BAM の詳細については、次を参照してください。[を使用したビジネス アクティビティ監視](../core/using-business-activity-monitoring.md)です。 追跡プロファイル エディター (TPE) についての詳細について、次を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)です。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>OrchestrationEventStream オブジェクトのラップ処理  
 サービス指向ソリューションのラップ、 **OrchestrationEventStream**クラス、 **ServiceLevelTracking**クラスです。 **ServiceLevelTracking**クラスは、アプリケーション固有のマイルス トーン メソッドを提供し、いくつかの使用方法の詳細の表示と非**OrchestrationEventStream**です。  
  
 として**OrchestrationEventStream**のすべてのメソッド**ServiceLevelTracking**は静的です。 したがって、オーケストレーションまたはカスタム コンポーネントのインスタンスを作成する必要はありません。 アクティビティの追跡を開始するメソッド**TrackingBeginRequest**、一意のアクティビティ インスタンス ID を返します。 すべての後続の追跡イベントに関連付ける必要がこのアクティビティ インスタンス ID 正しく、サービス レベルのデータを取得するためのインスタンスを一意になっているため、 **CustomerService**オーケストレーションです。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md)   
 [指向ソリューションのサービスの実装の要点](../core/implementation-highlights-of-the-service-oriented-solution.md)