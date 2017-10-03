---
title: "ビジネス アクティビティ監視 (BAM) のパフォーマンスを最適化する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83801a4e147b3e1eaf34c5e264d6adecfbdf8f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a>ビジネス アクティビティ監視 (BAM) のパフォーマンスを最適化します。
このトピックでは、ビジネス アクティビティ監視 (BAM) のパフォーマンス要因について説明します。  
  
## <a name="bam-disk-usage-configuration"></a>BAM のディスク使用量の構成  
 BAM では、大量のデータを BAM データベースに保存されているため、BizTalk システムに負荷がときに大幅なオーバーヘッドが発生します。 したがって、BAM データベースのディスク I/O の手法を賢く利用は非常に重要です。  
  
## <a name="bam-eventstream-apis"></a>BAM の EventStream Api  
 EventStreams の 4 つの種類は、BizTalk BAM シナリオで使用可能です。  
  
-   DirectEventStream (DES)  
  
-   BufferedEventStream (BES)  
  
-   OrchestrationEventStream (OES)  
  
-   MessageEventStream (MES)  
  
 次の要因に基づくこれらの Api のいずれかを選択する必要があります。  
  
-   待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。  
  
-   重視する場合はパフォーマンスとイベント挿入のスループット、非同期 API (BES、OES または MES) を選択します。  
  
-   BizTalk Server がインストールされてがないコンピューターで実行されるアプリケーションを作成している場合、DES および BES; を使用します。これらの Api は、非 BizTalk アプリケーションで使用できます。  
  
    > [!NOTE]  
    >  シナリオによっては、複数種類の EventStream を使用する必要があります。 たとえば、パイプライン処理でのかどうか、パイプラインはロールバック、トランザクションに関係なく、BAM で特定のデータをキャプチャすることがあります。 具体的には、失敗したメッセージの数に関するデータの取得または回数がパイプライン処理中に発生したい場合があります。 この状況でデータを取得するには、BES を使用する必要があります。  
  
-   BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します  (これらの API は BizTalk アプリケーションでのみ使用できます)。  
  
    > [!NOTE]  
    >  OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。  
  
-   パイプライン トランザクションと同期する BAM イベントの永続化する場合は、メッセージング イベント ストリーム (MES) を使用する必要があります。  
  
 すべて、非同期 EventStreams (BES、MES、OES) は、BizTalk メッセージ ボックス データベースに最初のデータを保持します。 このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。  
  
 BAM の EventStream Api の詳細については、次を参照してください。 [EventStream クラス](http://go.microsoft.com/fwlink/?LinkId=158046)(http://go.microsoft.com/fwlink/?LinkId=158046)、BizTalk Server のドキュメントにします。  
  
## <a name="bam-performance-counters"></a>BAM パフォーマンス カウンター  
 BAM のパフォーマンス カウンターの詳細な一覧についてを参照してください。 [BAM パフォーマンス カウンター](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048)、BizTalk Server のドキュメントにします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-performance.md)