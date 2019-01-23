---
title: MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル) |Microsoft Docs
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
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: 5127d743-bb79-4e97-a2f3-446892e1bfa0
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a41d62b7c8e578f7e89e7802ed5eaecd0e2b61
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443399"
---
# <a name="mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample"></a>MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル)
MQSCorrelationSetOrchestrationWithSolicitResponse サンプルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではなく、MQSeries Server によって作成された関連付け識別子を使用する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 オーケストレーションに空の値を含むメッセージを送信する、 **MQMD_MsgID**メッセージ ヘッダーのプロパティ。 MQSeries が、MessageID と CorrelationID を生成しに割り当てられている値を持つメッセージが返されます**MQMD_MsgID**と**MQMD_CorrelId**送信請求-応答で応答の一部として送信アダプターのポート. オーケストレーションは、関連付けセットを初期化するために生成された関連付け識別子を使用してし、を確認して受信場所を関連付けセットの後ろに続くで次のように、 **MQMD_CorrelId**メッセージのプロパティ。 アダプターは、また関連付け識別子を割り当てます**BizTalk_CorrelationID**オーケストレーションで使用することもできます。 これです。 アダプターと関連付け識別子の使用に関する詳細については、次を参照してください。[関連付けメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)します。  
  
> [!IMPORTANT]
>  この方法を使用するオーケストレーションでは、MQSeries Server からのメッセージを関連付け識別子より前に受信すると、問題が発生する場合があります。 オーケストレーションをデザインするときは、MQSeries Server が関連付け識別子を返すことができるよう、処理時間を十分にとるようにしてください。 この例では、このような競合状態が発生する可能性については考慮していません。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|**[最近使ったファイル]**|**[説明]**|  
|--------------|---------------------|  
|**MQSCorrelationSolicitResponse.btproj,**<br /><br /> **MQSCorrelationSolicitResponse.sln**|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|**[Mqscorrelationsolicitresponse.odx]**|アプリケーションの BizTalk オーケストレーション ファイル。|  
|**MQSCorrelationSolicitResponse.snk**|厳密な名前のキー ファイル。|  
|Setup.bat|このサンプルを作成および初期化します。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 アプリケーションを作成するには、次の手順を実行します。  
  
- MQSeries キューを 2 つ作成します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所と送信ポートを設定します。  
  
- 受信場所を有効化します。  
  
- 送信ポートを開始します。  
  
- 必要なフォルダーを作成します。  
  
- オーケストレーションを変更します。  
  
- オーケストレーションを展開してバインドし、開始します。  
  
  MQSeries Server for Windows のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して MQSeries キューを作成できるため、次の手順を省略できます。 必要なアクセス許可がない場合は、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。 WebSphere MQ エクスプローラーを使用してキューを作成するには、次の手順を実行します。  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプローラーを使用した MQSeries キューの作成  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプ ローラーを使用した MQSeries キューを作成するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。  
  
2.  ダブルクリック**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。 通常、既定のキュー マネージャーの名前**qm _**_< machine_name >_ 場所*machine_name*コンピューターの名前を指定します。  
  
3.  右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。  
  
4.  **ローカル キューの作成**] ダイアログ ボックスで**キュー名**"REPLYTOQ"を入力し、[クリックして**OK**。  
  
5.  右クリック**キュー**、 をクリックして**新規**、 をクリックし、**ローカル キュー**します。  
  
6.  **ローカル キューの作成**] ダイアログ ボックスで**キュー名**"solicitresponseq"し、[クリックして**OK**。  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューの作成  
 この手順では、MQSeries へのメッセージ送信および MQSeries からの関連メッセージの受信を行うための送信ポートと受信場所を作成します。 MQSeries キューは、受信場所がまだ作成されていない場合に受信場所を作成したときにも作成されます。  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューを作成するには  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  
  
4.  **一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQReply」を入力して  をクリックして**OK**します。  
  
5.  左側のウィンドウで次のようにクリックします。**受信場所**タブをクリックし、[] をクリックし、**新規**します。  
  
6.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、"MQReply"を入力します。  
  
7.  **トランスポートの種類**ボックスで、 **MQSeries**します。  
  
8.  **受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。  
  
9. **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。  
  
10. をクリックして**構成**です。  
  
11. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、「10」を入力します。  
  
12. **キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。  
  
13. **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
14. **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
15. **キュー**ボックスに「REPLYTOQ」を入力し、 クリック、**エクスポート**します。  
  
16. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします **[ok]** または**完了**すべてのダイアログ ボックスを終了します。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューの作成  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューを作成するには  
  
1.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqsolicitresponse」.  
  
3.  **トランスポートの種類**ボックスで、 **MQSeries**します。  
  
4.  **送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。  
  
5.  **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。  
  
6.  をクリックして**構成**です。  
  
7.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。  
  
8.  **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
9. **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
10. **キュー**ボックス、solicitresponseq」、およびクリックして**エクスポート**します。  
  
11. [エクスポート] ダイアログ ボックスで、**キューの作成**、順にクリックします**OK**または**完了**すべてのダイアログ ボックスを終了します。  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a>受信場所の有効化と送信ポートの開始  
 この手順では、オーケストレーション内でファイルを受信するために必要なフォルダーを作成し、関連付けられたメッセージと応答メッセージを出力フォルダーに送信します。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  
  
1.  BizTalk Server 管理コンソールで、次のようにクリックします。**受信ポート**します。  
  
2.  詳細ペインで右クリックし、 **MQIn**受信場所とクリックして**を有効にする**します。  
  
3.  詳細ペインで右クリックし、 **MQOut**送信ポートを**を開始します。**  
  
## <a name="creating-the-folders-used-by-the-application"></a>アプリケーションが使用するフォルダーの作成  
  
#### <a name="to-create-the-folders-used-by-the-application"></a>アプリケーションが使用するフォルダーを作成するには  
  
1.  C:\ ドライブに "temp" という名前のフォルダーが存在しない場合は、これを作成します。  
  
2.  下のフォルダーを作成、 **C:\temp** "Pickup2"、"Dropit2"、および"MoveIt"という名前のディレクトリ。  
  
## <a name="modifying-the-orchestration-used-by-the-application"></a>アプリケーションが使用するオーケストレーションの変更  
 この手順では、アプリケーションが使用するオーケストレーションを変更します。  
  
||  
|-|  
|アプリケーションが使用するオーケストレーションを変更するには|  
|Microsoft で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイルをダブルクリックして **[mqscorrelationsolicitresponse.sln]** ソリューションを開きます。<br /><br /> のソリューション エクスプ ローラー ウィンドウで、元オーケストレーションをダブルクリックして**mqscorrelationsolicitresponse.odx**にオーケストレーションを表示します。<br /><br /> -メッセージの割り当て図形をダブルクリックして **[messageassignment_1]** BizTalk 式エディタを起動します。<br /><br /> -次の式の適切な MQSeries キュー マネージャー名を入力します。<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_ReplyToQMgr) = "QM_<machine_name>";`<br /><br /> 場合、最初の 100 バイトだけではなく、元のメッセージの内容全体を格納する BizTalk から送信されるメッセージに応答には、BizTalk 式エディターで次の行を変更します。<br /><br /> -元の行。<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 768;`<br /><br /> 変更後:<br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 1792;`<br /><br /> BizTalk 式エディターをクリックして**OK**を変更した式を保存します。<br /><br /> -[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を選択します**ファイル**、し、**すべて保存**します。|  
  
## <a name="building-and-deploying-the-sample"></a>ビルドと配置のサンプル  
 この手順では、このアプリケーションで使用するオーケストレーションを含むソリューションをビルドして展開します。  
  
#### <a name="to-build-and-deploy-the-sample"></a>サンプルをビルドして展開するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse`  
  
2.  ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
    1.  プロジェクトの厳密な名前のキー ファイルを作成します。  
  
    2.  オーケストレーション プロジェクトをコンパイルして展開します。  
  
    3.  ファイル アダプター用の送信ポートと受信ポートを作成します。  
  
    > [!NOTE]
    >  このオーケストレーションでは、ファイル アダプターとのファイルの送受信に使用するバインドが指定されているため、オーケストレーションの展開時には、ファイルをオーケストレーション内で受信し、関連付けメッセージと応答メッセージを出力するために必要な送信ポート、受信ポート、および受信場所が作成されます。  
  
## <a name="binding-and-starting-the-orchestration"></a>バインドとオーケストレーションの開始  
 この手順では、ホスト、適切な送信ポート、および受信場所にオーケストレーションをバインドします。  
  
#### <a name="to-bind-and-start-the-orchestration"></a>バインドし、オーケストレーションを開始するには  
  
1.  BizTalk Server 管理コンソールで、**オーケストレーション**フォルダー。  
  
2.  詳細ペインで右クリックし、 **MQSCorrelationSolicitResponse**オーケストレーションをクリックします**バインド**します。  
  
3.  オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。  
  
    |**オーケストレーション ポート**|**メッセージ ポート/受信場所**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSolicitResponse.Orchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQReply|  
    |SolicitResponsePort|MQSolicitResponse|  
    |TempPort|MQSCorrelationSolicitResponse.Orchestration.TempPort|  
    |FileSendPort|MQSCorrelationSolicitResponse.Orchestration.FileSendPort|  
  
4.  クリックして**ホスト**します。  
  
5.  **ホスト**ボックスで、 **BizTalkServerApplication**  をクリック**OK**します。  
  
6.  **送信ポート**、右クリック**mqscorrelationsolicitresponse.orchestration.tempport**、し、**開始**します。  
  
7.  **送信ポート**、右クリック**mqscorrelationsolicitresponse.orchestration.filesendport**、し、**開始**します。  
  
8.  **受信場所**、右クリックして**mqscorrelationsolicitresponse.orchestration.filereceiveport**、し、**を有効にする**します。  
  
9. オーケストレーションを右クリックし、をクリックして**開始**します。  
  
    > [!NOTE]
    >  オーケストレーションを開始すると、オーケストレーションの参加も自動的に実行されます。  
  
## <a name="testing-the-application"></a>アプリケーションのテスト  
 この手順では、アプリケーションをテストします。  
  
#### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1. ファイルを配置、 **C:\Temp\Pickup2**フォルダー。  
  
2. 内のファイルを調べて、 **C:\Temp\Dropit2**フォルダーと**C:\Temp\Moveit**フォルダー。  
  
   - **C:\Temp\Dropit2**フォルダーは、もともと取得されたメッセージのコピーを含める必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
   - **C:\Temp\Moveit**フォルダーは、メッセージ識別子 (MQMD_MsgId) と関連付け識別子 (MQMD_CorrelId) を含む応答ドキュメントを含める必要があります。  
  
   > [!NOTE]
   >  無効にした場合、 **MQReply**受信場所は、WebSphere MQ エクスプ ローラーでメッセージを確認し、メッセージと関連付け識別子が設定されていることができます。 これを行うには、起動、 **WebSphere MQ エクスプ ローラー**にメッセージを調べ、 **REPLYTOQ**キュー。 メッセージ識別子と関連付け識別子が表示されます、**識別子**のタブ、 **Messageproperties**  ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [要求/応答を使用してメッセージの関連付け](../core/correlating-messages-using-request-reply.md)   
 [MQSeries アダプタ サンプル](../core/mqseries-adapter-samples.md)
