---
title: BAM イベント バス サービスを管理する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, migrating data
- Primary Import database [BAM], migrating data
- migrating, data [BAM]
- managing [BAM], Event Bus Service
- Event Bus Service [BAM], managing
- Tracking Data Decode Service (TDDS)
ms.assetid: 556e7fe2-4a7d-46f6-8e55-f41be4e666dc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f265201e371a86072c06b336b4d00bb1742f5f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262818"
---
# <a name="managing-the-bam-event-bus-service"></a>BAM イベント バス サービスの管理
BAM イベント バス サービスは、Tracking Data Decode Service (TDDS) とも呼ばれており、転送元データベースに格納されている追跡データ (ストリーム) を処理し、そのデータを後で簡単にクエリできるように保存します。  
  
 BAM イベント バス サービスは、ビジネス インテリジェンス データを BAM プライマリ インポート データベースに移動し、BizTalk 稼働状況の監視データを DTA データベースに移動します。 BAM イベント バス サービスは、BizTalk サービス内のサブサービスとして実行されます。  
  
 実行中に、イベント データを収集し、アプリケーションの状態と同じデータベースにデータを一時的に保存して Microsoft BizTalk® Server などのトランザクションのアプリケーションのアクティビティを監視する-たとえば、メッセージ ボックス データベースです。  
  
> [!NOTE]
>  異なる BizTalk グループの追跡をホストするアプリケーション インスタンスを、同じコンピューターに複数作成しないでください。 同じすべての BizTalk グループが表示されるために、イベントが BizTalk 管理コンソールで、またはイベント ログにどの BizTalk グループに属するを区別することはできません、同じコンピューターに別の BizTalk グループを追跡するインスタンスがある場合名前です。  
  
 BAM イベント バス サービスでは、イベント データを読み取ってデコードしてから、簡単にデータをクエリできる Microsoft SQL Server™ データベースに保存します。  
  
 BAM イベント バス サービスには次の利点があります。  
  
-   常にイベント データがアプリケーションの状態に一致します。また、コミットされていない進行状況は公開されません。  
  
-   イベント データは、アプリケーションの状態が変化するとその状態と同じローカル トランザクションに少数のレコードとして保存されるため、実行中のアプリケーションへの影響を最小限に抑えることができます。  
  
-   アプリケーションの状態用の SQL Server ストレージは、さらに最適化され、実行パフォーマンスが向上します。 データは TDDS によってデコードされ、個別のデータベース (BAM プライマリ インポート データベースまたは DTA データベースのいずれか) に格納されます。 レポートが生成されると、データはデータベースから照会され、アプリケーションの状態を格納するメッセージ ボックス データベースに影響を与えます。  
  
-   アプリケーション サーバーおよびデータベースでは、クエリできる形式でイベント データを保存する操作が行われません。 この操作は、BAM イベント バス サービスと転送先の SQL Server データベースを実行しているコンピューターによって行われます。  
  
-   イベント データは短い待機時間で処理され、TDDS クエリ処理を高速にすることができます。 BAM イベント バス サービスでは、待機時間を最小限に抑えるためにリソースを調整します。  
  
 BAM イベント バス サーバーでは、構成情報が含まれた中央データベースへの接続を使用することにより、リソースを調整します。 1 分ごとに、BAM イベント バス サービスによって中央データベースにメッセージが送信されます。中央データベースには、その時点の BAM イベント バス サービスの状態が格納されます。  
  
 このメッセージは、ハートビート メッセージといいます。 各 BAM イベント バス サービスでは、次に実行する作業があるかどうかもチェックされます。 たとえば、追加されたメッセージ ボックス データベースなど、所有されていないセッションがあるかどうかがチェックされます。  
  
 BAM イベント バス セッションとは、イベント データを、メッセージ ボックス データベースなどの転送元データベースから、クエリできる形式で格納される転送先データベースに移動する処理です。 同じ BAM イベント バス サービスで 1 つ以上のセッションを処理できます。  
  
 次の図に、BAM イベント バス サーバー プールを構成する BAM イベント バス サーバーのグループを示します。  
  
 ![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")  
BAM イベント バス サーバー プールの図  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM パフォーマンス カウンター](../core/bam-performance-counters.md)  
  
-   [BAM イベント バス サービスのストアド プロシージャ](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [BAM イベント バス サービス サーバーのフェールオーバー](../core/bam-event-bus-service-server-failover.md)  
  
-   [BAM イベント バス サービスのインスタンスを作成します。](../core/creating-instances-of-the-bam-event-bus-service.md)