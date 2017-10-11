---
title: "Wcf-netmsmq 受信場所を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82b323b-9870-42fb-9992-c23dca909b4d
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16491259826159f18791e35efb226dd159c12c27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-netmsmq-receive-location"></a>WCF-NetMsmq 受信場所を構成する方法
WCF-NetMsmq 受信場所は、プログラムから、または BizTalk 管理コンソールを使用して構成できます。  
  
## <a name="configuratin-properties"></a>設定のプロパティ
  
 BizTalk エクスプローラー オブジェクト モデルにより、プログラムから受信場所を作成および構成することができます。 BizTalk エクスプ ローラー オブジェクト モデルは、公開、**という**受信場所の構成インターフェイスを持つ、 **TransportTypeData**読み取り/書き込みプロパティです。 このプロパティでは、名前と値の組の XML 文字列の形式で WCF-NetMsmq 受信場所の構成プロパティ バッグを指定できます。 BizTalk エクスプローラ オブジェクト モデルでこのプロパティを設定に設定する必要があります、 **InboundTransportLocation**のプロパティ、**という**インターフェイスです。  
  
 **TransportTypeData**のプロパティ、**という**インターフェイスを設定する必要はありません。 このプロパティを設定しない場合、WCF-NetMsmq アダプターでは、次の表に記載されている WCF-NetMsmq 受信場所の構成の既定値が使用されます。  
  
 次の表に、BizTalk エクスプローラーのオブジェクト モデルで WCF-NetMsmq 受信場所用に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Identity**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName 値 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|この受信場所が提供するサービスの ID を指定します。 指定できる値、 **Identity**プロパティが、セキュリティ構成によって異なります。 これらの設定により、クライアントはこの受信場所を認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**OpenTimeout**|**System.TimeSpan**|チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**SendTimeout**|**System.TimeSpan**|送信操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**MaxReceivedMessageSize**|Integer|有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。<br /><br /> 既定値:65536|  
|**EnableTransaction**|ブール値|メッセージ キューの種類 (トランザクションまたは非トランザクション) を指定します。 このプロパティが選択されている場合、各メッセージは一度だけ配信され、送信者には配信エラーが通知されます。 トランザクション送信を経由してメッセージを送信するポートを両方とも、**持続性のある**と**exactlyOnce**に設定する必要があります、クライアントの要素をバインディング**True**です。 このプロパティがオフの場合、配信が保証されずにメッセージが転送されます。 **注:**受信場所でこのトランザクション キューを使用する場合、このプロパティを選択する必要があります。 <br /><br /> 既定値: **False**|  
|**OrderedProcessing**|ブール値|メッセージを順番に処理するかどうかを指定します。 この受信場所でこのプロパティがオンの場合は、BizTalk メッセージングまたはオーケストレーション送信ポートを持つと組み合わせて使用すると、メッセージの順次配送を提供、**順次配送**オプションに設定`True`です。 この場合にのみを選択することができます、 **EnableTransaction**プロパティに設定されている**True**です。<br /><br /> 詳細については、**順次配送**オプションで、適切なトピックを参照を参照してください。<br /><br /> このプロパティに設定するときに**True**、Wcf-netmsmq 受信場所アダプターをシングル スレッド化して大きなメッセージを処理する場合は、リソースの利用状況を最適化します。<br /><br /> 既定値: **False**|  
|**MaxConcurrentCalls**|Integer|単一のサービス インスタンスに対する同時呼び出しの数を指定します。 制限を超える呼び出しはキューに格納されます。 このプロパティの範囲は 0 ~ **Int32.MaxValue**です。<br /><br /> 既定値:200|  
|**SecurityMode**|Enum<br /><br /> -   **[なし]**<br />-   **メッセージ**<br />-   **トランスポート**<br />-   **両方とも**<br /><br /> メンバー名の詳細については、 **SecurityMode**プロパティを参照してください、**セキュリティ モード**プロパティに、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|使用するセキュリティの種類を指定します。<br /><br /> 既定値:**トランスポート**|  
|**MsmqAuthenticationMode**|Enum<br /><br /> -   **[なし]**<br />-   **WindowsDomain**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MsmqAuthenticationMode**プロパティを参照してください、 **MSMQ 認証モード**プロパティに、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス表示された場合は、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|MSMQ トランスポートによるメッセージの認証方法を指定します。<br /><br /> 既定値: **WindowsDomain**|  
|**MsmqProtectionLevel**|Enum<br /><br /> -   **None**: 保護されません。<br />-   **サインオン**: メッセージは署名されます。<br />-   **EncryptAndSign**: メッセージの暗号化および署名されます。 この保護レベルを使用する必要がありますを有効にした**Active Directory 統合**の**MSMQ**です。|MSMQ トランスポートのレベルでメッセージをセキュリティ保護する方法を指定します。 暗号化により、メッセージの整合性が保証されます。また、署名および暗号化により、メッセージの整合性と否認不可の両方が保証されます。<br /><br /> 既定値:**記号**|  
|**MsmqSecureHashAlgorithm**|Enum<br /><br /> -   **MD5**<br />-   **SHA1**<br />-   **SHA25**<br />-   **SHA512**|メッセージ ダイジェストの計算に使用するハッシュ アルゴリズムを指定します。 このプロパティは使用できない場合、 **MsmqProtectionLevel**プロパティに設定されている**None**です。<br /><br /> 既定値: **SHA1**|  
|**MsmqEncryptionAlgorithm**|Enum<br /><br /> -   **RC4Stream**<br />-   **AES**|メッセージ キュー マネージャー間でメッセージを転送するときに、有線ネットワーク上でメッセージを暗号化するために使用するアルゴリズムを指定します。 このプロパティは使用可能な場合にのみ、 **MsmqProtectionLevel**プロパティに設定されている**EncryptAndSign**です。<br /><br /> 既定値: **RC4Stream**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **[なし]**<br />-   **Windows**<br />-   **ユーザー名**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MessageClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のメッセージ**プロパティに、 **Wcf-netmsmq トランスポートのプロパティダイアログ ボックスで、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。<br /><br /> 既定値: **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> メンバー名の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティに、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。<br /><br /> 既定値: **Basic256**|  
|**ServiceCertificate**|文字列|クライアントがサービスの認証に使用する、この受信場所に対する X.509 証明書の拇印を指定します。 このプロパティに使用する証明書をインストールする必要があります、 **My**に格納、**現在のユーザー**場所。 **注:**にサービス証明書をインストールする必要があります、**現在のユーザー**この受信場所をホストする受信ハンドラーのユーザー アカウントの場所。 <br /><br /> 既定値は空の文字列です。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成する**エンベロープ**受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression**プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直接の子要素に対して評価されます**本文**受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 エンコードします。<br />-   **16 進**: 16 進エンコードします。<br />-   **文字列**: テキスト エンコード - utf-8。<br />-   **XML** -WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で、BizTalk メッセージ本文を作成する**InboundBodyPathExpression**です。|Wcf-netmsmq 受信アダプターで指定されたボディ パス式で識別されるノードのデコードに使用するエンコードの種類の指定**InboundBodyPathExpression**です。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。<br /><br /> 既定値: **XML**|  
|**DisableLocationOnFailure**|ブール値|受信パイプラインまたはルーティングの障害によって受信処理に失敗した受信場所を無効にするかどうかを指定します。<br /><br /> 既定値: **False**|  
|**SuspendMessageOnFailure**|ブール値|受信パイプラインまたはルーティングの障害によって受信処理に失敗した要求メッセージを保留するかどうかを指定します。<br /><br /> 既定値:**は True。**|  
|**IncludeExceptionDetailInFaults**|ブール値|デバッグの目的でクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めるかどうかを指定します。<br /><br /> 既定値: **False**|  
  
## <a name="configure-a-wcf-netmsmq-receive-location-with-the-biztalk-administration-console"></a>Wcf-netmsmq を構成する BizTalk 管理コンソールでの受信場所
  
 WCF-NetMsmq 受信場所のアダプター変数は、BizTalk 管理コンソールで設定できます。 プロパティが受信場所に設定されていない場合は、BizTalk 管理コンソールで設定された既定の受信ハンドラーの値が使用されます。  
  
> [!NOTE]
>  次の手順を実行する前に、受信ポートを追加する必要があります。 詳細については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。  
  
> [!NOTE]
>  WCF クライアントと WCF-NetMsmq 受信場所のバインド構成は一致する必要があります。 一致しない場合、WCF-NetMsmq 受信場所で受信メッセージが失われることがあります。  
  
## <a name="configure-variables-for-a-wcf-netmsmq-receive-location"></a>Wcf-netmsmq 受信場所の変数を構成します。  
  
1.  BizTalk 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションを展開し、受信場所を作成するには。  
  
2.  BizTalk 管理コンソールの左側のウィンドウで、[ **受信ポート** ] ノードをクリックします。 次に右ウィンドウで、既存の受信場所に関連付けられているか、新しい受信場所に関連付ける受信ポートを右クリックし、 **プロパティ**をクリックします。  
  
3.  **受信ポートのプロパティ**ダイアログ ボックスで、左ペインで、select、**受信場所**、右側のペインをダブルクリックして、既存の受信場所またはをクリックし **新規**新しい受信場所を作成します。  
  
4.  **受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**横**型**[ **Wcf-netmsmq**から、クリックしてドロップダウン リスト、**構成**です。  
  
5.  **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、エンドポイント アドレスを構成し、サービス id を Wcf-netmsmq 受信場所。 詳細については、**全般** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、受信、[全般]**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
6.  **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで、タイムアウトおよびトランザクションのプロパティを構成します。 詳細については、**バインド** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、受信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
7.  **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスの**セキュリティ** タブで、セキュリティを定義する機能、Wcf-netmsmq 受信場所。 詳細については、**セキュリティ** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
8.  **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**メッセージ** タブで、SOAP のデータ選択を指定**本文**要素。 詳細については、**メッセージ** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、受信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
## <a name="configure-a-wcf-netmsmq-receive-location-programmatically"></a>構成、Wcf-netmsmq 受信場所をプログラムで
  
 次の形式を使用してプロパティを設定できます。  
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <MaxConcurrentCalls vt="3">16</MaxConcurrentCalls>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <OrderedProcessing vt="11">0</OrderedProcessing>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <MsmqEncryptionAlgorithm vt="8">RC4Stream</MsmqEncryptionAlgorithm>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <MsmqProtectionLevel vt="8">Sign</MsmqProtectionLevel>  
  <DisableLocationOnFailure vt="11">0</DisableLocationOnFailure>  
  <MsmqSecureHashAlgorithm vt="8">Sha1</MsmqSecureHashAlgorithm>  
  <SuspendMessageOnFailure vt="11">-1</SuspendMessageOnFailure>  
  <EnableTransaction vt="11">-1</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <MsmqAuthenticationMode vt="8">WindowsDomain</MsmqAuthenticationMode>  
</CustomProps>  
  
```  
  
 次のコードは、WCF-NetMsmq 受信場所の作成方法を示しています。  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetMsmq receive location   
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
// Find a receive handler for WCF-NetMsmq   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-NetMsmq" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.msmq://mycomputer/private/sampleQueue";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-NetMsmq"];  
recieveLocation.TransportTypeData = transportConfigData;  
// Save  
explorer.SaveChanges();   
```  
  
## <a name="see-also"></a>参照  
 [受信アダプターの wcf サービス メタデータの公開](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)   
 [BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md)   
 [サービス アカウントとパスワードを変更する方法](../core/how-to-change-service-accounts-and-passwords.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Wcf-netmsmq アダプタを構成します。](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)   
 [送信して、トランザクション内でメッセージを取得します。](http://go.microsoft.com/fwlink/?LinkID=75752)   
 [メッセージ キューと Active Directory](http://go.microsoft.com/fwlink/?LinkID=75769)   
 [パブリック キューと専用キュー](http://go.microsoft.com/fwlink/?LinkId=196673)