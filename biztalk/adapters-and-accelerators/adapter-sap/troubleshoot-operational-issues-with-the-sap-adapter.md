---
title: SAP アダプターの BizTalk で運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的なエラー、問題、および BizTalk アダプター パック (BAP) での mySAP アダプターを使用した解決策
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb0f005b-7548-478b-8243-69e07c29d02c
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c137b60c9c9a8c354baf39b91349e0836c94b91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998275"
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a>SAP アダプターを使用した運用上の問題をトラブルシューティングします。
このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。  
  
### <a name="enable-tracing"></a>トレースを有効にします。  
 トレースのサポートについては、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[診断トレースとメッセージ ログを SAP アダプターの](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)します。  
  
##  <a name="client_dll"></a> バインディングの読み込みエラー  
 **問題**  
  
 開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]GUI では、次のエラー。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 開始すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストールされているすべてのアダプターのアダプターのバインドを読み込みます。 さらに、アダプターのバインドは、エンタープライズ アプリケーションの特定のクライアント ソフトウェアに依存します。 この問題は次の理由の両方またはいずれかに直面する可能性があります。  
  
- アダプターがインストールされているコンピューターでは、必要な LOB クライアント ソフトウェアがインストールされていません。  
  
- 含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了した、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 ただし、1 つだけのエンタープライズ アプリケーション用に LOB クライアント ライブラリをインストールする場合があります。 その結果、GUI の他のアダプターのバインドの読み込みに失敗します。  
  
  **解決方法**  
  
- 必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。  
  
- 必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされているかどうかを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 [サポートされている LOB システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示します。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]も、SAP システムとのインターフェイスの特定の Dll が必要です。 アダプターに必要な Dll の詳細については、次を参照してください。 [Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。
  
##  <a name="BKMK_SAPDisplay"></a> SAP アダプターが BizTalk 管理コンソールではありません。  
 **問題**  
  
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]に含まれている[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF カスタム バインドします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
 **解決方法**  
  
 明示的に追加することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)します。  
  
##  <a name="BKMK_SAPConnOpen"></a> Dll の SAP への接続を開くときにエラーがないです。  
 **問題**  
  
 使用して SAP システムへの接続を開くしようとすると、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、いくつかの Dll が見つからないことを通知 ダイアログ ボックスは、SAP システムに表示されます。  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Librfc32u.dll を使用して、SAP システムとの接続を確立します。 さらに、librfc32u.dll には、関数を Dll のセットが必要です。 これらの Dll のサポートは、コンピューターの PATH 変数に追加されていない場合にこのエラーが発生した場所、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がインストールされています。  
  
 **解決方法**  
  
 解決方法として指定されたテーブルを参照してください、[アダプターのバインドを読み込み中にエラー](#client_dll)問題。 表は、サポートに使用して SAP システムとやり取りするために必要な Dll、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
##  <a name="BKMK_SAPXmlRetrieve"></a> 65,536 個を超えるノードを持つ XML を取得中にエラー  
 **問題**  
  
 アダプターは、65,536 を超えるノードを持つ XML 出力の取得中に、次のエラーを説明します。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 アダプターは、シリアル化し、65,536 を超える項目を含むオブジェクトを逆シリアル化できません。  
  
 **解決方法**  
  
 この問題を解決するには、設定して、`maxItemsInObjectGraph`で次の 2 つの方法のいずれかのパラメーター。  
  
- 変更することで、このパラメーターを設定、`maxItemsInObjectGraph`パラメーター、`ServiceBehavior`サービス クラスの属性。  
  
- 次のアプリケーションの app.config ファイルに追加します。  
  
  ```  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="NewBehavior">  
        <dataContractSerializer maxItemsInObjectGraph="65536000" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  ```  
  
  サンプルの app.config を次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
         <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <client>  
      <endpoint   behaviorConfiguration="NewBehavior" binding="sapBinding"  
       contract="IOutboundContract" name="sap_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
##  <a name="BKMK_SAPConnURI"></a> BizTalk Server で WCF カスタム ポートの接続 URI の入力エラー  
 **問題**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 接続、SAP システムに接続するための URI を指定する場合は、次のエラーを得られます。  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 **原因**  
  
 接続 URI は標準のエンコード形式に準拠していません。 たとえば、パラメーターの値にスペースを含めることがあります。  
  
 **解決方法**  
  
 指定した URI は、標準のエンコード形式に準拠する接続を確認します。 たとえば、"%20"を空白の領域を置き換える必要があります。  
  
##  <a name="BKMK_SAPOperate"></a> SAP に対する操作の完了中にエラーが System.ArgumentNullException  
 **問題**  
  
 使用して SAP システムに対して任意の操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 **原因**  
  
 メッセージの WCF アクションが指定されていません。 WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。  
  
 **解決方法**  
  
 送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [SAP システムの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)各操作のアクションの一覧を表示します。  
  
##  <a name="BKMK_SAPXmlParsing"></a> 指定したアクションで正しくない操作名により XmlReaderParsingException  
 **問題**  
  
 BizTalk Server 管理コンソールでの SAP システムにメッセージを送信するときに、次のエラー。  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 **原因**  
  
 によって作成されたポートのバインド ファイルをインポートして WCF カスタム ポートを構成する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートのアクションは、次の形式で指定されます。  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。 RFC_CUSTOMER_GET 用にスキーマを生成した場合など、アクションで操作名では、"RFC_CUSTOMER_GET"になります。 ただし、論理ポートの操作名が BizTalk のオーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。  
  
 **解決方法**  
  
 確実に操作名の両方の論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) (BizTalk Server 管理コンソール) で物理ポートが同じであるとします。  
  
##  <a name="BKMK_SAPHundredCons"></a> SAP に 100 を超える接続を開くときのエラー  
 **問題**  
  
 SAP システムに 100 を超える接続を開くときに、アダプターは、次の例外をスローします。  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 **原因**  
  
 既定では、SAP は、システムに 100 を超える接続を有効にできません。  
  
 **解決方法**  
  
 接続の最大数を増やすには、SAP クライアント ライブラリがインストールされているし、数値の値に設定されているコンピューターで環境変数を作成する必要があります。 この環境変数に指定した値は、SAP システムに可能な接続の最大数です。 次の内容で環境変数を作成します。  
  
- **変数名**: CPIC_MAX_CONV  
  
- **変数値**: 任意の正の数値。 たとえば、SAP システムに 200 の接続を有効にするには、200 として値を指定します。  
  
  環境変数を作成する方法の詳細については、次を参照してください。"で"Windows 2000 のシステム変数を作成する方法[ http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020)します。  
  
##  <a name="BKMK_SAPIDOCMetadata"></a> エラーを生成するか、Idoc のメタデータを取得します。  
 **問題**  
  
 メタデータを生成するときに、**受信**IDOC を SAP システムでの操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]というエラーが発生します。  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOCTYPE_READ_COMPLETE RFC を使用してメタデータを取得する、**受信**IDOC に対する操作。 この RFC を呼び出すと、SAP システムで特定のユーザーのアクセス許可が必要です。 IDOCTYPE_READ_COMPLETE RFC を呼び出すアクセス許可がない資格情報を使用して SAP システムに接続している場合、メタデータを生成する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エラーが発生しました。  
  
 **解決方法**  
  
 アダプターを使用したのと同じ資格情報を使用して、SAP GUI にログインします。 トランザクション SE37 に移動し、IDOCTYPE_READ_COMPLETE として実行するには、RFC の名前を入力します。  
  
 PI_IDOCTYP と PI_CIMTYP の入力パラメーターでは、カスタム IDoc に対応する値を入力します。 PI_VERSION と PI_RELEASE パラメーター、アダプター メタデータの UI で選ばれているとして同じ値を入力します。 実行には f8 キーを押します。  
  
 としてどのようなアダプターを受け取ると、問題に関する詳細情報を同じ例外が発生する必要があります。  
  
 それでも問題を解決できない場合は、スキーマを生成、 **ReceiveIdoc**操作の代わりに、**受信**操作。 この場合、SAP アダプターは IDOCTYPE_READ_COMPLETE を使用しないと、エラーをスローしません。  
  
##  <a name="BKMK_SAPIDOCReceive"></a> エラーを送信または受信するが解放されていないセグメントの Idoc  
 **問題**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で Idoc を送信中には、XmlReaderParsingException (を使用して**送信**操作) Idoc を受信するか (を使用して**受信**操作) が解放されていないセグメント。  
  
 **原因**  
  
 セグメントの Idoc を使用したされます。 メタデータの生成中に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムに存在するすべてのリリースされたセグメントを取得します。 など、IDOC の受信操作を実行するにアダプターのクライアントがメタデータを使用する場合に、ただし、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] XmlReaderParsingException を提供します。 これには、IDOC を受信すると、SAP システムがいくつか解放されていないセグメントも、対象のメタデータは、アダプターによって生成されませんでしたを送信がある可能性があるために発生します。  
  
 **解決方法**  
  
 次のいずれかを行います。  
  
-   解放されていないセグメントの適切な修正プログラムを適用することで、SAP システムをアップグレードします。  
  
-   使用**SendIdoc**または**ReceiveIdoc**操作を送信し、それぞれに Idoc を受信します。 これらの操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。  
  
##  <a name="BKMK_SAPIDOCSend"></a> Sap SAP FilePort で受信したフラット ファイル Idoc を送信するエラー  
 **問題**  
  
 送信しようとする場合 (を使用して**送信**操作) されるため、XML 形式に flatf ファイルを変換するフラット ファイル IDOC を SAP FilePort を使用して生成された SAP システムには、BizTalk オーケストレーションで、フラット ファイル パーサーの失敗、IDOD**送信**操作。  
  
 **原因**  
  
 SAP システムは、FilePort を使用して IDOC を生成するときは、セグメントの最後にすべての空白をトリムします。 ただし、フラット ファイル パーサーを正常にフラット ファイルを XML に変換するために、セグメントの最後のフィールドのデータが必要です。 空のスペースがセグメントに存在しないため、フラット ファイル パーサーが XML をフラット ファイルの解析に失敗します。  
  
 **解決方法**  
  
 フラット ファイル Idoc が SAP FilePort を使用して生成されたこのような使用、 **SendIdoc**操作代わりにします。 この操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a> EnableBizTalkCompatibilityMode プロパティが設定されている場合、SAP の Idoc を受信中にエラーを true に  
 **問題**  
  
 IDOC を受信中に、次の例外が発生した、 **EnableBizTalkCompatibilityMode**プロパティ セットを true にバインドします。  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 **原因**  
  
 場合、バインド プロパティ**EnableBizTalkCompatibilityMode**に設定されている**true**、BizTalk プロパティ スキーマ DLL を追加する必要がありますの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、つまり、BizTalk アプリケーションにリソースとして、プロジェクトがデプロイされているアプリケーション。  
  
 **解決方法**  
  
 BizTalk プロパティ スキーマの名前、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*します。 これには、インストールによって、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ\<インストール ドライブ\>: \Program files \microsoft BizTalk アダプター Pack\bin します。 このアセンブリを BizTalk アプリケーション内のリソースとして追加するには、次のタスクを実行します。  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a>BizTalk アプリケーションにリソースとしてアセンブリを追加します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーションでは、します。  
  
3. 展開**アプリケーション**と BizTalk アセンブリを追加するアプリケーション。  
  
4. 右クリック**リソース**、 をポイント**追加**、 をクリックし、 **BizTalk アセンブリ**します。  
  
5. クリックして**追加**、BizTalk アセンブリ ファイルを含むフォルダーに移動し、BizTalk アセンブリ ファイルを選択を順にクリックします**オープン**します。  
  
6. **オプション**、BizTalk アセンブリを GAC にインストールするためのオプションを指定し、クリックして**OK**します。  
  
##  <a name="BKMK_SAPIDOCValidate"></a> SAP システムから Idoc を受信中に検証エラー  
 **問題**  
  
 SAP システムから受信した IDOC には、次のようなエラーで検証が失敗します。  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 **原因**  
  
 IDOC を受信するために生成されたメタデータには、受信操作の一部として、特定の列用に受信することを指定できる値が含まれています。 これらの値は、生成されたメタデータ内の列挙型として公開されます。 ただし、IDOC が実際に受信されると、受信した値は、列挙値を異なる場合があります。 そのため、値の検証中に受信操作が失敗します。 たとえば、上記のエラーでは、TAXBS 列にメッセージの検証が失敗します。  
  
 **解決方法**  
  
 必要があります手動で編集する (BizTalk プロジェクト) のスキーマまたはクライアント プロキシで列挙型 (サービス モデルの WCF を使用して .NET プロジェクト) の SAP システムから受信した値を含める。  
  
##  <a name="BKMK_SAPFFIDOC"></a> フラット ファイル Idoc を前に、と後、XML への変換が同一でないです。  
 **問題**  
  
 フラット ファイル IDOC をスキーマを使用して XML に変換し、スキーマを使用して、パイプライン経由のフラット ファイル IDOC を XML に変換するフラット ファイル パーサーを使用する場合は 2 つのフラット ファイル Idoc が一致しません。  
  
 **原因**  
  
 XML フラット ファイル IDOC からを生成するときに、フラット ファイル パーサーが空白の値を持つ XML ノードを生成しません。 この XML は、フラット ファイルに変換するときに、XML から不足しているノードは、フラット ファイル IDOC に反映されません。 そのため、フラット ファイル Idoc が一致しません。  
  
 **解決方法**  
  
 フラット ファイルを XML、および「送信」または「受信」のノード定義内で、その逆に変換するために使用するスキーマで、次の手順を実行します。  
  
1. 設定、 **suppress_empty_nodes**プロパティを**false**設定と、 **generate_empty_nodes**プロパティを**true**します。 既定で、 **suppress_empty_nodes**プロパティに設定されて**true**と**generate_empty_nodes**プロパティに設定されて**false**とそのためすべての空のノードは、XML には反映されません。  
  
2. フラット ファイルには、末尾に余分な改行を含めることができます。 設定することができます、 **suppress_trailing_delimiters**プロパティを**はい**この余分なキャリッジ リターンを回避するためにします。 このプロパティも公開、**末尾の区切り記号の抑制**プロパティ内のスキーマを開く場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
##  <a name="BKMK_SAPAction"></a> バインド ファイルと共に作成する物理ポートを使用して、誤った操作エラー  
 **問題**  
  
 使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SAP システムで特定の操作のスキーマを生成するアドインも作成ポートのバインド ファイル。 インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server で物理ポートを作成します。 ただし、このようなポートを使用して SAP システムにメッセージを送信するとき、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk オーケストレーションでの論理ポートを作成するときにこれらのポートの操作に特定の名前を指定または Operation_1、Operation_2 などのように既定の名前を使用します。ただし、によって生成されたバインド ファイルで、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する操作の名前と同じです。 たとえば、RFC_CUSTOMER_GET のメタデータを生成する場合に、次のアクションは設定されます。  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 バインド ファイルをインポートすると、物理ポートで同じアクションが設定されます。 そのため、論理ポート (Operation_1、Operation_2 など) の操作名では、エラーが発生する物理ポートで、アクションで指定された操作名が一致しません。  
  
 **解決方法**  
  
 論理ポートで操作の名前は、物理ポートにアクションの一部として指定された操作名と同じことを確認します。 次のいずれかの操作を行います。  
  
-   RFC_CUSTOMER_GET などのメタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートの操作名を変更します。  
  
-   論理ポートで、操作名に物理ポートのアクションで、操作名を変更します。 たとえば、次のように物理ポートにアクションを変更できます。  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a> 応答メッセージにはで SAP 操作が実行されたが含まれていないテーブル パラメーターには  
 **原因**  
  
 使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでの操作を実行する多数のテーブルを返すし、各テーブルには、SAP システムからの応答メッセージの一部として返される大規模なデータセットに金額は、レコードの数が多い。 既定で、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答メッセージの一部としてテーブル パラメーターは返されません。  
  
 **解決方法**  
  
 追加するテーブルを要求する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答の一部として返すにします。 SAP システムに送信する要求メッセージの一部として、空のテーブルのパラメーターを提供することで行うことができます。 たとえば、 `<table_parameter_name />`のようにします。  
  
##  <a name="BKMK_SAPIncorrectCreds"></a> アダプター クライアントは、SAP からの応答を受け取りません
 **問題**  
  
 アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、資格情報、wcf-custom 送信ポートが正しくない要求メッセージは処理されません。 正しい資格情報を指定した後、SAP システムにメッセージを送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。  
  
 **解決方法**  
  
 BizTalk ホスト インスタンスを再起動します。  
  
##  <a name="BKMK_SAPInboundConn"></a> SAP サーバーから受信メッセージの受信接続の問題  
 **問題**  
  
 WCF カスタムを使用して、SAP サーバーからの受信メッセージの受信ポートを受信中にのみ、次のエラーが発生した、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 ただしは、正常に送信ポートの WCF カスタムを使用して SAP システムへのメッセージを送信できます。  
  
 **解決方法**  
  
 アダプター クライアントを実行し、受信メッセージの受信をもう一度お試しください。 場所は、同じコンピューターには、SAP GUI をインストールします。 SAP GUI をインストールする方法の詳細については、SAP のマニュアルを参照してください。  
  
##  <a name="BKMK_SAPRootNode"></a> BizTalk プロジェクト内の RootNode TypeName とエラー  
 **問題**  
  
 BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決方法**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。  
  
##  <a name="BKMK_SAPVS2008"></a> Visual Studio で、アダプターを使用する際に無効なバインド警告  
 **問題**  
  
 Visual Studio でアプリケーションを作成するアダプターを使用すると、アダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド、`sapBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。  
  
 **解決方法**  
  
 この警告は無視してかまいません。  
  
##  <a name="BKMK_SAPSimilarSchema"></a> BizTalk Server での XLANG 例外
 **問題**  
  
 BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかの原因で発生します。  
  
- 1 つ以上を生成した (SendIdoc ReceiveIdoc など)、BizTalk Server プロジェクト内の汎用的な操作のスキーマを BizTalk Server アプリケーションに展開し、SAP システムのそれぞれの操作を実行するアプリケーションを実行します。 競合が、スキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
- 複数のプロジェクトが発生した場合の各 BizTalk Server プロジェクトの一般的な操作のスキーマを生成、各プロジェクトを同じ BizTalk Server アプリケーション ホスト、および、実行、またはアプリケーションを実行するそれぞれの個別にデプロイSAP システムに対する操作。 競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。  
  
  **解決方法**  
  
  BizTalk Server アプリケーションの 1 つの一般的な操作のスキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで汎用的な操作のスキーマを使用する必要がある場合は、1 つの汎用操作スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションからジェネリック操作のスキーマを使用します。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)