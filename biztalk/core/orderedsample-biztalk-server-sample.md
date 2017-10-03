---
title: "OrderedSample (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf7b0de69005957a333e0c4f884e748e6ab5bbe9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orderedsample-biztalk-server-sample"></a>OrderedSample (BizTalk Server サンプル)
OrderedSample サンプルは、オーケストレーションを使用して、順序付けられた一連のメッセージをラウンド トリップ方式で送受信する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、サンプルにメッセージを配信する MQSeries キューにメッセージがあることを前提とします。 MQSeries キューのメッセージは、アダプターによって順番に読み取られて [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されます。  
  
 オーケストレーションで受信ポート**mqreceive**がその**順次配送**プロパティに設定**True**です。  
  
 送信側では、オーケストレーションによってメッセージが送信され、配信通知の受信後に次のメッセージが送信されます。 送信ポート**mqsend**がその**配信通知**プロパティに設定**送信**です。 サンプルをシンプルにするために、オーケストレーションでは無限ループが使用されています。  
  
 オーケストレーションでは、メッセージのバッチおよび 1 つのメッセージを受信できます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<サンプル パス >*\AdaptersUsage\MQSeriesAdapter\OrderedSample  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|----------|-----------------|  
|OrderedReceiveSend.btproj,<br /><br /> OrderedReceiveSend.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|OrderedReceiveSendOrchestration.odx|アプリケーションのオーケストレーション。|  
|OrderedSample.snk|厳密な名前のキー ファイル。|  
|**Setup.bat**|このサンプルを作成および初期化します。|  
  
## <a name="building-and-running-the-sample"></a>サンプルのビルドと実行  
  
#### <a name="to-build-and-deploy-the-sample"></a>サンプルをビルドして展開するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    1.  プロジェクトの厳密な名前のキー ファイルを作成します。  
  
    2.  オーケストレーション プロジェクトをコンパイルして展開します。  
  
 MQSeries Server for Windows のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して MQSeries キューを作成できるため、次の手順を省略できます。 必要なアクセス許可がない場合は、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。 WebSphere MQ エクスプローラーを使用してキューを作成するには、次の手順を実行します。  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプローラーを使用した MQSeries キューの作成  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプ ローラーを使用して MQSeries キューを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**IBM WebSphere MQ**、順にクリック**WebSphere MQ エクスプ ローラー**です。  
  
2.  ダブルクリックして**キュー マネージャー**、順にダブルクリックし、**既定のキュー マネージャー**です。 通常、既定のキュー マネージャーの名前は QM_<コンピューター名> です。<コンピューター名> は、使用しているコンピューターの名前です。  
  
3.  右クリック**キュー**、 をポイント**新規**、クリックして**ローカル キュー**です。  
  
4.  **ローカル キューの作成**ダイアログ ボックスで、**キュー名**、型**"queue1"**、クリックして**[ok]**です。  
  
5.  右クリック**キュー**をクリックして**新規**、順にクリック**ローカル キュー**です。  
  
6.  **ローカル キューの作成**ダイアログ ボックスで、**キュー名**、型**queue2**、クリックして**[ok]**です。  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューの作成  
 この手順では、MQSeries へのメッセージ送信および MQSeries からの関連メッセージの受信を行うための送信ポートと受信場所を作成します。 MQSeries キューは、受信場所がまだ作成されていない場合に受信場所を作成したときにも作成されます。  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューを作成するには  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
4.  **一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OrderedSampleReceive**  をクリック**OK**です。  
  
5.  左側のウィンドウでをクリックして**受信場所** タブをクリックして**新規**です。  
  
6.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「"**OrderedSampleReceiveLocation**"です。  
  
7.  **トランスポートの種類**ボックスで、 **MQSeries**です。  
  
8.  **受信ハンドラー**ボックスで、 **BizTalkServerApplication**です。  
  
9. **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**です。  
  
10. をクリックして**構成**です。  
  
11. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、入力**「10」**です。  
  
12. **キュー定義**ボックスで、クリックして、**省略記号 (...)**ボタンをクリックします。  
  
13. **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
14. **キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**です。  
  
15. **キュー**ボックスに、入力" **queue1**"、クリックして**エクスポート**です。  
  
16. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**[ok]**または**完了**すべてのダイアログ ボックスを終了します。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューの作成  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューを作成するには  
  
1.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  **静的ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力"**OrderedSampleSend**"です。  
  
3.  **トランスポートの種類**ボックスで、 **MQSeries**です。  
  
4.  **送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**です。  
  
5.  をクリックして**構成**です。  
  
6.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、クリックして、**省略記号 (...)**ボタンをクリックします。  
  
7.  **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
8.  **キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**です。  
  
9. **キュー**ボックスに、入力" **queue2**"、クリックして**エクスポート**です。  
  
10. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**[ok]**または**完了**すべてのダイアログ ボックスを終了します。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  
  
1.  BizTalk Server 管理コンソールで **受信ポート**です。  
  
2.  詳細ウィンドウで右クリックし、 **MQIn**受信場所をクリックして**を有効にする**です。  
  
3.  詳細ウィンドウで右クリックし、 **MQOut**送信ポートをクリックして**を開始します。**  
  
#### <a name="to-bind-and-start-the-orchestration"></a>バインドし、オーケストレーションの開始  
  
1.  BizTalk Server 管理コンソールで、展開、**オーケストレーション**フォルダーです。  
  
2.  ダブルクリックして、 **OrderedSampleOrchestration**オーケストレーション、およびクリック**バインド**です。  
  
3.  オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。  
  
    |オーケストレーション ポート|メッセージ ポート/受信場所|  
    |------------------------|----------------------------------------|  
    |mqreceive|OrderedSampleReceive|  
    |mqsend|OrderedSampleSend|  
  
4.  をクリックして**ホスト**です。  
  
5.  **ホスト**ボックスで、 **BizTalkServerApplication**、 をクリック**OK**です。  
  
6.  右クリックして、**オーケストレーション** をクリック**開始**です。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  オーケストレーションを開始します。  
  
2.  受信場所で読み取るよう構成した MQSeries キューにメッセージを配置します。  
  
3.  送信ポートでメッセージを送信するよう構成した送信キューのメッセージを WebSphere MQ エクスプローラーで表示します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタ サンプル](../core/mqseries-adapter-samples.md)