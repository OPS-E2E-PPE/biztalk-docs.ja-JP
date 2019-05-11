---
title: EventStream クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba599c008c571af520dbc9b7919157371e32750f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388315"
---
# <a name="eventstream-classes"></a>EventStream クラス
BAM の EventStream Api は、Microsoft.BizTalk.BAM.EventObservation 名前空間に存在します。 Api に対するコードを記述、開発用コンピューターに、次の Dll をインストールする必要があります。  
  
- Microsoft.BizTalk.BAM.EventObservation.dll  
  
- Microsoft.Biztalk.BAM.Xlangs.dll:オーケストレーション イベント ストリームをコーディングする際、この DLL が必要です。  
  
- Microsoft.biztalk.pipeline.dll 内:メッセージング イベント ストリームのコード パイプライン コンテキストを使用する場合、この DLL が必要です。  
  
  DLL のプロジェクト参照を追加して、コードを次に、名前空間を含めるステートメントを使用します。  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 **クラス**  
  
|名前|説明|  
|----------|-----------------|  
|DirectEventStream (DES)|同期、待機時間なし。|  
|BufferedEventStream (BES)|非同期、高スループット、いくつかの待機時間|  
|OrchestrationEventStream (OES)|非同期、BizTalk オーケストレーション トランザクションに参加します。|  
|IPipelineContext インターフェイス|非同期は、BizTalk Server パイプライン トランザクションに参加します。 メッセージング イベント ストリーム (MES) を作成するために使用します。|  
  
 次の要因に基づく API を選択する必要があります。  
  
- 待機時間を重視する場合は DES を選択します。DES では、データが BAM プライマリ インポート データベースと同期された状態で保持されます。 DES を除くその他のすべての EventStream クラスは非同期であり待ち時間が発生します。 データはまずメッセージ ボックス データベースに保存され、BAMPrimaryImport データベースにデータを移動する TDDS により処理された後。  
  
- イベント挿入のパフォーマンスとスループット、問題がある場合は、非同期 API を選択します。  
  
- ないコンピューターで実行されるアプリケーションを作成する場合は、BizTalk Server がインストールされている、DES および BES を使用します。 (つまり、これらの Api できます非 BizTalk アプリケーションにします。)  
  
- BizTalk Server がインストールされているコンピューターでアプリケーションを実行する場合は、MES および OES を使用します  (これらの API は BizTalk アプリケーションでのみ使用できます)。  
  
  -   BAM イベントの永続化をパイプライン トランザクションと同期する場合は、メッセージングのイベント Stream を使用する必要があります。  
  
  -   OES は MES と同等ですが、BizTalk オーケストレーションを対象としています。  
  
  シナリオによっては、複数種類の EventStream を使用する必要があります。 たとえば、パイプライン処理でかどうか、パイプラインはロールバック、トランザクションに関係なく、BAM で特定のデータをキャプチャすることがあります。 具体的には、パイプライン処理中に失敗したメッセージの数に関するデータをキャプチャまたは再試行の回数をする可能性があります。 この状況でデータを取得するには、BES を使用する必要があります。  
  
  すべて、非同期 EventStreams (BES、MES、OES) は、BizTalk メッセージ ボックス データベースで最初にデータを保持します。 このデータは Tracking Data Decode Service (TDDS) によって定期的に処理され、BAM プライマリ インポート データベースに保存されます。  
  
> [!NOTE]
>  EventStream の呼び出しは BizTalk アプリケーションからボトルネックを作成しないようにするには、非同期 Api を使用することをお勧めします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [OrchestrationEventStream](../core/orchestrationeventstream.md)  
  
-   [メッセージング イベント ストリーム](../core/messaging-event-streams.md)