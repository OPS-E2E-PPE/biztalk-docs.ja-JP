---
title: "Biztalk SQL アダプターでの運用上の問題のトラブルシューティング |Microsoft ドキュメント"
description: "共通の問題と、SQL アダプターの BizTalk アダプター パック (BAP) の解決策"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d3febbda1799c1f002ed352caecc5d9d838db00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a>SQL アダプタで運用上の問題をトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。  
  
## <a name="enabling-tracing"></a>トレースを有効にします。  
 アダプターの間でトレースを有効にする必要があります[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、問題の詳細については、いずれかを収集する SQL Server が使用中に発生して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 トレースのサポートの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[診断トレースおよび SQL アダプターでメッセージのログ記録](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)です。  
  
## <a name="known-issues"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なエラーは、次のとおり、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、およびその考えられる原因と解決します。  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a>アダプターのバインドを読み込み中にエラー  
 **問題**  
  
 起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生します。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 起動しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。 一方、アダプターのバインドは、エンタープライズ アプリケーション用の特定のクライアント ソフトウェアに依存します。 含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了した場合は、この問題に直面する可能性があります、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 ただし、1 つだけのエンタープライズ アプリケーションに LOB クライアント ライブラリをインストールする可能性があります。 その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。  
  
 **解決策**  
  
 必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。  
  
###  <a name="BKMK_SQLDisplay"></a>SQL アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
 付属するアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]アダプターの一覧に表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 **原因**  
  
 最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]WCF カスタム バインドがします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
 **解決策**  
  
 明示的に追加することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。  
  
###  <a name="BKMK_MissingAction"></a>SQL Server データベースに対する操作の実行中のエラー  
 **問題**  
  
 使用して SQL Server データベースに任意の操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   **の[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **原因**  
  
 メッセージの WCF アクションが指定されていません。 WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。  
  
 **解決策**  
  
 送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)です。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧を表示します。  
  
###  <a name="BKMK_SQLInvalidOp"></a>エラー コードでの InvalidOperationException FILESTREAM 操作の実行中に 5 を =  
 **問題**  
  
 使用しているときに、次のエラーを取得する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] FILESTREAM 操作を実行します。  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 **原因**  
  
 SQL Server データベースに接続するデータベースの資格情報を指定する可能性があります。 FILESTREAM 操作を行うには、常に Windows 認証を使用する必要があります。 エラー コード「5」は、正しくない資格情報のためのアクセスが拒否されることを示します。 別のエラー コードの詳細については、次を参照してください。[システム エラー コード (0 ~ 499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)です。
  
 **解決策**  
  
 SQL Server データベースに接続するには、Windows 認証を使用します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、これを行う空白のままユーザー名とパスワードのフィールド、Wcf-custom または WCF SQL ポートの構成 ダイアログ ボックスでします。  
  
###  <a name="BKMK_SQLPolling"></a>操作をポーリング返さないメッセージ PollingStatement と PolledDataAvailableStatement 有効なステートメントに指定されている場合でも  
 **問題**  
  
 PollingStatement および PolledDataAvailableStatement のバインド プロパティの有効な値を指定する場合でもは、アダプターは SQL Server からポーリング メッセージを受け取りません。  
  
 **原因**  
  
 他のトランザクションがアダプターをポーリングするテーブルのロックを取得するかどうかを確認します。  
  
 **解決策**  
  
 別のトランザクションの一部として更新されるテーブルをポーリングする場合は、使用を検討"(nolock)"を使用したパラメーター PolledDataAvailableStatement バインド プロパティの指定されたクエリの一部として、ロックが適用される場合でも、データが返されることを確認するにはによって他のトランザクションです。 詳細については、次を参照してください。[データベース エンジンの SQL ロック](https://msdn.microsoft.com/library/ms190615.aspx)です。
  
###  <a name="BKMK_SQLSingleOp"></a>アダプターは、挿入、更新、または大量の BizTalk Server を使用して単一の操作でデータを削除に失敗しました。  
 **問題**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]大量のデータを使用して、1 つの操作での挿入、更新、削除に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 **原因**  
  
 挿入、更新、または大量のデータを削除する時間がかかる場合があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で操作が実行されている、トランザクションがタイムアウトになった可能性があります。  
  
 **解決策**  
  
-   **の[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**  
  
    1.  Machine.config には、WCF アダプターのタイムアウトを指定します。下にある machine.config ファイルに移動\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。  
  
        ```  
        <configuration>  
         \<system.transactions>  
          <machineSettings maxTimeout="02:00:00" />  
         \</system.transactions>  
        </configuration>  
        ```  
  
         この設定では、WCF アダプターのタイムアウトは 2 時間に設定されます。  
  
    2.  Machine.config には、MSDTC トランザクションのタイムアウト設定を指定します。下にある machine.config ファイルに移動\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。  
  
        ```  
        \<system.transactions>   
                <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
            \</system.transactions>  
  
        ```  
  
         この設定では、MSDTC のタイムアウトは 2 時間に設定されます。 MSDTC のタイムアウトの既定値は、10 分です。  
  
        > [!IMPORTANT]
        >  アダプターのクライアントと SQL Server を実行するコンピューターでこの変更を行う必要があります。 例では、アダプターのクライアントと SQL Server を実行しているコンピューターの名前で < computer_name > を置き換えます。  
  
    3.  設定、 **SendTimeout**バインディングのプロパティ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]非常に大きな値にします。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a>データセットを含む応答メッセージを BizTalk Server のフル スキーマ検証に失敗します。  
 **問題**  
  
 データセットでは、たとえばの ExecuteReader を含む応答メッセージを返す操作の完全スキーマの検証に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 **解決策**  
  
 データセットを含む応答メッセージのスキーマ完全検証を行わないをお勧めします。 代わりに、次の操作を行う可能性があります。  
  
1.  スキーマと応答メッセージを返すと、操作を実行します。  
  
2.  .Xsd ファイルへの応答メッセージからスキーマをコピーし、BizTalk プロジェクトにこのファイルを追加します。  
  
3.  オーケストレーションで xpath クエリを使用して、応答メッセージからデータを抽出します。  
  
###  <a name="BKMK_SQLRootNode"></a>RootNode TypeName BizTalk プロジェクト内のエラー  
 **問題**  
  
 BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決策**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a>アダプターは一時テーブルとストアド プロシージャを厳密に型指定のメタデータを生成できません。  
 **問題**  
  
 アダプターは、それらの定義で一時テーブルが含まれた厳密に型指定されたストアド プロシージャのメタデータを生成に失敗します。 アダプターは、次の例外を説明します。  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 **解決策**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]をそれらの定義内の一時テーブルを含む厳密に型指定されたストアド プロシージャのメタデータの生成をサポートしていません。 代わりに、下から同じプロシージャのメタデータを生成する必要があります、**プロシージャ**ノードを使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
###  <a name="BKMK_SQLVS2008"></a>Visual Studio でのアダプターの使用時の無効なバインドの警告  
 **問題**  
  
 アプリケーションを作成するアダプターを使用すると[!INCLUDE[vs2010](../../includes/vs2010-md.md)]アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインド、`sqlBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。  
  
 **解決策**  
  
 この警告は無視してかまいません。  
  
###  <a name="BKMK_SQLNotification"></a>BizTalk Server が、同じアプリケーションで 1 つ以上の通知スキーマを使用して、同じホスト上の複数のアプリケーション間で通知スキーマを使用するか、例外をスローします。  
 **問題**  
  
 BizTalk Server は、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかのため発生します。  
  
-   1 つ以上を生成する、BizTalk Server プロジェクトでの通知スキーマを BizTalk Server アプリケーションに展開し、通知を受信する SQL Server データベースからアプリケーションを実行します。 競合が通知スキーマは、一般的なであるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
-   複数のプロジェクトが発生した場合、BizTalk Server が配置されたプロジェクトの各プロジェクトの場合、同じホスト上の別の BizTalk Server アプリケーションの各通知スキーマを生成したし、し、実行、アプリケーションまたはアプリケーションからの通知を受信するにはSQL Server データベースです。 スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるため競合があるさまざまな BizTalk Server アプリケーションおよびアセンブリの下でデプロイされる共通のスキーマ間でします。  
  
 **解決策**  
  
 BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションからの通知スキーマを使用します。  
  
###  <a name="BKMK_SQLRestoreConn"></a>アダプターのクライアントは、アダプターのクライアントと SQL Server データベース間の接続が復元された後に、演算を実行することで例外をスローします。  
 **問題**  
  
 アダプターのクライアントには、SQL Server データベースに対する操作を実行するのには、次の例外がスローされます。  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 **原因**  
  
 操作の実行中に、アダプターが SQL Server データベースに接続し、操作を実行する SQL ADO.NET 接続プールから接続を使用します。 アダプターのクライアントと SQL Server データベース間で簡単なネットワーク障害がある場合、または SQL Server データベースを一時的にある場合は、SQL の ADO.NET 接続プール内のすべての接続が無効になります。 接続が復元され、SQL Server データベースで操作を実行しようとする、アダプターでは、同じの無効な接続を使用して、SQL の ADO.NET 接続プールからとアダプターのクライアントが例外をスローするため。  
  
 **解決策**  
  
 アダプターのクライアントは、ここで例外をキャッチされ"n+1"として操作の再試行回数を指定する必要があります、操作の実行で再試行ロジックを実装する必要があります、"n"は MaxConnectionPoolSize バインディング プロパティに指定された値。 つまり、こと"n"が無効ですが表示される接続プール内の接続数がある場合は、理論上はアダプター クライアントを再試行する"n+1"の最大の有効な接続を取得し、そのため、操作を実行する時間。  
  
 などを指定する、再試行回数は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、開かれている、**プロパティ** ダイアログ ボックスをクリックして、アプリケーションで、送信ポートの**トランスポートの詳細オプション**とダイアログ ボックスの左側のウィンドウで、**トランスポートのオプション** 領域で値を指定、**再試行の回数** ボックスの一覧。  
  
###  <a name="BKMK_MemUsage"></a>メモリ使用量とスレッド数の増加トランザクション受信操作で、アダプターを使用する場合  
 **問題**  
  
 ポーリングなどのトランザクション受信操作で**かどうかはデータをポーリングするテーブルで使用できる**アダプターがポーリングを継続しは、メモリ使用量とスレッド数の増加が発生する期間にわたっています。  
  
 **原因**  
  
 **かどうかはデータをポーリングするテーブルで使用できる**の後にすべて受信タイムアウト サイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。 そのため、時間の期間にわたって、スレッドの数とメモリの使用量が増加します。 ただし、一部のデータをポーリングするテーブルには、同じスレッドが継続後続のすべてのポーリングを実行します。  
  
 **解決策**  
  
 設定を推奨、 **ReceiveTimeout**に最大の可能な値は 24.20:31:23.6470000 (24 日)、新しいスレッドが 24 日間にのみを生成できるようにします。 これにより、メモリ使用量とスレッド数が大きくならないが多すぎるが早すぎます。  
  
> [!NOTE]
>  SqlAdapterInboundTransactionBehavior が設定されている場合、TransactionTimeout が 24.20:31:23.6470000 (24 日) である最大の可能な値にも構成されていることを確認します。 この回避策を使用する場合、トランザクション分離レベルを構成する場合のみ、SqlAdapterInboundTransactionBehavior を追加できます。 それ以外の場合、その動作を削除することを勧めします。  
  
 詳細については、 **ReceiveTimeout**バインディング プロパティを参照してください[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 バインドのプロパティを指定する方法の詳細については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。  
  
> [!NOTE]
>  付いたアダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。  
  
## <a name="see-also"></a>参照  
[SQL アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)