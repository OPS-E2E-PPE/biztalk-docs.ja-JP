---
title: Siebel アダプターの BizTalk で運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的な問題と解決策の Siebel アダプターの BizTalk アダプター パック (BAP) の
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d17e325465ce5aa575a6d499aa6b8bf73e07696
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978939"
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a>Siebel アダプターを使用した運用上の問題をトラブルシューティングします。
ここでは説明を使用する場合に発生する可能性が運用上の問題に関する情報をまとめて、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。  
  
## <a name="enabling-tracing"></a>トレースを有効にします。  
 トレースのサポートについては、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[診断トレースとメッセージのログの Siebel アダプターの](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)します。  
  
## <a name="known-issues"></a>既知の問題  
 次にいくつかの問題と推奨されるソリューションを使用しているときに発生する可能性を[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
  
###  <a name="BKMK_SiebelBindingError"></a> アダプターのバインドを読み込み中にエラー  
 **問題**  
  
 開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]GUI では、次のエラー。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 開始すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。 さらに、アダプターのバインドは、特定のエンタープライズ アプリケーションのクライアント ソフトウェアに依存します。 そのため、次の理由の両方またはいずれかには、この問題に直面する可能性があります。  
  
- アダプターがインストールされているコンピューターでは、必要な LOB クライアント ソフトウェアがインストールされていません。  
  
- 内のすべてのアダプターをインストールすると、アダプターの「標準」や「完了」のインストールを行った、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 ただし、1 つだけのエンタープライズ アプリケーションのクライアント ライブラリをインストールする場合があります。 その結果、GUI の他のアダプターのバインドの読み込みに失敗します。  
  
  **解決方法**  
  
- 必要なクライアントのバージョンがインストールされているコンピューターにインストールされているかどうかを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
  
- 必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。  
  
###  <a name="BKMK_SiebelDispAdap"></a> Siebel アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
 付属するアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]に付属する[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。  
  
 **原因**  
  
 最新[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]WCF カスタム バインドします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
 **解決方法**  
  
 明示的に追加することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。  
  
###  <a name="BKMK_SiebelConnecting"></a> Siebel システムへの接続中にエラー  
 **問題**  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]Siebel システムに接続しようとすると、次のエラーを示します。  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 **原因**  
  
 Siebel Web クライアントは、コンピューターにインストールされていない可能性があります。  
  
 **解決方法**  
  
 Siebel Web クライアントのサポートされているバージョンがコンピューターにインストールされていることを確認します。 サポートされているクライアントのインストール ガイドと Siebel 用 server のバージョンを参照してください。 インストール ガイドは\<システム ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a> 65536 の複数のノードを持つ Xml を取得中にエラー  
 **問題**  
  
 アダプターは、65536 の複数のノードを持つ XML 出力の取得中に、次のエラーを説明します。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 アダプターは、シリアル化し、65536 の複数の項目を含むオブジェクトを逆シリアル化できません。  
  
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
  
###  <a name="BKMK_SiebelConnURI"></a> Biztalk WCF カスタム ポートの接続 URI を指定するときにエラー  
 **問題**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Siebel システムへの接続 uri を指定すると、次のエラーを示します。  
  
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
  
###  <a name="BKMK_SiebelPerfOps"></a> Siebel システムに対して操作を実行中のエラー  
 **問題**  
  
 使用して Siebel システムに対して任意の操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
- **BizTalk Server 用**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  メッセージの WCF アクションが指定されていません。 WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。  
  
  **解決方法**  
  
  送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、[Siebel の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md)を参照してください。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)の各操作のアクションの一覧。  
  
###  <a name="BKMK_SiebelXmlParsing"></a> 指定したアクションで、正しくない操作名により XmlReaderParsingException  
 **問題**  
  
 BizTalk Server 管理コンソールで Siebel システムにメッセージを送信する場合は、次のエラー。  
  
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
  
 前の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。 Siebel ビジネス コンポーネントでのクエリ操作のスキーマを生成した場合など、アクションで操作名では、"Query"になります。 ただし、論理ポートの操作名が BizTalk のオーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。  
  
 **解決方法**  
  
 確実に操作名の両方の論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) と (BizTalk Server 管理コンソール) で物理ポートが同じです。  
  
###  <a name="BKMK_SiebelTerminate"></a> Siebel アダプターを使用してアプリケーションを終了しません。  
 **問題**  
  
 使用するアプリケーション、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel とクライアント バージョン 7.5 を終了しません。  
  
 **原因**  
  
 これは、Siebel クライアントの問題により、Siebel サーバーからログオフするときで、プロセスが終了しません。  
  
 **解決方法**  
  
 7.5.3.17 クイック修正 QF0H05 と共に、Siebel サーバーにインストールされている修正プログラムがあることを確認します。  
  
###  <a name="BKMK_SiebelHang"></a> Siebel アダプターがハングする場合は、Siebel サーバーを再起動  
 **問題**  
  
 Siebel サーバーを再起動した場合に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel サーバーを使用するメッセージを送信する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ぶら下げることができます。  
  
 **解決方法**  
  
 BizTalk アプリケーションのホスト インスタンスを再起動します。 そのためには、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールのコンソール ツリーで  **BizTalk グループ**、展開**プラットフォームの設定**、順にクリックします**ホスト インスタンス**します。 右側のウィンドウからホスト名を右クリックし、**再起動**します。  
  
###  <a name="BKMK_SiebelAction"></a> Consume Adapter Service アドインによって生成されたバインド ファイルを使用して、ポートを作成する場合でも、アダプターが物理ポートでアクションを認識しません  
 **問題**  
  
 使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Siebel システムで特定の操作のスキーマを生成するアドインも作成ポートのバインド ファイル。 インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server で物理ポートを作成します。 ただし、このようなポートを使用して Siebel システムにメッセージを送信するとき、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk オーケストレーションでの論理ポートを作成するときにこれらのポートの操作に特定の名前を指定または Operation_1、Operation_2 などのように既定の名前を使用します。ただし、によって生成されたバインド ファイルで、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する操作の名前と同じです。 たとえば、アカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成する場合に、次のアクションは設定されます。  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 バインド ファイルをインポートすると、物理ポートで同じアクションが設定されます。 そのため、論理ポート (Operation_1、Operation_2 など) の操作名では、エラーが発生する物理ポートで、アクションで指定された操作名が一致しません。  
  
 **解決方法**  
  
 論理ポートで操作の名前は、物理ポートにアクションの一部として指定された操作名と同じことを確認します。 次のいずれかの操作を行います。  
  
-   Insert の例については、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートの操作名を変更します。  
  
-   論理ポートで、操作名に物理ポートのアクションで、操作名を変更します。 たとえば、次のように物理ポートにアクションを変更できます。  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a> Siebel アダプターでは、名前でエンコードされた XML 文字列を持つ Siebel オブジェクトを処理しません  
 **問題**  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を名前でエンコードされた XML 文字列を持つ Siebel オブジェクト (ビジネス オブジェクト、ビジネス コンポーネント、ビジネス サービス、候補リスト、メソッド、フィールド、引数など) に関連する操作を実行することはできません。 たとえば、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Time_x0020_Stamp という名前のビジネス サービス メソッドを呼び出すことはできません。  
  
 **解決方法**  
  
 Siebel オブジェクトには、名前でエンコードされた XML 文字列が含まれていないことを確認します。  
  
###  <a name="BKMK_SiebelRootNode"></a> BizTalk プロジェクト内の RootNode TypeName とエラー  
 **問題**  
  
 BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決方法**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。  
  
###  <a name="BKMK_SiebelVS2008"></a> Visual Studio で、アダプターを使用する際に無効なバインド警告  
 **問題**  
  
 Visual Studio でアプリケーションを作成するアダプターを使用すると、アダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインド、`siebelBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。  
  
 **解決方法**  
  
 この警告は無視してかまいません。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)