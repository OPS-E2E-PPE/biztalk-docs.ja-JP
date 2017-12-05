---
title: "Wcf-netmsmq 送信ポートを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13f55e53-12af-473b-b73f-1c98edadfc28
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48ad9e8f7ce806e0570877702fbccb432ca2946a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-wcf-netmsmq-send-port"></a>WCF-NetMsmq 送信ポートを構成する方法
WCF-NetMsmq 送信ポートは、プログラムから、または BizTalk 管理コンソールを使用して構成できます。  
  
## <a name="configuration-properties"></a>構成プロパティ
  
 BizTalk エクスプローラ オブジェクト モデルがという名前の送信ポートのアダプターに固有のインターフェイスを公開する**ITransportInfo**を持つ、 **TransportTypeData**読み取り/書き込みプロパティです。 このプロパティでは、名前と値の組の XML 文字列の形式で WCF-NetMsmq 送信ポートの構成プロパティ バッグを指定できます。  
  
 **TransportTypeData**のプロパティ、 **ITransportInfo**インターフェイスは必要ありません。 このプロパティを設定しない場合、アダプタでは、次の表に記載されている WCF-NetMsmq 送信ポートの構成の既定値が使用されます。  
  
 次の表に、BizTalk エクスプローラ オブジェクト モデルで WCF-NetMsmq 送信ポート用に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Identity**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName 値 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|この送信ポートが必要とするサービスの ID を指定します。 これらの設定により、この送信ポートでサービスを認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**StaticAction**|文字列|指定して、 **SOAPAction**送信メッセージのヘッダー フィールド。 このプロパティは、メッセージ コンテキスト プロパティからも設定できます**WCF です。アクション**パイプラインまたはオーケストレーションでします。 2 つの異なる方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式です。 シングル アクション形式 http://contoso.com/Svc/Op1-など、このプロパティを設定する場合、 **SOAPAction**ヘッダーは常に送信メッセージの値に設定、このプロパティで指定します。<br /><br /> 送信アクション マッピング形式でこのプロパティを設定する場合**SOAPAction**ヘッダーはによって決定されます、 **BTS です。操作**コンテキスト プロパティです。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**プロパティを Op1 に設定は、WCF 送信アダプタでは、http://contoso.com/Svc/Op1 を使用、送信を**SOAPAction**ヘッダー。<br /><br /> \<BtsActionMapping\><br /><br /> \<操作名"Op1"アクションを = ="http://contoso.com/Svc/Op1"/\><br /><br /> \<操作名"Op2"アクションを = ="http://contoso.com/Svc/Op2"/\><br /><br /> \</BtsActionMapping\><br /><br /> 送信メッセージには、オーケストレーション ポートから場合、オーケストレーション インスタンスは動的に設定、 **BTS です。操作**ポートの操作の名前を持つプロパティです。 コンテンツ ベースのルーティングと、送信メッセージのルーティングされる場合は、設定、 **BTS です。操作**パイプライン コンポーネントのプロパティです。<br /><br /> 既定値は空の文字列です。|  
|**OpenTimeout**|**System.TimeSpan**|チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**SendTimeout**|**System.TimeSpan**|送信操作が完了するまでの間隔を示す期間値を指定します。 送信請求 - 応答の送信ポートを使用する場合は、サービスから大きいメッセージが返される場合でも、この値には対話処理がすべて完了するまでの時間を指定します。<br /><br /> 既定値:00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**EnableTransactional**|ブール値|移動先のサービスのメッセージ キューの種類を指定します。 トランザクションまたは非トランザクションです。 このプロパティ設定されている場合**True**、この送信ポートによって処理される各メッセージが 1 回だけ配信され、送信者が配信エラー通知です。 トランザクション送信を経由してメッセージを送信するポートを両方とも、**持続性のある**と**exactlyOnce**バインド、サービスの要素に設定する必要があります**True**です。 このプロパティ設定されている場合**False**配信が保証されずにメッセージが転送されます。<br /><br /> 既定値:**は True。**|  
|**DeadLetterQueue**|Enum<br /><br /> -   **None** -使用する配信不能キューはありません。<br />-   **システム**-システム全体の配信不能キューを使用します。<br />-   **カスタム**-カスタム配信不能キューを使用します。|アプリケーションへの配信に失敗したメッセージの転送先となる配信不能キューを指定します。 配信不能キューに配信されたメッセージの詳細については、次を参照してください。、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。<br/><br/> **注**: カスタムの配信不能キューにのみでメッセージ キュー (MSMQ) 4.0 では、Windows Vista でリリースされたはサポートされています。 <br /><br /> 既定値:**システム**|  
|**CustomDeadLetterQueue**|文字列|完全修飾 URI を指定、 **net.msmq**アプリケーションごとの配信不能メッセージ キューの有効期限が切れているか、転送または配信に失敗したメッセージが置かれる場所のスキーム。 たとえば、net.msmq://localhost/deadLetterQueueName と指定します。 配信不能キューは、配信に失敗した期限切れのメッセージの送信アプリケーションのキュー マネージャのキューです。 このプロパティは必要な場合、 **DeadLetterQueue**プロパティに設定されている**カスタム**です。<br /><br /> 既定値は空の文字列です。|  
|**TimeToLive**|**System.TimeSpan**|メッセージが期限切れになり、配信不能キューに格納されるまでのメッセージが有効な期間を指定します。 このプロパティは、時間が重要な要素になるメッセージがこの送信ポートによって処理されるまで古くならないようにするために設定されます。 指定された時間間隔内にこの送信ポートによって処理されないキュー内のメッセージは、期限切れのメッセージといいます。 期限切れのメッセージは、配信不能キューと呼ばれる特別なキューに送信されます。 配信不能メッセージ キューの場所に設定されて、 **DeadLetterQueue**プロパティです。<br /><br /> 既定値: 1.00:00:00|  
|**UseSourceJournal**|ブール値|この送信ポートによって処理されるメッセージのコピーをソース ジャーナル キューに保存する必要があるかどうかを指定します。<br /><br /> 既定値: **False**|  
|**SecurityMode**|Enum<br /><br /> -   **[なし]**<br />-   **メッセージ**<br />-   **トランスポート**<br />-   **両方とも**<br /><br /> メンバー名の詳細については、 **SecurityMode**プロパティを参照してください、**セキュリティ モード**プロパティに、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|使用するセキュリティの種類を指定します。<br /><br /> 既定値:**トランスポート**|  
|**MsmqAuthenticationMode**|Enum<br /><br /> -   **[なし]**<br />-   **WindowsDomain**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MsmqAuthenticationMode**プロパティを参照してください、 **MSMQ 認証モード**プロパティに、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックスセキュリティを送信します。**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|MSMQ トランスポートによるメッセージの認証方法を指定します。<br /><br /> 既定値: **WindowsDomain**|  
|**MsmqProtectionLevel**|Enum<br /><br /> -   **None**: 保護されません。<br />-   **サインオン**: メッセージは署名されます。<br />-   **EncryptAndSign**: メッセージの暗号化および署名されます。 この保護レベルを使用する必要がありますを有効にした**Active Directory 統合**の**MSMQ**です。|MSMQ トランスポートのレベルでメッセージをセキュリティ保護する方法を指定します。<br /><br /> 既定値:**記号**|  
|**MsmqSecureHashAlgorithm**|Enum<br /><br /> -   **MD5**<br />-   **SHA1**<br />-   **SHA25**<br />-   **SHA512**|メッセージ ダイジェストの計算に使用するハッシュ アルゴリズムを指定します。 このプロパティは使用できない場合、 **MsmqProtectionLevel**プロパティに設定されている**None**です。<br /><br /> 既定値: **SHA1**|  
|**MsmqEncryptionAlgorithm**|Enum<br /><br /> -   **RC4Stream**<br />-   **AES**|メッセージ キュー マネージャー間でメッセージを転送するときに、有線ネットワーク上でメッセージを暗号化するために使用するアルゴリズムを指定します。 このプロパティは使用可能な場合にのみ、 **MsmqProtectionLevel**プロパティに設定されている**EncryptAndSign**です。<br /><br /> 既定値: **RC4Stream**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **[なし]**<br />-   **Windows**<br />-   **ユーザー名**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MessageClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のメッセージ**プロパティに、 **Wcf-netmsmq トランスポートのプロパティダイアログ ボックスの 送信セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。<br /><br /> 既定値: **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> メンバー名の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティに、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。<br /><br /> 既定値: **Basic256**|  
|**ClientCertificate**|文字列|この送信ポートをサービスに対して認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティは必要な場合、 **ClientCredentialsType**プロパティに設定されている**証明書**です。 このプロパティに使用する証明書をインストールする必要があります、 **My**に格納、**現在のユーザー**場所。<br /><br /> 既定値は空の文字列です。|  
|**ServiceCertificate**|文字列|この送信ポートのメッセージ送信先のサービスを認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティに使用する証明書をインストールする必要があります、**ほかの人**に格納、**ローカル マシン**場所。<br /><br /> 既定値は空の文字列です。|  
|**AffiliateApplicationName**|文字列|エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。<br /><br /> 既定値は空の文字列です。|  
|**UseSSO**|ブール値|接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。<br /><br /> 既定値: **False**|  
|**UserName**|文字列|移行先サーバーで認証に使用するユーザー名を指定するときに、 **UseSSO**プロパティに設定されている**False**です。 このプロパティでは domain\user 形式は使用できません。<br /><br /> 既定値は空の文字列です。|  
|**Password**|文字列|移行先サーバーでの認証を使用するパスワードを指定するときに、 **UseSSO**プロパティに設定されている**False**です。<br /><br /> 既定値は空の文字列です。|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ**本文**送信メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**送信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定**本文**送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation**プロパティに設定されている**UseTemplate**です。<br /><br /> 既定値は空の文字列です。|  
  
## <a name="configure-a-wcf-netmsmq-send-port-with-the-biztalk-administration-console"></a>BizTalk 管理コンソールで、Wcf-netmsmq 送信ポートを構成します。
  
 BizTalk 管理コンソールで、WCF-NetMsmq 送信ポート アダプタの変数を設定できます。 送信ポートのプロパティが設定されていない場合は、上の表に記載されている WCF-NetMsmq 送信ポートの構成の既定値が使用されます。  
  
## <a name="configure-variables-for-a-wcf-netmsmq-send-port"></a>Wcf-netmsmq 送信ポートの変数を構成します。  
  
1.  BizTalk 管理コンソールで、新しい送信ポートを作成するか、既存の送信ポートをダブルクリックして変更します。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定**Wcf-netmsmq**の**型**オプション、**トランスポート**のセクションで、**全般**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
2.  **全般**] タブの [、**トランスポート**セクションで、をクリックして、**構成**横に**型**です。  
  
3.  **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスの**全般** タブで、エンドポイント アドレス、サービス id を構成して、 **SOAPAction**ヘッダーをWcf-netmsmq 送信ポートです。 詳細については、**全般** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポート プロパティ] ダイアログ ボックスの [送信全般**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
4.  **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスの**バインド** タブで、タイムアウトおよびトランザクションのプロパティを構成し、キューに設定します。 詳細については、**バインド** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
5.  **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**セキュリティ** タブで、Wcf-netmsmq 送信ポートのセキュリティ機能を定義します。 詳細については、**セキュリティ** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
6.  **Wcf-netmsmq トランスポートのプロパティ** ダイアログ ボックスで、**メッセージ** タブで、SOAP のデータ選択を指定**本文**要素。 詳細については、**メッセージ** タブで、 **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、送信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
## <a name="configure-a-wcf-netmsmq-send-port-programmatically"></a>プログラムから Wcf-netmsmq 送信ポートを構成します。
  
 次の形式を使用してプロパティを設定できます。  
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <UseSSO vt="11">0</UseSSO>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <MsmqProtectionLevel vt="8">Sign</MsmqProtectionLevel>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <UseSourceJournal vt="11">0</UseSourceJournal>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <CustomDeadLetterQueue vt="8" />  
  <ClientCertificate vt="8" />  
  <MsmqEncryptionAlgorithm vt="8">RC4Stream</MsmqEncryptionAlgorithm>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <MsmqSecureHashAlgorithm vt="8">Sha1</MsmqSecureHashAlgorithm>  
  <EnableTransaction vt="11">-1</EnableTransaction>  
  <TimeToLive vt="8">1.00:00:00</TimeToLive>  
  <MsmqAuthenticationMode vt="8">WindowsDomain</MsmqAuthenticationMode>  
  <DeadLetterQueue vt="8">System</DeadLetterQueue>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 次のコードは、WCF-NetMsmq 送信ポートの作成方法を示しています。  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetMsmq send port.  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetMsmq"];  
sendPort.PrimaryTransport.Address = "net.msmq://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [Wcf-netmsmq アダプタを構成します。](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)