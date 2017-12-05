---
title: "Siebel アダプターの BizTalk での運用上の問題のトラブルシューティング |Microsoft ドキュメント"
description: "共通の問題と解決策の Siebel アダプターの BizTalk アダプター パック (BAP) の"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff6e36afd7cecc967069fd3ecf5414c6afdb014
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a>Siebel アダプターでの運用上の問題をトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性が運用上の問題に関する情報をまとめて、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。  
  
## <a name="enabling-tracing"></a>トレースを有効にします。  
 トレースのサポートについては、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[診断トレースと Siebel アダプターのメッセージがログ](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)です。  
  
## <a name="known-issues"></a>既知の問題  
 いくつかの問題と推奨されるソリューションを使用しているときに発生する可能性を次のとおり、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
  
###  <a name="BKMK_SiebelBindingError"></a>アダプターのバインドを読み込み中にエラー  
 **問題**  
  
 起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]GUI では、次のエラー。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 開始すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。 さらに、アダプターのバインドは、特定のエンタープライズ アプリケーションのクライアント ソフトウェアに依存します。 そのため、次の理由の一方または両方について、この問題に直面する可能性があります。  
  
-   必要な LOB クライアント ソフトウェアは、アダプターがインストールされているコンピューターにインストールされていません。  
  
-   すべてのアダプターをインストールすると、アダプターの「標準」や「完了」のインストールで実行した、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 ただし、1 つだけのエンタープライズ アプリケーション用のクライアント ライブラリをインストールする可能性があります。 その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。  
  
 **解決策**  
  
-   必要なクライアントのバージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。  
  
-   必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。  
  
###  <a name="BKMK_SiebelDispAdap"></a>Siebel アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
 付属するアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]に付属の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。  
  
 **原因**  
  
 最新[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]WCF カスタム バインドがします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
 **解決策**  
  
 明示的に追加することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。  
  
###  <a name="BKMK_SiebelConnecting"></a>Siebel システムへの接続中にエラー  
 **問題**  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]Siebel システムに接続しようとすると、次のエラーを示します。  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 **原因**  
  
 Siebel Web クライアントは、コンピューターにインストールされていない可能性があります。  
  
 **解決策**  
  
 Siebel Web クライアントのサポートされているバージョンがコンピューターにインストールされていることを確認してください。 サポートされているクライアントのインストール ガイドおよび Siebel のサーバー バージョンを参照してください。 インストール ガイドは\<システム ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a>65536 以上のノードを持つ Xml を取得中にエラー  
 **問題**  
  
 アダプターは、65536 以上のノードを持つ XML 出力を取得中に、次のエラーを説明します。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 アダプターは、シリアル化および 65536 以上の項目を含むオブジェクトを逆シリアル化できません。  
  
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
  
 サンプルの app.config をようになります。  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="siebelBinding"  
       contract="IOutboundContract" name="siebel_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_SiebelConnURI"></a>Biztalk WCF カスタム ポートの接続 URI を指定する際にエラー  
 **問題**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接続の Siebel システムへの接続に URI を指定する場合は、次のエラーを得られます。  
  
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
  
###  <a name="BKMK_SiebelPerfOps"></a>Siebel システムに対する演算を実行中のエラー  
 **問題**  
  
 Siebel システムを使用して、すべての操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   **BizTalk server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **原因**  
  
 メッセージの WCF アクションが指定されていません。 WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。  
  
 **解決策**  
  
 送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [Siebel の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md)です。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)各操作のアクションの一覧についてはします。  
  
###  <a name="BKMK_SiebelXmlParsing"></a>正しくない操作名が指定したアクションで XmlReaderParsingException  
 **問題**  
  
 BizTalk Server 管理コンソールは、Siebel システムにメッセージを送信するときに、次のエラーを示します。  
  
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
  
 上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。 Siebel ビジネス コンポーネントでクエリ操作のスキーマを生成した場合など、アクションで操作名では、「クエリ」になります。 ただし、論理ポートにある操作名で BizTalk オーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。  
  
 **解決策**  
  
 確認操作名の両方、論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) と物理ポート (BizTalk Server 管理コンソール) が同じです。  
  
###  <a name="BKMK_SiebelTerminate"></a>Siebel アダプターを使用してアプリケーションを終了しません。  
 **問題**  
  
 使用するアプリケーション、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel とクライアント バージョン 7.5 を終了しません。  
  
 **原因**  
  
 これは、Siebel クライアントの問題により、プロセスを終了しません Siebel サーバーからログオフするときです。  
  
 **解決策**  
  
 7.5.3.17 クイック フィックス QF0H05 と共に、Siebel サーバー用にインストールされた更新プログラムがあることを確認してください。  
  
###  <a name="BKMK_SiebelHang"></a>Siebel アダプターがハングする Siebel サーバーが再起動した場合  
 **問題**  
  
 場合は、Siebel サーバーを再起動中に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel サーバーを使用するメッセージを送信する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ハングする可能性があります。  
  
 **解決策**  
  
 BizTalk アプリケーションのホスト インスタンスを再起動します。 これを行うに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールのコンソール ツリーで  **BizTalk グループ**、展開**プラットフォームの設定**、クリックして**ホスト インスタンス**です。 右側のウィンドウからホスト名を右クリックし、**再起動**です。  
  
###  <a name="BKMK_SiebelAction"></a>アダプター サービスのアドインで生成されたバインド ファイルを使用して、ポートを作成する場合でも、アダプターで物理ポートのアクションが認識されません。  
 **問題**  
  
 使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Siebel システムで特定の操作のスキーマを生成するには、アドインでもポート バインド ファイルが作成されます。 インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server での物理ポートを作成します。 ただし、このようなポートを使用して、Siebel システムにメッセージを送信するときに、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk オーケストレーションの論理ポートを作成するときにそれらのポートでの操作の特定の名前を指定するか、Operation_1、Operation_2 などのように既定の名前に使用します。ただし、によって生成されたバインド ファイルでは、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する操作の名前と同じです。 たとえば、アカウント ビジネス コンポーネントに対する挿入操作のメタデータを生成する場合、次に、アクションは設定されます。  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 バインド ファイルをインポートするときに、同じアクションは物理ポートに設定されます。 そのため、論理ポート ([operation_1]、Operation_2 など) での操作名では、エラーが発生しましたの物理ポートのアクションで指定した操作名が一致しません。  
  
 **解決策**  
  
 論理ポートにある操作名は、物理ポートにアクションの一部として指定された操作名と同じことを確認してください。 次のいずれかの操作を行います。  
  
-   Insert の例については、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートにある操作名を変更します。  
  
-   論理ポートでの操作名には、物理ポートのアクションで、操作名を変更します。 たとえば、次のように物理ポートにアクションを変更します。  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a>Siebel アダプターは、名前の XML でエンコードされた文字列が Siebel オブジェクトを処理しません  
 **問題**  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を名前にエンコードされた XML 文字列を持つ Siebel オブジェクト (ビジネス オブジェクト、ビジネス コンポーネント、ビジネス サービス、候補リスト、メソッド、フィールド、引数など) に関連する操作を実行することはできません。 たとえば、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]名前 Time_x0020_Stamp のビジネス サービス メソッドを呼び出すことはできません。  
  
 **解決策**  
  
 Siebel オブジェクトには、名前にエンコードされた XML 文字列が含まれていないことを確認してください。  
  
###  <a name="BKMK_SiebelRootNode"></a>RootNode TypeName BizTalk プロジェクト内のエラー  
 **問題**  
  
 BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決策**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。  
  
###  <a name="BKMK_SiebelVS2008"></a>Visual Studio でのアダプターの使用時の無効なバインドの警告  
 **問題**  
  
 Visual Studio でアプリケーションを作成するアダプターを使用して、アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインド、`siebelBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。  
  
 **解決策**  
  
 この警告は無視してかまいません。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)