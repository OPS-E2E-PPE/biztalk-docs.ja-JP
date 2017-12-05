---
title: "手順 4: ロード テストのための BizTalk Server 環境の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f336c5f-5a18-493d-8fc0-a8a475ab47b3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2e8b2b3751f31401ef0353944be0bdad3cbb2b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-configure-biztalk-server-environment-for-load-testing"></a>手順 4: ロード テストのための BizTalk Server 環境を構成します。
このトピックは、BizTalk Server 受信場所、受信ポートを作成するための情報を提供し、送信ポートのトピックで説明するサンプル コードを実行するために必要[手順 1: BizTalk Server に送信ドキュメントに単体テストを作成](~/technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)および[手順 3: 複数の単体テストを同時に実行するロード テストの作成](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)です。  
  
## <a name="configure-biztalk-server-environment-for-load-tests"></a>ロード テスト用に BizTalk Server 環境を構成します。  
 トピックの説明に従って[手順 3: 実行複数単体テストを同時にロード テストを作成](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)、ロード テスト**BTS_Messaging_Step**単体テストを実行するように構成**BTSMessaging**と**BTSMessaging2**です。 さらに、これらの単体テストは C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml メッセージのコピーを読み込むし、エンドポイントに送信**BTSMessagingEP**と**BTSMessagingEP2**で定義されています。プロジェクトのアプリケーション構成 (app.config) ファイルの次のセクション:  
  
 \<\!--BTSMessagingEP--\>\<エンドポイント address="net.tcp://*BizTalk Server コンピューター*: 8123/btsloadtest"バインド"netTcpBinding"bindingConfiguration を ="netTcpBinding"コントラクトを = ="System.ServiceModel.Channels.IRequestChannel"名前 ="BTSMessagingEP"/\>\<エンドポイント address="net.tcp://*BizTalk Server コンピューター*: 8123/btsloadtest"バインド"netTcpBinding"を =bindingConfiguration ="netTcpBinding"contract="System.ServiceModel.Channels.IRequestChannel"名前 ="BTSMessagingEP2"/                  \>  
  
> [!NOTE]
>  既に述べた*BizTalk Server コンピューター*プレース ホルダーの実際の BizTalk Server コンピューター名または BizTalk Server コンピューターがネットワーク負荷分散 (NLB) クラスターのメンバーとして構成されている場合は、*BizTalk Server コンピューター*名または対応する NLB 仮想サーバーのアドレスのプレース ホルダーです。  
  
 この例の目的は、2 つの BizTalk Server コンピューターが使用されていたし、BizTalk Server メッセージ ボックス データベースがリモートの SQL Server コンピューターにします。  
  
### <a name="create-biztalk-server-send-and-receive-hosts"></a>BizTalk Server の送信を作成し、受信ホスト  
 BizTalk Server のドキュメントのトピックの手順に従って[を新しいホストを作成する方法](http://go.microsoft.com/fwlink/?LinkId=208595)送信ポートおよび送信アダプター ハンドラーの BizTalk Server の「送信」ホストを作成するには、(http://go.microsoft.com/fwlink/?LinkId=208595)。 次のプロパティで、ホストを構成します。  
  
|プロパティ|値|  
|--------------|-----------|  
|名前|TxHost|  
|型|処理中|  
|[ホストの追跡を許可する]|このボックスの取り消しがないことを確認します。|  
|[信頼されている認証]|このボックスの取り消しがないことを確認します。|  
|32 ビットのみ|このボックスの取り消しがないことを確認します。|  
|[グループの既定のホストにする]|このボックスの取り消しがないことを確認します。|  
|[Windows グループ]|このホストと関連付けられているホスト インスタンスへのアクセスを制御するために使用する Windows グループです。 既定のインプロセス ホストの名前はいずれかの用に作成ウィンドウ グループ*\<コンピューター名\>*\BizTalk Application Users (用、1 台のサーバーの BizTalk Server インストールの場合) または *\<ドメイン名\>*\BizTalk Application Users (複数のサーバーのドメイン グループの使用を必要とする BizTalk Server のインストールの場合) 用です。 **注:***\<コンピューター名\>*と*\<ドメイン名\>*実際のコンピューター名またはドメイン名のプレース ホルダーグループの作成時に使用されます。   <br /><br /> かどうかには、このホストの新しいグループを作成し、トピックで説明されている特権が必要[ホスト グループ](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803)、BizTalk Server のドキュメントにします。|  
  
 「受信」ホストを作成する「送信」ホストを作成するときに実行した手順を繰り返します。 次のプロパティ値を持つ、「受信」ホストを構成します。  
  
|プロパティ|値|  
|--------------|-----------|  
|名前|RxHost|  
|型|処理中|  
|[ホストの追跡を許可する]|このボックスの取り消しがないことを確認します。|  
|[信頼されている認証]|このボックスの取り消しがないことを確認します。|  
|32 ビットのみ|このボックスの取り消しがないことを確認します。|  
|[グループの既定のホストにする]|このボックスの取り消しがないことを確認します。|  
|[Windows グループ]|このホストと関連付けられているホスト インスタンスへのアクセスを制御するために使用する Windows グループです。 既定のインプロセス ホストの名前はいずれかの用に作成ウィンドウ グループ*\<コンピューター名\>*\BizTalk Application Users (用、1 台のサーバーの BizTalk Server インストールの場合) または *\<ドメイン名\>*\BizTalk Application Users (複数のサーバーのドメイン グループの使用を必要とする BizTalk Server のインストールの場合) 用です。 **注:***\<コンピューター名\>*と*\<ドメイン名\>*実際のコンピューター名またはドメイン名のプレース ホルダーグループの作成時に使用されます。   <br /><br /> かどうかには、このホストの新しいグループを作成し、トピックで説明されている特権が必要[ホスト グループ](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803)、BizTalk Server のドキュメントにします。|  
  
### <a name="create-instances-of-the-biztalk-server-send-and-receive-hosts"></a>BizTalk Server 送信のインスタンスを作成し、受信ホスト  
 BizTalk Server のドキュメントのトピックの手順に従って[ホスト インスタンスを追加する方法](http://go.microsoft.com/fwlink/?LinkId=208596)(http://go.microsoft.com/fwlink/?LinkId=208596) を作成および BizTalk Server の「送信」ホストのインスタンスを開始します。 BizTalk Server グループ内の各 BizTalk サーバーでを実行し、次のプロパティ値を持つ各ホスト インスタンスを構成する「送信」ホストのインスタンスを構成します。  
  
|プロパティ|値|  
|--------------|-----------|  
|**ホスト名**|選択**TxHost**横にドロップダウン リストからリスト**ホスト名**です。|  
|**[サーバー]**|実行するこのホスト インスタンス、ドロップ ダウン リストから次に、BizTalk Server を選択して**サーバー**です。|  
|**ログオン**|1.クリックして、**構成**を表示するボタン、**ログオン資格情報** ダイアログ ボックス。<br />2.**ログオン資格情報** ダイアログ ボックスは、指定したプロパティの次の値を入力します。<br />     **プロパティ**<br />     **ログオン**: この BizTalk Server ホストに関連付けられている Windows グループのメンバーであるユーザー アカウントの名前。<br />     **パスワード**: に指定されたユーザー アカウントのパスワード、**ログオン** テキスト ボックス。<br />3.をクリックして**OK**を閉じる、**ログオン資格情報** ダイアログ ボックス。|  
|**ホスト インスタンスの開始を無効にします。**|このボックスの取り消しがないことを確認します。|  
  
 ホスト インスタンスを作成した後、ホスト インスタンスを右クリックし、選択**開始**コンテキスト メニュー。  
  
 「受信」ホスト インスタンスを作成する「送信」ホスト インスタンスを作成するときに実行した手順を繰り返します。 BizTalk Server グループ内の各 BizTalk サーバーでを実行し、次のプロパティ値を持つ各ホスト インスタンスを構成する「受信」ホストのインスタンスを構成します。  
  
|プロパティ|値|  
|--------------|-----------|  
|ホスト名|選択**RxHost**横にドロップダウン リストからリスト**ホスト名**です。|  
|[サーバー]|実行するこのホスト インスタンス、ドロップ ダウン リストから次に、BizTalk Server を選択して**サーバー**です。|  
|ログオン|1.クリックして、**構成**を表示するボタン、**ログオン資格情報** ダイアログ ボックス。<br />2.**ログオン資格情報** ダイアログ ボックスは、指定したプロパティの次の値を入力します。<br />     **プロパティ**<br />     **ログオン**: この BizTalk Server ホストに関連付けられている Windows グループのメンバーであるユーザー アカウントの名前。<br />     **パスワード**: に指定されたユーザー アカウントのパスワード、**ログオン** テキスト ボックス。<br />3.をクリックして**OK**ログオン資格情報 ダイアログ ボックスを閉じます。|  
|[ホスト インスタンスの開始を無効にする]|このボックスの取り消しがないことを確認します。|  
  
 ホスト インスタンスを作成した後、ホスト インスタンスを右クリックし、選択**開始**コンテキスト メニュー。  
  
### <a name="create-a-biztalk-server-receive-port"></a>BizTalk Server を作成する受信ポート  
 トピックの手順に従って[受信ポートを作成する方法](http://go.microsoft.com/fwlink/?LinkID=154843)(http://go.microsoft.com/fwlink/?LinkID=154843) 一方向受信ポートを作成する BizTalk Server のドキュメントにします。 受信ポートを作成するときにそのままにすべてのプロパティ、以外の既定値次の表に記載されています。  
  
|プロパティ|値|  
|--------------|-----------|  
|General\Name|BTSLoadTestMessaging.OneWay.ReceivePort|  
|General\Port 型|一方向|  
|General\Authentication|認証なし|  
|失敗したメッセージをルーティング General\Enable|このボックスの取り消しがないことを確認します。|  
|General\Description|空白のままに|  
|[受信マップ]|なし|  
|Tracking|すべてのボックスの取り消しがないことを確認します。|  
|受信場所|をクリックして**新規**、これが表示されます、**受信場所のプロパティ** ダイアログ ボックスで、次のセクションに示すように構成する必要があります**BizTalk Server 受信場所の作成**.|  
  
### <a name="create-a-biztalk-server-receive-location"></a>BizTalk Server を作成する受信場所  
 **受信場所のプロパティ**BizTalk Server 受信ポートを作成するときにダイアログ ボックスが表示されたら、指定したプロパティの値を適用します。  
  
|プロパティ|値|  
|--------------|-----------|  
|名前 :|BTSLoadTest.Messaging.OneWay.WCF Customer.ReceiveLocation|  
|ハンドラーが表示されます。|RxHost|  
|[受信パイプライン]:|PassThruReceive|  
|説明:|空白のままに|  
|型:|選択**Wcf-custom**をクリックし、ドロップダウン リストから、**構成** ボタンが表示されます、 **Wcf-custom トランスポートのプロパティ**する必要があります ダイアログ ボックス次のセクションで説明したように構成**Wcf-custom 受信トランスポート構成**です。|  
  
### <a name="configure-the-wcf-custom-receive-transport"></a>Wcf-custom 受信トランスポートを構成します。  
 **Wcf-custom トランスポートのプロパティ**BizTalk Server 受信場所を作成するときにダイアログ ボックスが表示されたら、次の表で説明したとおり、既定値を除くすべてのプロパティのままにします。  
  
|プロパティ|値|  
|--------------|-----------|  
|General\Address (URI)|net.tcp://localhost: 8123/btsloadtest|  
|Binding\Binding 型|netTcpbinding|  
|Binding\NetTcpBindingElement\listenBacklog|400|  
|Binding\NetTcpBindingElement\maxConnections|400|  
|Binding\Security\NetTcpSecurityElement\mode|なし|  
|Behavior\ServiceBehavior\serviceThrottling\ServiceThrottlingElement**注:** serviceThrottling 動作を右クリックして ServiceBehavior の動作の一覧に追加する] をクリックして**拡張機能の追加**[ **serviceThrottling**クリックして動作拡張機能の一覧から**OK**です。|設定、 **ServiceThrottlingElement**プロパティを次の値。<br /><br /> -   **maxConcurrentCalls** 400<br />-   **maxConcurrentInstances** 400<br />-   **maxConcurrentSessions** 400|  
|Behavior\ServiceBehavior\serviceDebug\ServiceDebugElement**注:**を右クリックして ServiceBehavior の動作の一覧に、serviceDebug 動作を追加する をクリックして**拡張機能の追加**の選択**serviceDebug**クリックして動作拡張機能の一覧から**OK**です。|リストをそのまま**ServiceDebugElement**プロパティが、既定値 (空) を除き、次のプロパティが True の値を変更する必要があります。<br /><br /> -   **httpHelpPageEnabled**は True。<br />-   **httpsHelpPageEnabled**は True。<br />-   **includeExceptionDetailInFaults**は True。|  
  
 をクリックして**OK** Wcf-custom トランスポートのプロパティ ダイアログ ボックスを閉じ、をクリックする**OK**受信場所のプロパティ ダイアログ ボックスを閉じます。  
  
### <a name="create-a-biztalk-server-send-port"></a>BizTalk Server 送信ポートを作成します。  
 トピックの手順に従って[送信ポートを作成する方法](http://go.microsoft.com/fwlink/?LinkID=154845)(http://go.microsoft.com/fwlink/?LinkID=154845)、BizTalk Server のドキュメントを作成する、**静的な一方向**送信ポート。 送信ポートを作成するときにそのままにすべてのプロパティ、以外の既定値次の表に記載されています。  
  
|プロパティ|値|  
|--------------|-----------|  
|General\Name|BTSLoadTest.Messaging.Send.WCF カスタム|  
|General\Send ハンドラー|TxHost|  
|General\Send パイプライン|PassThruTransmit|  
|Filters\Name|BTS.ReceivePortName|  
|Filters\Operator|==|  
|Filters\Value|BTSLoadTest.Messaging.OneWay.ReceivePort|  
|によって Filters\Group|および**注:**としてフィルターを表示するかを適切な値は、これらのプロパティが構成されている場合、 `BTS.ReceivePortName == BTSLoadTest.Messaging.OneWay.ReceivePort` b の送信ポートのプロパティ ダイアログの フィルタ ページの下部に表示されます。ox です。 このフィルターを適用すると、結果として、この送信ポートは BTSLoadTest.Messaging.OneWay.ReceivePort をという名前の受信ポートを使用して BizTalk Server での受信メッセージをサブスクライブします。|  
|Tracking|すべてのボックスの取り消しがないことを確認します。|  
|General\Type|選択**Wcf-custom**をクリックし、ドロップダウン リストから、**構成** ボタンが表示されます、 **Wcf-custom トランスポートのプロパティ**する必要があります ダイアログ ボックス次のセクションで説明したように構成**Wcf-custom 送信トランスポート構成**です。|  
  
### <a name="configure-the-wcf-custom-send-transport"></a>Wcf-custom 送信トランスポートを構成します。  
 **Wcf-custom トランスポートのプロパティ**BizTalk Server 送信ポートを作成するときにダイアログ ボックスが表示されたら、次の表で説明したとおり、既定値を除くすべてのプロパティのままにします。  
  
|プロパティ|値|  
|--------------|-----------|  
|General\Address (URI)|net.tcp://*\<コンピューター名\>*: 2001/TCP1**重要:***\<コンピューター名\>*プレース ホルダーIndigoService.exe をホストするために使用する実際のコンピューター名、するには WCF を介して送信されるメッセージを使用する設計されています。   IndigoService.exe には、ごくわずかなリソースが必要であるために、それで何 IndigoService.exe を BizTalk Server グループのデータベースに使用する SQL Server コンピューターで実行するは多くの場合です。 使用される BizTalk ベンチマーク ウィザードの一部である IndigoService.exe [BizTalk ベンチマーク ウィザード](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)。|  
|Binding\Binding 型|**customBinding**|  
  
 WCF カスタム バインドの種類のほとんどの場合と同様、 **customBinding**次の値に設定する必要がありますが、いくつかのプロパティを公開するバインドの種類。  
  
1.  下にある、**バインド**セクションがある、 **CustomBindingElement**プロパティが関連付け**構成**セクションです。 [構成] セクションで、すべての値のままにして、 **CustomBindingElement**プロパティが既定値です。  
  
2.  **CustomBindingElement**を右クリックして**textMessageEncoding**選択**拡張機能 (Del) を削除**です。 同様を右クリックして**httpTransport**選択**拡張機能 (Del) を削除**です。  
  
3.  今すぐを右クリックして**CustomBindingElement**選択**Ins 拡張機能を追加**を表示する、**バインド要素拡張機能の選択** ダイアログ ボックス。  
  
4.  選択**binaryMessageEncoding**  をクリック**OK**を追加する、 **binaryMessageEncoding**要素の拡張。 表示するには、手順を繰り返して、**バインド要素拡張機能の選択** ダイアログ ボックスとスクロール ダウン、利用可能な要素の拡張機能の一覧が表示されるまで、 **tcpTransport**要素拡張を選択**tcpTransport**  をクリック**OK**です。  
  
5.  **CustomBindingElement**選択、 **tcpTransport**要素の構成セクションで**tcpTransport**、すべてのプロパティとして以外の既定値のままにして次の表で説明します。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |connectionBufferSize|2097152|  
    |maxBufferSize|2097152|  
    |maxPendingAccepts|400|  
    |maxPendingConnections|400|  
    |listenBacklog|400|  
    |maxBufferPoolSize|2097152|  
    |maxReceivedMessageSize|2097152|  
  
6.  下にある、 **tcpTransport**要素の選択、 **ConnectionPoolSettings**要素と既定ですべてのプロパティの値を除くのままにして、 **maxOutboundConnectionsPerEndpoint**プロパティで、400 の値に変更する必要があります。  
  
7.  をクリックして**ok** Wcf-custom トランスポートのプロパティ ダイアログ ボックスを閉じるをクリックして**OK** BTSLoadTest.Messaging.Send.WCF Custom – 送信ポートのプロパティ ダイアログ ボックスを閉じます。  
  
### <a name="configure-a-computer-to-consume-messages-sent-by-the-biztalk-server-send-port"></a>BizTalk Server 送信ポートによって送信されるメッセージを使用するコンピューターを構成します。  
 前述のように、WCF を介して送信されるメッセージを使用する、IndigoService.exe は設計されています。 使用される BizTalk ベンチマーク ウィザードの一部である IndigoService.exe [BizTalk ベンチマーク ウィザード](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)。 設定し、この例の目的の IndigoService.exe を実行する最も簡単な方法から BizTalk ベンチマーク ウィザード zip ファイルをダウンロードする、 [BizTalk ベンチマーク ウィザード ダウンロード ページ](http://go.microsoft.com/fwlink/?LinkID=209100)(http://go.microsoft.com/fwlink/?LinkID = 209100) および IndigoService.exe を実行するには、コンピューター上に次の 4 つのファイルを抽出します。  
  
1.  \IndigoService\bin\Release\IndigoService.exe  
  
2.  \IndigoService\bin\Release\IndigoService.exe.config  
  
3.  \IndigoService\bin\Release\Response.xml  
  
4.  \IndigoService\bin\Release\StartIndigoService.bat  
  
 その後、StartIndigoService.bat をダブルクリックして IndigoService.exe を起動します。 IndigoService.exe は、IndigoService.exe.config ファイルで指定されたエンドポイントに送信されたメッセージを消費します。  
  
 \<エンドポイント アドレス ="net.tcp://localhost: 2001/TCP1"バインド"netTcpBinding"bindingConfiguration を = =「"binding1 という」名前 ="endpoint1"contract="IndigoService.IServiceTwoWaysVoidNonTransactional"/\>  
  
 これは、送信ポート アドレスが構成で、アドレス (URI) net.tcp:// の理由*\<コンピューター名\>*: 2001/TCP1  
  
 IndigoService.exe には、ごくわずかなリソースが必要であるために、それで何 IndigoService.exe を BizTalk Server データベース用の SQL Server コンピューターで実行するは多くの場合です。  
  
### <a name="disable-tracking-and-throttling-for-the-biztalk-server-group"></a>追跡および BizTalk Server グループの調整を無効にします。  
 システムでは、両方のメッセージの絶対最大スループットを判断するための追跡と調整する必要があります無効にするロード テストを開始する前にします。 これを行う次の手順に従って、BizTalk Server 管理コンソールを使用します。  
  
1.  BizTalk Server 管理コンソールを起動します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**BizTalk Server 2010**  をクリックし、 **BizTalk Server 管理コンソール**です。  
  
2.  **BizTalk Server 管理コンソール**、記載されている場合、BizTalk グループを選択するかが表示されない場合を右クリックし**BizTalk Server 管理コンソール**[**既存のグループへの接続**、横に、BizTalk グループの BizTalk Server 管理データベースを格納する SQL Server の名前を入力**SQL Server 名:**の横にあるBizTalkグループの管理データベース名の名前を入力**データベース名:** ] をクリックし、 **OK**です。  
  
3.  BizTalk グループ] ノードを右クリックし [**設定**を表示する、 **BizTalk 設定ダッシュ ボード**です。  
  
4.  クリックして選択**ホスト**BizTalk 設定ダッシュ ボードの左側のウィンドウでします。  
  
5.  横にドロップダウン リストをクリックして**ホスト**パフォーマンス テスト中に使用されるホストのいずれかを選択します。  
  
6.  次の表に示すように既定値以外のプロパティのままにします。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**追跡データを DTA DB、General\Move**|オンの場合は、このボックスをオフにします。|  
    |**General\32 ビットのみ**|オンの場合は、このボックスをオフにします。|  
    |**General\Polling Intervals\Messaging**|20000000 の値に設定します。|  
    |**General\Polling Intervals\Orchestrations**|20000000 の値に設定します。|  
    |**リソースに基づく Throttling\In プロセス メッセージ**|10000 の値に設定します。|  
    |**リソースに基づく Throttling\Internal メッセージ キューのサイズ**|10000 の値に設定します。|  
    |**DB でのリソースに基づく Throttling\Message 数**|値を 0 に設定します。|  
    |**リソースに基づく Throttling\Memory Usage\Process の仮想**|値を 0 に設定します。|  
    |**割合に基づく Throttling\Publishing\Throttling の上書き**|設定すると、制限しません。|  
    |**割合に基づく Throttling\Delivery\Throttling の上書き**|設定すると、制限しません。|  
  
7.  パフォーマンス テストの実行中に使用されるすべてのホストについて、手順 6. で説明されているプロセスを繰り返します。  
  
8.  クリックして選択**ホスト インスタンス**BizTalk 設定ダッシュ ボードの左側のウィンドウでします。  
  
9. 横にドロップダウン リストをクリックして**ホスト インスタンス:**パフォーマンス テストに使用するホスト インスタンスのいずれかを選択します。  
  
10. プロパティの値のままにして、既定の設定の変更を除く、 **.NET CLR 最大ワーカー スレッド**の値に**100**を変更して、 **.NET CLR 最小ワーカー スレッド**に、値**25**です。  
  
11. パフォーマンス テストの実行中に使用されるすべてのホスト インスタンスに対して手順 10 での手順を繰り返します。  
  
 追跡と調整を無効にする場合でもは任意の方法ではなく表してな運用シナリオでどのように処理するため、これらの操作はそれらについては、true 最大持続可能なを無効にすると良いパフォーマンスの観点からコストが高くBizTalk Server 環境のスループット (MST)。 これにより、テスト担当者がはっきりと調整を任意のパフォーマンスの影響は、環境に適用されています。 確かに引数は、追跡する必要がありますを無効にできません的に把握している場合、最初から、BizTalk Server アプリケーションで追跡を必要とする必要がありますを有効に追跡ことに行われる可能性があります。 **パフォーマンス テストのための制限が無効に努力が行われる**です。 調整は、実稼働環境での負荷が高すぎるため「経由でフォール」から BizTalk Server を回避するために役立ちます。 ただし、たくない調整のパフォーマンスとパフォーマンスの観点からコストが高いため、ロード テスト中に開始を制限する場合、時間がある、非常に困難にパフォーマンスのレベルを決定するためのテスト中に有効になっている、BizTalk Server アプリケーションを実際に実現できます。 次のトピックでは、MST を超える、BizTalk Server 環境をプッシュし、その後に実際の MST の持続ロード テストを実行するステップ ロード テストを実行する方法について説明します。 調整が有効になっている場合には MST とはどのような true をさらに検出できなかったように、MST を超える BizTalk 環境をプッシュすることがほぼ不可能。