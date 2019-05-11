---
title: WCF アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 423c6021-5fb7-48c9-9319-11e7a18c775c
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05951b5bfd2f586cdaf88bc11bdf12f505ef15b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330724"
---
# <a name="known-issues-for-the-wcf-adapters"></a>WCF アダプターに関する既知の問題
このトピックでは、BizTalk Server に含まれている WCF アダプターに関する既知の問題について説明します。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-receive-adapters"></a>受信 SOAP マーシャ リングの処理に失敗するが、WCF では中断されていないメッセージの受信アダプター  
 WCF にメッセージが到着すると、受信アダプター、WCF アダプターは受信 SOAP メッセージから BizTalk メッセージを作成および BizTalk メッセージをエンドポイント マネージャーによって管理されるトランスポート プロキシに渡します。 アダプターは、BizTalk メッセージを作成するときに、SOAP エンベロープと本文の読み取りに失敗した場合、アダプターでは、高速、非キャッシュ、前方参照専用のリーダーを使用して、SOAP メッセージにアクセスするため、メッセージは中断されません。  
  
 失敗したメッセージのイベント ログを確認する必要があります。 本文のパス式を使用するなど、**メッセージ**WCF アダプターを介して受信 SOAP メッセージから受信 BizTalk メッセージ本文を作成する方法を指定する WCF アダプター トランスポートのプロパティ ダイアログ ボックスのタブ。 上の受信 SOAP メッセージの無効なボディ パス式が指定されると、**メッセージ**] タブの [アダプターの BizTalk メッセージの作成に失敗し、受信メッセージを中断できません。 ボディ パス式を使用する方法について、**メッセージ** タブを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。  
  
 次に示します、**メッセージ** タブの受信 SOAP メッセージから受信 BizTalk メッセージを作成する方法を指定できます。  
  
## <a name="a-message-that-fails-in-the-inbound-soap-marshaling-processing-is-not-suspended-in-wcf-send-adapters"></a>WCF 送信アダプタの受信 SOAP マーシャ リング プロセスで失敗したメッセージが中断されていません。  
 送信請求-応答 WCF 送信ポートは、応答メッセージとして、WCF メッセージを受信できます。 メッセージが到着すると、WCF 送信アダプターは、WCF アダプターは受信 SOAP メッセージから BizTalk メッセージを作成および BizTalk メッセージをエンドポイント マネージャーによって管理されるトランスポート プロキシに渡します。 アダプターは、BizTalk メッセージを作成するときに、SOAP エンベロープと本文の読み取りに失敗した場合、アダプターでは、高速、非キャッシュ、前方参照専用のリーダーを使用して、SOAP メッセージにアクセスするため、メッセージは中断されません。  
  
 失敗したメッセージのイベント ログを確認する必要があります。 XPath 式を使用するなど、**メッセージ**WCF アダプターを介して受信 SOAP メッセージから受信 BizTalk メッセージ本文を作成する方法を指定する WCF アダプター トランスポートのプロパティ ダイアログ ボックスのタブ。 受信 SOAP メッセージの無効な XPath 式が入力された場合、**メッセージ**] タブの [アダプターの BizTalk メッセージの作成に失敗し、受信メッセージを中断できません。 XPath 式を使用する方法について、**メッセージ** タブを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。  
  
 次に示します、**メッセージ**例として、Wcf-netnamedpipe 送信アダプターのタブ。  
  
 ![[メッセージ] タブの wcf 送信アダプタ](../core/media/54623ccf-49a9-4b6a-9487-da0d94bab64d.gif "54623ccf-49a9-4b6a-9487-da0d94bab64d")  
  
## <a name="messages-can-be-lost-when-using-onewaybindingelement-in-a-two-way-transport-with-custom-binding-in-non-transactional-wcf-receive-locations"></a>ときにメッセージが失われる可能性が非トランザクションの WCF でのカスタム バインドの双方向トランスポートで OneWayBindingElement を使用して受信場所  
 双方向の通信で、メッセージがメッセージ ボックス データベースに保存されるまで、WCF アダプターは応答を送信します。 ただしを使用して**OneWayBindingElement** WCF アダプターに受信したメッセージをディスパッチする直前にダミーの応答が生成されます。 そのため、使用して、カスタム バインドを構成する場合、 **OneWayBindingElement**双方向トランスポートで非トランザクションのチャネル スタックの受信場所、WCF アダプターは、処理、受信したため、メッセージが失われることができます一方向のメッセージ。  
  
## <a name="default-values-of-the-readerquotas-attributes-in-the-wcf-custom-and-wcf-customisolated-transport-properties-dialog-boxes-are-used-when-constructing-the-bindings"></a>既定では、Wcf-custom および Wcf-customisolated トランスポート プロパティ ダイアログ ボックスを使用して、バインドを作成するときにある ReaderQuotas 属性の値  
 Wcf-custom および Wcf-customisolated トランスポートのプロパティ ダイアログ ボックス、 **ReaderQuotas**属性値が 0 と表示されます。 ただし、バインドを作成するときに、次の値が使用されます。  
  
|属性|説明|値|  
|---------------|-----------------|-----------|  
|maxArrayLength|許容される最大配列長を指定する正の整数。|16384|  
|MaxBytesPerRead|読み取りあたり最大バイト数を指定する正の整数が返されます。|4096|  
|maxDepth|読み取りあたりの最大ネスト ノード深度を指定する正の整数。|32|  
|MaxNameTableCharCount|テーブル名の最大文字数を指定する正の整数。|16384|  
|maxStringContentLength|XML 要素のコンテンツで許可される最大文字数を指定する正の整数。|8192|  
  
## <a name="the-wcf-receive-locations-may-be-disabled-if-you-change-the-wcf-adapter-type-and-keep-the-same-address"></a>WCF 受信場所、WCF アダプターの種類を変更し、同じアドレスを維持した場合、無効にすることがあります  
 アダプターの種類を変更する場合: たとえば、WCF アダプターの種類を Wcf-nettcp から NetTcp バインドされた Wcf-custom に変更 — と同じアドレスを維持、エンドポイント マネージャーでのキャッシュの問題により、受信場所を無効にすることがあります。 この問題を回避するには、次のいずれかの操作を行います。  
  
-   BTSNTSvc サービスを再起動します。  
  
-   別のアドレスに URI を変更し、保存し、URI を元のアドレスに変更し、もう一度保存します。  
  
## <a name="the-wcf-action-set-in-the-orchestration-does-not-override-the-action-setting-in-the-static-send-port"></a>オーケストレーションで設定された WCF アクションでは、静的な送信ポートでアクションの設定は上書きされません。  
 設定した場合、 **WCF です。アクション**オーケストレーションのコンテキスト プロパティのままにする必要があります、**アクション**WCF アダプター トランスポートのプロパティ ダイアログ ボックスでフィールドを空白。 また、静的送信ポートでアクションを指定した場合、 **WCF です。アクション**オーケストレーションで設定したコンテキスト プロパティは、静的送信ポートで設定した値によって上書きされます。  
  
## <a name="propagating-a-fault-message-is-not-supported-in-the-transactional-send"></a>トランザクション送信でエラー メッセージの伝達はサポートされていません  
 **エラー メッセージを伝達**送信請求-応答の送信ポートのオプションでは、サブスクライブするアプリケーションの送信処理に失敗したメッセージをルーティングできます。 ただし場合、**トランザクションを有効にする** チェック ボックスがトランスポートのプロパティ ダイアログ ボックスも選択されていると、トランザクションは中止できる場合もできなくなる場合、エラー応答がアダプターに到着するはしないに反映されるまで、サブスクライブしているアプリケーションへのエラー メッセージ  
  
## <a name="the-msmq-cluster-resource-group-needs-to-be-restarted-before-restarting-the-biztalk-host-cluster-resource-group-during-the-cluster-failover"></a>MSMQ クラスター リソース グループがクラスター フェールオーバー中に、BizTalk ホストのクラスター リソース グループを再起動する前に再起動する必要があります。  
 フェールオーバー クラスターのシナリオで、フェールオーバーが行われて、MSMQ クラスター リソース グループは、BizTalk ホストのクラスター リソース グループを再起動する前に再起動しなければ。 そのため、MSMQ の受信に失敗した場所が無効になっている可能性があります。 この問題を回避するには、行うことができます、BizTalk ホストのクラスター リソース グループの BizTalk ホストのクラスター リソース グループの前に MSMQ クラスター リソース グループが開始されることを確認するには、MSMQ クラスター リソース グループに依存します。 また、この問題を回避するには、BizTalk ホスト クラスター リソース グループを再起動することができます。  
  
## <a name="you-receive-an-error-when-sending-messages-to-a-wcf-service-that-uses-wsfederationhttpbinding-in-the-endpoint"></a>エンドポイントで wsFederationHttpBinding を使用する WCF サービスにメッセージを送信するときにエラーが表示されます。  
 次のようなエラーが表示されます。  
  
```  
The adapter failed to transmit message going to send port "MySendPort" with URL "http://localohost/MywsFedHttp". It will be retransmitted after the retry interval specified for this Send Port. Details:"The channel is configured to use interactive initializer 'System.ServiceModel.Security.InfocardInteractiveChannelInitializer', but the channel was Opened without calling DisplayInitializationUI.  Call DisplayInitializationUI before calling Open or other methods on this channel.".  
```  
  
 この動作は仕様による結果です。 WCF アダプタを使用している WCF サービスにメッセージを送信できません**wsFederationHttpBinding**でそれらのエンドポイント。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-enable-you-to-select-message-types-or-port-types-from-the-wsdl"></a>BizTalk WCF サービス使用ウィザードで使用すると、WSDL からメッセージの種類またはポートの種類を選択できません。  
 BizTalk WCF サービス使用ウィザードでは、WCF サービスをインポートするときに、WSDL からメッセージの種類またはポートの種類を選択できません。 この制限を回避するには、スキーマを取得し、BizTalk プロジェクトに必要なスキーマを追加し、次のコードを使用できます。  
  
```  
svcutil.exe /t:metadata http://service/metadataendpoint  
```  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-the-combination-of-one-way-and-request-response-operations"></a>BizTalk WCF サービス使用ウィザードが一方向の組み合わせを許可しないと要求-応答操作  
 BizTalk WCF サービス使用ウィザードが一方向の組み合わせを持つポートの種類のインポートを許可していないと要求-応答操作。 この問題を回避するのにには、ポートの種類を生成するのに、ServiceModel メタデータ ユーティリティ ツールを使用することができます。  
  
## <a name="the-biztalk-wcf-service-consuming-wizard-does-not-allow-you-to-set-certificate-credentials-when-retrieving-the-wsdl"></a>BizTalk WCF サービス使用ウィザードにより、WSDL を取得するときに、証明書資格情報を設定します。  
 BizTalk WCF サービス使用ウィザードでは、WSDL を取得するときに、証明書資格情報を設定できません。 この問題を回避するには、は、ServiceModel メタデータ ユーティリティ ツールを使用するには、WSDL を生成して証明書資格情報を使用する WCF サービスからの XSD ファイルは、svcutil.exe.config ファイルで設定し、BizTalk WCF サービスにインポート使用を選択してウィザード**メタデータ ファイル (WSDL と XSD)** オプション、**メタデータ ソース**ページ。  
  
## <a name="wcf-adapters-do-not-support-one-way-operations"></a>WCF アダプターでは、一方向の操作をサポートしていません  
 場合は、次のようなエラー メッセージ (Wcf-netmsmq 受信アダプター) 以外の WCF アダプターによって公開された WCF サービスの使用時に受信するが、 **IsOneWay**プロパティに設定されて**true**クライアント側でします。 これは、ため、 **System.ServiceModel.OperationContractAttribute.IsOneWay** にWCFアダプタ(Wcf-netmsmqによって公開されたサービスの受信アダプターを除く)で公開されたWCFサービスのプロパティが設定されて**false**一方向の受信場所に対してもします。  
  
```  
The channel received an unexpected input message while closing. Your Channel.Close() calls are not synchronized.  
```  
  
 指定された WCF サービスを使用するときに、次のようなエラー メッセージが表示されるが、 **IsOneWay**プロパティに設定**true**します。 送信されたメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]一時停止、再開可能になります。  
  
```  
The request operation at net.tcp://localhost:8088/MyService/tcp did not receive a reply within timeout 00:01:00.  
```  
  
## <a name="a-memory-leak-may-occur-when-sending-messages-to-non-transactional-msmq-queues-using-wcf-netmsmq-binding"></a>Wcf-netmsmq バインドを使用して、非トランザクション MSMQ キューにメッセージを送信するときに、メモリ リークが発生します。  
 メモリ リークは、BizTalk NT サービスで、Wcf-netmsmq バインドを使用して、非トランザクション MSMQ キューにメッセージを送信するときに発生します。 これは、Wcf-netmsmq トランスポートを使用して非トランザクション MSMQ キューにメッセージを送信するとき、または Wcf-custom トランスポートで netMsmqBinding を使用して非トランザクション MSMQ キューにメッセージを送信するときに発生する可能性があります。  
  
 この問題を解決するで KB 記事 936512 で説明されている .NET Framework 3.0 修正プログラムをインストールする必要があります[ http://go.microsoft.com/fwlink/?LinkId=92962](http://go.microsoft.com/fwlink/?LinkId=92962)します。 修正プログラムでは、システムの再起動は必要ありませんを使用して送信ポートをホストする BizTalk NT サービスを再起動する必要がある、Wcf-netmsmq バインドします。  
  
## <a name="you-may-receive-exception-when-communicating-with-apache-web-servers-using-wcf-basichttp-adapter"></a>Wcf-basichttp アダプターを使用して Apache Web サーバーと通信するときに例外が発生する可能性があります。  
 使用する場合、Wcf-basichttp アダプタのトランスポート セキュリティには、次のような例外が発生する、Apache Web サーバーと通信します。  
  
```  
System.Net.WebException: The underlying connection was closed: An unexpected error occurred on a send.  
System.IO.IOException: Unable to write data to the transport connection: An established connection was aborted by the software in your host machine. System.Net.Sockets.SocketException: An established connection was aborted by the software in your host machine  
```  
  
 この問題を回避するには、Wcf-basichttp アダプタではなく Wcf-custom アダプタを使用して、次のように Apache Web サーバーと通信する必要があります。  
  
1.  送信ポートを作成し、トランスポートの種類を設定**Wcf-custom**します。  
  
2.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで  **customBinding**から、**バインドの種類**ドロップダウン リスト。  
  
3.  [ **CustomeBindingElement**を右クリックして**httpTransport**、] をクリックし、**拡張機能を削除**します。  
  
4.  右クリック**CustomeBindingElement**、 をクリックし、**拡張機能の追加**します。  
  
5.  **バインド要素拡張機能の選択**ダイアログ ボックスで、 **httpTransport**順にクリックします**OK**します。  
  
6.  クリックして**httpTransport**、し、**構成**ペインで、設定の値**keepAliveEnabled**に**False**します。  
  
7.  クリックして**textMessageEncoding**、し、**構成**ペインで、設定の値**messageVersion**に`Soap11WSAddressing10`します。  
  
8.  必要に応じて、追加のプロパティを構成する必要があります。  
  
## <a name="biztalk-server-does-not-work-with-wcf-clients-that-using-clientviabehavior-for-multiple-hop-conversations"></a>BizTalk Server では機能しません WCF クライアントを使用して複数ホップの交換に ClientViaBehavior  
 WCF クライアントは、直接のネットワーク送信先が想定される呼び出し元のアプリケーションが最終的な送信先を必ずしも判断できない場合は、複数ホップの交換を有効にするメッセージのプロセッサではない場合に、ClientViaBehavior を使用します。 ClientViaBehavior を指定し、To アドレスをリモート サービスに設定したかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仲介役として機能する、次のようなエラー メッセージが表示されます。  
  
```  
The message with To 'net.tcp://localhost:5555/test.svc' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher. Check that the sender and receiver's EndpointAddresses agree  
```