---
title: "SAP アダプターの BizTalk での運用上の問題のトラブルシューティング |Microsoft ドキュメント"
description: "一般的なエラーの問題、および mySAP アダプターの BizTalk アダプター パック (BAP) と解像度"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb0f005b-7548-478b-8243-69e07c29d02c
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5298782f23cb8c7c32a2bcbd512f3a1b78f8a69d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a>SAP アダプターでの運用上の問題をトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。  
  
### <a name="enable-tracing"></a>トレースを有効にします。  
 トレースのサポートについては、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[診断トレースとメッセージ ログを SAP アダプターの](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)します。  
  
##  <a name="client_dll"></a>バインディングの読み込みエラー  
 **問題**  
  
 起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]GUI では、次のエラー。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 開始すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストールされているすべてのアダプターのアダプターのバインドを読み込みます。 一方、アダプターのバインドは、エンタープライズ アプリケーション用の特定のクライアント ソフトウェアに依存します。 次の理由の一方または両方について、この問題に直面する可能性があります。  
  
-   必要な LOB クライアント ソフトウェアは、アダプターがインストールされているコンピューターにインストールされていません。  
  
-   含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了したとき、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 ただし、1 つだけのエンタープライズ アプリケーションに LOB クライアント ライブラリをインストールする可能性があります。 その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。  
  
 **解決策**  
  
-   必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。  
  
-   必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 [サポートされている LOB システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示します。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]も SAP システムとのインターフェイスの特定の Dll が必要です。 アダプターで必要な Dll の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。
  
##  <a name="BKMK_SAPDisplay"></a>SAP アダプターが BizTalk 管理コンソールではありません。  
 **問題**  
  
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]に含まれている[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF カスタム バインドがします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
 **解決策**  
  
 明示的に追加することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。  
  
##  <a name="BKMK_SAPConnOpen"></a>Dll の SAP への接続を開くときにエラーがないです。  
 **問題**  
  
 使用して SAP システムへの接続を開くしようとすると、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、いくつかの Dll が欠落していることを通知 ダイアログ ボックスは、SAP システムに表示されます。  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Librfc32u.dll を使用して SAP システムとの接続を確立します。 さらに、librfc32u.dll には、関数への Dll のセットが必要です。 これらの Dll のサポートが、コンピューター上のパス変数に追加されていない場合、このエラーを取得する場所、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がインストールされています。  
  
 **解決策**  
  
 解決策としては、表を参照してください、[アダプターのバインドを読み込み中にエラー](#client_dll)問題です。 表は、サポートされる SAP システムを使用するとのやり取りに必要な Dll、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
##  <a name="BKMK_SAPXmlRetrieve"></a>65,536 個を超えるノードを持つ XML を取得中にエラー  
 **問題**  
  
 アダプターは、65,536 個を超えるノードを持つ XML 出力を取得中に、次のエラーを説明します。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 アダプターは、シリアル化して、65,536 個を超える項目を含むオブジェクトを逆シリアル化できません。  
  
 **解決策**  
  
 この問題を解決するには、設定、`maxItemsInObjectGraph`次の 2 つの方法のいずれかのパラメーター。  
  
-   このパラメーターを変更することによって設定、`maxItemsInObjectGraph`内のパラメーター、`ServiceBehavior`サービス クラスの属性です。  
  
-   次のアプリケーションの app.config ファイルに追加します。  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 サンプルの app.config は、次のようになります。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  \<system.serviceModel>  
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
  \</system.serviceModel>  
</configuration>  
```  
  
##  <a name="BKMK_SAPConnURI"></a>BizTalk Server で WCF カスタム ポートの接続 URI を入力するエラー  
 **問題**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接続の SAP システムへの接続に URI を指定する場合は、次のエラーを示します。  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 **原因**  
  
 接続 URI は、標準のエンコード形式には従っていません。 たとえば、パラメーターの値にスペースを含めることがあります。  
  
 **解決策**  
  
 接続を指定する URI は、標準のエンコード形式に準拠して確認します。 たとえば、"%20"空白を置き換える必要があります。  
  
##  <a name="BKMK_SAPOperate"></a>SAP に対する操作の完了中にエラーが System.ArgumentNullException  
 **問題**  
  
 SAP システムを使用して、任意の操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 **原因**  
  
 メッセージの WCF アクションが指定されていません。 WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。  
  
 **解決策**  
  
 送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [SAP システムの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)です。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)各操作のアクションの一覧を表示します。  
  
##  <a name="BKMK_SAPXmlParsing"></a>指定されたアクション名が正しくない操作 XmlReaderParsingException  
 **問題**  
  
 BizTalk Server 管理コンソールは、SAP システムにメッセージを送信するときに、次のエラーを示します。  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 **原因**  
  
 によって作成されたポートのバインド ファイルをインポートすることによって、WCF カスタム ポートを構成する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートのアクションは、次の形式で指定されます。  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。 RFC_CUSTOMER_GET に対してスキーマを生成する場合など、アクションで操作名では、"RFC_CUSTOMER_GET"になります。 ただし、論理ポートにある操作名で BizTalk オーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。  
  
 **解決策**  
  
 確認操作名の両方、論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) (BizTalk Server 管理コンソール) での物理ポートは同じです。  
  
##  <a name="BKMK_SAPHundredCons"></a>SAP に 100 を超える接続を開くときのエラー  
 **問題**  
  
 アダプターは、SAP システムに 100 を超える接続を開く際に、次の例外をスローします。  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 **原因**  
  
 既定では、SAP は、システムに 100 を超える接続を有効にできません。  
  
 **解決策**  
  
 接続の最大数を増やすには、SAP クライアント ライブラリがインストールされ、値を数値に設定をあるコンピューター上で環境変数を作成する必要があります。 この環境変数に指定した値は、SAP システムに変更できる接続の最大数です。 次の内容で、環境変数を作成します。  
  
-   **変数名**: CPIC_MAX_CONV  
  
-   **変数値**: 任意の正の数値。 たとえば、SAP システムに 200 の接続を有効にするには、200 として値を指定します。  
  
 環境変数を作成する方法の詳細については、次を参照してください。「How To Windows 2000 でのシステム変数の作成」で[http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020)です。  
  
##  <a name="BKMK_SAPIDOCMetadata"></a>エラーを生成するか、Idoc のメタデータを取得します。  
 **問題**  
  
 メタデータを生成するときに、**受信**、IDOC を SAP システムでの操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]というエラーが発生します。  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOCTYPE_READ_COMPLETE RFC を使用してのメタデータを取得する、**受信**IDOC に対する操作です。 この RFC を呼び出すと、SAP システムで特定のユーザー権限が必要です。 メタデータを生成する、IDOCTYPE_READ_COMPLETE RFC を呼び出すためのアクセス許可がない資格情報を使用して SAP システムに接続している場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エラーが発生しました。  
  
 **解決策**  
  
 アダプターを使用した同じ資格情報を使用して、SAP GUI にログインします。 トランザクション SE37 に移動し、IDOCTYPE_READ_COMPLETE として実行するには、RFC の名前を入力します。  
  
 入力パラメーター PI_IDOCTYP PI_CIMTYP、カスタム IDoc に対応する値を入力します。 パラメーター PI_VERSION および PI_RELEASE、アダプター メタデータの UI で選択されていると同じ値を入力します。 実行に f8 キーを押します。  
  
 どのようなアダプターを受け取ると、問題に関する詳細な情報として、同じ例外を取得する必要があります。  
  
 それでも問題を解決できない場合は、スキーマを生成、 **ReceiveIdoc**操作の代わりに、**受信**操作します。 ここでは、SAP アダプターは IDOCTYPE_READ_COMPLETE を使用しないと、エラーをスローしません。  
  
##  <a name="BKMK_SAPIDOCReceive"></a>エラーの送信または受信するが解放されていないセグメントの Idoc  
 **問題**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc の送信中に、XmlReaderParsingException を示します (を使用して**送信**操作) Idoc を受信または (を使用して**受信**操作) が解放されていないセグメント。  
  
 **原因**  
  
 Idoc はセグメントの角形で構成します。 メタデータの生成中に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムに存在するすべてのリリースのセグメントを取得します。 ただし、ときに、アダプターのクライアントはメタデータを使用、IDOC の受信などの操作を実行する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] XmlReaderParsingException を提供します。 これは、IDOC を受信すると、SAP システムが送信されることがいくつか解放されていないセグメント同様に、対象のメタデータは、アダプターによって生成されなかったために発生します。  
  
 **解決策**  
  
 次のいずれかを行います。  
  
-   解放されていないセグメントの適切な修正プログラムを適用することで、SAP システムをアップグレードします。  
  
-   使用して**SendIdoc**または**ReceiveIdoc**操作を送信し、それぞれの Idoc を受信します。 これらの操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。  
  
##  <a name="BKMK_SAPIDOCSend"></a>フラット ファイル Idoc を SAP FilePort で受信した SAP に送信中にエラー  
 **問題**  
  
 送信しようとする場合 (を使用して**送信**操作) flatf ファイルを失敗したため、XML 形式に変換するフラット ファイル IDOC を SAP FilePort を使用して生成された SAP システムには、BizTalk オーケストレーションで、フラット ファイル パーサーは失敗しますIDOD**送信**操作します。  
  
 **原因**  
  
 SAP システムは、FilePort を使用して、IDOC を生成するとき、セグメントの末尾のすべての空白をトリムします。 ただし、フラット ファイル パーサーでは、XML にフラット ファイルを正常に変換するには、存在するセグメントの最後のフィールドのデータが必要です。 空のスペースは、セグメント内に存在できないため、XML にフラット ファイルの解析をフラット ファイル パーサーは失敗します。  
  
 **解決策**  
  
 フラット ファイル Idoc が SAP FilePort を使用して生成されたこのような使用、 **SendIdoc**操作代わりにします。 この操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a>EnableBizTalkCompatibilityMode プロパティが設定されている場合、SAP からの Idoc を受信中にエラーを true に  
 **問題**  
  
 IDOC を受信中に、次の例外が発生した、 **EnableBizTalkCompatibilityMode**プロパティ セットを true にバインドします。  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 **原因**  
  
 場合、バインディング プロパティ**EnableBizTalkCompatibilityMode**に設定されている**true**、BizTalk プロパティ スキーマ DLL を追加する必要がありますの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、つまり、BizTalk アプリケーションにリソースとして、プロジェクトを配置するアプリケーション。  
  
 **解決策**  
  
 BizTalk プロパティ スキーマの名前、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*です。 これには、インストールによって、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]下にあるセットアップ\<インストール ドライブ >: \プログラム \microsoft BizTalk アダプター Pack\bin です。 このアセンブリを BizTalk アプリケーションにリソースとして追加する、次のタスクを実行します。  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a>BizTalk アプリケーションにリソースとしてアセンブリを追加します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーション、します。  
  
3.  展開**アプリケーション**および BizTalk アセンブリを追加するアプリケーション。  
  
4.  右クリック**リソース**、 をポイント**追加**、クリックして**BizTalk アセンブリ**です。  
  
5.  をクリックして**追加**は、BizTalk アセンブリ ファイルを含むフォルダーに移動し、BizTalk アセンブリ ファイルを選択し、をクリックして**開く**です。  
  
6.  **オプション**、GAC に BizTalk アセンブリをインストールするためのオプションを指定し、クリックして**OK**です。  
  
##  <a name="BKMK_SAPIDOCValidate"></a>SAP システムから Idoc を受信中に検証のエラー  
 **問題**  
  
 SAP システムから受信した IDOC には、次のようなエラーで検証が失敗します。  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 **原因**  
  
 IDOC を受信するために生成されるメタデータには、受信操作の一部として特定の列用に受信することが許可される値が含まれます。 これらの値は、生成されたメタデータ内の列挙型として公開されます。 ただし、IDOC が実際に受信されると、受信した値は、列挙値を異なる場合があります。 そのため、受信操作は、値の検証中に失敗します。 たとえば、上記のエラーでは、TAXBS 列にメッセージの検証が失敗します。  
  
 **解決策**  
  
 必要があります手動で編集する schema (BizTalk プロジェクトの場合) またはクライアント プロキシ内の列挙型 (.NET プロジェクトの WCF を使用してサービス モデル) の SAP システムから受信した値を含めます。  
  
##  <a name="BKMK_SAPFFIDOC"></a>フラット ファイル Idoc 前に、と後、XML への変換が一致しません  
 **問題**  
  
 フラット ファイル IDOC をスキーマを使用して XML に変換し、スキーマを使用して、パイプライン経由のフラット ファイル IDOC を XML に変換し、フラット ファイル パーサーを使用する場合は 2 つのフラット ファイル Idoc が一致しません。  
  
 **原因**  
  
 XML フラット ファイル IDOC からを生成するときに、フラット ファイル パーサーは空白の値を持つ XML ノードを生成しません。 この XML は、フラット ファイルに変換するときに、XML に表示されないノードは、フラット ファイル IDOC に反映されません。 そのため、フラット ファイル Idoc が一致しません。  
  
 **解決策**  
  
 XML と、「送信」または「受信」のノード定義内で、その逆に、フラット ファイルを変換するために使用するスキーマでは、次の操作を行います。  
  
1.  設定、 **suppress_empty_nodes**プロパティを**false**設定と、 **generate_empty_nodes**プロパティを**true**です。 既定では、 **suppress_empty_nodes**プロパティに設定されている**true**と**generate_empty_nodes**プロパティに設定されている**false**、およびそのため空のすべてのノードは、XML には反映されません。  
  
2.  フラット ファイルには、末尾に余分な改行を含めることがあります。 設定することができます、 **suppress_trailing_delimiters**プロパティを**はい**この余分なキャリッジ リターンを回避します。 このプロパティも公開、**末尾の区切り記号の抑制**プロパティ内のスキーマを開く場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
##  <a name="BKMK_SAPAction"></a>バインド ファイルと共に作成する物理ポートを使用して、誤った操作エラー  
 **問題**  
  
 使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SAP システムで特定の操作のスキーマを生成するには、アドインでもポート バインド ファイルが作成されます。 インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server での物理ポートを作成します。 ただし、このようなポートを使用して SAP システムにメッセージを送信するときに、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk オーケストレーションの論理ポートを作成するときにそれらのポートでの操作の特定の名前を指定するか、Operation_1、Operation_2 などのように既定の名前に使用します。ただし、によって生成されたバインド ファイルでは、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する操作の名前と同じです。 たとえば、RFC_CUSTOMER_GET のメタデータを生成する場合、次に、アクションは設定されます。  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 バインド ファイルをインポートするときに、同じアクションは物理ポートに設定されます。 そのため、論理ポート ([operation_1]、Operation_2 など) での操作名では、エラーが発生しましたの物理ポートのアクションで指定した操作名が一致しません。  
  
 **解決策**  
  
 論理ポートにある操作名は、物理ポートにアクションの一部として指定された操作名と同じことを確認してください。 次のいずれかの操作を行います。  
  
-   たとえば RFC_CUSTOMER_GET、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートにある操作名を変更します。  
  
-   論理ポートでの操作名には、物理ポートのアクションで、操作名を変更します。 たとえば、次のように物理ポートにアクションを変更します。  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a>応答メッセージ SAP 上で実行された操作を含まないテーブル パラメーター  
 **原因**  
  
 使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムに対して操作を実行する多数のテーブルを返すし、各テーブルには、するための SAP システムからの応答メッセージの一部として返されるデータセットが大きいレコードの数が多い。 既定では、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答メッセージの一部として、テーブル パラメーターは返しません。  
  
 **解決策**  
  
 追加するテーブルを要求する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答の一部として返すためにします。 SAP システムに送信する要求メッセージの一部として、空のテーブルのパラメーターを提供することによって行うことができます。 たとえば、 `<table_parameter_name />`のようにします。  
  
##  <a name="BKMK_SAPIncorrectCreds"></a>アダプターのクライアントが SAP からの応答を受信しません
 **問題**  
  
 アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF カスタムの資格情報の送信ポートが正しくない要求メッセージは処理されません。 正しい資格情報を指定すると後、メッセージは、SAP システムに送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。  
  
 **解決策**  
  
 BizTalk ホスト インスタンスを再起動します。  
  
##  <a name="BKMK_SAPInboundConn"></a>SAP サーバーから受信メッセージを受信接続の問題  
 **問題**  
  
 WCF カスタムを使用して、SAP サーバーからの受信メッセージの受信ポートの受信中にのみ、次のエラーを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 ただしは、正常に Wcf-custom を使用して、SAP システムへのメッセージの送信ポートを送信できます。  
  
 **解決策**  
  
 SAP GUI、同じコンピューターにインストール場所、アダプターのクライアントを実行しているし、受信メッセージの受信をもう一度やり直してください。 SAP の GUI をインストールする方法の詳細については、SAP のマニュアルを参照してください。  
  
##  <a name="BKMK_SAPRootNode"></a>RootNode TypeName BizTalk プロジェクト内のエラー  
 **問題**  
  
 BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決策**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。  
  
##  <a name="BKMK_SAPVS2008"></a>Visual Studio でのアダプターの使用時の無効なバインドの警告  
 **問題**  
  
 Visual Studio でアプリケーションを作成するアダプターを使用して、アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド、`sapBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。  
  
 **解決策**  
  
 この警告は無視してかまいません。  
  
##  <a name="BKMK_SAPSimilarSchema"></a>BizTalk Server での XLANG 例外
 **問題**  
  
 BizTalk Server は、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかのため発生します。  
  
-   1 つ以上を生成する (SendIdoc ReceiveIdoc など)、BizTalk Server プロジェクト内の汎用的な操作のスキーマは、BizTalk Server アプリケーションに展開し、SAP システム上のそれぞれの操作を実行するアプリケーションを実行します。 競合が、スキーマは、一般的なであるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
-   複数のプロジェクトが発生した場合の各 BizTalk Server プロジェクトの一般的な操作のスキーマを生成を同じ BizTalk Server アプリケーションをホストして、実行、アプリケーションまたはアプリケーションを実行するそれぞれの個別の各プロジェクトの配置SAP システムに対する操作。 スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるため競合があるさまざまな BizTalk Server アプリケーションおよびアセンブリの下でデプロイされる共通のスキーマ間でします。  
  
 **解決策**  
  
 BizTalk Server アプリケーションの 1 つの一般的な操作のスキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで一般的な操作のスキーマを使用する必要がある場合、1 つの汎用操作スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから汎用の操作のスキーマを使用します。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)