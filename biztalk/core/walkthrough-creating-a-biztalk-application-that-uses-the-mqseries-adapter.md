---
title: "チュートリアル: MQSeries アダプターを使用する BizTalk アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- MQSeries adapters, tutorial
- MQSeries adapters, testing
- tutorials, MQSeries adapters
- MQSeries adapters, IBM WebSphere MQ queues
- testing, MQSeries adapters
- MQSeries adapters, queues
- configuring [MQSeries adapters], tutorial
ms.assetid: e9e169e4-d41c-4e5d-b165-7bd36b481f24
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0132387b86e048c26c0dab61ca174f3e10c55012
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-mqseries-adapter"></a>チュートリアル: MQSeries アダプターを使用する BizTalk アプリケーションの作成
このセクションでは、MQSeries アダプターを使用する簡単な Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを作成する手順について説明します。  
  
> [!NOTE]
>  このアプリケーションは、Windows プラットフォームのサーバー コンポーネントである IBM WebSphere MQ が BizTalk Server と同じコンピューターにインストールされていることを前提としています。 また、送信ポートまたは受信場所をまだ作成していないことも前提としています。 既存の送信ポートまたは受信場所がある場合、手順を実行する際に適切な名前に置き換えてください。  
  
 このアプリケーションは、受信場所と送信ポートのみを使用する、コンテンツベースの単純なルーティング アプリケーションです。 受信場所では、IBM WebSphere MQ キューから読み取りを行います。 送信ポートは、受信場所からメッセージを取得して、そのメッセージを別の IBM WebSphere MQ キューに送信します。  
  
 このアプリケーションを作成するには、IBM WebSphere MQ キューの作成、BizTalk Server の受信場所と送信ポートの設定、送信ポートの開始と受信場所の有効化、およびキューへのテスト メッセージの送信を行う必要があります。  
  
 IBM WebSphere MQ のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して IBM WebSphere MQ キューを作成できるため、次の手順を省略できます。 このようなアクセス許可を持っていない場合は、Windows プラットフォームのクライアント コンポーネントである IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。 IBM WebSphere MQ エクスプローラー スナップインを使用してキューを作成するには、次の手順を実行します。  
  
## <a name="to-create-the-ibm-websphere-mq-queues-through-the-ibm-websphere-mq-explorer"></a>IBM WebSphere MQ エクスプローラーを使用して IBM WebSphere MQ キューを作成するには  
 IBM WebSphere MQ エクスプローラーを使用して IBM WebSphere MQ キューを作成するには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリック**WebSphere MQ エクスプ ローラー**です。  
  
2.  ダブルクリックして**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。 既定のキュー マネージャーの名前は通常**qm _***< machine_name >*場所*machine_name*お使いのコンピューターの名前を指定します。  
  
3.  右クリック**キュー**、 をポイント**新規**、クリックして**ローカル キュー**です。  
  
4.  **ローカル キューの作成**ダイアログ ボックスで、**キュー名**、型**BTStoMQS**、クリックして**[ok]**です。  
  
5.  右クリック**キュー**、 をポイント**新規**、クリックして**ローカル キュー**です。  
  
6.  **ローカル キューの作成**ダイアログ ボックスで、**キュー名**、型**MQStoBTS**、クリックして**[ok]**です。  
  
 次の手順では、受信場所と送信ポートの作成、および送信ポートの開始と受信場所の有効化を行います。 IBM WebSphere MQ キューも作成します。  
  
## <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューを作成するには  
 受信場所と MQSeries キューを作成するには、次の手順を実行します。  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、既定値を展開アプリケーション (**BizTalk アプリケーション 1**既定)。  
  
2.  右クリックし、**受信ポート**ノード、をクリックして**新規**を選択して**一方向のポート**です。  
  
3.  **受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**MQStoBTS**です。  
  
4.  左側のウィンドウでをクリックして**受信場所**、右側のウィンドウでをクリックして**新規**です。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**MQStoBTS**です。  
  
6.  選択**MQSeries**ドロップ ダウン リストから次に、**型**オプション。  
  
7.  **トランスポート**セクションで、**構成**です。  
  
8.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、入力**1**です。  
  
9. **キュー定義**ボックスで、省略記号ボタン (**.**) ボタンをクリックします。  
  
10. **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
11. **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
12. **キュー**ボックスに、入力**MQStoBTS**、クリックして**エクスポート**です。  
  
13. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**ok**と**ok**に戻るには、もう一度、**受信場所のプロパティ** ダイアログ ボックス。  
  
14. **受信ハンドラー**ボックスで、 **BizTalkServerApplication**です。  
  
15. **受信パイプライン**ボックスで、 **PassThruReceive**です。  
  
16. をクリックして**OK**変更を適用します。  
  
## <a name="to-create-the-send-port-and-the-mqseries-queue"></a>送信ポートと MQSeries キューを作成するには  
 送信ポートと MQSeries キューを作成するには、次の手順を実行します。  
  
1.  右クリック**送信ポート**をクリックして**新規**を選択し、**静的な一方向送信ポート**です。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**BTStoMQS です。**  
  
3.  選択**MQSeries**ドロップ ダウン リストから次に、**型**オプション。  
  
4.  **トランスポート**セクションで、**構成**です。  
  
5.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号ボタンをクリックして (**.**) ボタンをクリックします。  
  
6.  **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
7.  **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
8.  **キュー**ボックスに、入力**BTStoMQS**、クリックして**エクスポート**です。  
  
9. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**ok**と**ok**に戻るには、もう一度、**送信ポートプロパティ** ダイアログ ボックス。  
  
10. **送信パイプライン**ボックスで、 **PassThruTransmit**です。  
  
11. クリックして選択**フィルター**左側のウィンドウでし、右ペインでフィルター オプションを構成します。  
  
12. **プロパティ**ドロップダウン リストで、 **BTS です。ReceivePortName**です。  
  
13. **値**ボックスに、入力**MQStoBTS**です。  
  
14. をクリックして**OK**変更を適用します。  
  
## <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  
 受信場所を有効にし、送信ポートを開始するには、次の手順を実行します。  
  
1.  右クリックし、 **MQStoBTS**受信場所をクリックして**を有効にする**です。  
  
2.  右クリックし、 **BTStoMQS**送信ポートをクリックして**開始**です。  
  
 次の手順では、テスト メッセージを受信キューに送信することにより、アプリケーションをテストします。  
  
## <a name="to-test-the-application"></a>アプリケーションをテストするには  
 アプリケーションをテストするには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリック**WebSphere MQ エクスプ ローラー**です。  
  
2.  右クリック**MQStoBTS**、クリックして**テスト ・ メッセージ**です。  
  
3.  **メッセージ データ**ボックスに、テスト メッセージを入力します。 **[OK]**をクリックします。  
  
 データを入力した後、**現在の深さ**の**MQStoBTS**キューは 1 です)。 カウントがゼロ (0) に戻る、アプリケーションでは、メッセージを処理するとき、**現在の深さ**の**BTStoMQS**が 1 (1)。 また、メッセージの内容を表示することもできます。  
  
## <a name="to-view-the-message"></a>メッセージを表示するには  
 メッセージを表示するには、次の手順を実行します。  
  
1.  ダブルクリックして、 **BTStoMQS**キュー。  
  
2.  メッセージをダブルクリックし、、**データ**シートです。 内のメッセージのテキストを表示することができます、**メッセージ データ**ボックス。  
  
3.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターとは何ですか。](../core/what-is-the-mqseries-adapter.md)   
 [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)