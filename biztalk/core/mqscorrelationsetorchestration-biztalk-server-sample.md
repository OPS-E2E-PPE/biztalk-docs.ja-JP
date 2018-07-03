---
title: MQSCorrelationSetOrchestration (BizTalk Server サンプル) |Microsoft Docs
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
ms.assetid: fcda65d0-e3ec-4ead-978d-3904903b8762
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0057e9a9276de5eb3724f1af298822b03065a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011779"
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a>MQSCorrelationSetOrchestration (BizTalk Server サンプル)
MQSCorrelationSetOrchestration サンプルは、実行中のオーケストレーションに MQSeries キューをルーティングして戻すために送信されるメッセージを関連付けるための MQSeries 関連付け識別子を使用する方法を示します。 オーケストレーションが、識別子の値を使用して MQSeries 関連付け識別子とメッセージを設定、 **MQMD_CorrelId**と**MQMD_MsgID**プロパティ。 MQSeries キュー マネージャーは、MessageID の値をメッセージの CorrelationID プロパティにコピーします。  

## <a name="prerequisites"></a>前提条件  
 このサンプルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているのと同じサーバー上に IBM WebSphere MQSeries がインストールされていることを前提としています。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、IBM WebSphere MQSeries サーバーに送信されるメッセージにメッセージ識別子と関連付け識別子を設定する方法について示します。 これは、実行中のオーケストレーションにルーティングして戻すメッセージを関連付けるための 1 つの方法として挙げられます。 MQSeries キュー マネージャーはメッセージを受信すると、その MessageID の値をメッセージの CorrelationID プロパティにコピーします。 この CorrelationID (**MQMD_CorrelId**) を使用して、オーケストレーションの MQSeries の応答メッセージを MQSeries にメッセージを送信するために使用するインスタンスに関連付けます。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルは、オーケストレーションで処理中のドキュメントを MQSeries キューに送信可能であり (多くの場合、追加の処理を行うため)、実行中のオーケストレーションにルーティングして戻されるというシナリオを示します。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration  

 次の表は、このサンプルのファイルとその目的を示しています。  

|**[最近使ったファイル]**|**[説明]**|  
|--------------|---------------------|  
|**MQSCorrelationSetOrchestration.btproj、**<br /><br /> **MQSCorrelationSetOrchestration.sln**|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|**MQSCorrelationSetOrchestration.odx**|アプリケーションのオーケストレーション。|  
|**MQSCorrelationSetOrchestration.snk**|厳密な名前のキー ファイル。|  
|**Setup.bat**|このサンプルを作成および初期化します。|  

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 全体的なワークフローの 1 つのステップとして MQSeries サーバーにメッセージを送信する必要がある場合は、このサンプルで採用されているロジックを組み込みます。  

### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a>WebSphere MQ エクスプローラーを使用して MQSeries キューを作成するには  

1.  クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。  

2.  ダブルクリック**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。 通常、既定のキュー マネージャーの名前**qm _ < コンピューター名 >** 場所*machine_name*コンピューターの名前を指定します。  

3.  右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。  

4.  **ローカル キューの作成**] ダイアログ ボックスで**キュー名**"MQCorrelation"を入力し、[クリックして**OK**します。  

### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a>受信場所と MQSeries キューを作成するには  

1.  BizTalk Server 管理コンソールを開きます。  

2.  展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。  

3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  

4.  **一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQIn」を入力し、 をクリック**OK**します。  

5.  左側のウィンドウで次のようにクリックします。**受信場所**タブをクリックし、[] をクリックし、**新規**します。  

6.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQIn」を入力します。  

7.  **トランスポートの種類**ボックスで、 **MQSeries**します。  

8.  **受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。  

9. **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。  

10. クリックして**構成**します。  

11. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、「10」を入力します。  

12. **キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。  

13. **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  

14. **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  

15. **キュー**ボックスに「MQCorrelation」を入力し、 クリック、**エクスポート**します。  

16. **エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします **[ok]** または**完了**すべてのダイアログ ボックスを終了します。  

### <a name="to-create-the-send-port-to-mqseries"></a>MQSeries に対する送信ポートを作成するには  

1.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。  

2.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqout」.  

3.  **トランスポートの種類**ボックスで、 **MQSeries**します。  

4.  **送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。  

5.  クリックして**構成**します。  

6.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。  

7.  **キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。  

8.  **キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。  

9. **キュー**ボックスに「MQCorrelation」を入力し、 クリック、 **OK**します。  

10. クリックして**OK**すべてのダイアログ ボックスを終了します。  

### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  

1.  BizTalk Server 管理コンソールで、次のようにクリックします。**受信ポート**します。  

2.  詳細ペインで右クリックし、 **MQIn**受信場所とクリックして**を有効にする**します。  

3.  詳細ペインで右クリックし、 **MQOut**送信ポートを**を開始します。**  

### <a name="to-create-the-folders-used-by-the-application"></a>アプリケーションが使用するフォルダーを作成するには  

1.  **C:\\** ドライブは、存在しない場合、"temp"という名前のフォルダーを作成します。  

2.  で、 **C:\temp**ディレクトリ、"Pickup"および"Dropit"という名前のフォルダーを作成します。  

### <a name="building-and-deploying-this-sample"></a>サンプルのビルドと展開  

1.  コマンド ウィンドウで、次のフォルダーに移動します。  

     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  

2.  ファイルは、次の操作を実行します。 Setup.bat を実行します。  

    1.  プロジェクトの厳密な名前のキー ファイルを作成します。  

    2.  オーケストレーション プロジェクトをコンパイルして展開します。  

    3.  ファイル アダプター用の送信ポートと受信ポートを作成します。  

### <a name="bind-and-start-the-orchestration"></a>オーケストレーションのバインドと開始  

1.  BizTalk Server 管理コンソールで、**オーケストレーション**フォルダー。  

2.  詳細ペインで右クリックし、 **MQSCorrelationSetOrchestration**オーケストレーション、およびクリック**バインド**します。  

3.  オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。  

    |**オーケストレーション ポート**|**メッセージ ポート/受信場所**|  
    |----------------------------|--------------------------------------------|  
    |FileReceivePort|MQSCorrelationSetOrchestration.FileReceivePort|  
    |MQSeriesResponseReceivePort|MQIn|  
    |MQSeriesRequestSendPort|MQOut|  
    |FileSendPort|MQSCorrelationSetOrchestration.FileSendPort|  

4.  クリックして**ホスト**します。  

5.  **ホスト**ボックスで、 **BizTalkServerApplication**、 をクリック**OK**します。  

6.  **送信ポート**、右クリック**mqscorrelationsetorchestration.filesendport**、し、**開始**します。  

7.  **受信場所**を右クリックして **[mqscorrelationsetorchestration.filereceiveport]** 選び**を有効にする**します。  

8.  オーケストレーションを右クリックし、をクリックして**開始**します。  

    > [!NOTE]
    >  オーケストレーションを開始すると、オーケストレーションの参加も自動的に実行されます。  

### <a name="to-test-the-application"></a>アプリケーションをテストするには  

1.  ファイルを配置、 **C:\Temp\Pickup**フォルダー。  

2.  内のファイルを調べて、 **C:\Temp\Dropit**フォルダー。  

    > [!NOTE]
    >  無効にした場合、 **MQIn**受信場所は、WebSphere MQ エクスプ ローラーでメッセージを確認し、メッセージと関連付け識別子が設定されていることができます。 これを行うには、起動、 **WebSphere MQ エクスプ ローラー**にメッセージを調べ、 **MQCorrelation**キュー。 メッセージ識別子と関連付け識別子が表示されます、**識別子**のタブ、**メッセージ プロパティ** ダイアログ ボックス。  

    > [!NOTE]
    >  実稼働環境では、MQSeries キューに送信されるメッセージごとに一意の ID を割り当てる必要があります。 これを行うには、オーケストレーションの式図形を変更します。 次の行を変更してこれらのプロパティを一意の 24 バイト ID に設定します。  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";  
    >   
    >  これらのプロパティは、セクションを参照してください。 一意の 24 バイト ID を設定する場合**MQSeries に送信されるメッセージの一意の 24 バイト ID を作成する**します。  

### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a>MQSeries に送信されるメッセージに一意の 24 バイト ID を作成するには  

1. 新しい C# クラス ライブラリ プロジェクトを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で作成します。  

2. クラスの .cs ファイルに次のコードを貼り付けます。  

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

3. 指定、**既定の名前空間**の**MQId**と**アセンブリ名**の**GetId**プロジェクトのプロパティで**アプリケーション**ページ。  

4. プロジェクトのプロパティでアセンブリに署名する厳密な名前キー ファイルを指定**署名**ページし、プロジェクトをビルドします。  

5. グローバル アセンブリ キャッシュ ツール (gacutil.exe) を使用して、コンパイルされたアセンブリを GAC に読み込むに (gacutil/i \<*コンパイル済み dll ファイルの名前*\>)。  

6. このサンプルの BizTalk プロジェクトに GetId アセンブリへの参照を追加します。  

7. このサンプルで使用するオーケストレーションに 2 つの変数を追加します。  


   | 変数名 (ID) |     型      |
   |----------------------------|---------------|
   |           GetId            |  MQId.GetId   |
   |          strGuid           | System.String |


8. このサンプルのオーケストレーションに使用する式図形に次のコードを貼り付けます。このコードで既存のコードを上書きします。  

   ```  
   GetId = new MQId.GetId();  
   strGuid = GetId.getGuidstr();  
   MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
   ```  

9. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのオーケストレーションが展開済みの場合、停止して削除します。 セクションの手順に従います**のビルドとこのサンプルをデプロイ**、**のバインドと開始オーケストレーション**と**アプリケーションをテストする**します。  

    > [!NOTE]
    >  この方法で MQSeries に送信されるメッセージに一意の 24 バイト ID を作成しても、送信されるすべてのメッセージに対して一意の ID が 100% 保証されるわけではありません。ただし、メッセージ ID が重複する可能性は非常に低くなります。 ビジネス要件により、重複するメッセージ ID がないことを 100% 保証する必要がある場合、別のカスタム コードを使用してこの機能を確保する必要があります。  

## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 このサンプルでは、クラスやメソッドを明示的に使用しません。  

## <a name="see-also"></a>参照  
 [要求/応答を使用してメッセージの関連付け](../core/correlating-messages-using-request-reply.md)   
 [MQSeries アダプタ サンプル](../core/mqseries-adapter-samples.md)