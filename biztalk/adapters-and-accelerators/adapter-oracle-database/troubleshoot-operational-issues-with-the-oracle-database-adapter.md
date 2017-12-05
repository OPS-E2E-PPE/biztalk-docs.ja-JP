---
title: "Oracle データベース アダプターの運用上の問題のトラブルシューティング |Microsoft ドキュメント"
description: "共通の問題と Oracle データベース アダプターの BizTalk アダプター パック (BAP) の解決策"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ac926a378224e09dce36a52b52c171fb27911b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a>Oracle データベース アダプターの運用上の問題をトラブルシューティングします。
トラブルシューティングの手法を使用して発生する可能性がある操作のエラーを解決するのには[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。  
  
## <a name="enable-tracing"></a>トレースを有効にします。  
 トレースのサポートについては、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[診断トレースとメッセージ ログの Oracle データベース アダプター](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)です。  
  
## <a name="known-issues"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なエラーは、次のとおり、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、およびその考えられる原因と解決します。   
  
### <a name="BKMK_OraDBLoading"></a>アダプターのバインドを読み込み中にエラー  
 **問題**  
  
 起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生します。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 起動しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。 一方、アダプターのバインドは、エンタープライズ アプリケーション用の特定のクライアント ソフトウェアに依存します。 次の理由の一方または両方について、この問題に直面する可能性があります。  
  
-   必要な LOB クライアント ソフトウェアは、アダプターがインストールされているコンピューターにインストールされていません。  
  
-   含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了したとき、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 ただし、1 つだけのエンタープライズ アプリケーションに LOB クライアント ライブラリをインストールする可能性があります。 その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。  
  
 **解決策**  
  
-   必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認してください、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 [サポートされている基幹業務 (LOB) とエンタープライズ システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされるクライアント バージョンを一覧表示します。  
  
-   必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。  
  
    > [!NOTE]
    >  アプリケーションは ODP.NET の最新のバージョンで動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイトです。  
  
###  <a name="BKMK_OraDBAdapDisplay"></a>Oracle データベース アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]およびこの[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。  
  
 **原因**  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF カスタム バインドがします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 **解決策**  
  
 明示的に追加することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。  
  
###  <a name="BKMK_OraDBXMLRetrieve"></a>65,536 個を超えるノードを持つ XML 出力を取得中にエラー  
 **問題**  
  
 アダプターは、65,536 個を超えるノードを持つ出力 XML を取得するときに、次のエラーを示します。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 アダプターは、シリアル化して、65,536 個を超える項目を含むオブジェクトを逆シリアル化できません。  
  
 **解決策**  
  
 この問題を解決するには、設定、`maxItemsInObjectGraph`パラメーター。 これは、次の 2 つの方法のいずれかで設定できます。  
  
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
  
 サンプルの app.config では、次のように検索します。  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="oracleDBBinding"  
       contract="IOutboundContract" name="oracle_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_OraDBPerfOps"></a>Oracle データベースに対する操作の実行中のエラー  
 **問題**  
  
 操作を使用して Oracle データベースに対して実行する場合に、アダプターが、次のエラーをによって[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   **BizTalk server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **原因**  
  
 メッセージの WCF アクションが指定されていません。 WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。  
  
 **解決策**  
  
 送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)です。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)各操作のアクションの一覧を表示します。  
  
###  <a name="BKMK_OraDBXmlParsing"></a>正しくない操作名が指定したアクションで XmlReaderParsingException  
 **問題**  
  
 BizTalk Server 管理コンソールでは、Oracle データベースにメッセージを送信するときに、次のエラーが与えられます。  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
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
  
 上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。 たとえば、テーブルに対する挿入操作のスキーマを生成した場合、アクション内の操作名されます"Insert"。 ただし、論理ポートにある操作名で BizTalk オーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。  
  
 **解決策**  
  
 確認操作名の両方、論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) (BizTalk Server 管理コンソール) での物理ポートは同じです。  
  
###  <a name="BKMK_OraDBConnURI"></a>Biztalk WCF カスタム ポートの接続 URI を指定する際にエラー  
 **問題**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースに接続する URI の接続を指定する場合は、次のエラーを示します。  
  
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
  
###  <a name="BKMK_OraDBInvalCursor"></a>REF CURSOR パラメーターを受け取るストアド プロシージャの呼び出し中に無効なカーソル例外  
 **問題**  
  
 で REF CURSOR の入力を行う、Oracle データベースでのプロシージャを呼び出すときは、次の例外を取得する可能性があります。  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 **原因**  
  
 呼び出しているプロシージャの PL/SQL ブロックをパイプでした REF Cursor は、REF CURSOR でしたを取得するのに割り当てるアウト REF CURSOR です。  
  
 **解決策**  
  
 PL/SQL ブロックは、IN、OUT の REF Cursor 適切な処理せずをパイプいない必要があります。  
  
###  <a name="BKMK_OraDBValidateResp"></a>BizTalk Server を使用して、ReadLOB 操作に対する応答を検証中にエラー  
 **問題**  
  
 使用して ReadLOB 操作の実行中に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、Oracle データベースからの応答は検証に対して、Web サービス記述言語 (WSDL) に失敗します。  
  
 **原因**  
  
 WSDL には、サービス ベースの要求の実行に対して定義されたが、BizTalk のシナリオは必要ありません StreamBody ノード名が含まれています。 したがって、出力が含まれていない StreamBody ノードが XML では、WSDL と比べると、検証が失敗します。  
  
 **解決策**  
  
 BizTalk Server を使用して生成された出力に対して検証するときに、WSDL から StreamBody ノードを削除します。 そのためには、次の手順を実行します。  
  
1.  StreamBody ノードを含む WSDL は、次のように検索します。  
  
    ```  
    <xs:element name="ReadLOBResponse">  
        <xs:annotation>  
          <xs:documentation>  
            <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>  
          </xs:documentation>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" nillable="true" type="ns3:StreamBody" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    ```  
  
     次のように、上記に置き換えます。  
  
    ```  
    <xs:element name="ReadLOBResponse">  
     <xs:annotation>  
     <xs:documentation>  
      <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>   
      </xs:documentation>  
      </xs:annotation>  
     <xs:complexType>  
     <xs:sequence>  
      <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" type="xs:base64Binary" />   
      </xs:sequence>  
      </xs:complexType>  
      </xs:element>  
    ```  
  
     この手順では、型への参照を削除元の XSD で"ns3:StreamBody"= = し、型に置き換え"xs:base64Binary"を = です。 また、元の XSD から nillable ="true"の値を削除します。  
  
2.  WSDL から、次を削除します。  
  
    ```  
    <xs:complexType name="StreamBody">  
        <xs:sequence>  
          <xs:element minOccurs="1" maxOccurs="1" name="Stream">  
            <xs:simpleType>  
              <xs:restriction base="xs:base64Binary">  
                <xs:minLength value="0" />  
              </xs:restriction>  
            </xs:simpleType>  
          </xs:element>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:element name="StreamBody" nillable="true" type="ns3:StreamBody" />  
    ```  
  
    > [!NOTE]
    >  ReadLOB 操作はサポートされていません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 テーブルの選択操作を使用から LOB データを読み取る必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
###  <a name="BKMK_OraDBSchemaValidateFail"></a>ポーリングのシナリオでスキーマの検証が失敗します。  
 **問題**  
  
 シナリオでスキーマの検証に失敗した場所、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]データベース ROWID または UNROWID 型のフィールドを含むテーブルをポーリングします。  
  
 **原因**  
  
 デザイン時に、アダプターは、ROWID または UNROWID、型のフィールドを含むテーブルのメタデータを生成するときに、スキーマが含まれています"nillable = false"、つまり、ROWID または UNROWID 型のフィールドが null にできません。 ただし、実行時にアダプターが、メタデータを取得するときに ROWID または UNROWID 型のフィールド値が含まれる null です。 そのため、スキーマ検証が失敗します。  
  
 **解決策**  
  
 使用している場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]スキーマの検証を無効にすることもできます。 スキーマが変更を手動で編集する代わりに、"nillbale = true"ROWID および UNROWID データ型のです。  
  
###  <a name="BKMK_OraDBUnreasonConv"></a>実行時に、'不合理 conversion 要求' エラーを持つストアド プロシージャのレコードの種類のパラメーターとして  
 **原因**  
  
 パラメーターとして、Oracle がプロシージャが格納されているシナリオをレコードの種類について考えてみます。 レコードの種類として宣言されていると仮定\<テーブル名\>%rowtype、テーブルが長い形式のデータ型の列がします。 ときに、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]検出すると、長いデータ型、データ型のサイズを指定された値と等しい設定、 **LongDatatypeColumnSize**プロパティをバインドします。 ただし、Oracle データベースでは、長い形式のデータ型のサイズが定義されていません。 そのため、アダプターは、ストアド プロシージャが呼び出されるときにエラーが発生、'不合理 conversion 要求' です。  
  
 **解決策**  
  
 レコードの種類には LONG データ型がある場合は、パッケージの一部として明示的に定義する必要があります。  
  
###  <a name="BKMK_OraDBAdapRecognize"></a>アダプター サービスのアドインで生成されたバインド ファイルを使用して、ポートを作成する場合でも、アダプターで物理ポートのアクションが認識されません。  
 **問題**  
  
 使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Oracle データベースで特定の操作のスキーマを生成するには、アドインでもポート バインド ファイルが作成されます。 インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server での物理ポートを作成します。 ただし、このようなポートを使用して Oracle データベースにメッセージを送信するときに、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk オーケストレーションの論理ポートを作成するときにそれらのポートでの操作の特定の名前を指定するか、Operation_1、Operation_2 などのように既定の名前に使用します。ただし、によって生成されたバインド ファイルでは、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する Oracle データベース操作の名前と同じです。 たとえば、Oracle データベースで ACCOUNTACTIVITY テーブルに対する Select 操作のメタデータを生成する場合に、次のアクションは設定されます。  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 バインド ファイルをインポートするときに、同じアクションは物理ポートに設定されます。 そのため、論理ポート ([operation_1]、Operation_2 など) での操作名では、エラーが発生しましたの物理ポートのアクションで指定した操作名が一致しません。  
  
 **解決策**  
  
 論理ポートにある操作名は、物理ポートにアクションの一部として指定された操作名と同じことを確認してください。 次のいずれかの操作を行います。  
  
-   たとえばを選択して、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートにある操作名を変更します。  
  
-   論理ポートでの操作名には、物理ポートのアクションで、操作名を変更します。 たとえば、次のように物理ポートにアクションを変更します。  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <a name="BKMK_OraDBOverflowExcep"></a>アダプターは例外処理オーバーフロー ("System.OverflowException")、操作を実行する方法  
 **問題**  
  
 データセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型を含む操作を実行しようとする場合は、アダプターを使用して、アダプターではオーバーフロー例外がスロー可能性があります。  
  
 **原因**  
  
 これは、データセットまたはそれぞれの .NET 型に収まらない弱い型指定の REF CURSOR の内部 Oracle 数値データ型の大きな値を指定する場合に発生します。  
  
 **解決策**  
  
 データセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型の大きな値を渡す場合は、セーフである入力の値を設定して有効にする必要があります、 **EnableSafeTyping**にプロパティのバインド**true**. 文字列としてデータセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型を公開するセーフである入力の有効化します。  
  
###  <a name="BKMK_OraDBRootNode"></a>RootNode TypeName BizTalk プロジェクト内のエラー  
 **問題**  
  
 BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決策**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。  
  
###  <a name="BKMK_OraDBInvalBinding"></a>Visual Studio でのアダプターの使用時の無効なバインドの警告  
 **問題**  
  
 アプリケーションを作成するアダプターを使用すると[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド、`oracleDBBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。  
  
 **解決策**  
  
 この警告は無視してかまいません。  
  
###  <a name="BKMK_OraDBNotification"></a>BizTalk Server が、同じアプリケーションで 1 つ以上の通知スキーマを使用して、同じホスト上の複数のアプリケーション間で通知スキーマを使用するか、例外をスローします。  
 **問題**  
  
 BizTalk Server は、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかのため発生します。  
  
-   1 つ以上を生成する、BizTalk Server プロジェクトでの通知スキーマを BizTalk Server アプリケーションに展開し、Oracle データベースから通知を受け取るアプリケーションを実行します。 競合が通知スキーマは、一般的なであるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
-   複数のプロジェクトが発生した場合、BizTalk Server が配置されたプロジェクトの各プロジェクトの場合、同じホスト上の別の BizTalk Server アプリケーションの各通知スキーマを生成したし、し、実行、アプリケーションまたはアプリケーションからの通知を受信するにはOracle データベースです。 スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるため競合があるさまざまな BizTalk Server アプリケーションおよびアセンブリの下でデプロイされる共通のスキーマ間でします。  
  
 **解決策**  
  
 BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションからの通知スキーマを使用します。  
  
###  <a name="BKMK_MemUsage"></a>メモリ使用量とスレッド数の増加トランザクション受信操作で、アダプターを使用する場合  
 **問題**  
  
 ポーリングなどのトランザクション受信操作で**かどうかはデータをポーリングするテーブルで使用できる**アダプターがポーリングを継続しは、メモリ使用量とスレッド数の増加が発生する期間にわたっています。  
  
 **原因**  
  
 **かどうかはデータをポーリングするテーブルで使用できる**の後にすべて受信タイムアウト サイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。 そのため、時間の期間にわたって、スレッドの数とメモリの使用量が増加します。 ただし、一部のデータをポーリングするテーブルには、同じスレッドが継続後続のすべてのポーリングを実行します。  
  
 **解決策**  
  
 設定を推奨、 **ReceiveTimeout**に最大の可能な値は 24.20:31:23.6470000 (24 日)、新しいスレッドが 24 日間にのみを生成できるようにします。 これにより、メモリ使用量とスレッド数が大きくならないが多すぎるが早すぎます。  
  
> [!NOTE]
>  SqlAdapterInboundTransactionBehavior が設定されている場合、TransactionTimeout が 24.20:31:23.6470000 (24 日) である最大の可能な値にも構成されていることを確認します。 この回避策を使用する場合、トランザクション分離レベルを構成する場合のみ、SqlAdapterInboundTransactionBehavior を追加できます。 それ以外の場合、その動作を削除することを勧めします。  
  
 詳細については、 **ReceiveTimeout**バインディング プロパティを参照してください[Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。 バインドのプロパティを指定する方法の詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
> [!NOTE]
>  付いたアダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。  
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[Oracle データベース アダプターのインストールに関するをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)