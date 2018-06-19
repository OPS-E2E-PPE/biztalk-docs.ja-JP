---
title: Wcf-netnamedpipe 受信場所を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2e8242a-64c7-43de-af5e-25c22e182c72
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29c52e8a92a842958ed9d4dcf30f7b02eedfa749
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250570"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-location"></a>WCF-NetNamedPipe 受信場所を構成する方法
WCF-NetNamedPipe 受信場所は、プログラムから、または BizTalk 管理コンソールを使用して構成できます。  
  
## <a name="configuration-properties"></a>構成プロパティ
  
 BizTalk エクスプローラー オブジェクト モデルにより、プログラムから受信場所を作成および構成することができます。 BizTalk エクスプ ローラー オブジェクト モデルは、公開、**という**受信場所の構成インターフェイスを持つ、 **TransportTypeData**読み取り/書き込みプロパティです。 このプロパティでは、名前と値を組み合わせた XML 文字列の形式で WCF-NetNamedPipe 受信場所の構成プロパティ バッグを指定できます。 BizTalk エクスプローラ オブジェクト モデルでこのプロパティを設定に設定する必要があります、 **InboundTransportLocation**のプロパティ、**という**インターフェイスです。  
  
 **TransportTypeData**のプロパティ、**という**インターフェイスを設定する必要はありません。 このプロパティを設定しない場合、WCF-NetNamedPipe アダプタでは、次の表に記載されている WCF-NetNamedPipe 受信場所の構成の既定値が使用されます。  
  
 次の表に、BizTalk エクスプローラのオブジェクト モデルで WCF-NetNamedPipe 受信場所用に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Identity**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName 値 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|この受信場所が提供するサービスの ID を指定します。 指定できる値、 **Identity**プロパティが、セキュリティ構成によって異なります。 これらの設定により、クライアントはこの受信場所を認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**OpenTimeout**|**System.TimeSpan**|チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**SendTimeout**|**System.TimeSpan**|送信操作が完了するまでの間隔を示す期間値を指定します。 要求 - 応答受信ポートを使用する場合、この値は、対話処理がすべて完了するまでの時間を指定します。これは、クライアントが大きなメッセージを返した場合にも適用されます。<br /><br /> 既定値:00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**MaxReceivedMessageSize**|Integer|有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。<br /><br /> 既定値:65536|  
|**EnableTransaction**|ブール値|クライアントから流れてくるトランザクションを使用してメッセージをメッセージ ボックス データベースに送信するかどうかを指定します。 このプロパティ設定されている場合**True**、クライアントがで指定されているトランザクション プロトコルを使用してメッセージを送信するために必要な**TransactionProtocol**プロパティです。 クライアントがトランザクション スコープの外側のメッセージを送信した場合、この受信場所によって例外がクライアントに返され、メッセージは保留されません。<br /><br /> オプションは、一方向の受信場所に対してのみ使用できます。 クライアントが要求 - 応答の受信場所に対するトランザクション コンテキスト内でメッセージを送信した場合、例外がクライアントに返され、メッセージは保留されません。<br /><br /> 既定値:`False`|  
|**TransactionProtocol**|Enum<br /><br /> -   **[Oletransaction]**<br />-   **Ws-atomictransaction**|この受信場所で使用するトランザクション プロトコルを指定します。<br /><br /> 既定値: **[oletransaction]**|  
|**MaxConcurrentCalls**|Integer|単一のサービス インスタンスに対する同時呼び出しの数を指定します。 制限を超える呼び出しはキューに格納されます。 このプロパティの最小値は 1、最大値は Int32.MaxValue です。<br /><br /> 既定値:200|  
|**SecurityMode**|Enum<br /><br /> -   **None**: セキュリティが無効になります。<br />-   **トランスポート**: トランスポート ベースのセキュリティを基になるを使用してセキュリティを提供します。 このモードでは保護レベルを制御することができます。|使用するセキュリティの種類を指定します。<br /><br /> 既定値:**トランスポート**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **None**: 保護されません。<br />-   **サインオン**: メッセージは署名されます。<br />-   **EncryptAndSign**: メッセージの暗号化および署名されます。|TCP トランスポートのレベルでセキュリティを定義します。 メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。 暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。<br /><br /> 既定値: **EncryptAndSign**|  
|**UseSSO**|ブール値|エンタープライズ シングル サインオン (SSO) を使用して SSO チケットを発行するためにクライアントの資格情報を取得するかどうかを指定します。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成する**エンベロープ**受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression**プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直接の子要素に対して評価されます**本文**受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 エンコードします。<br />-   **16 進**: 16 進エンコードします。<br />-   **文字列**: テキスト エンコード - utf-8。<br />-   **XML** -WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で、BizTalk メッセージ本文を作成する**InboundBodyPathExpression**です。|Wcf-netnamedpipe 受信アダプターで指定されたボディ パス式で識別されるノードのデコードに使用するエンコードの種類の指定**InboundBodyPathExpression**です。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。<br /><br /> 既定値: **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信応答メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ**本文**送信応答メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**送信 WCF メッセージの要素。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定**本文**送信応答メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation**プロパティに設定されている**UseTemplate**です。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 既定値は空の文字列です。|  
|**SuspendMessageOnFailure**|ブール値|受信パイプラインまたはルーティングの障害によって受信処理に失敗した要求メッセージを保留するかどうかを指定します。<br /><br /> 既定値:**は True。**|  
|**IncludeExceptionDetailInFaults**|ブール値|デバッグの目的でクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めるかどうかを指定します。<br /><br /> 既定値: **False**|  
  
## <a name="configure-a-wcf-netnamedpipe-receive-location-with-the-biztalk-administration-console"></a>Wcf-netnamedpipe を構成する BizTalk 管理コンソールでの受信場所
  
 WCF-NetNamedPipe 受信場所のアダプタ変数は、BizTalk 管理コンソールで設定できます。 プロパティが受信場所に設定されていない場合は、BizTalk 管理コンソールで設定された既定の受信ハンドラーの値が使用されます。  
  
> [!NOTE]
>  次の手順を実行する前に、受信ポートを追加する必要があります。 詳細については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。  
  
## <a name="configure-variables-for-a-wcf-netnamedpipe-receive-location"></a>Wcf-netnamedpipe 受信場所の変数を構成します。  
  
1.  BizTalk 管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、し、受信場所を作成するアプリケーションを展開します。  
  
2.  BizTalk 管理コンソールの左側のウィンドウで、[ **受信ポート** ] ノードをクリックします。 次に右ウィンドウで、既存の受信場所に関連付けられているか、新しい受信場所に関連付ける受信ポートを右クリックし、 **プロパティ**をクリックします。  
  
3.  **受信ポートのプロパティ**ダイアログ ボックスで、左ペインで、select、**受信場所**、右側のペインをダブルクリックして、既存の受信場所またはをクリックし **新規**新しい受信場所を作成します。  
  
4.  **受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**横**型**[ **Wcf-netnamedpipe**から、クリックしてドロップダウン リスト、**構成**です。  
  
5.  **Wcf-netnamedpipe トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、エンドポイント アドレスを構成し、サービス id を Wcf-netnamedpipe 受信場所。 詳細については、**全般** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポートのプロパティ ダイアログ ボックス、受信の [全般]** タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
6.  **Wcf-netnamedpipe トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで、タイムアウトおよびトランザクションのプロパティを構成します。 詳細については、**バインド** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポートのプロパティ ダイアログ ボックス、受信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
7.  **Wcf-netnamedpipe トランスポートのプロパティ** ダイアログ ボックスで、**セキュリティ** タブで、セキュリティを定義、Wcf-netnamedpipe の機能の受信場所。 詳細については、**セキュリティ** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポートのプロパティ ダイアログ ボックス、受信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
8.  **Wcf-netnamedpipe トランスポートのプロパティ** ダイアログ ボックスで、**メッセージ** タブで、SOAP のデータ選択を指定**本文**要素。 詳細については、**メッセージ** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポートのプロパティ ダイアログ ボックス、受信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="configure-a-wcf-netnamedpipe-receive-location-programmatically"></a>構成、Wcf-netnamedpipe 受信場所をプログラムで
  
 これらのプロパティを設定するには、以下の形式を使用します。  
  
```  
<CustomProps>  
  <UseSSO vt="11">0</UseSSO>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundBodyPathExpression vt="8" />  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <TransactionProtocol vt="8">WSAtomicTransactions</TransactionProtocol>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <TransportProtectionLevel vt="8">EncryptAndSign</TransportProtectionLevel>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <EnableTransaction vt="11">-1</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <MaxConcurrentCalls vt="3">16</MaxConcurrentCalls>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 次のコードは、WCF-NetNamedPipe 受信場所の作成方法を示しています。  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetNamedPipe receive location   
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
// Find a receive handler for WCF-NetNamedPipe   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-NetNamedPipe" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.pipe://mycomputer/samplePipeName";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-NetNamedPipe"];  
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
 [Wcf-netnamedpipe アダプタを構成します。](../core/configuring-the-wcf-netnamedpipe-adapter.md)