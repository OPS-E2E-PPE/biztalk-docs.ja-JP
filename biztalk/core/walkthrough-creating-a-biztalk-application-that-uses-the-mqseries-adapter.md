---
title: 'チュートリアル: MQSeries アダプターを使用する BizTalk アプリケーションの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c086c69dee4318b9ab15f8746291594a815870
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024528"
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
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。  
  
2. ダブルクリック**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。 通常、既定のキュー マネージャーの名前 **qm _ * * * < machine_name >* 場所*machine_name*コンピューターの名前を指定します。  
  
3. 右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。  
  
4. **ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**BTStoMQS**、順にクリックします**OK**します。  
  
5. 右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。  
  
6. **ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**MQStoBTS**、順にクリックします**OK**します。  
  
   次の手順では、受信場所と送信ポートの作成、および送信ポートの開始と受信場所の有効化を行います。 IBM WebSphere MQ キューも作成します。  
  
## <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューを作成するには  
 受信場所と MQSeries キューを作成するには、次の手順を実行します。  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、既定値を順に展開アプリケーション (**BizTalk アプリケーション 1**既定)。  
  
2.  右クリックし、**受信ポート**ノード、をクリックして**新規**を選択し、**一方向のポート**します。  
  
3.  **受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **MQStoBTS**します。  
  
4.  左側のウィンドウで次のようにクリックします。**受信場所**、右側のウィンドウで次のようにクリックします。**新規**します。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **MQStoBTS**します。  
  
6.  選択**MQSeries**横にドロップダウン リストからリスト、**型**オプション。  
  
7.  **トランスポート**セクションで、**構成**します。  
  
8.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに「 **1**します。  
  
9. **キュー定義**ボックスで、省略記号ボタンをクリックします (**.**) ボタンをクリックします。  
  
10. **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
11. **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
12. **キュー**ボックスに「 **MQStoBTS**、 をクリックし、**エクスポート**します。  
  
13. **エクスポート**ダイアログ ボックスで、をクリックして**Create Queue**、順にクリックします**ok**と**ok**に戻るにもう一度、**受信場所のプロパティ** ダイアログ ボックス。  
  
14. **受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。  
  
15. **受信パイプライン**ボックスで、 **PassThruReceive**します。  
  
16. をクリックして**OK**変更を適用します。  
  
## <a name="to-create-the-send-port-and-the-mqseries-queue"></a>送信ポートと MQSeries キューを作成するには  
 送信ポートと MQSeries キューを作成するには、次の手順を実行します。  
  
1.  右クリック**送信ポート**、 をクリックして**新規**、選び**静的な一方向送信ポート**します。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **BTStoMQS します。**  
  
3.  選択**MQSeries**横にドロップダウン リストからリスト、**型**オプション。  
  
4.  **トランスポート**セクションで、**構成**します。  
  
5.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号ボタンをクリックします (**.**) ボタンをクリックします。  
  
6.  **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
7.  **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
8.  **キュー**ボックスに「 **BTStoMQS**、 をクリックし、**エクスポート**します。  
  
9. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします**ok**と**ok**に戻るにもう一度、**送信ポートプロパティ** ダイアログ ボックス。  
  
10. **送信パイプライン**ボックスで、 **PassThruTransmit**します。  
  
11. クリックして選択**フィルター**左側のウィンドウでし、右側のウィンドウでフィルター オプションを構成します。  
  
12. **プロパティ**ドロップダウン リストで、 **BTS します。ReceivePortName**します。  
  
13. **値**ボックスに「 **MQStoBTS**します。  
  
14. をクリックして**OK**変更を適用します。  
  
## <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  
 受信場所を有効にし、送信ポートを開始するには、次の手順を実行します。  
  
1. 右クリックし、 **MQStoBTS**受信場所をクリックして**を有効にする**します。  
  
2. 右クリックし、 **BTStoMQS**送信ポート、およびクリックして**開始**します。  
  
   次の手順では、テスト メッセージを受信キューに送信することにより、アプリケーションをテストします。  
  
## <a name="to-test-the-application"></a>アプリケーションをテストするには  
 アプリケーションをテストするには、次の手順を実行します。  
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。  
  
2. 右クリック**MQStoBTS**、 をクリックし、 **Put のテスト メッセージ**します。  
  
3. **メッセージ データ**ボックスに、テスト メッセージを入力します。 **[OK]** をクリックします。  
  
   データを入力した後、**現在の深さ**の**MQStoBTS**キューが 1 つ (1)。 カウントがゼロ (0) に戻る、アプリケーションがメッセージを処理するとき、**現在の深さ**の**BTStoMQS**が 1 つ (1)。 また、メッセージの内容を表示することもできます。  
  
## <a name="to-view-the-message"></a>メッセージを表示するには  
 メッセージを表示するには、次の手順を実行します。  
  
1.  ダブルクリックして、 **BTStoMQS**キュー。  
  
2.  メッセージをダブルクリックし、、**データ**シート。 内のメッセージのテキストを表示することができます、**メッセージ データ**ボックス。  
  
3.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターとは何ですか。](../core/what-is-the-mqseries-adapter.md)   
 [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)