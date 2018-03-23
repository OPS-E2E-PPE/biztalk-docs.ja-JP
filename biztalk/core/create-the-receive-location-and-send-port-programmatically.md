---
title: 受信場所を作成および送信ポートをプログラムによって |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47850e66-ce33-4c6a-8190-168071792c0b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d2f6871ca730e741ca4877907593931fc362a4d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="create-the-receive-location-and-send-port-programmatically"></a>受信場所を作成し、プログラムでの送信ポート
構成、Wcf-basichttp 受信場所と送信ポートをプログラムでします。 BizTalk 管理コンソールを使用するのを参照してください。 [、Wcf-basichttp アダプタ](../core/wcf-basichttp-adapter.md)です。 
  
## <a name="configure-the-receive-location-programmatically"></a>プログラムを使用して、受信場所を構成します。  
  
 BizTalk エクスプローラー オブジェクト モデルにより、プログラムから受信場所を作成および構成することができます。 BizTalk エクスプ ローラー オブジェクト モデルは、公開、**IReceiveLocation** 受信場所の構成インターフェイスを持つ、 **TransportTypeData** 読み取り/書き込みプロパティです。 このプロパティでは、名前と値の組の XML 文字列の形式で WCF-BasicHttp 受信場所の構成プロパティ バッグを指定できます。 BizTalk エクスプ ローラー オブジェクト モデルでは、このプロパティを設定するに設定する必要があります、 **InboundTransportLocation** のプロパティ、 **IReceiveLocation** インターフェイスです。  
  
 **TransportTypeData** のプロパティ、 **IReceiveLocation** インターフェイスを設定する必要はありません。 このプロパティを設定しない場合、WCF-BasicHttp アダプタでは、次の表に記載されている WCF-BasicHttp 受信場所の構成の既定値が使用されます。  
 
 次のコード フラグメントでは、Wcf-basichttp を作成する方法を示して受信場所の BizTalk エクスプ ローラー オブジェクト モデルを使用します。  
  
```  
// Use BizTalk Explorer object model to create new WCF-BasicHttp receive location   
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
  <InboundBodyLocation vt=""8"">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt=""11"">0</UseSSO>  
  <Identity vt=""8"">  
    <identity>  
    <userPrincipalName value=""username@contoso.com"" />  
    </identity>  
  </Identity>  
</CustomProps>";  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
// Add a new BizTalk application  
Application application = explorer.AddNewApplication();  
application.Name = "SampleBizTalkApplication";  
// Save  
explorer.SaveChanges();  
// Add a new one-way receive port  
IReceivePort receivePort = application.AddNewReceivePort(false);  
receivePort.Name = "SampleReceivePort";  
// Add a new one-way receive location  
IReceiveLocation recieveLocation = receivePort.AddNewReceiveLocation();  
recieveLocation.Name = "SampleReceiveLocation";  
// Find a receive handler for WCF-BasicHttp  
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-BasicHttp" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "/samplepath/sampleservice.svc";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-BasicHttp"];  
recieveLocation.TransportTypeData = transportConfigData;  
// Save  
explorer.SaveChanges();  
  
```  

次の形式を使用するには、プロパティで設定する `<CustomProps>`: 
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt="11">0</UseSSO>  
  <MessageClientCredentialType vt="8">UserName</MessageClientCredentialType>  
  <InboundBodyPathExpression vt="8" />  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <Identity vt="8">  
    <identity>  
    <userPrincipalName value="username@contoso.com" />  
    </identity>  
  </Identity>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">None</SecurityMode>  
  <TransportClientCredentialType vt="8">None</TransportClientCredentialType>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <TextEncoding vt="8">utf-8</TextEncoding>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <MaxConcurrentCalls vt="3">16</MaxConcurrentCalls>  
  <MessageEncoding vt="8">Text</MessageEncoding>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```   
  
次の表は、受信場所に対して設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Id**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt;|この受信場所が提供するサービスの ID を指定します。 指定できる値、 **Identity** プロパティが、セキュリティ構成によって異なります。 これらの設定により、クライアントはこの受信場所を認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**Opentimeout します。**|**System.TimeSpan**|チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**SendTimeout**|**System.TimeSpan**|送信操作が完了するまでの間隔を示す期間値を指定します。 要求 - 応答受信ポートを使用する場合、この値は、対話処理がすべて完了するまでの時間を指定します。これは、クライアントが大きなメッセージを返した場合にも適用されます。<br /><br /> 既定値:00:01:00|  
|**Closetimeout します。**|**System.TimeSpan**|チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**MaxReceivedMessageSize**|Integer|有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。<br /><br /> Wcf-basichttp アダプターを活用、 [BasicHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81086) クラスには、バッファリングされた送信モードで、エンドポイントと通信します。 バッファリングされたトランスポート モード用、 [BasicHttpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=80659) プロパティは常にこのプロパティの値とします。<br /><br /> 既定値:65536|  
|**MessageEncoding**|Enum<br /><br /> -   **テキスト**-テキスト メッセージ エンコーダーを使用します。<br />-   **Mtom** -メッセージ Transmission Optimization Mechanism 1.0 (MTOM) エンコーダーを使用します。|SOAP メッセージをエンコードするために使用されるエンコーダーを指定します。<br /><br /> 既定値: **テキスト**|  
|**TextEncoding**|Enum<br /><br /> -   **unicodeFFF** -Unicode BigEndian エンコーディングします。<br />-   **utf-16** : 16 ビット エンコーディングします。<br />-   **utf-8** : 8 ビット エンコーディング|文字セットのバインディングでメッセージを出力するために使用するエンコーディングを指定時に、 **MessageEncoding** にプロパティが設定されている **テキスト**します。<br /><br /> 既定値: **utf-8**|  
|**MaxConcurrentCalls**|Integer|単一のサービス インスタンスに対する同時呼び出しの数を指定します。 制限を超える呼び出しはキューに格納されます。 このプロパティの範囲は 1 ~ **Int32.MaxValue**します。<br /><br /> 既定値:200|  
|**SecurityMode**|Enum<br /><br /> -   **[なし]**<br />-   **メッセージ**<br />-   **トランスポート**<br />-   **TransportWithMessageCredential**<br />-   **TransportCredentialOnly**<br /><br /> メンバー名の詳細については、 **SecurityMode**プロパティを参照してください、**セキュリティ モード**プロパティに、 **Wcf-basichttp トランスポートのプロパティ ダイアログ ボックス、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|使用するセキュリティの種類を指定します。<br /><br /> 既定値: **なし**|  
|**TransportClientCredentialType**|メンバー名の詳細については、 **TransportClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のトランスポート**プロパティ**Wcf-basichttp トランスポートプロパティ ダイアログ ボックスで、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|クライアント認証の実行時に使用する資格情報の種類を指定します。<br /><br /> 既定値: **なし**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **ユーザー名**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MessageClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のメッセージ**プロパティ**Wcf-basichttp トランスポートのプロパティダイアログ ボックスで、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。<br /><br /> 既定値: **ユーザー名**|  
|**AlgorithmSuite**|Enum<br /><br /> メンバー名の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティ**Wcf-basichttp トランスポートのプロパティ ダイアログ ボックス、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。<br /><br /> 既定値: **Basic256**|  
|**ServiceCertificate**|文字列|クライアントがサービスの認証に使用する、この受信場所に対する X.509 証明書の拇印を指定します。 このプロパティを使用する証明書をインストールする必要があります、 **マイ** に格納、 **現在のユーザー** 場所です。 **注:**  にサービス証明書をインストールする必要があります、 **現在のユーザー** この受信場所をホストする受信ハンドラーのユーザー アカウントの場所。 <br /><br /> 既定値は空の文字列です。|  
|**UseSSO**|ブール値|エンタープライズ シングル サインオン (SSO) を使用して SSO チケットを発行するためにクライアントの資格情報を取得するかどうかを指定します。 セキュリティ構成の詳細については、SSO のサポートを参照して、」アダプタ エンタープライズ シングル サインオン サポートの「Wcf-basichttp 受信「 **Wcf-basichttp トランスポートのプロパティ ダイアログ ボックス、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。<br /><br /> 既定値: **False**|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成 **エンベロープ** 受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression** プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直下の子要素に対して評価されます **本文** 受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** の Base64 エンコードします。<br />-   **16 進** : 16 進エンコードします。<br />-   **文字列** : テキスト エンコード - utf-8<br />-   **XML** の WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で BizTalk メッセージ本文を作成する **InboundBodyPathExpression**します。|Wcf-basichttp 受信アダプターで指定されたボディ パス式で識別されるノードのデコードに使用するエンコードの種類を指定 **InboundBodyPathExpression**します。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。<br /><br /> 既定値: **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信応答メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ **本文** 、送信応答メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 送信 WCF メッセージの要素。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定 **本文** 、送信応答メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation** プロパティに設定されて **UseTemplate**します。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 既定値は空の文字列です。|  
|**SuspendMessageOnFailure**|ブール値|受信パイプラインまたはルーティングの障害によって受信処理に失敗した要求メッセージを保留するかどうかを指定します。<br /><br /> 既定値: **False**|  
|**IncludeExceptionDetailInFaults**|ブール値|デバッグの目的でクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めるかどうかを指定します。<br /><br /> 既定値: **False**|  
  
## <a name="configure-the-send-port-programmatically"></a>プログラムを使用して、送信ポートを構成します。   

 次のコード フラグメントは、BizTalk エクスプ ローラー オブジェクト モデルを使用して、Wcf-basichttp 送信ポートの作成を示しています。    
  
```  
// Use BizTalk Explorer object model to create new WCF-BasicHttp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 <MessageEncoding vt=""8"">Text</MessageEncoding>  
                                 <TextEncoding vt=""8"">utf-8</TextEncoding>  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-BasicHttp"];  
sendPort.PrimaryTransport.Address = "http://mycomputer/samplepath";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```    

次の形式を使用するには、プロパティで設定する `<CustomProps>`: 
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt="11">0</UseSSO>  
  <MessageClientCredentialType vt="8">UserName</MessageClientCredentialType>  
  <InboundBodyPathExpression vt="8" />  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">None</SecurityMode>  
  <TransportClientCredentialType vt="8">None</TransportClientCredentialType>  
  <ClientCertificate vt="8" />  
  <ProxyUserName vt="8" />  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <TextEncoding vt="8">utf-8</TextEncoding>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <ProxyToUse vt="8">Default</ProxyToUse>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <ProxyAddress vt="8" />  
  <MessageEncoding vt="8">Text</MessageEncoding>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  

次の表は、送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**SecurityMode**|Enum<br /><br /> -   **[なし]**<br />-   **メッセージ**<br />-   **トランスポート**<br />-   **TransportWithMessageCredential**<br />-   **TransportCredentialOnly**<br /><br /> メンバー名の詳細については、 **SecurityMode**プロパティを参照してください、**セキュリティ モード**プロパティ**Wcf-basichttp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|使用するセキュリティの種類を指定します。<br /><br /> 既定値: **なし**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **ユーザー名**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MessageClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のメッセージ**プロパティ**Wcf-basichttp トランスポートのプロパティダイアログ ボックスの 送信セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。<br /><br /> 既定値: **ユーザー名**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **[なし]**<br />-   **基本的です**<br />-   **Windows**<br />-   **証明書**<br />-   **ダイジェスト**<br />-   **Ntlm**<br /><br /> メンバー名の詳細については、 **TransportClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のトランスポート**プロパティ**Wcf-basichttp トランスポートプロパティ] ダイアログ ボックスの [送信セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|送信ポート認証の実行時に使用する資格情報の種類を指定します。<br /><br /> 既定値: **なし**|  
|**ユーザー名**|文字列|接続先サーバーで認証を使用するユーザー名を指定時に、 **UseSSO** にプロパティが設定されている **False**します。 このプロパティでは domain\user 形式は使用できません。<br /><br /> 既定値は空の文字列です。|  
|**パスワード**|文字列|接続先サーバーで認証を使用するパスワードを指定するときに、 **UseSSO** にプロパティが設定されている **False**します。<br /><br /> 既定値は空の文字列です。|  
|**AffiliateApplicationName**|文字列|エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。<br /><br /> 既定値は空の文字列です。|  
|**UseSSO**|ブール値|接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。<br /><br /> 既定値: **False**|  
|**ClientCertificate**|文字列|この送信ポートをサービスに対して認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティは必要な場合、 **ClientCredentialsType** プロパティに設定されて **証明書**します。 このプロパティを使用する証明書をインストールする必要があります、 **マイ** に格納、 **現在のユーザー** 場所です。<br /><br /> 既定値は空の文字列です。|  
|**ServiceCertificate**|文字列|この送信ポートのメッセージ送信先のサービスを認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティを使用する証明書をインストールする必要があります、 **その他のユーザー** に格納、 **ローカル マシン** 場所です。<br /><br /> 既定値は空の文字列です。|  
|**ProxyToUse**|Enum<br /><br /> -   **None** -この送信ポートのプロキシ サーバーを使用できません。<br />-   **既定の** -この送信ポートをホストする送信ハンドラーのプロキシ設定を使用します。<br />-   **UserSpecified** -指定されたプロキシ サーバーを使用して、 **ProxyAddress** プロパティ|送信 HTTP トラフィックに使用するプロキシ サーバーを指定します。<br /><br /> 既定値: **なし**|  
|**ProxyAddress**|文字列|プロキシ サーバーのアドレスを指定します。 使用して、 **https** または **http** セキュリティ構成に応じて設定します。 このアドレスの後に、コロンとポート番号を指定します。 たとえば、http://127.0.0.1:8080 と指定します。<br /><br /> 既定値は空の文字列です。|  
|**ProxyUserName**|文字列|プロキシに使用するユーザー名を指定します。 Wcf-basichttp アダプターを活用、 [BasicHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81086) のバッファリングされた送信モードで、エンドポイントと通信します。 プロキシの資格情報の **BasicHttpBinding** セキュリティ モードが場合にのみ当てはまる **トランスポート**, 、**なし**, 、または **TransportCredentialOnly**します。 設定した場合、 **SecurityMode** プロパティを **メッセージ** または **TransportWithMessageCredential**, 、Wcf-basichttp アダプターがで指定された資格情報を使用していない、 **ProxyUserName** と **ProxyPassword** プロキシに対する認証のプロパティです。 **注:**  、Wcf-basichttp 送信アダプターの使用、プロキシに対して基本認証. <br /><br /> 既定値は空の文字列です。|  
|**ProxyPassword**|文字列|プロキシに使用するパスワードを指定します。<br /><br /> 既定値は空の文字列です。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成 **エンベロープ** 受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression** プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ **本文** 、送信メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 送信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直下の子要素に対して評価されます **本文** 受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値は空の文字列です。|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定 **本文** 、送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation** プロパティに設定されて **UseTemplate**します。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** の Base64 エンコードします。<br />-   **16 進** : 16 進エンコードします。<br />-   **文字列** : テキスト エンコード - utf-8<br />-   **XML** の WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で BizTalk メッセージ本文を作成する **InboundBodyPathExpression**します。|Wcf-basichttp 送信アダプターがで指定されたボディ パス式で識別されるノードのデコードに使用するエンコーディングの種類を指定 **InboundBodyPathExpression**します。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **XML**|  
|**StaticAction**|文字列|指定の **SOAPAction** 送信メッセージの HTTP ヘッダー フィールドです。 このプロパティは、メッセージ コンテキスト プロパティからは設定も **WCF です。アクション** パイプラインまたはオーケストレーションします。 2 つの方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式です。 シングル アクション形式では、このプロパティを設定するかどうか: たとえば、 http://contoso.com/Svc/Op1—、 **SOAPAction**ヘッダーは常に送信メッセージの設定をこのプロパティで指定された値にします。<br /><br /> 送信アクション マッピング形式でこのプロパティを設定した場合 **SOAPAction** によってヘッダーが決定、 **BTS します。操作** コンテキスト プロパティです。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**を Op1 に設定されているプロパティ、WCF 送信アダプタを使用してhttp://contoso.com/Svc/Op1アウトゴーイング**SOAPAction**ヘッダー。<br /><br /> \<BtsActionMapping\><br /><br /> \<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /\><br /><br /> \<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> 送信メッセージは、オーケストレーション ポートから送られてきた場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作** ポートの操作の名前を持つプロパティです。 コンテンツ ベースのルーティングと送信メッセージがルーティングされる場合は、設定、 **BTS します。操作** パイプライン コンポーネントのプロパティです。<br /><br /> 既定値は空の文字列です。|  
|**MaxReceivedMessageSize**|Integer|有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。<br /><br /> Wcf-basichttp アダプターを活用、 [BasicHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81086) クラスには、バッファリングされた送信モードで、エンドポイントと通信します。 バッファリングされたトランスポート モード用、 [BasicHttpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=80659) プロパティは常にこのプロパティの値とします。<br /><br /> 既定値: 65,536|  
|**MessageEncoding**|Enum<br /><br /> -   **テキスト**-テキスト メッセージ エンコーダーを使用します。<br />-   **Mtom** -メッセージ Transmission Organization Mechanism 1.0 (MTOM) エンコーダーを使用します。|SOAP メッセージをエンコードするために使用されるエンコーダーを指定します。<br /><br /> 既定値: **テキスト**|  
|**TextEncoding**|Enum<br /><br /> -   **unicodeFFF** -Unicode BigEndian エンコーディングします。<br />-   **utf-16** : 16 ビット エンコーディングします。<br />-   **utf-8** : 8 ビット エンコーディング|文字セットのバインディングでメッセージを出力するために使用するエンコーディングを指定時に、 **MessageEncoding** にプロパティが設定されている **テキスト**します。<br /><br /> 既定値: **utf-8**|  
|**SendTimeout**|**System.TimeSpan**|送信操作が完了するまでの間隔を示す期間値を指定します。 送信請求 - 応答の送信ポートを使用する場合は、サービスから大きいメッセージが返される場合でも、この値には対話処理がすべて完了するまでの時間を指定します。<br /><br /> 既定値:00:01:00|  
|**Opentimeout します。**|**System.TimeSpan**|チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**Closetimeout します。**|**System.TimeSpan**|チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**AlgorithmSuite**|Enum<br /><br /> メンバー名の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティ**Wcf-basichttp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。<br /><br /> 既定値: **Basic256**|  
|**Id**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt;|この送信ポートが必要とするサービスの ID を指定します。 これらの設定により、この送信ポートでサービスを認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**PropagateFaultMessage**|ブール値<br /><br /> -   **True**にサブスクライブしているアプリケーションへの送信処理に失敗したメッセージのルーティング (別の受信ポートやオーケストレーション スケジュールなど)。<br />-   **False** -中断失敗したメッセージおよび否定受信確認応答 (NACK) を生成します。|送信処理に失敗したメッセージをルーティングまたは中断するかどうかを指定します。<br /><br /> このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **は True。**|  
  
## <a name="see-also"></a>参照  
 [WCF アダプターについて](../core/what-are-the-wcf-adapters.md)  
 [発行の WCF サービスを分離 WCF 受信アダプター](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)   
 [構成の IIS 分離 wcf 受信アダプター](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)   
 [BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md)   
 [サービス アカウントとパスワードを変更する方法](../core/how-to-change-service-accounts-and-passwords.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)    
  [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)