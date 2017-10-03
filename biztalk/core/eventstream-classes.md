---
title: "EventStream クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89eafdced54927007bcc8dfc02e4834641e2ae2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="eventstream-classes"></a>EventStream クラス
BAM の EventStream API は、Microsoft.BizTalk.BAM.EventObservation 名前空間に含まれています。 これらの API に対してコードを記述するには、次の DLL を開発用コンピューターにインストールする必要があります。  
  
-   Microsoft.BizTalk.BAM.EventObservation.dll  
  
-   Microsoft.Biztalk.BAM.Xlangs.dll: この DLL がオーケストレーション イベント ストリームのコーディング時に必要です。  
  
-   Microsoft.biztalk.pipeline.dll 内: この DLL は、メッセージング イベント ストリームのコード パイプライン コンテキストを使用する場合に必要です。  
  
 プロジェクト参照に DLL を追加し、次のステートメントを使用してコードに名前空間を組み込みます。  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 **クラス**  
  
|名前|Description|  
|----------|-----------------|  
|DirectEventStream (DES)|同期、待機時間なし。|  
|BufferedEventStream (BES)|非同期、高スループット、ある程度の待機時間あり。|  
|OrchestrationEventStream (OES)|非同期、BizTalk オーケストレーション トランザクションに参加。|  
|IPipelineContext インターフェイス|非同期、BizTalk Server パイプライン トランザクションに参加。 メッセージング イベント ストリーム (MES) の作成に使用。|  
  
 API は、次の要因に基づいて選択する必要があります。  
  
-   待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。 DES を除くその他すべての EventStream クラスは非同期であり、多少の待機時間があります。 データは、まずメッセージ ボックスに保持され、その後 TDDS によって処理されて BAMPrimaryImport データベースに移動されます。  
  
-   イベント挿入のパフォーマンスとスループットを重視する場合は、非同期 API を選択します。  
  
-   BizTalk Server がインストールされていないコンピューターで実行するアプリケーションを作成する場合は、DES および BES を使用します  (つまり、これらの API は非 BizTalk アプリケーションで使用できます)。  
  
-   BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します  (これらの API は BizTalk アプリケーションでのみ使用できます)。  
  
    -   BAM イベントをパイプライン トランザクションと同期された状態で保持する場合は、メッセージング イベント ストリームを使用する必要があります。  
  
    -   OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。  
  
 シナリオによっては、複数種類の EventStream を使用する必要があります。 たとえば、パイプライン処理では、パイプラインがそのトランザクションをロールバックするかどうかにかかわらず、BAM で特定のデータを取得する必要があります。 特に、パイプライン処理での失敗したメッセージの数や再試行の回数に関するデータの取得が必要です。 この状況でデータを取得するには、BES を使用する必要があります。  
  
 非同期 EventStream (BES、MES、OES) はいずれも、まず BizTalk メッセージ ボックス データベースにデータを保存します。 このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。  
  
> [!NOTE]
>  EventStream の呼び出しによって BizTalk アプリケーションからボトルネックが生じないようにするために、非同期 API の使用をお勧めします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [OrchestrationEventStream](../core/orchestrationeventstream.md)  
  
-   [メッセージング イベント ストリーム](../core/messaging-event-streams.md)