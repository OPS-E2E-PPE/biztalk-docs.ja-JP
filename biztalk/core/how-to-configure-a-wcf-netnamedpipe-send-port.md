---
title: Wcf-netnamedpipe 送信ポートを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57684e09-1f72-4bde-976c-3fcec65dc182
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed9b2138aaad8c2cccb60d75d7331c2331eeddc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-port"></a>WCF-NetNamedPipe 送信ポートを構成する方法
WCF-NetNamedPipe 送信ポートは、プログラムから、または BizTalk 管理コンソールを使用して構成できます。  
  
## <a name="configuration-properties"></a>構成プロパティ
  
 BizTalk エクスプ ローラー オブジェクト モデルがという名前の送信ポートのアダプターに固有のインターフェイスを公開する **ITransportInfo** を持つ、 **TransportTypeData** 読み取り/書き込みプロパティです。 このプロパティでは、名前と値の組の XML 文字列の形式で WCF-NetNamedPipe 送信ポートの構成プロパティ バッグを指定できます。  
  
 **TransportTypeData** のプロパティ、 **ITransportInfo** インターフェイスは必要ありません。 このプロパティを設定しない場合は、次の表に記載されている WCF-NetNamedPipe 送信ポートの構成の既定値がアダプタで使用されます。  
  
 次の表に、BizTalk エクスプローラ オブジェクト モデルで WCF-NetNamedPipe 送信ポート用に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Id**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt;|この送信ポートが必要とするサービスの ID を指定します。 これらの設定により、この送信ポートでサービスを認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**StaticAction**|文字列|指定の **SOAPAction** 送信メッセージのヘッダー フィールドです。 このプロパティは、メッセージ コンテキスト プロパティからは設定も **WCF です。アクション** パイプラインまたはオーケストレーションします。 2 つの方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式です。 たとえば、シングル アクション形式にこのプロパティを設定する場合http://contoso.com/Svc/Op1-、 **SOAPAction**ヘッダーは常に送信メッセージの値に設定、このプロパティで指定します。<br /><br /> 送信アクション マッピング形式でこのプロパティを設定した場合 **SOAPAction** によってヘッダーが決定、 **BTS します。操作** コンテキスト プロパティです。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**を Op1 に設定されているプロパティ、WCF 送信アダプタを使用してhttp://contoso.com/Svc/Op1アウトゴーイング**SOAPAction**ヘッダー。<br /><br /> \<BtsActionMapping\><br /><br /> \<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /\><br /><br /> \<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> 送信メッセージは、オーケストレーション ポートから送られてきた場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作** ポートの操作の名前を持つプロパティです。 コンテンツ ベースのルーティングと送信メッセージがルーティングされる場合は、設定、 **BTS します。操作** パイプライン コンポーネントのプロパティです。<br /><br /> 既定値は空の文字列です。|  
|**Opentimeout します。**|**System.TimeSpan**|チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値: 00時 01分: 00|  
|**SendTimeout**|**System.TimeSpan**|送信操作が完了するまでの間隔を示す期間値を指定します。 送信請求 - 応答の送信ポートを使用する場合は、サービスから大きいメッセージが返される場合でも、この値には対話処理がすべて完了するまでの時間を指定します。<br /><br /> 既定値:00:01:00|  
|**Closetimeout します。**|**System.TimeSpan**|チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00|  
|**MaxReceivedMessageSize**|Integer|有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。<br /><br /> 既定値:65536|  
|**EnableTransaction**|ブール値|メッセージが転送先サービスに転送され、トランザクション コンテキストを使用してメッセージ ボックス データベースから削除するかどうかを指定する、 **Ws-atomictransaction** プロトコルです。<br /><br /> 既定値: **False**|  
|**TransactionProtocol**|Enum<br /><br /> -   **OleTransaction**<br />-   **Ws-atomictransaction**|このバインドで使用するトランザクション プロトコルを指定します。<br /><br /> 既定値: **OleTransaction**|  
|**SecurityMode**|Enum<br /><br /> -   **None**-セキュリティを無効にします。<br />-   **トランスポート**: の基になるトランスポート ベース セキュリティを使用してセキュリティを提供します。 このモードでは保護レベルを制御することができます。|使用するセキュリティの種類を指定します。<br /><br /> 既定値: **トランスポート**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **None** -保護されません。<br />-   **記号** -メッセージが署名されます。<br />-   **EncryptAndSign** -メッセージの暗号化および署名されます。|名前付きパイプの保護レベルを指定します。 メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。 暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。<br /><br /> 既定値: **EncryptAndSign**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ **本文** 、送信メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 送信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定 **本文** 、送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation** プロパティに設定されて **UseTemplate**します。<br /><br /> 既定値は空の文字列です。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成 **エンベロープ** 受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression** プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直下の子要素に対して評価されます **本文** 受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** の Base64 エンコードします。<br />-   **16 進** : 16 進エンコードします。<br />-   **文字列** : テキスト エンコード - utf-8。<br />-   **XML** の WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で BizTalk メッセージ本文を作成する **InboundBodyPathExpression**します。|指定されたボディ パスで識別されるノードに対して、Wcf-netnamedpipe 送信アダプターがデコードに使用するエンコードの種類を指定 **InboundBodyPathExpression**します。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **XML**|  
|**PropagateFaultMessage**|ブール値<br /><br /> -   **True**にサブスクライブしているアプリケーションへの送信処理に失敗したメッセージのルーティング (別の受信ポートやオーケストレーション スケジュールなど)。<br />-   **False** -中断失敗したメッセージおよび否定受信確認応答 (NACK) を生成します。|送信処理に失敗したメッセージをルーティングまたは中断するかどうかを指定します。<br /><br /> このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **は True。**|  
  
## <a name="configure-a-wcf-netnamedpipe-send-port-with-the-biztalk-administration-console"></a>BizTalk 管理コンソールで、Wcf-netnamedpipe 送信ポートを構成します。
  
 BizTalk 管理コンソールで、WCF-NetNamedPipe 送信ポート アダプタの変数を設定できます。 プロパティが送信ポートに設定されていない場合は、前の表に記載されている WCF-NetNamedPipe 送信ポートの構成の既定値が使用されます。  
  
## <a name="configure-variables-for-a-wcf-netnamedpipe-send-port"></a>Wcf-netnamedpipe 送信ポートの変数を構成します。  
  
1.  BizTalk 管理コンソールで、新しい送信ポートを作成するか、既存の送信ポートをダブルクリックして変更します。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定 **Wcf-netnamedpipe** の **型** オプション、 **トランスポート** のセクション、 **全般**  タブをクリックします。  
  
2.  **全般**  タブの 、 **トランスポート**  をクリックして、 **構成** ボックスの横に **型**します。  
  
3.  **Wcf-netnamedpipe トランスポートのプロパティ**  ダイアログ ボックスの 、 **全般**  タブで、エンドポイント アドレス、サービス id を構成して、 **SOAPAction** ヘッダーを Wcf-netnamedpipe 送信ポート。 詳細については、**全般** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポート プロパティ] ダイアログ ボックスの [送信[全般]**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
4.  **Wcf-netnamedpipe トランスポートのプロパティ**  ダイアログ ボックスの 、 **バインド**  タブで、タイムアウトおよびトランザクションのプロパティを構成します。 詳細については、**バインド** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
5.  **Wcf-netnamedpipe トランスポートのプロパティ**  ダイアログ ボックスの 、 **セキュリティ**  タブで、Wcf-netnamedpipe 送信ポートのセキュリティ機能を定義します。 詳細については、**セキュリティ** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
6.  **Wcf-netnamedpipe トランスポートのプロパティ**  ダイアログ ボックスで、 **メッセージ**  タブで、SOAP のデータ選択を指定 **本文** 要素。 詳細については、**メッセージ** タブで、 **Wcf-netnamedpipe トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-netnamedpipe トランスポートのプロパティ ダイアログ ボックス、送信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="configure-a-wcf-netnamedpipe-send-port-programmatically"></a>プログラムから Wcf-netnamedpipe 送信ポートを構成します。
  
 次の形式を使用してプロパティを設定できます。  
  
```  
<CustomProps>  
  <TransportProtectionLevel vt="8">EncryptAndSign</TransportProtectionLevel>  
  <TransactionProtocol vt="8">OleTransactions</TransactionProtocol>  
  <InboundBodyPathExpression vt="8" />  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
</CustomProps>  
  
```  
  
 次のコードは、WCF-NetNamedPipe 送信ポートの作成方法を示しています。  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetNamedPipe send port.  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetNamedPipe"];  
sendPort.PrimaryTransport.Address = "net.pipe://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [Wcf-netnamedpipe アダプタを構成します。](../core/configuring-the-wcf-netnamedpipe-adapter.md)   
 [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)