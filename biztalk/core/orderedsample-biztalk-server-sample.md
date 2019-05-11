---
title: OrderedSample (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84490c48cc4f43f226cc65d4baa90ce7bca347f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322248"
---
# <a name="orderedsample-biztalk-server-sample"></a>OrderedSample (BizTalk Server サンプル)
OrderedSample サンプルは、オーケストレーションを使用してラウンド トリップ方式で、順序付けられた一連のメッセージを送受信する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 サンプルでは、元のメッセージを受信する MQSeries キューにメッセージが前提としています。 順番に読み取らし、送信アダプターは、MQSeries キューからメッセージを読み取り、ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 オーケストレーションで受信ポート**mqreceive**がその**順次配送**プロパティに設定**True**します。  
  
 送信側のオーケストレーションはメッセージを送信し、次のメッセージを送信する前に、配信通知を待ちます。 送信ポート、 **mqsend**がその**配信通知**プロパティに設定**送信**します。 例を簡潔にするには、オーケストレーションでは、無限ループを使用しています。  
  
 オーケストレーションでは、1 つのメッセージおよびメッセージのバッチを受信できます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|----------|-----------------|  
|OrderedReceiveSend.btproj,<br /><br /> OrderedReceiveSend.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|OrderedReceiveSendOrchestration.odx|アプリケーションのオーケストレーションです。|  
|OrderedSample.snk|厳密な名前のキー ファイル。|  
|**Setup.bat**|このサンプルを作成および初期化します。|  
  
## <a name="building-and-running-the-sample"></a>ビルドとサンプルを実行します。  
  
#### <a name="to-build-and-deploy-the-sample"></a>サンプルをビルドして展開するには  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
   1.  プロジェクトの厳密な名前のキー ファイルを作成します。  
  
   2.  オーケストレーション プロジェクトをコンパイルして展開します。  
  
   MQSeries Server for Windows のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して MQSeries キューを作成できるため、次の手順を省略できます。 必要なアクセス許可がない場合は、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。 WebSphere MQ エクスプローラーを使用してキューを作成するには、次の手順を実行します。  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプローラーを使用した MQSeries キューの作成  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプ ローラーを使用した MQSeries キューを作成するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。  
  
2.  ダブルクリック**キュー マネージャー**、し、ダブルクリック、**既定のキュー マネージャー**します。 Qm _ < コンピューター名 > コンピューター名が、コンピューターの名前を通常、既定のキュー マネージャーの名前します。  
  
3.  右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。  
  
4.  **ローカル キューの作成** ダイアログ ボックスで**キュー名**、型 **"queue1"**、順にクリックします**OK**します。  
  
5.  右クリック**キュー**、 をクリックして**新規**、 をクリックし、**ローカル キュー**します。  
  
6.  **ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**queue2**、順にクリックします**OK**します。  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューの作成  
 この手順では、MQSeries へのメッセージ送信および MQSeries からの関連メッセージの受信を行うための送信ポートと受信場所を作成します。 MQSeries キューは、受信場所がまだ作成されていない場合に受信場所を作成したときにも作成されます。  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューを作成するには  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  
  
4.  **一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OrderedSampleReceive**  をクリック**OK**します。  
  
5.  左側のウィンドウで次のようにクリックします。**受信場所**タブをクリックし、[] をクリックし、**新規**します。  
  
6.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「"**OrderedSampleReceiveLocation**"。  
  
7.  **トランスポートの種類**ボックスで、 **MQSeries**します。  
  
8.  **受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。  
  
9. **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。  
  
10. をクリックして**構成**です。  
  
11. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに「 **「10」** します。  
  
12. **キュー定義**ボックスで、、**省略記号 (...)** ボタンをクリックします。  
  
13. **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
14. **キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**します。  
  
15. **キュー**ボックスに「" **queue1**"、 をクリックし、**エクスポート**します。  
  
16. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします **[ok]** または**完了**すべてのダイアログ ボックスを終了します。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューの作成  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューを作成するには  
  
1.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。  
  
2.  **静的ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「"**OrderedSampleSend**"。  
  
3.  **トランスポートの種類**ボックスで、 **MQSeries**します。  
  
4.  **送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。  
  
5.  をクリックして**構成**です。  
  
6.  **MQSeries トランスポートのプロパティ**] ダイアログ ボックスで、**キュー定義**ボックスで、[、**省略記号 (...)** ボタンをクリックします。  
  
7.  **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
8.  **キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**します。  
  
9. **キュー**ボックスに「" **queue2**"、 をクリックし、**エクスポート**します。  
  
10. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします **[ok]** または**完了**すべてのダイアログ ボックスを終了します。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  
  
1.  BizTalk Server 管理コンソールで、次のようにクリックします。**受信ポート**します。  
  
2.  詳細ペインで右クリックし、 **MQIn**受信場所とクリックして**を有効にする**します。  
  
3.  詳細ペインで右クリックし、 **MQOut**送信ポートを**を開始します。**  
  
#### <a name="to-bind-and-start-the-orchestration"></a>バインドし、オーケストレーションを開始するには  
  
1.  BizTalk Server 管理コンソールで、**オーケストレーション**フォルダー。  
  
2.  ダブルクリックして、 **OrderedSampleOrchestration**オーケストレーション、およびクリック**バインド**。  
  
3.  オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。  
  
    |オーケストレーション ポート|メッセージ ポート/受信場所|  
    |------------------------|----------------------------------------|  
    |mqreceive|OrderedSampleReceive|  
    |mqsend|OrderedSampleSend|  
  
4.  クリックして**ホスト**します。  
  
5.  **ホスト**ボックスで、 **BizTalkServerApplication**、 をクリック**OK**します。  
  
6.  右クリックして、**オーケストレーション**クリック**開始**。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  オーケストレーションを開始します。  
  
2.  元の読み取り、受信場所を構成した MQSeries キューにメッセージを配置します。  
  
3.  WebSphere MQ エクスプ ローラーでメッセージを送信する送信ポートを構成する送信キューにメッセージを表示します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタ サンプル](../core/mqseries-adapter-samples.md)