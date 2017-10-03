---
title: "MQSCorrelationSetOrchestration (BizTalk Server サンプル) |Microsoft ドキュメント"
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
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: fcda65d0-e3ec-4ead-978d-3904903b8762
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea8de4f60907e465f37502b5b0227e31ddcd92b5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a>MQSCorrelationSetOrchestration (BizTalk Server サンプル)
MQSCorrelationSetOrchestration サンプルは、実行中のオーケストレーションに MQSeries キューをルーティングして戻すために送信されるメッセージを関連付けるための MQSeries 関連付け識別子を使用する方法を示します。 オーケストレーションが、識別子の値を使用して MQSeries 関連付け識別子とメッセージを設定、 **MQMD_CorrelId**と**MQMD_MsgID**プロパティです。 MQSeries キュー マネージャーは、MessageID の値をメッセージの CorrelationID プロパティにコピーします。  
  
## <a name="prerequisites"></a>前提条件  
 このサンプルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているのと同じサーバー上に IBM WebSphere MQSeries がインストールされていることを前提としています。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、IBM WebSphere MQSeries サーバーに送信されるメッセージにメッセージ識別子と関連付け識別子を設定する方法について示します。 これは、実行中のオーケストレーションにルーティングして戻すメッセージを関連付けるための 1 つの方法として挙げられます。 MQSeries キュー マネージャーはメッセージを受信すると、その MessageID の値をメッセージの CorrelationID プロパティにコピーします。 この CorrelationID (**MQMD_CorrelId**) に MQSeries の応答メッセージを MQSeries にメッセージを送信するために使用するインスタンスに関連付ける、オーケストレーションで使用しています。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルは、オーケストレーションで処理中のドキュメントを MQSeries キューに送信可能であり (多くの場合、追加の処理を行うため)、実行中のオーケストレーションにルーティングして戻されるというシナリオを示します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<サンプル パス >*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|**ファイル**|**Description**|  
|--------------|---------------------|  
|**MQSCorrelationSetOrchestration.btproj、**<br /><br /> **MQSCorrelationSetOrchestration.sln**|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|**MQSCorrelationSetOrchestration.odx**|アプリケーションのオーケストレーション。|  
|**MQSCorrelationSetOrchestration.snk**|厳密な名前のキー ファイル。|  
|**Setup.bat**|このサンプルを作成および初期化します。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 全体的なワークフローの 1 つのステップとして MQSeries サーバーにメッセージを送信する必要がある場合は、このサンプルで採用されているロジックを組み込みます。  
  
### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプローラーを使用して MQSeries キューを作成するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリック**WebSphere MQ エクスプ ローラー**です。  
  
2.  ダブルクリックして**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。 既定のキュー マネージャーの名前は通常**qm _ < コンピューター名 >**場所*machine_name*お使いのコンピューターの名前を指定します。  
  
3.  右クリック**キュー**、 をポイント**新規**、クリックして**ローカル キュー**です。  
  
4.  **ローカル キューの作成**ダイアログ ボックスで、**キュー名**「mqcorrelation」、および [] をクリック**OK**です。  
  
### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューを作成するには  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
4.  **一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQIn」を入力し、 をクリック**OK**です。  
  
5.  左側のウィンドウでをクリックして**受信場所** タブをクリックして**新規**です。  
  
6.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、"MQIn"を入力します。  
  
7.  **トランスポートの種類**ボックスで、 **MQSeries**です。  
  
8.  **受信ハンドラー**ボックスで、 **BizTalkServerApplication**です。  
  
9. **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**です。  
  
10. をクリックして**構成**です。  
  
11. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、「10」を入力します。  
  
12. **キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。  
  
13. **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
14. **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
15. **キュー**ボックスで「mqcorrelation」をクリック**エクスポート**です。  
  
16. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**[ok]**または**完了**すべてのダイアログ ボックスを終了します。  
  
### <a name="to-create-the-send-port-to-mqseries"></a>MQSeries に対する送信ポートを作成するには  
  
1.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqout"です。  
  
3.  **トランスポートの種類**ボックスで、 **MQSeries**です。  
  
4.  **送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**です。  
  
5.  をクリックして**構成**です。  
  
6.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。  
  
7.  **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  
  
8.  **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  
  
9. **キュー**ボックスで「mqcorrelation」をクリック**OK**です。  
  
10. をクリックして**OK**すべてのダイアログ ボックスを終了します。  
  
### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  
  
1.  BizTalk Server 管理コンソールで **受信ポート**です。  
  
2.  詳細ウィンドウで右クリックし、 **MQIn**受信場所をクリックして**を有効にする**です。  
  
3.  詳細ウィンドウで右クリックし、 **MQOut**送信ポートをクリックして**を開始します。**  
  
### <a name="to-create-the-folders-used-by-the-application"></a>アプリケーションが使用するフォルダーを作成するには  
  
1.  **C:\\** ドライブが既に存在しない場合、"temp"という名前のフォルダーを作成します。  
  
2.  下にある、 **C:\temp**ディレクトリ、"Pickup"および"Dropit"という名前のフォルダーを作成します。  
  
### <a name="building-and-deploying-this-sample"></a>サンプルのビルドと展開  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    1.  プロジェクトの厳密な名前のキー ファイルを作成します。  
  
    2.  オーケストレーション プロジェクトをコンパイルして展開します。  
  
    3.  ファイル アダプター用の送信ポートと受信ポートを作成します。  
  
### <a name="bind-and-start-the-orchestration"></a>オーケストレーションのバインドと開始  
  
1.  BizTalk Server 管理コンソールで、展開、**オーケストレーション**フォルダーです。  
  
2.  詳細ウィンドウで右クリックし、 **MQSCorrelationSetOrchestration**オーケストレーション、およびクリック**バインド**です。  
  
3.  オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。  
  
    |**オーケストレーション ポート**|**メッセージ ポート/受信場所**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSetOrchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQIn|  
    |MQSeriesRequestSendPort|MQOut|  
    |FileSendPort|MQSCorrelationSetOrchestration.FileSendPort|  
  
4.  をクリックして**ホスト**です。  
  
5.  **ホスト**ボックスで、 **BizTalkServerApplication**、 をクリック**OK**です。  
  
6.  **送信ポート**を右クリックして**mqscorrelationsetorchestration.filesendport**、し、**開始**です。  
  
7.  **受信場所**を右クリックして**mqscorrelationsetorchestration.filereceiveport**し、**を有効にする**です。  
  
8.  オーケストレーションを右クリックし、をクリックして**開始**です。  
  
    > [!NOTE]
    >  オーケストレーションを開始すると、オーケストレーションの参加も自動的に実行されます。  
  
### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  ファイルを配置、 **C:\Temp\Pickup**フォルダーです。  
  
2.  内のファイルを調べて、 **C:\Temp\Dropit**フォルダーです。  
  
    > [!NOTE]
    >  無効にした場合、 **MQIn**受信場所、WebSphere MQ エクスプ ローラーでメッセージを確認し、メッセージ識別子と関連付け識別子が設定されていることができます。 これを行うには、起動、 **WebSphere MQ エクスプ ローラー**で配置されているメッセージを確認し、 **MQCorrelation**キュー。 メッセージ識別子と関連付け識別子が表示されます、**識別子**のタブ、**メッセージ プロパティ** ダイアログ ボックス。  
  
    > [!NOTE]
    >  実稼働環境では、MQSeries キューに送信されるメッセージごとに一意の ID を割り当てる必要があります。 これを行うには、オーケストレーションの式図形を変更します。 次の行を変更してこれらのプロパティを一意の 24 バイト ID に設定します。  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  これらのプロパティ」セクションを参照して、一意の 24 バイト ID を設定する場合**MQSeries に送信されるメッセージの一意の 24 バイト ID を作成する**です。  
  
### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a>MQSeries に送信されるメッセージに一意の 24 バイト ID を作成するには  
  
1.  新しい C# クラス ライブラリ プロジェクトを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で作成します。  
  
2.  クラスの .cs ファイルに次のコードを貼り付けます。  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Security.Cryptography;  
  
    namespace MQId  
    {[Serializable]  
        public class GetId  
        {  
            RNGCryptoServiceProvider randomCryptoString = new RNGCryptoServiceProvider();  
  
            public string getGuidstr()  
            {  
                byte[] newGuid = GetRandomData(24);  
                return ConvertToHex(newGuid);  
            }  
  
            private byte[] GetRandomData(int keySize)  
            {  
                byte[] randomData = new byte[keySize];  
                randomCryptoString.GetBytes(randomData);  
                return randomData;  
            }  
  
            private string ConvertToHex(byte[] key)  
            {  
                StringBuilder hexString = new StringBuilder();  
                for (int i = 0; i < key.Length; ++i)  
                {  
                    hexString.Append(String.Format("{0:X2}", key[i]));  
                }  
                return hexString.ToString();  
            }  
        }  
    }  
    ```  
  
3.  指定して、**既定の名前空間**の**MQId**と**アセンブリ名**の**GetId**プロジェクト プロパティ**アプリケーション**ページ。  
  
4.  プロジェクトのプロパティでアセンブリに署名する厳密な名前キー ファイルを指定**署名**ページし、プロジェクトをビルドします。  
  
5.  グローバル アセンブリ キャッシュ ツール (gacutil.exe) を使用してに、コンパイルされたアセンブリを GAC に読み込む (gacutil/i \<*コンパイル済み dll ファイルの名前*>)。  
  
6.  このサンプルの BizTalk プロジェクトに GetId アセンブリへの参照を追加します。  
  
7.  このサンプルで使用するオーケストレーションに 2 つの変数を追加します。  
  
    |変数名 (ID)|型|  
    |----------------------------------|----------|  
    |GetId|MQId.GetId|  
    |strGuid|System.String|  
  
8.  このサンプルのオーケストレーションに使用する式図形に次のコードを貼り付けます。このコードで既存のコードを上書きします。  
  
    ```  
    GetId = new MQId.GetId();  
    strGuid = GetId.getGuidstr();  
    MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
    ```  
  
9. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのオーケストレーションが展開済みの場合、停止して削除します。 セクションで手順**のビルドとこのサンプルを展開**、**のバインドとオーケストレーションの開始**と**アプリケーションをテストする**です。  
  
    > [!NOTE]
    >  この方法で MQSeries に送信されるメッセージに一意の 24 バイト ID を作成しても、送信されるすべてのメッセージに対して一意の ID が 100% 保証されるわけではありません。ただし、メッセージ ID が重複する可能性は非常に低くなります。 ビジネス要件により、重複するメッセージ ID がないことを 100% 保証する必要がある場合、別のカスタム コードを使用してこの機能を確保する必要があります。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 このサンプルでは、クラスやメソッドを明示的に使用しません。  
  
## <a name="see-also"></a>参照  
 [要求/応答を使用してメッセージを相互に関連付ける](../core/correlating-messages-using-request-reply.md)   
 [MQSeries アダプタ サンプル](../core/mqseries-adapter-samples.md)