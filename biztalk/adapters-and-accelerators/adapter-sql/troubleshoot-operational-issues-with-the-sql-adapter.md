---
title: Biztalk SQL アダプターを使用した運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的な問題と、SQL アダプターの BizTalk アダプター パック (BAP) の解決策
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb3f48fca23825ec98fdc7f38012e44f7b2a00e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994587"
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a>SQL アダプターを使用した運用上の問題をトラブルシューティングします。
このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]します。  
  
## <a name="enabling-tracing"></a>トレースを有効にします。  
 アダプターのトレースを有効にする必要があります[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、問題の詳細については、収集するために SQL Server が使用中に発生して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 トレースのサポートの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[診断トレースと SQL アダプターでメッセージのログ記録](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)します。  
  
## <a name="known-issues"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と共に、考えられる原因と解決します。  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a> アダプターのバインドを読み込み中にエラー  
 **問題**  
  
 開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生しました。  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 開始しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。 さらに、アダプターのバインドは、エンタープライズ アプリケーションの特定のクライアント ソフトウェアに依存します。 含まれているすべてのアダプターをインストールすると、アダプターの標準または完了のインストールを実行した場合に、この問題が発生する可能性があります、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 ただし、1 つだけのエンタープライズ アプリケーション用に LOB クライアント ライブラリをインストールする場合があります。 その結果、GUI の他のアダプターのバインドの読み込みに失敗します。  
  
 **解決方法**  
  
 必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。  
  
###  <a name="BKMK_SQLDisplay"></a> SQL アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
 付属のアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]でアダプターの一覧が表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 **原因**  
  
 最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]WCF カスタム バインドします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
 **解決方法**  
  
 明示的に追加することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)します。  
  
###  <a name="BKMK_MissingAction"></a> SQL Server データベースに対する操作の実行中のエラー  
 **問題**  
  
 使用して SQL Server データベースに対して任意の操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
- **BizTalk Server 用**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  メッセージの WCF アクションが指定されていません。 WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。  
  
  **解決方法**  
  
  送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧を表示します。  
  
###  <a name="BKMK_SQLInvalidOp"></a> Errorcode InvalidOperationException FILESTREAM 操作を実行中に 5 を =  
 **問題**  
  
 使用中に次のエラーが発生した、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] FILESTREAM 操作を実行します。  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 **原因**  
  
 SQL Server データベースに接続するデータベース資格情報を指定する可能性があります。 FILESTREAM 操作を実行するには、必ずに Windows 認証を使用する必要があります。 エラー コード「5」では、正しくない資格情報のためのアクセスが拒否されることを示します。 別のエラー コードの詳細については、次を参照してください。[システム エラー コード (0 ~ 499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)します。
  
 **解決方法**  
  
 SQL Server データベースに接続するには、Windows 認証を使用します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、これを行う空白のままユーザー名とパスワードのフィールド、Wcf-custom または WCF SQL ポートの構成 ダイアログ ボックスでします。  
  
###  <a name="BKMK_SQLPolling"></a> 操作のポーリングは返しませんメッセージ PollingStatement と PolledDataAvailableStatement に有効なステートメントが指定されている場合でも  
 **問題**  
  
 PollingStatement および PolledDataAvailableStatement のバインド プロパティの有効な値が指定されている場合でも、アダプターでは、SQL Server からは、ポーリング メッセージは受け取りません。  
  
 **原因**  
  
 他のトランザクションが、アダプターがポーリングされるテーブルでロックを取得するかどうかを確認します。  
  
 **解決方法**  
  
 別のトランザクションの一部として更新されるテーブルをポーリングする場合は、PolledDataAvailableStatement バインド プロパティに指定されたクエリの一部として、ロックが適用される場合でもデータが返されるようにする"(nolock)"を使用したパラメーターを使用してを考慮することができます。その他のトランザクション。 詳細については、次を参照してください。[データベース エンジンの SQL ロック](https://msdn.microsoft.com/library/ms190615.aspx)します。
  
###  <a name="BKMK_SQLSingleOp"></a> アダプターは、挿入、更新、または大量のデータを BizTalk Server を使用して 1 つの操作を削除に失敗しました。  
 **問題**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]が挿入、更新、または大量の 1 つの操作を使用してデータの削除に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
 **原因**  
  
 挿入、更新、または大量のデータを削除していますが、時間がかかると[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を操作が実行される、トランザクションがタイムアウトになる可能性があります。  
  
 **解決方法**  
  
- **BizTalk Server 用**  
  
  1. Machine.config ファイルでは、WCF アダプターのタイムアウトを指定します。Machine.config ファイルの下に移動\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。  
  
     ```  
     <configuration>  
      <system.transactions>  
       <machineSettings maxTimeout="02:00:00" />  
      </system.transactions>  
     </configuration>  
     ```  
  
      この設定では、WCF アダプターのタイムアウトは 2 時間に設定されます。  
  
  2. Machine.config ファイルでは、MSDTC トランザクションのタイムアウト設定を指定します。Machine.config ファイルの下に移動\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG し、次のような抜粋を追加します。  
  
     ```  
     <system.transactions>   
             <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
         </system.transactions>  
  
     ```  
  
      この設定では、MSDTC のタイムアウトは 2 時間に設定されます。 MSDTC のタイムアウトの既定値は、10 分です。  
  
     > [!IMPORTANT]
     >  アダプターのクライアントと SQL Server を実行するコンピューターでこの変更を行う必要があります。 例では、< computer_name > をアダプターのクライアントと SQL Server を実行しているコンピューターの名前に置き換えます。  
  
  3. 設定、 **SendTimeout**のプロパティのバインド、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]非常に大きな値にします。 バインドのプロパティを設定する方法については、次を参照してください。 [SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)します。  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a> データセットを含む応答メッセージの BizTalk Server の完全なスキーマ検証の失敗します。  
 **問題**  
  
 たとえば ExecuteReader、データセットを含む応答メッセージを返す操作の完全なスキーマの検証に失敗した[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
 **解決方法**  
  
 データセットを含む応答メッセージの完全なスキーマ検証を行わないことをお勧めします。 代わりに、次の操作を行う可能性があります。  
  
1.  スキーマと応答メッセージを返すと、操作を実行します。  
  
2.  応答メッセージからスキーマを .xsd ファイルにコピーし、このファイルを BizTalk プロジェクトに追加します。  
  
3.  オーケストレーションで xpath クエリを使用して、応答メッセージからデータを抽出します。  
  
###  <a name="BKMK_SQLRootNode"></a> BizTalk プロジェクト内の RootNode TypeName とエラー  
 **問題**  
  
 BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決方法**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a> アダプターが一時テーブルとストアド プロシージャを厳密に型指定のメタデータの生成に失敗します。  
 **問題**  
  
 アダプターは、その定義の一時テーブルを含む厳密に型指定されたストアド プロシージャのメタデータの生成に失敗します。 アダプターは、次の例外を示します。  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 **解決方法**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は、それらの定義の一時テーブルが含まれている厳密に型指定されたストアド プロシージャのメタデータの生成をサポートしていません。 代わりの下にある同じプロシージャのメタデータを生成する必要があります、**プロシージャ**ノードを使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
###  <a name="BKMK_SQLVS2008"></a> Visual Studio で、アダプターを使用する際に無効なバインド警告  
 **問題**  
  
 Visual Studio でアプリケーションを作成するアダプターを使用すると、アダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインド、`sqlBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。  
  
 **解決方法**  
  
 この警告は無視してかまいません。  
  
###  <a name="BKMK_SQLNotification"></a> 同じアプリケーション内で 1 つ以上の通知スキーマを使用するか、同じホスト上の複数のアプリケーションで通知スキーマを使用している場合、BizTalk Server は例外をスローします。  
 **問題**  
  
 BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかの原因で発生します。  
  
- 1 つ以上を生成した通知スキーマを BizTalk Server プロジェクト内に BizTalk Server アプリケーションでは、展開し、SQL Server データベースから通知を受け取るアプリケーションを実行します。 競合が通知のスキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
- 複数のプロジェクトが発生した場合、同じホスト上の別の BizTalk Server アプリケーションを各プロジェクト配置されたプロジェクト、BizTalk Server の各通知スキーマを生成したから通知を受信するアプリケーションを実行し、SQL Server データベース。 競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。  
  
  **解決方法**  
  
  BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから通知スキーマを使用します。  
  
###  <a name="BKMK_SQLRestoreConn"></a> アダプター クライアントは、アダプターのクライアントと SQL Server データベース間の接続が復元された後に、演算を実行することで例外をスローします。  
 **問題**  
  
 アダプターのクライアントでは、SQL Server データベースでの操作を実行する方法は、次の例外がスローされます。  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 **原因**  
  
 操作の実行中に、アダプターが、SQL Server データベースに接続し、操作を実行する SQL ADO.NET 接続プールから接続を使用します。 アダプターのクライアントと SQL Server データベース間で簡単なネットワーク障害が発生した場合、または SQL Server データベースが一時的がダウンした場合は、SQL の ADO.NET 接続プール内のすべての接続は無効になります。 接続が復元され、SQL Server データベースに対して操作を実行しようとした、アダプターでは、同じ無効な接続を使用して、SQL の ADO.NET 接続プールからとアダプターのクライアントが例外をスローするため。  
  
 **解決方法**  
  
 アダプター クライアントは、その操作の実行が例外をキャッチし、"n+1"として操作の再試行回数を指定の場所での再試行ロジックを実装する必要があります、"n"は MaxConnectionPoolSize バインド プロパティに指定された値。 つまり、ことがレンダリングされている無効な接続プール内の接続数の"n"がある場合は、理論的には、アダプター クライアントが再試行"n+1"の最大の有効な接続を取得し、そのため、操作を実行する時間。  
  
 などを指定する、再試行回数は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、オープン、**プロパティ** ダイアログ ボックスのアプリケーションでの送信ポートをクリックします**トランスポートの詳細オプション**と、ダイアログ ボックスの左側のウィンドウで、。**トランスポート オプション**領域の値を指定、**再試行の回数**一覧。  
  
###  <a name="BKMK_MemUsage"></a> メモリ使用量とスレッド数の増加、トランザクション受信操作で、アダプターを使用する場合  
 **問題**  
  
 ポーリングなどのトランザクション受信操作で**かどうかデータがないポーリングされるテーブルで使用できる**アダプターがポーリングを継続しは、時間の期間にわたってメモリ使用量とスレッド数の増加が発生します。  
  
 **原因**  
  
 **かどうかはデータがないポーリングされるテーブルで使用できる**後にすべて受信タイムアウトのサイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。 そのため、期間のスレッドの数とメモリ使用量が増加します。 ただし、ポーリングされるテーブルにいくつかのデータがある場合、同じスレッドは、すべての後続のポーリングを実行する継続します。  
  
 **解決方法**  
  
 設定をお勧め、 **ReceiveTimeout**に最大の可能な値である 24.20:31:23.6470000 (24 日)、新しいスレッドは 24 日間にのみを生成できるようにします。 メモリ使用量とスレッドの数が大きくが多すぎるが早すぎるようになります。  
  
> [!NOTE]
>  SqlAdapterInboundTransactionBehavior が設定されている場合、TransactionTimeout が 24.20:31:23.6470000 (24 日) である最大の可能な値にも構成されていることを確認します。 この回避策を使用する場合、トランザクション分離レベルを構成する場合のみ、SqlAdapterInboundTransactionBehavior を追加できます。 それ以外の場合、これはその動作を削除することをお勧めします。  
  
 詳細については、 **ReceiveTimeout**プロパティ、バインドを参照してください[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。 バインドのプロパティを指定する方法の詳細については、次を参照してください。 [SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)します。  
  
> [!NOTE]
>  アダプターを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。  
  
## <a name="see-also"></a>参照  
[SQL アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)