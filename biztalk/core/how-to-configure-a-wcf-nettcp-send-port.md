---
title: "Wcf-nettcp 送信ポートを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8fff07e-b08e-4f95-8ce2-27b508674a5c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f46c4b521c754bd2096916a03e356262dfa4d46
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-wcf-nettcp-send-port"></a>WCF-NetTcp 送信ポートを構成する方法
WCF-NetTcp 送信ポートは、プログラムまたは BizTalk 管理コンソールを使用して構成できます。  
  
## <a name="configuration-properties"></a>構成プロパティ
  
 BizTalk エクスプローラ オブジェクト モデルがという名前の送信ポートのアダプターに固有のインターフェイスを公開する**ITransportInfo**を持つ、 **TransportTypeData**読み取り/書き込みプロパティです。 このプロパティでは、名前と値のペアの XML 文字列の形式で WCF-NetTcp 送信ポートの構成プロパティ バッグを指定できます。  
  
 **TransportTypeData**のプロパティ、 **ITransportInfo**インターフェイスは必要ありません。 このプロパティを設定しない場合は、アダプタで、次の表に記載されている WCF-NetTcp 送信ポートの構成の既定値が使用されます。  
  
 次の表に、BizTalk エクスプローラ オブジェクト モデルで WCF-NetTcp 送信ポート用に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Identity**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName 値 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|この送信ポートが必要とするサービスの ID を指定します。 これらの設定により、この送信ポートでサービスを認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**StaticAction**|文字列|指定して、 **SOAPAction**送信メッセージのヘッダー フィールド。 このプロパティは、メッセージ コンテキスト プロパティからも設定できます**WCF です。アクション**パイプラインまたはオーケストレーションでします。 2 つの異なる方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式です。 シングル アクション形式では、このプロパティを設定するかどうかは、http://contoso.com/Svc/Op1 など —、 **SOAPAction**ヘッダーは常に送信メッセージの設定をこのプロパティで指定された値にします。<br /><br /> 送信アクション マッピング形式でこのプロパティを設定する場合**SOAPAction**ヘッダーはによって決定されます、 **BTS です。操作**コンテキスト プロパティです。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**プロパティを Op1 に設定は、WCF 送信アダプタでは、http://contoso.com/Svc/Op1 を使用、送信を**SOAPAction**ヘッダー。<br /><br /> \<BtsActionMapping\><br /><br /> \<操作名"Op1"アクションを = ="http://contoso.com/Svc/Op1"/\><br /><br /> \<操作名"Op2"アクションを = ="http://contoso.com/Svc/Op2"/\><br /><br /> \</BtsActionMapping\><br /><br /> 送信メッセージには、オーケストレーション ポートから場合、オーケストレーション インスタンスは動的に設定、 **BTS です。操作**ポートの操作の名前を持つプロパティです。 コンテンツ ベースのルーティングと、送信メッセージのルーティングされる場合は、設定、 **BTS です。操作**パイプライン コンポーネントのプロパティです。<br /><br /> 既定値は空の文字列です。|  
|**OpenTimeout**|**System.TimeSpan**|チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**SendTimeout**|**System.TimeSpan**|送信操作が完了するまでの間隔を示す期間値を指定します。 送信請求 - 応答の送信ポートを使用する場合は、サービスから大きいメッセージが返される場合でも、この値には対話処理がすべて完了するまでの時間を指定します。<br /><br /> 既定値:00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**MaxReceivedMessageSize**|Integer|有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。<br /><br /> Wcf-nettcp アダプター活用して、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)クラス、エンドポイントと通信するために、バッファリングされた送信モードにします。 バッファリングされたトランスポート モードの場合、 [NetTcpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=81088)プロパティは常にこのプロパティの値とします。<br /><br /> 既定値:65536|  
|**EnableTransaction**|ブール値|メッセージが転送先サービスに転送されで指定されているトランザクション プロトコルを使用して、トランザクションのコンテキストでメッセージ ボックス データベースから削除するかどうかを指定して、 **TransactionProtocol**プロパティです。<br /><br /> 既定値: **False**|  
|**TransactionProtocol**|Enum<br /><br /> -   **[Oletransaction]**<br />-   **Ws-atomictransaction**|このバインドで使用するトランザクション プロトコルを指定します。<br /><br /> 既定値: **[oletransaction]**|  
|**SecurityMode**|Enum<br /><br /> -   **[なし]**<br />-   **メッセージ**<br />-   **トランスポート**<br />-   **TransportWithMessageCredential**<br /><br /> メンバー名の詳細については、 **SecurityMode**プロパティを参照してください、**セキュリティ モード**プロパティに、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|使用するセキュリティの種類を指定します。<br /><br /> 既定値:**トランスポート**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **[なし]**<br />-   **Windows**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **TransportClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のトランスポート**プロパティに、 **Wcf-nettcp トランスポートプロパティ] ダイアログ ボックスの [送信セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|送信ポート認証の実行時に使用する資格情報の種類を指定します。<br /><br /> 既定値: **Windows**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **None** -保護されません。<br />-   **サインオン**-メッセージは署名されます。<br />-   **EncryptAndSign** -メッセージの暗号化および署名されます。|TCP トランスポートのレベルでのセキュリティを指定します。 メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。 暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。<br /><br /> 既定値: **EncryptAndSign**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **[なし]**<br />-   **Windows**<br />-   **ユーザー名**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MessageClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のメッセージ**プロパティに、 **Wcf-nettcp トランスポートのプロパティダイアログ ボックスの 送信セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。<br /><br /> 既定値: **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> メンバー名の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティに、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。<br /><br /> 既定値: **Basic256**|  
|**ClientCertificate**|文字列|この送信ポートをサービスに対して認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティは必要な場合、 **ClientCredentialsType**プロパティに設定されている**証明書**です。 このプロパティに使用する証明書をインストールする必要があります、 **My**に格納、**現在のユーザー**場所。<br /><br /> 既定値は空の文字列です。|  
|**AffiliateApplicationName**|文字列|エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。<br /><br /> 既定値は空の文字列です。|  
|**UseSSO**|ブール値|接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。<br /><br /> 既定値: **False**|  
|**UserName**|文字列|移行先サーバーで認証に使用するユーザー名を指定するときに、 **UseSSO**プロパティに設定されている**False**です。 このプロパティでは domain\user 形式は使用できません。<br /><br /> 既定値は空の文字列です。|  
|**Password**|文字列|移行先サーバーでの認証を使用するパスワードを指定するときに、 **UseSSO**プロパティに設定されている**False**です。<br /><br /> 既定値は空の文字列です。|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ**本文**送信メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**送信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定**本文**送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation**プロパティに設定されている**UseTemplate**です。<br /><br /> 既定値は空の文字列です。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成する**エンベロープ**受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression**プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直接の子要素に対して評価されます**本文**受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** -Base64 エンコードします。<br />-   **16 進**: 16 進エンコードします。<br />-   **文字列**: テキスト エンコード - utf-8。<br />-   **XML** -WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で、BizTalk メッセージ本文を作成する**InboundBodyPathExpression**です。|指定された XPath で識別されるノードに対して、Wcf-nettcp 送信アダプタがデコードに使用するエンコードの種類を指定**InboundBodyPathExpression**です。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **XML**|  
|**PropagateFaultMessage**|ブール値<br /><br /> -   **True**にサブスクライブしているアプリケーションへの送信処理に失敗したメッセージのルーティング (別の受信ポートやオーケストレーション スケジュールなど)。<br />-   **False** -一時停止に失敗したメッセージおよび否定受信確認応答 (NACK) を生成します。|送信処理に失敗したメッセージをルーティングまたは中断するかどうかを指定します。<br /><br /> このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値:**は True。**|  
  
 **BizTalk 管理コンソールで、Wcf-nettcp 送信ポートを構成する方法**  
  
 BizTalk 管理コンソールで、WCF-NetTcp 送信ポート アダプタの変数を設定できます。 プロパティが送信ポートに設定されていない場合は、前の表に記載されている WCF-NetTcp 送信ポートの構成の既定値が使用されます。  
  
## <a name="configure-variables-for-a-wcf-nettcp-send-port"></a>Wcf-nettcp 送信ポートの変数を構成します。  
  
1.  BizTalk 管理コンソールで、新しい送信ポートを作成するか、既存の送信ポートをダブルクリックして変更します。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定**Wcf-nettcp**の**型**オプション、**トランスポート**のセクションで、**全般**タブ  
  
2.  **全般**] タブの [、**トランスポート**セクションで、をクリックして、**構成**横に**型**です。  
  
3.  **Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスの**全般** タブで、エンドポイント アドレス、サービス id を構成して、 **SOAPAction**ヘッダーをWcf-nettcp 送信ポートです。 詳細については、**全般** タブで、 **Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、一般的な**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
4.  **Wcf-nettcp トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで、タイムアウトおよびトランザクションのプロパティを構成します。 詳細については、**バインド** タブで、 **Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
5.  **Wcf-nettcp トランスポートのプロパティ** ダイアログ ボックスで、**セキュリティ** タブで、Wcf-nettcp 送信ポートのセキュリティ機能を定義します。 詳細については、**セキュリティ** タブで、 **Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
6.  **Wcf-nettcp トランスポートのプロパティ** ダイアログ ボックスで、**メッセージ** タブで、SOAP のデータ選択を指定**本文**要素。 詳細については、**メッセージ** タブで、 **Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="configure-a-wcf-nettcp-send-port-programmatically"></a>プログラムで、Wcf-nettcp 送信ポートを構成します。
  
 次の形式を使用してプロパティを設定できます。  
  
 \<CustomProps\>  
  
```  
  <UseSSO vt="11">0</UseSSO>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <ClientCertificate vt="8" />  
  <TransactionProtocol vt="8">OleTransactions</TransactionProtocol>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <TransportProtectionLevel vt="8">EncryptAndSign</TransportProtectionLevel>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 次のコードは、WCF-NetTcp 送信ポートの作成方法を示しています。  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetTcp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
<OpenTimeout vt=""8"">00:01:00</OpenTimeout>  
                               </CustomProps>";  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
// Add a new BizTalk application  
Application application = explorer.AddNewApplication();  
application.Name = "SampleBizTalkApplication";  
// Save  
explorer.SaveChanges();  
  
// Add a new static one-way send port  
SendPort sendPort = application.AddNewSendPort(false, false);   
sendPort.Name = "SampleSendPort";  
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetTcp"];  
sendPort.PrimaryTransport.Address = "net.tcp://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md)   
 [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)