---
title: ビジネス アクティビティ監視 (BAM) のパフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f28771f2611a8b5f7c2522b7cd45e875897645e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996203"
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a>ビジネス アクティビティ監視 (BAM) のパフォーマンスを最適化します。
このトピックでは、ビジネス アクティビティ監視 (BAM) のパフォーマンス要因について説明します。  
  
## <a name="bam-disk-usage-configuration"></a>BAM のディスク使用率の構成  
 BAM では、BizTalk システムが原因で BAM データベースに保存されているデータ量の大きな負荷がときに大きなオーバーヘッドが発生します。 そのため、BAM データベースのディスク I/O の手法を賢く利用は、非常に重要です。  
  
## <a name="bam-eventstream-apis"></a>BAM の EventStream Api  
 BizTalk BAM シナリオで使用するため EventStreams の 4 種類があります。  
  
- DirectEventStream (DES)  
  
- BufferedEventStream (BES)  
  
- OrchestrationEventStream (OES)  
  
- MessageEventStream (MES)  
  
  次の要因に基づくこれらの Api のいずれかを選択する必要があります。  
  
- 待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。  
  
- イベント挿入のパフォーマンスとスループット、問題がある場合は、非同期 API (BES、OES または MES) を選択します。  
  
- ないコンピューターで実行されるアプリケーションを作成している場合は、BizTalk Server がインストールされている DES および BES; を使用して、これらの Api は、BizTalk 以外のアプリケーションで使用できます。  
  
  > [!NOTE]  
  >  シナリオによっては、複数種類の EventStream を使用する必要があります。 たとえば、パイプライン処理のかどうか、パイプラインはロールバック、トランザクションに関係なく、BAM で特定のデータをキャプチャすることがあります。 具体的には、失敗したメッセージの数に関するデータの取得や再試行の回数がパイプライン処理中に発生する可能性があります。 この状況でデータを取得するには、BES を使用する必要があります。  
  
- BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します  (これらの API は BizTalk アプリケーションでのみ使用できます)。  
  
  > [!NOTE]  
  >  OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。  
  
- BAM イベントの永続化をパイプライン トランザクションと同期する場合は、メッセージング イベント Stream (MES) を使用する必要があります。  
  
  すべて、非同期 EventStreams (BES、MES、OES) は、BizTalk メッセージ ボックス データベースに最初にデータを保持します。 このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。  
  
  BAM の EventStream Api の詳細については、次を参照してください。 [EventStream クラス](http://go.microsoft.com/fwlink/?LinkId=158046)(http://go.microsoft.com/fwlink/?LinkId=158046) 、BizTalk Server のドキュメントにします。  
  
## <a name="bam-performance-counters"></a>BAM パフォーマンス カウンター  
 BAM のパフォーマンス カウンターの詳細な一覧を参照してください。 [BAM パフォーマンス カウンター](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) 、BizTalk Server のドキュメントにします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)