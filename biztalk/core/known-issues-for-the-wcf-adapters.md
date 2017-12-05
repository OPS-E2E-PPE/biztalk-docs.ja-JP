---
title: "WCF アダプタに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 423c6021-5fb7-48c9-9319-11e7a18c775c
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c296dfb2ca1f05a2f403aa31a73b67934fb23a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-for-the-wcf-adapters"></a>WCF アダプタに関する既知の問題
このトピックでは、BizTalk Server に含まれる WCF アダプターに関する既知の問題について説明します。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-receive-adapters"></a>受信 SOAP マーシャリング プロセスでエラーとなったメッセージが WCF 受信アダプターで中断されない  
 メッセージが WCF 受信アダプターに到着すると、WCF アダプターは受信 SOAP メッセージから BizTalk メッセージを作成し、この BizTalk メッセージをエンドポイント マネージャーによって管理されるトランスポート プロキシに渡します。 BizTalk メッセージの作成中にアダプターが SOAP エンベロープと本文の読み取りに失敗した場合でも、アダプターは非キャッシュで順方向専用の高速リーダーを使用して SOAP メッセージにアクセスするので、メッセージは中断されません。  
  
 失敗したメッセージのイベント ログを確認してください。 たとえばのボディ パス式を使用することができます、**メッセージ** タブで、WCF アダプターを介して受信 SOAP メッセージから受信 BizTalk メッセージ本文を作成する方法を指定する WCF アダプター トランスポートのプロパティ ダイアログ ボックス。 受信 SOAP メッセージに無効なボディ パス式が入力された場合、**メッセージ** タブで、アダプターは BizTalk メッセージの作成に失敗し、受信メッセージを中断できません。 ボディ パス式を使用する方法について、**メッセージ** タブを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。  
  
 次の図に示しています、**メッセージ** タブの受信 SOAP メッセージから受信 BizTalk メッセージを作成する方法を指定することができます。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-send-adapters"></a>受信 SOAP マーシャリング プロセスでエラーとなったメッセージが WCF 送信アダプターで中断されない  
 送信請求 - 応答の WCF 送信ポートは、WCF メッセージを応答メッセージとして受信できます。 メッセージが WCF 送信アダプターに到着すると、WCF アダプターは受信 SOAP メッセージから BizTalk メッセージを作成し、この BizTalk メッセージをエンドポイント マネージャーによって管理されるトランスポート プロキシに渡します。 BizTalk メッセージの作成中にアダプターが SOAP エンベロープと本文の読み取りに失敗した場合でも、アダプターは非キャッシュで順方向専用の高速リーダーを使用して SOAP メッセージにアクセスするので、メッセージは中断されません。  
  
 失敗したメッセージのイベント ログを確認してください。 たとえばの XPath 式を使用することができます、**メッセージ** タブで、WCF アダプターを介して受信 SOAP メッセージから受信 BizTalk メッセージ本文を作成する方法を指定する WCF アダプター トランスポートのプロパティ ダイアログ ボックス。 受信 SOAP メッセージの無効な XPath 式が入力された場合、**メッセージ** タブで、アダプターは BizTalk メッセージの作成に失敗し、受信メッセージを中断できません。 XPath 式を使用する方法について、**メッセージ** タブを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。  
  
 次の図に示しています、**メッセージ**例として、Wcf-netnamedpipe 送信アダプターのタブです。  
  
 ![[メッセージ] タブ、WCF 送信アダプタ](../core/media/54623ccf-49a9-4b6a-9487-da0d94bab64d.gif "54623ccf-49a9-4b6a-9487-da0d94bab64d")  
  
## <a name="messages-can-be-lost-when-using-onewaybindingelement-in-a-two-way-transport-with-custom-binding-in-non-transactional-wcf-receive-locations"></a>トランザクションではない WCF 受信場所においてカスタム バインドされた双方向トランスポートで OneWayBindingElement を使用すると、メッセージが失われることがある  
 双方向通信では、WCF アダプターは、メッセージ ボックス データベースにメッセージが保存されるまで応答を返します。 ただしを使用して**OneWayBindingElement** WCF アダプターに受信したメッセージをディスパッチする直前にダミーの応答が生成されます。 そのため、使用してカスタム バインドを構成する場合、 **OneWayBindingElement**非トランザクションで双方向トランスポートのチャネル スタック内の 受信場所、WCF アダプターは、処理、受信したため、メッセージが失われることができます一方向のメッセージです。  
  
## <a name="default-values-of-the-readerquotas-attributes-in-the-wcf-custom-and-wcf-customisolated-transport-properties-dialog-boxes-are-used-when-constructing-the-bindings"></a>WCF-Custom および WCF-CustomIsolated トランスポート プロパティのダイアログ ボックスにある ReaderQuotas 属性の既定値が、バインドを構築するときに使用される  
 Wcf-custom および Wcf-customisolated トランスポートのプロパティ ダイアログ ボックス、 **ReaderQuotas**属性値が 0 と表示されます。 ただし、バインドを構築するときには、次の値が使用されます。  
  
|属性|Description|値|  
|---------------|-----------------|-----------|  
|maxArrayLength|許容される配列の長さの最大値を指定する正の整数。|16384|  
|maxBytesPerRead|読み取りごとに返される最大許容サイズ (バイト単位) を指定する正の整数。|4096|  
|maxDepth|読み取りごとにネストされるノードの深さの最大値を指定する正の整数。|32|  
|maxNameTableCharCount|テーブル名に使用できる最大文字数を指定する正の整数。|16384|  
|maxStringContentLength|XML 要素のコンテンツに使用できる最大文字数を指定する正の整数。|8192|  
  
## <a name="the-wcf-receive-locations-may-be-disabled-if-you-change-the-wcf-adapter-type-and-keep-the-same-address"></a>WCF アダプターの種類を変更し、同じアドレスを維持すると、WCF 受信場所が無効になる場合がある  
 アダプターの種類を変更する場合: たとえば、WCF アダプターの種類を Wcf-nettcp から NetTcp バインドされた Wcf-custom に変更 — と同じアドレスを保持する、キャッシュの問題により、エンドポイント マネージャーで、受信場所を無効にすることがあります。 この問題を回避するには、次のいずれかを実行します。  
  
-   BTSNTSvc サービスを再起動します。  
  
-   URI を別のアドレスに変更し、保存してから、元のアドレスに戻して、再度保存します。  
  
## <a name="the-wcf-action-set-in-the-orchestration-does-not-override-the-action-setting-in-the-static-send-port"></a>オーケストレーションの WCF アクション設定が静的送信ポートのアクション設定を上書きしない  
 設定した場合、 **WCF です。アクション**オーケストレーションのコンテキスト プロパティのままにする必要があります、**アクション**WCF アダプター トランスポートのプロパティ ダイアログ ボックスでフィールドを空白。 また、静的送信ポートでアクションを指定した場合、 **WCF です。アクション**オーケストレーションで設定したコンテキスト プロパティは、静的送信ポートで設定した値によって上書きされます。  
  
## <a name="propagating-a-fault-message-is-not-supported-in-the-transactional-send"></a>エラー メッセージの伝達がトランザクション送信でサポートされない  
 **エラー メッセージを伝達**送信請求-応答送信ポートのオプションでは、サブスクライブしているアプリケーションへの送信処理に失敗したメッセージをルーティングすることができます。 ただし場合、**トランザクションを有効にする** チェック ボックスがトランスポートのプロパティ ダイアログ ボックスも選択されていると、トランザクションは中止またはできなくなる場合、エラー応答がアダプターに到着すると、することはできませんに反映されるまで、任意のサブスクライブしているアプリケーションへのエラー メッセージ  
  
## <a name="the-msmq-cluster-resource-group-needs-to-be-restarted-before-restarting-the-biztalk-host-cluster-resource-group-during-the-cluster-failover"></a>クラスターのフェールオーバー時に、BizTalk ホストのクラスター リソース グループを再起動する前に MSMQ クラスター リソース グループを再起動する必要がある  
 フェールオーバー クラスターのシナリオでは、フェールオーバーが発生したとき、BizTalk ホストのクラスター リソース グループを再起動する前に MSMQ クラスター リソース グループを再起動する必要があります。 この操作を行わないと、MSMQ 受信場所が無効になる場合があります。 この問題を回避するには、BizTalk ホストのクラスター リソース グループが MSMQ クラスター リソース グループに従属するように設定して、BizTalk ホストのクラスター リソース グループより MSMQ クラスター リソース グループが先に起動するように指定できます。 または、BizTalk ホストのクラスター リソース グループを再起動して、この問題を回避することもできます。  
  
## <a name="you-receive-an-error-when-sending-messages-to-a-wcf-service-that-uses-wsfederationhttpbinding-in-the-endpoint"></a>エンドポイントで wsFederationHttpBinding を使用する WCF サービスにメッセージを送信すると、エラーが表示される  
 次のようなエラーが表示されます。  
  
```  
The adapter failed to transmit message going to send port "MySendPort" with URL "http://localohost/MywsFedHttp". It will be retransmitted after the retry interval specified for this Send Port. Details:"The channel is configured to use interactive initializer 'System.ServiceModel.Security.InfocardInteractiveChannelInitializer', but the channel was Opened without calling DisplayInitializationUI.  Call DisplayInitializationUI before calling Open or other methods on this channel.".  
```  
  
 この動作は仕様による結果です。 WCF アダプタを使用している WCF サービスにメッセージを送信できません**wsFederationHttpBinding**エンドポイントにします。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-enable-you-to-select-message-types-or-port-types-from-the-wsdl"></a>BizTalk WCF サービス使用ウィザードで、WSDL からメッセージの種類またはポートの種類を選択できない  
 BizTalk WCF サービス使用ウィザードでは、WCF サービスをインポートするときに、WSDL からメッセージの種類またはポートの種類を選択できません。 この制限を回避するには、次のコードを使用してスキーマを取得し、必要なスキーマを BizTalk プロジェクトに追加します。  
  
```  
svcutil.exe /t:metadata http://service/metadataendpoint  
```  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-the-combination-of-one-way-and-request-response-operations"></a>BizTalk WCF サービス使用ウィザードで、一方向の操作と要求 - 応答操作の組み合わせを実行できない  
 BizTalk WCF サービス使用ウィザードでは、一方向の操作と要求 - 応答操作の組み合わせを持つポートの種類をインポートできません。 この問題を回避するには、ServiceModel メタデータ ユーティリティ ツールを使用して、ポートの種類を生成します。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-you-to-set-certificate-credentials-when-retrieving-the-wsdl"></a>BizTalk WCF サービス使用ウィザードで、WSDL を取得するときに証明書の資格情報を設定できない  
 BizTalk WCF サービス使用ウィザードでは、WSDL を取得するときに証明書の資格情報を設定することはできません。 この問題を回避するには、は、ServiceModel メタデータ ユーティリティ ツールを使用するには、WSDL の生成にして、証明書資格情報で使用する WCF サービスからの XSD ファイルは、svcutil.exe.config ファイルで設定し、し、BizTalk WCF サービスにインポート選択してウィザードを使用**メタデータ ファイル (WSDL と XSD)**オプション、**メタデータ ソース**ページ。  
  
## <a name="wcf-adapters-do-not-support-one-way-operations"></a>WCF アダプターが一方向の操作をサポートしない  
 次のようなエラー メッセージ (Wcf-netmsmq 受信アダプター) 以外の WCF アダプタによって公開された WCF サービスの使用時に表示、 **IsOneWay**プロパティに設定されている**true**クライアント側でします。 これは、ため、 **System.ServiceModel.OperationContractAttribute.IsOneWay** (Wcf-netmsmq によって公開されたサービスの受信アダプターを除く)、WCF アダプタによって公開された WCF サービスのプロパティが**false**一方向の受信場所に対してもします。  
  
```  
The channel received an unexpected input message while closing. Your Channel.Close() calls are not synchronized.  
```  
  
 指定された WCF サービスを使用するときに、次のようなエラー メッセージが表示されます、 **IsOneWay**プロパティに設定**true**です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から送信したメッセージは中断され、再開することができます。  
  
```  
The request operation at net.tcp://localhost:8088/MyService/tcp did not receive a reply within timeout 00:01:00.  
```  
  
## <a name="a-memory-leak-may-occur-when-sending-messages-to-non-transactional-msmq-queues-using-wcf-netmsmq-binding"></a>WCF-NetMsmq バインドを使用して、トランザクションではない MSMQ キューにメッセージを送信すると、メモリ リークが発生する場合がある  
 WCF-NetMsmq バインドを使用して、トランザクションではない MSMQ キューにメッセージを送信すると、BizTalk NT サービスでメモリ リークが発生する場合があります。 これは、WCF-NetMsmq トランスポートを使用してトランザクションではない MSMQ キューにメッセージを送信する場合、または WCF-Custom トランスポートで netMsmqBinding を使用してトランザクションではない MSMQ キューにメッセージを送信する場合に発生します。  
  
 問題を解決するのには、サポート技術情報の記事 936512 で説明されている .NET Framework 3.0 修正プログラムをインストールする必要があります[http://go.microsoft.com/fwlink/?LinkId=92962](http://go.microsoft.com/fwlink/?LinkId=92962)です。 この修正プログラムをインストールした後にシステムを再起動する必要はありませんが、WCF-NetMsmq バインドを使用する送信ポートをホストする BizTalk NT サービスは再起動する必要があります。  
  
## <a name="you-may-receive-exception-when-communicating-with-apache-web-servers-using-wcf-basichttp-adapter"></a>WCF-BasicHttp アダプターを使用して Apache Web サーバーと通信すると、例外が発生する場合がある  
 トランスポート セキュリティを備える WCF-BasicHttp アダプターを使用して Apache Web サーバーと通信すると、次のような例外が発生する場合があります。  
  
```  
System.Net.WebException: The underlying connection was closed: An unexpected error occurred on a send.  
System.IO.IOException: Unable to write data to the transport connection: An established connection was aborted by the software in your host machine. System.Net.Sockets.SocketException: An established connection was aborted by the software in your host machine  
```  
  
 この問題を回避するには、次の手順に従って、WCF-BasicHttp アダプターではなく WCF-Custom アダプターを使用して Apache Web サーバーと通信する必要があります。  
  
1.  送信ポートを作成し、トランスポートの種類を設定**Wcf-custom**です。  
  
2.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで  **customBinding**から、**バインディングの種類**ドロップダウン リスト。  
  
3.  **CustomeBindingElement**を右クリックして**httpTransport**、クリックして**拡張機能を削除**です。  
  
4.  右クリック**CustomeBindingElement**、クリックして**拡張機能を追加**です。  
  
5.  **バインド要素拡張機能の選択**ダイアログ ボックスで、 **httpTransport**  をクリックし、 **OK**です。  
  
6.  をクリックして**httpTransport**、し、**構成**の値の設定 ウィンドウで、 **keepAliveEnabled**に**False**です。  
  
7.  をクリックして**textMessageEncoding**、し、**構成**の値の設定 ウィンドウで、 **messageVersion**に`Soap11WSAddressing10`です。  
  
8.  必要に応じて、追加のプロパティを構成する必要があります。  
  
## <a name="biztalk-server-does-not-work-with-wcf-clients-that-using-clientviabehavior-for-multiple-hop-conversations"></a>複数ホップの交換に ClientViaBehavior を使用する WCF クライアントで BizTalk Server が動作しない  
 WCF クライアントでは、隣接するネットワーク宛先でメッセージを処理して複数ホップの交換を可能にする場合、呼び出し元のアプリケーションが最終的な宛先を認識する必要がないときには ClientViaBehavior を使用します。 ClientViaBehavior を指定し、To アドレスを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が仲介として機能するリモート サービスに設定すると、次のようなエラー メッセージが表示されます。  
  
```  
The message with To 'net.tcp://localhost:5555/test.svc' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher. Check that the sender and receiver's EndpointAddresses agree  
```