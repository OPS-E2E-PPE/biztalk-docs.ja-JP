---
title: BAM イベント バス サービスの管理 |Microsoft Docs
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
ms.openlocfilehash: 2c9c2851ed6e4c126475ad21f65999a131b24629
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329065"
---
# <a name="managing-the-bam-event-bus-service"></a>BAM イベント バス サービスの管理
BAM イベント バス サービスとも呼ばれる、Tracking Data Decode Service (TDDS) は、ソース データベースに格納されている追跡データ (ストリーム) を処理し、そのデータを簡単に、後でクエリを実行するように保持します。  
  
 BAM イベント バス サービスは、BAM プライマリ インポート データベースへのビジネス インテリジェンス データと BizTalk 稼働状況の監視データを DTA データベースに移動します。 BAM イベント バス サービスは、BizTalk サービス内のサブサービスとして実行されます。  
  
 実行中に、イベント データを収集し、アプリケーションの状態と同じデータベース内のデータを一時的に保存して Microsoft BizTalk® Server などのトランザクション アプリケーションのアクティビティを監視する — たとえば、メッセージ ボックス データベース。  
  
> [!NOTE]
>  同じコンピューター上の別の BizTalk グループの追跡をホストする 1 つ以上のアプリケーション インスタンスを作成しないでください。 すべての BizTalk グループが同じで表示されるため、BizTalk 管理コンソールで、またはイベント ログには、どの BizTalk グループに属しているイベントを区別することはできません異なる BizTalk グループを追跡するインスタンスが同じコンピューターに存在する場合名前。  
  
 BAM イベント バス サービスは、イベント データを読み取る、それをデコードし、データを簡単にクエリできる、Microsoft SQL Server™ データベースに格納します。  
  
 BAM イベント バス サービスには次の利点があります。  
  
- イベント データ、アプリケーションの状態を常に一致して、コミットされていない進行状況は公開されません。  
  
- イベント データには、アプリケーションの状態の変化と同じローカル トランザクションに少数のレコードとしてが保存されるため、実行中のアプリケーションのパフォーマンスに影響は最小限です。  
  
- アプリケーションの状態の記憶域を SQL Server が実行のパフォーマンスをさらに最適化されています。 データは TDDS によってデコードし、別のデータベース、BAM プライマリ インポート データベースまたは DTA データベースのいずれかに格納されています。 レポートが生成されるデータは、データベースから問い合わせが実行されは、アプリケーションの状態を格納するメッセージ ボックス データベースに影響します。  
  
- クエリを実行できる形式でイベント データを格納する作業は、アプリケーション サーバーとデータベースでは行われません。 BAM イベント バス サービスと転送先 SQL Server データベースを実行するマシンにオフロードします。  
  
- イベント データは、TDDS クエリ処理を高速化できる、短い待機時間で処理されます。 BAM イベント バス サービスでは、最小の待機時間を実現するためのリソースを調整します。  
  
  BAM イベント バス サーバーでは、構成情報を格納する中央データベースへの接続を使用して、リソースを調整します。 1 分ごとに、アクティブな各 BAM イベント バス サービスは、中央のデータベースは、その時点で BAM イベント バス サービスの状態を格納するメッセージを送信します。  
  
  このメッセージは、ハートビート メッセージと呼ばれます。 各 BAM イベント バス サービスは、新しい作業を行う必要があるのも確認します。 たとえば、BAM イベント バス サービスは、所有されていない追加されているメッセージ ボックス データベースなどのセッションをチェックします。  
  
  BAM イベント バス セッションとは、クエリを実行できる形式でイベント データを格納する出力先データベースに、メッセージ ボックスなど、ソース データベースからイベント データの移動です。 同じ BAM イベント バス サービスでは、1 つまたは複数のセッションを処理できます。  
  
  次の図は、BAM イベント バス サーバー プールを構成する BAM イベント バス サーバーのグループを示しています。  
  
  ![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")  
  BAM イベント バス サーバー プールの図  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM パフォーマンス カウンター](../core/bam-performance-counters.md)  
  
-   [BAM イベント バス サービスのストアド プロシージャ](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [BAM イベント バス サービス サーバーのフェールオーバー](../core/bam-event-bus-service-server-failover.md)  
  
-   [BAM イベント バス サービスのインスタンスの作成](../core/creating-instances-of-the-bam-event-bus-service.md)