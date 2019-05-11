---
title: Oracle データベース アダプターを使用した運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的な問題と Oracle データベース アダプターの BizTalk アダプター パック (BAP) の解決策
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9b5cdf5dd7667b2bfdddf61b77591455829d98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375923"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a>Oracle データベース アダプターを使用した運用上の問題をトラブルシューティングします。
トラブルシューティングの手法を使用して発生する可能性がある操作のエラーを解決するのには[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。  
  
## <a name="enable-tracing"></a>トレースを有効にします。  
 トレースのサポートについては、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[診断トレースとメッセージ ログの Oracle データベース アダプター](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)します。  
  
## <a name="known-issues"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]と共に、考えられる原因と解決します。   
  
### <a name="BKMK_OraDBLoading"></a> アダプターのバインドを読み込み中にエラー  
 **問題**  
  
 開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生しました。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 開始しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。 さらに、アダプターのバインドは、エンタープライズ アプリケーションの特定のクライアント ソフトウェアに依存します。 この問題は次の理由の両方またはいずれかに直面する可能性があります。  
  
- アダプターがインストールされているコンピューターでは、必要な LOB クライアント ソフトウェアがインストールされていません。  
  
- 含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了した、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 ただし、1 つだけのエンタープライズ アプリケーション用に LOB クライアント ライブラリをインストールする場合があります。 その結果、GUI の他のアダプターのバインドの読み込みに失敗します。  
  
  **解決方法**  
  
- 必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 [サポートされている基幹業務 (LOB) とエンタープライズ システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているクライアント バージョンを一覧表示します。  
  
- 必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。  
  
  > [!NOTE]
  >  ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイト。  
  
###  <a name="BKMK_OraDBAdapDisplay"></a> Oracle データベース アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]付属しています[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧にも記載されていません。  
  
 **原因**  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF カスタム バインドします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
 **解決方法**  
  
 明示的に追加することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。  
  
###  <a name="BKMK_OraDBXMLRetrieve"></a> 65,536 個を超えるノードを持つ XML 出力の取得中にエラー  
 **問題**  
  
 アダプターは、65,536 を超えるノードを持つ出力 XML を取得するときに、次のエラーを示します。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 アダプターは、シリアル化し、65,536 を超える項目を含むオブジェクトを逆シリアル化できません。  
  
 **解決方法**  
  
 この問題を解決するには、設定して、`maxItemsInObjectGraph`パラメーター。 これは、次の 2 つの方法のいずれかで設定できます。  
  
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
  
###  <a name="BKMK_OraDBPerfOps"></a> Oracle データベースに対する操作の実行中のエラー  
 **問題**  
  
 使用して Oracle データベースに対して任意の操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
- **BizTalk Server 用**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  メッセージの WCF アクションが指定されていません。 WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。  
  
  **解決方法**  
  
  送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)各操作のアクションの一覧を表示します。  
  
###  <a name="BKMK_OraDBXmlParsing"></a> 指定したアクションで、正しくない操作名により XmlReaderParsingException  
 **問題**  
  
 BizTalk Server 管理コンソールは、Oracle データベースにメッセージを送信するときに、次のエラーを示します。  
  
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
  
 上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。 たとえば、テーブルに対する挿入操作のスキーマを生成すると、アクションで、操作名が、"Insert"になります。 ただし、論理ポートの操作名が BizTalk のオーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。  
  
 **解決方法**  
  
 確実に操作名の両方の論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) (BizTalk Server 管理コンソール) で物理ポートが同じであるとします。  
  
###  <a name="BKMK_OraDBConnURI"></a> Biztalk WCF カスタム ポートの接続 URI を指定するときにエラー  
 **問題**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 接続、Oracle データベースに接続するための URI を指定する場合は、次のエラーを得られます。  
  
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
  
###  <a name="BKMK_OraDBInvalCursor"></a> REF CURSOR パラメーターを受け取るストアド プロシージャの呼び出し中に無効なカーソル例外  
 **問題**  
  
 REF CURSOR の入力を受け取る、Oracle データベースでプロシージャを呼び出すと、次の例外が発生可能性があります。  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 **原因**  
  
 REF Cursor PL/SQL のブロックを呼び出しているプロシージャをパイプ処理できますは、IN の REF CURSOR でしたの取得に割り当てられますアウト REF カーソル。  
  
 **解決方法**  
  
 PL/SQL ブロックは、適切な処理を行わなくても OUT REF Cursor をパイプしない必要があります。  
  
###  <a name="BKMK_OraDBValidateResp"></a> BizTalk Server を使用して、ReadLOB 操作に対する応答の検証中にエラー  
 **問題**  
  
 使用して ReadLOB 操作の実行中に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、Oracle データベースからの応答が Web サービス記述言語 (WSDL) に対して検証が失敗します。  
  
 **原因**  
  
 WSDL には、サービス ベースの要求の実行が定義されているが、BizTalk のシナリオは必要ありません StreamBody ノード名が含まれています。 そのため、XML で、StreamBody ノードが含まれていませんが、出力は、WSDL と比較すると、検証は失敗します。  
  
 **解決方法**  
  
 BizTalk Server を使用して生成された出力結果に対して検証するときに、WSDL から StreamBody ノードを削除します。 そのためには、次の手順を実行します。  
  
1. StreamBody ノードを含む WSDL は、次のように検索します。  
  
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
  
    次のように、前に置き換えます。  
  
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
  
    型への参照を削除するこの手順で元の XSD では、"ns3:StreamBody"= し、型に置き換え"xs:base64Binary"を = です。 また、元の XSD から nillable ="true"の値を削除します。  
  
2. 次は、WSDL から削除します。  
  
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
   >  ReadLOB 操作はサポートされていません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 LOB データを読み取るテーブルの選択操作を使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
###  <a name="BKMK_OraDBSchemaValidateFail"></a> ポーリングのシナリオでスキーマの検証が失敗します。  
 **問題**  
  
 シナリオでスキーマの検証に失敗した場所、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]データベース ROWID または UNROWID 型のフィールドが含まれているテーブルをポーリングします。  
  
 **原因**  
  
 デザイン時に、アダプターは、ROWID または UNROWID、型のフィールドを含むテーブルのメタデータを生成するときに、スキーマが含まれています"nillable = false"、つまり、ROWID または UNROWID 型のフィールドが null にできません。 ただし、実行時に、アダプターは、メタデータを取得するときに ROWID または UNROWID 型のフィールドの null 値を格納します。 そのため、スキーマの検証が失敗します。  
  
 **解決方法**  
  
 使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]スキーマの検証を無効にすることができます。 スキーマが変更を手動で編集する代わりに、"nillbale = true"ROWID と UNROWID データ型。  
  
###  <a name="BKMK_OraDBUnreasonConv"></a> 実行するときに、'要求された不合理変換' エラーでは、パラメーターとしてレコードの種類を使用したプロシージャが格納されています。  
 **原因**  
  
 パラメーターとして、Oracle がプロシージャが格納されているシナリオのレコードの種類を検討します。 レコードの種類として宣言されていることを前提としています\<テーブル名\>%rowtype、テーブルと長い形式のデータ型の列があります。 ときに、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]検出すると長い形式のデータ型、データ型のサイズを指定された値と等しく設定する、 **LongDatatypeColumnSize**プロパティをバインドします。 ただし、Oracle データベースでは、長い形式のデータ型のサイズは定義しません。 そのため、アダプターが、ストアド プロシージャを呼び出すときに、'要求された不合理変換' エラーになります。  
  
 **解決方法**  
  
 レコード型の長い形式のデータ型の場合は、パッケージの一部として明示的に定義する必要があります。  
  
###  <a name="BKMK_OraDBAdapRecognize"></a> Consume Adapter Service アドインによって生成されたバインド ファイルを使用して、ポートを作成する場合でも、アダプターが物理ポートでアクションを認識しません  
 **問題**  
  
 使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Oracle データベースで特定の操作のスキーマを生成するアドインも作成ポートのバインド ファイル。 インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server で物理ポートを作成します。 ただし、このようなポートを使用して Oracle データベースにメッセージを送信するとき、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk オーケストレーションでの論理ポートを作成するときにこれらのポートの操作に特定の名前を指定または Operation_1、Operation_2 などのように既定の名前を使用します。ただし、によって生成されたバインド ファイルで、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する Oracle データベース操作の名前と同じです。 たとえば、Oracle データベースで ACCOUNTACTIVITY テーブルに対する Select 操作のメタデータを生成する場合に、次のアクションは設定されます。  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 バインド ファイルをインポートすると、物理ポートで同じアクションが設定されます。 そのため、論理ポート (Operation_1、Operation_2 など) の操作名では、エラーが発生する物理ポートで、アクションで指定された操作名が一致しません。  
  
 **解決方法**  
  
 論理ポートで操作の名前は、物理ポートにアクションの一部として指定された操作名と同じことを確認します。 次のいずれかの操作を行います。  
  
-   Select の例については、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートの操作名を変更します。  
  
-   論理ポートで、操作名に物理ポートのアクションで、操作名を変更します。 たとえば、次のように物理ポートにアクションを変更できます。  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <a name="BKMK_OraDBOverflowExcep"></a> アダプターは、操作を実行する方法 ("System.overflowexception:") オーバーフロー例外をスローします。  
 **問題**  
  
 データセットまたは厳密に型指定の REF CURSOR の内部で Oracle の数値データ型を格納している操作を実行しようとする場合、アダプターを使用して、アダプターは、オーバーフロー例外をスロー可能性があります。  
  
 **原因**  
  
 これは、大規模なデータセットや、それぞれの .NET 型に収まらない厳密に型指定の REF CURSOR の内部で Oracle の数値データ型の値を指定する場合に発生します。  
  
 **解決方法**  
  
 データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型の大きな値を渡す場合は、安全な」と入力の値を設定して有効にする必要があります、 **EnableSafeTyping**プロパティをバインド**true**. 安全な入力を有効にすると、データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型が文字列として公開します。  
  
###  <a name="BKMK_OraDBRootNode"></a> BizTalk プロジェクト内の RootNode TypeName とエラー  
 **問題**  
  
 BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決方法**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。  
  
###  <a name="BKMK_OraDBInvalBinding"></a> Visual Studio で、アダプターを使用する際に無効なバインド警告  
 **問題**  
  
 アプリケーションを作成するアダプターを使用すると[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]とアダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド、`oracleDBBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。  
  
 **解決方法**  
  
 この警告は無視してかまいません。  
  
###  <a name="BKMK_OraDBNotification"></a> 同じアプリケーション内で 1 つ以上の通知スキーマを使用するか、同じホスト上の複数のアプリケーションで通知スキーマを使用している場合、BizTalk Server は例外をスローします。  
 **問題**  
  
 BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかの原因で発生します。  
  
- 1 つ以上を生成した通知スキーマを BizTalk Server プロジェクトで、BizTalk Server アプリケーションに展開し、Oracle データベースから通知を受け取るアプリケーションを実行します。 競合が通知のスキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
- 複数のプロジェクトが発生した場合、同じホスト上の別の BizTalk Server アプリケーションを各プロジェクト配置されたプロジェクト、BizTalk Server の各通知スキーマを生成したから通知を受信するアプリケーションを実行し、Oracle データベース。 競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。  
  
  **解決方法**  
  
  BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから通知スキーマを使用します。  
  
###  <a name="BKMK_MemUsage"></a> メモリ使用量とスレッド数の増加、トランザクション受信操作で、アダプターを使用する場合  
 **問題**  
  
 ポーリングなどのトランザクション受信操作で**かどうかデータがないポーリングされるテーブルで使用できる**アダプターがポーリングを継続しは、時間の期間にわたってメモリ使用量とスレッド数の増加が発生します。  
  
 **原因**  
  
 **かどうかはデータがないポーリングされるテーブルで使用できる**後にすべて受信タイムアウトのサイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。 そのため、期間のスレッドの数とメモリ使用量が増加します。 ただし、ポーリングされるテーブルにいくつかのデータがある場合、同じスレッドは、すべての後続のポーリングを実行する継続します。  
  
 **解決方法**  
  
 設定をお勧め、 **ReceiveTimeout**に最大の可能な値である 24.20:31:23.6470000 (24 日)、新しいスレッドは 24 日間にのみを生成できるようにします。 メモリ使用量とスレッドの数が大きくが多すぎるが早すぎるようになります。  
  
> [!NOTE]
>  SqlAdapterInboundTransactionBehavior が設定されている場合、TransactionTimeout が 24.20:31:23.6470000 (24 日) である最大の可能な値にも構成されていることを確認します。 この回避策を使用する場合、トランザクション分離レベルを構成する場合のみ、SqlAdapterInboundTransactionBehavior を追加できます。 それ以外の場合、これはその動作を削除することをお勧めします。  
  
 詳細については、 **ReceiveTimeout**プロパティ、バインドを参照してください[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。 バインドのプロパティを指定する方法の詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
  
> [!NOTE]
>  アダプターを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。  
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[Oracle データベース アダプターのインストールに関する問題をトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)