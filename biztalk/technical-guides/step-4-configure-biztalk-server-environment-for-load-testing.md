---
title: '手順 4: ロード テスト用の BizTalk Server 環境の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f336c5f-5a18-493d-8fc0-a8a475ab47b3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf3ab4c913a55be391d1e92522c257c4cd82d272
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990355"
---
# <a name="step-4-configure-biztalk-server-environment-for-load-testing"></a>手順 4: ロード テスト用の BizTalk Server 環境を構成します。
このトピックでは、BizTalk Server 受信場所、受信ポートを作成するための情報と、トピックで説明したサンプル コードを実行するために必要な送信ポート[手順 1: BizTalk Server にドキュメントを送信する単体テストを作成する](~/technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)[手順 3: 複数の単体テストを同時に実行するロード テストの作成](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)です。  

## <a name="configure-biztalk-server-environment-for-load-tests"></a>ロード テスト用の BizTalk Server 環境を構成します。  
 トピックの説明に従って[手順 3: を実行複数単体テストを同時にロード テストを作成](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)、ロード テスト**BTS_Messaging_Step**単体テストを実行するように構成**BTSMessaging**と**BTSMessaging2**します。 さらに、これらの単体テストは C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml メッセージのコピーを読み込むし、エンドポイントへの送信**BTSMessagingEP**と**BTSMessagingEP2**で定義されています。プロジェクトのアプリケーションの構成 (app.config) ファイルの次のセクション:  

 \<\!--BTSMessagingEP--\>\<エンドポイント address="net.tcp://*BizTalk Server コンピューター*: 8123/btsloadtest"バインド"netTcpBinding"bindingConfiguration ="netTcpBinding"コントラクトを = ="System.ServiceModel.Channels.IRequestChannel"名前 ="BTSMessagingEP"/\>\<エンドポイント address="net.tcp://*BizTalk Server コンピューター*: 8123/btsloadtest"バインド"netTcpBinding"を =bindingConfiguration ="netTcpBinding"contract="System.ServiceModel.Channels.IRequestChannel"名前 ="BTSMessagingEP2"/                  \>  

> [!NOTE]
>  前に説明したように*BizTalk Server コンピューター*は、実際の BizTalk Server コンピューター名のまたは複数の BizTalk Server コンピュータはネットワーク負荷分散 (NLB) クラスターのメンバーとして構成されている場合のプレース ホルダーです*BizTalk Server コンピューター*名前または対応する NLB 仮想サーバーのアドレスのプレース ホルダーです。  

 この例のために、2 つの BizTalk Server コンピューターが使用されていたし、BizTalk Server メッセージ ボックス データベースがリモートの SQL Server コンピューター。  

### <a name="create-biztalk-server-send-and-receive-hosts"></a>BizTalk Server 送信を作成し、受信ホスト  
 BizTalk Server のドキュメントのトピックの手順に従います[新しいホストを作成する方法](http://go.microsoft.com/fwlink/?LinkId=208595)(http://go.microsoft.com/fwlink/?LinkId=208595)送信ポートと送信アダプター ハンドラーの BizTalk Server の「送信」ホストを作成します。 次のプロパティで、ホストを構成します。  

|プロパティ|値|  
|--------------|-----------|  
|名前|TxHost|  
|型|インプロセス|  
|[ホストの追跡を許可する]|このボックスがオフであることを確認します。|  
|[信頼されている認証]|このボックスがオフであることを確認します。|  
|32 ビットのみ|このボックスがオフであることを確認します。|  
|[グループの既定のホストにする]|このボックスがオフであることを確認します。|  
|[Windows グループ]|このホストと関連付けられているホスト インスタンスへのアクセスを制御するために使用する Windows グループ。 用に作成された既定のインプロセス ホストがいずれかのウィンドウ グループ*\<コンピューター名\>* \BizTalk Application Users (用、1 台のサーバーの BizTalk Server インストールの場合) または *\<ドメイン名\>* \BizTalk Application Users (複数のサーバー、ドメイン グループの使用を必要とする BizTalk Server のインストールの場合) 用です。 **注:***\<コンピューター名\>* と*\<ドメイン名\>* 実際のコンピューター名または使用するドメイン名のプレース ホルダーグループの作成時にします。   <br /><br /> このホストの新しいグループを作成し、トピックで説明されている特権が必要かどうか[ホスト グループ](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803) BizTalk Server のドキュメントで。|  

 「受信」ホストを作成する「送信」ホストを作成するときに実行した手順を繰り返します。 次のプロパティ値を持つ、「受信」ホストを構成します。  

|プロパティ|値|  
|--------------|-----------|  
|名前|RxHost|  
|型|インプロセス|  
|[ホストの追跡を許可する]|このボックスがオフであることを確認します。|  
|[信頼されている認証]|このボックスがオフであることを確認します。|  
|32 ビットのみ|このボックスがオフであることを確認します。|  
|[グループの既定のホストにする]|このボックスがオフであることを確認します。|  
|[Windows グループ]|このホストと関連付けられているホスト インスタンスへのアクセスを制御するために使用する Windows グループ。 用に作成された既定のインプロセス ホストがいずれかのウィンドウ グループ*\<コンピューター名\>* \BizTalk Application Users (用、1 台のサーバーの BizTalk Server インストールの場合) または *\<ドメイン名\>* \BizTalk Application Users (複数のサーバー、ドメイン グループの使用を必要とする BizTalk Server のインストールの場合) 用です。 **注:***\<コンピューター名\>* と*\<ドメイン名\>* 実際のコンピューター名または使用するドメイン名のプレース ホルダーグループの作成時にします。   <br /><br /> このホストの新しいグループを作成し、トピックで説明されている特権が必要かどうか[ホスト グループ](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803) BizTalk Server のドキュメントで。|  

### <a name="create-instances-of-the-biztalk-server-send-and-receive-hosts"></a>BizTalk Server 送信のインスタンスを作成し、受信ホスト  
 BizTalk Server のドキュメントのトピックの手順に従います[ホスト インスタンスを追加する方法](http://go.microsoft.com/fwlink/?LinkId=208596)(http://go.microsoft.com/fwlink/?LinkId=208596)を作成して、BizTalk Server の「送信」ホストのインスタンスを開始します。 BizTalk Server グループ内の各 BizTalk サーバー上で実行し、次のプロパティ値で各ホスト インスタンスを構成する「送信」ホストのインスタンスを構成します。  

|プロパティ|値|  
|--------------|-----------|  
|**ホスト名**|選択**TxHost**横にドロップダウン リストからリスト**ホスト名**します。|  
|**[サーバー]**|実行するホスト インスタンスはこのドロップダウン リストから横に、BizTalk Server を選択します。 **Server**します。|  
|**ログオン**|1.をクリックして、**構成**を表示するボタン、**ログオン資格情報** ダイアログ ボックス。<br />2.**ログオン資格情報** ダイアログ ボックスが、指定したプロパティの次の値を入力します。<br />     **プロパティ**<br />     **ログオン**: この BizTalk Server ホストに関連付けられている Windows グループのメンバーであるユーザー アカウントの名前。<br />     **パスワード**: で指定されたユーザー アカウントのパスワード、**ログオン**テキスト ボックス。<br />3.をクリックして**OK**を閉じる、**ログオン資格情報** ダイアログ ボックス。|  
|**ホスト インスタンスの開始を無効にします。**|このボックスがオフであることを確認します。|  

 ホスト インスタンスを作成した後、ホスト インスタンスを右クリックし、選択**開始**コンテキスト メニュー。  

 「受信」ホスト インスタンスを作成する「送信」ホスト インスタンスを作成するときに実行した手順を繰り返します。 BizTalk Server グループ内の各 BizTalk サーバー上で実行し、次のプロパティ値で各ホスト インスタンスを構成する「受信」ホストのインスタンスを構成します。  

|プロパティ|値|  
|--------------|-----------|  
|ホスト名|選択**RxHost**横にドロップダウン リストからリスト**ホスト名**します。|  
|[サーバー]|実行するホスト インスタンスはこのドロップダウン リストから横に、BizTalk Server を選択します。 **Server**します。|  
|ログオン|1.をクリックして、**構成**を表示するボタン、**ログオン資格情報** ダイアログ ボックス。<br />2.**ログオン資格情報** ダイアログ ボックスが、指定したプロパティの次の値を入力します。<br />     **プロパティ**<br />     **ログオン**: この BizTalk Server ホストに関連付けられている Windows グループのメンバーであるユーザー アカウントの名前。<br />     **パスワード**: で指定されたユーザー アカウントのパスワード、**ログオン**テキスト ボックス。<br />3.クリックして**OK**ログオン資格情報 ダイアログ ボックスを閉じます。|  
|[ホスト インスタンスの開始を無効にする]|このボックスがオフであることを確認します。|  

 ホスト インスタンスを作成した後、ホスト インスタンスを右クリックし、選択**開始**コンテキスト メニュー。  

### <a name="create-a-biztalk-server-receive-port"></a>BizTalk Server を作成する受信ポート  
 トピックの手順に従って[受信ポートを作成する方法](http://go.microsoft.com/fwlink/?LinkID=154843)(http://go.microsoft.com/fwlink/?LinkID=154843)一方向受信ポートを作成する BizTalk Server のドキュメント。 受信ポートを作成するときのままにしてすべてのプロパティを除いて既定値以下の表で説明したように。  

|プロパティ|値|  
|--------------|-----------|  
|General\Name|BTSLoadTestMessaging.OneWay.ReceivePort|  
|General\Port 型|一方向|  
|General\Authentication|認証なし|  
|失敗したメッセージのルーティング General\Enable|このボックスがオフであることを確認します。|  
|General\Description|空白のままに|  
|[受信マップ]|なし|  
|Tracking|すべてのボックスがオフでないことを確認します。|  
|受信場所|クリックして**新規**、これが表示されます、**受信場所のプロパティ** ダイアログ ボックスで次のセクションで説明したように構成する必要があります**BizTalk Server 受信場所の作成**.|  

### <a name="create-a-biztalk-server-receive-location"></a>BizTalk Server を作成する受信場所  
 **受信場所のプロパティ**BizTalk Server 受信ポートを作成するときにダイアログ ボックスが表示されたら、指定したプロパティの値を適用します。  

|プロパティ|値|  
|--------------|-----------|  
|名前 :|BTSLoadTest.Messaging.OneWay.WCF Customer.ReceiveLocation|  
|ハンドラーが表示されます。|RxHost|  
|[受信パイプライン]:|PassThruReceive|  
|説明:|空白のままに|  
|型:|選択**Wcf-custom**クリックしてドロップダウン リストから、**構成**ボタンが表示されます、 **Wcf-custom トランスポートのプロパティ**として使用する ダイアログ ボックス次のセクションで説明したように構成**Wcf-custom 受信トランスポート構成**します。|  

### <a name="configure-the-wcf-custom-receive-transport"></a>Wcf-custom 受信トランスポートを設定します。  
 **Wcf-custom トランスポートのプロパティ**BizTalk Server 受信場所を作成するときにダイアログ ボックスが表示されたら、次の表で説明したように、既定値を除くすべてのプロパティのままにします。  

|プロパティ|値|  
|--------------|-----------|  
|General\Address (URI)|net.tcp://localhost: 8123/btsloadtest|  
|Binding\Binding 型|netTcpbinding|  
|Binding\NetTcpBindingElement\listenBacklog|400|  
|Binding\NetTcpBindingElement\maxConnections|400|  
|Binding\Security\NetTcpSecurityElement\mode|なし|  
|Behavior\ServiceBehavior\serviceThrottling\ServiceThrottlingElement**注:** serviceThrottling 動作を ServiceBehavior の右クリックして、動作の一覧に追加する をクリックして**追加拡張子**、 **serviceThrottling**クリックして、動作拡張機能の一覧から**OK**。|設定、 **ServiceThrottlingElement**プロパティを次の値にします。<br /><br /> -   **maxConcurrentCalls** 400<br />-   **maxConcurrentInstances** 400<br />-   **maxConcurrentSessions** 400|  
|Behavior\ServiceBehavior\serviceDebug\ServiceDebugElement**注:** 、ServiceBehavior の右クリックして、動作の一覧にして serviceDebug の動作を追加する をクリックして**拡張機能の追加**を選択します。**serviceDebug**クリックして、動作拡張機能の一覧から**OK**します。|リストをそのまま**ServiceDebugElement**プロパティで、既定以外の値 (空)、次のプロパティが True の値に変更する必要があります。<br /><br /> -   **httpHelpPageEnabled**は True。<br />-   **httpsHelpPageEnabled**は True。<br />-   **includeExceptionDetailInFaults**は True。|  

 をクリックして**ok** Wcf-custom トランスポートのプロパティ ダイアログ ボックスを閉じて をクリックする**OK** 受信場所のプロパティ ダイアログ ボックスを閉じます。  

### <a name="create-a-biztalk-server-send-port"></a>BizTalk Server 送信ポートを作成します。  
 トピックの手順に従って[送信ポートを作成する方法](http://go.microsoft.com/fwlink/?LinkID=154845)(http://go.microsoft.com/fwlink/?LinkID=154845)を作成する BizTalk Server のドキュメントを**静的な一方向**送信ポート。 送信ポートを作成するときのままにしてすべてのプロパティを除いて既定値以下の表で説明したように。  

|プロパティ|値|  
|--------------|-----------|  
|General\Name|BTSLoadTest.Messaging.Send.WCF カスタム|  
|General\Send ハンドラー|TxHost|  
|General\Send パイプライン|PassThruTransmit|  
|Filters\Name|BTS.ReceivePortName|  
|Filters\Operator|==|  
|Filters\Value|BTSLoadTest.Messaging.OneWay.ReceivePort|  
|によって Filters\Group|**注:** としてフィルターを表示する場合、適切な値は、これらのプロパティが構成されている、 `BTS.ReceivePortName == BTSLoadTest.Messaging.OneWay.ReceivePort` b の送信ポートのプロパティ ダイアログ ボックスの [フィルタ] ページの下部に示すようox します。 このフィルターを適用すると、結果として、この送信ポートは BTSLoadTest.Messaging.OneWay.ReceivePort をという名前の受信ポートを使用して BizTalk Server で受信メッセージにサブスクライブします。|  
|Tracking|すべてのボックスがオフでないことを確認します。|  
|General\Type|選択**Wcf-custom**クリックしてドロップダウン リストから、**構成**ボタンが表示されます、 **Wcf-custom トランスポートのプロパティ**として使用する ダイアログ ボックス次のセクションで説明したように構成**Wcf-custom 送信トランスポート構成**します。|  

### <a name="configure-the-wcf-custom-send-transport"></a>Wcf-custom 送信トランスポートを構成します。  
 **Wcf-custom トランスポートのプロパティ**BizTalk Server 送信ポートを作成するときにダイアログ ボックスが表示されたら、次の表で説明したように、既定値を除くすべてのプロパティのままにします。  

|プロパティ|値|  
|--------------|-----------|  
|General\Address (URI)|net.tcp://*\<コンピューター名\>*: 2001/TCP1**重要:***\<コンピューター名\>* プレース ホルダーですIndigoService.exe をホストするために使用する実際のコンピューター名、これは WCF 経由で送信されるメッセージを使用しています。 IndigoService.exe には、ごくわずかなリソースが必要であるため IndigoService.exe を BizTalk Server グループのデータベース用の SQL Server コンピューターで実行する完全に受け入れ可能です。 利用可能な BizTalk ベンチマーク ウィザードの一部である IndigoService.exe [BizTalk ベンチマーク ウィザード](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)します。|  
|Binding\Binding 型|**customBinding**|  

 WCF カスタム バインドの種類のほとんどと同様に、 **customBinding**バインドの種類は、次の値に設定する必要があります、いくつかのプロパティを公開します。  

1.  で、**バインド**セクションがある、 **CustomBindingElement**関連付けられているプロパティ**構成**セクション。 [構成] セクションで、すべての値のままに、 **CustomBindingElement**プロパティは既定値。  

2.  下で**CustomBindingElement**を右クリックして**textMessageEncoding**選択 **(Del) 拡張機能を削除**します。 同様に、右クリックして**httpTransport**選択 **(Del) 拡張機能を削除**します。  

3.  を右クリックして**CustomBindingElement**選択**Ins 拡張機能の追加**を表示する、**バインド要素拡張機能の選択** ダイアログ ボックス。  

4.  選択**binaryMessageEncoding**  をクリック**OK**を追加する、 **binaryMessageEncoding**要素拡張機能。 表示するには、手順を繰り返して、**バインド要素拡張機能の選択** ダイアログ ボックスとスクロール ダウン、利用可能な要素の拡張機能の一覧が表示されるまで、 **tcpTransport**要素拡張機能、を選択します**tcpTransport**クリック**OK**します。  

5.  [ **CustomBindingElement**選択、 **tcpTransport**要素との構成] セクションで**tcpTransport**、すべてのプロパティとして以外の既定値のままにして次の表に記載されました。  

    |プロパティ|値|  
    |--------------|-----------|  
    |connectionBufferSize|2097152|  
    |maxBufferSize|2097152|  
    |maxPendingAccepts|400|  
    |maxPendingConnections|400|  
    |listenBacklog|400|  
    |maxBufferPoolSize|2097152|  
    |MaxReceivedMessageSize|2097152|  

6.  下、 **tcpTransport**要素の選択、 **ConnectionPoolSettings**要素と参加解除が既定ですべてのプロパティの値を除く、 **maxOutboundConnectionsPerEndpoint**プロパティで、400 の値に変更する必要があります。  

7.  をクリックして**OK** Wcf-custom トランスポートのプロパティ ダイアログ ボックスを閉じる をクリックし、 **OK** BTSLoadTest.Messaging.Send.WCF Custom – 送信ポートのプロパティ ダイアログ ボックスを閉じます。  

### <a name="configure-a-computer-to-consume-messages-sent-by-the-biztalk-server-send-port"></a>BizTalk Server 送信ポートによって送信されたメッセージを使用するコンピューターを構成します。  
 前述のように、WCF 経由で送信されるメッセージを処理する、IndigoService.exe は設計されています。 利用可能な BizTalk ベンチマーク ウィザードの一部である IndigoService.exe [BizTalk ベンチマーク ウィザード](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)します。 設定して、この例の目的の IndigoService.exe を実行するには、最も簡単な方法がから BizTalk ベンチマーク ウィザードの zip ファイルをダウンロードするには、 [BizTalk ベンチマーク ウィザード ダウンロード ページ](http://go.microsoft.com/fwlink/?LinkID=209100)(http://go.microsoft.com/fwlink/?LinkID=209100)し、次の 4 つの抽出IndigoService.exe を実行するコンピューターにファイル:  

1. \IndigoService\bin\Release\IndigoService.exe  

2. \IndigoService\bin\Release\IndigoService.exe.config  

3. \IndigoService\bin\Release\Response.xml  

4. \IndigoService\bin\Release\StartIndigoService.bat  

   次に、StartIndigoService.bat をダブルクリックして IndigoService.exe を起動します。 IndigoService.exe は、IndigoService.exe.config ファイルで指定されたエンドポイントに送信されるメッセージを使用します。  

   \<エンドポイント アドレス ="net.tcp://localhost: 2001/TCP1"バインド"netTcpBinding"bindingConfiguration の = ="Binding1"名前 ="endpoint1"contract="IndigoService.IServiceTwoWaysVoidNonTransactional"/\>  

   これは、送信ポートのアドレスには、アドレス (URI) で始まる net.tcp:// が構成されている理由*\<コンピューター名\>*: 2001/TCP1  

   IndigoService.exe には、ごくわずかなリソースが必要であるため IndigoService.exe を BizTalk Server データベース用の SQL Server コンピューターで実行する完全に受け入れ可能です。  

### <a name="disable-tracking-and-throttling-for-the-biztalk-server-group"></a>追跡と BizTalk Server グループの調整を無効にします。  
 システムでは、両方のメッセージの絶対最大持続可能スループットを判断するためには、追跡および調整をロード テストを開始する前に無効にする必要があります。 これ行う次の手順に従って、BizTalk Server 管理コンソールを使用します。  

1. BizTalk Server 管理コンソールを起動します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**BizTalk Server 2010**順にクリックします**BizTalk Server 管理**します。  

2. **BizTalk Server 管理**、記載されている場合、BizTalk グループを選択するかが表示されない場合は、右**BizTalk Server 管理**を選択します**既存グループへの接続**、BizTalk グループの BizTalk Server 管理データベースの横にある SQL Server の名前を入力**SQL Server 名:** の横にあるBizTalkグループの管理データベース名の名前を入力**データベース名:**  をクリックし、 **OK**します。  

3. BizTalk グループ ノードを右クリックして**設定**を表示する、 **BizTalk 設定ダッシュ ボード**します。  

4. クリックして選択**ホスト**BizTalk 設定ダッシュ ボードの左側のウィンドウにします。  

5. 次に、ドロップダウン リストをクリックして**ホスト**パフォーマンス テスト中に使用されるホストのいずれかを選択します。  

6. プロパティの次の表に示すとおり以外の既定値のままにしてください。  


   |                          プロパティ                          |               値                |
   |------------------------------------------------------------|------------------------------------|
   |          **追跡データを DTA DB に General\Move**          | オンの場合は、このボックスをオフにします。 |
   |                  **General\32 ビットのみ**                   | オンの場合は、このボックスをオフにします。 |
   |          **General\Polling Intervals\Messaging**           |     20000000 の値に設定します。     |
   |        **General\Polling Intervals\Orchestrations**        |     20000000 の値に設定します。     |
   |     **リソースに基づく Throttling\In プロセス メッセージ**      |      10000 の値に設定します。       |
   | **リソースに基づく Throttling\Internal メッセージ キューのサイズ**  |      10000 の値に設定します。       |
   |     **Db のリソースに基づく Throttling\Message 数**      |        値を 0 に設定します。         |
   | **リソースに基づく Throttling\Memory Usage\Process の仮想** |        値を 0 に設定します。         |
   |  **割合に基づく Throttling\Publishing\Throttling の上書き**  |       制限しない に設定します。       |
   |   **割合に基づく Throttling\Delivery\Throttling の上書き**   |       制限しない に設定します。       |


7. パフォーマンス テストの実行中に使用されるすべてのホストについて、手順 6. で説明されているプロセスを繰り返します。  

8. クリックして選択**ホスト インスタンス**BizTalk 設定ダッシュ ボードの左側のウィンドウにします。  

9. 次に、ドロップダウン リストをクリックして**ホスト インスタンス:** パフォーマンスをテストするために使用されるホスト インスタンスのいずれかを選択します。  

10. プロパティの値のままにして、既定の設定の変更を除く、 **.NET CLR 最大ワーカー スレッド**の値に**100**を変更して、 **.NET CLR 最小ワーカー スレッド**に、値**25**します。  

11. パフォーマンス テストの実行中に使用されるすべてのホスト インスタンスに対して手順 10 で説明されているプロセスを繰り返します。  

    追跡と調整を無効にする場合でもは任意の方法ではなく表して内容は、実稼働のシナリオで行う必要がありますので、これらの操作は無効にして調べる場合は true。 最大持続可能にする方パフォーマンスの観点からコストが高くBizTalk Server 環境のスループット (MST)。 これにより、テスト担当者を調整する任意のパフォーマンスの影響は、環境に適用されているかを明確に確認できます。 確かに、引数は、追跡を無効にしない必要がありますおよび BizTalk Server アプリケーションで追跡を必要とする、最初からわかっている場合する必要があります有効にする追跡確立でした。 ただし、**パフォーマンス テストの目的での制限が無効にあらゆる努力が行われる**します。 スロットルは、BizTalk Server が、運用環境での負荷の増加による「経由である」ことを防ぐに便利です。 パフォーマンスの観点からの費用がかかると、ロード テスト中に開始を調整する場合なら、どのようなパフォーマンス レベルを決定する非常に困難にするためにパフォーマンスがテスト中に有効になっている調整をしたくない、ただし、BizTalk Server アプリケーションを実際に実現できます。 次のトピックでは、MST を超える、BizTalk Server 環境のプッシュを持続ロード テストで実際の MST に縮小し、ステップ ロード テストを実行する方法について説明します。 調整を有効にする場合になります MST はどのような真のさらにわかったように、MST を超える BizTalk 環境をプッシュすることはほぼ不可能です。