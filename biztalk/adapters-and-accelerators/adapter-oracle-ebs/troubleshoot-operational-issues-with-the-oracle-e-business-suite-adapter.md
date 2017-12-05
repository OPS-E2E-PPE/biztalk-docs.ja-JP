---
title: "Oracle E-business Suite アダプターでの運用上の問題のトラブルシューティング |Microsoft ドキュメント"
description: "一般的な問題と Oracle EBS アダプターの BizTalk アダプター パック (BAP) の解決策"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4654e228a4ca86c9d89686f826d57777f2353efd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターでの運用上の問題のトラブルシューティングします。
このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。  
  
## <a name="enabling-tracing"></a>トレースを有効にします。  
 トレースのサポートの詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、[診断トレースとメッセージ ログを Oracle E-business Suite アダプターで](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md)です。  
  
## <a name="known-issues"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なエラーは、次のとおり、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、およびその考えられる原因と解決します。  
  
  
  
###  <a name="BKMK_LoadBindings"></a>アダプターのバインドを読み込み中にエラー  
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
  
-   必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認してください、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 サポートされているクライアントのバージョンについてで利用可能なインストール ガイドを参照してください。\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。  
  
-   必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。  
  
###  <a name="BKMK_Display"></a>Oracle E-business Suite アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
 付属するアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]アダプターの一覧に表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 **原因**  
  
 最新[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]WCF カスタム バインドがします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
 **解決策**  
  
 明示的に追加することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)です。  
  
###  <a name="BKMK_MissingAction"></a>Oracle E-business Suite で操作の実行中のエラー  
 **問題**  
  
 Oracle E-business Suite を使用して、すべての操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   **BizTalk server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **原因**  
  
 メッセージの WCF アクションが指定されていません。 WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。  
  
 **解決策**  
  
 送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、次を参照してください。 [Oracle E-business Suite の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)です。 参照してください[メッセージと Oracle EBS アダプターのメッセージ スキーマを](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)各操作のアクションの一覧を表示します。  
  
###  <a name="BKMK_WrongClient"></a>要求メッセージが受信場所にドロップされたときに、Oracle クライアントのバージョンを誤ったため BizTalk プロセスがクラッシュ可能性があります。  
 **問題**  
  
 BizTalk オーケストレーションで定義されている受信場所で要求メッセージをドロップすると、オーケストレーションがメッセージを処理して、BizTalk ホスト (BTSNTSvc.exe) がクラッシュし、再起動します。  
  
 **原因**  
  
 Oracle クライアントをインストールすると、PATH 変数に最新のクライアント アセンブリへの参照が追加されます。 また、Oracle クライアント アセンブリの最新のインストールへの参照には、既存のクライアント アセンブリへの参照が前に付けます。 そのため、最新の Oracle クライアントのインストールがサポートされているクライアントのバージョンのでない場合 BizTalk ホストがクラッシュし、再起動します。  
  
 たとえば、パス変数は、次の参照をサポートされている Oracle クライアント 11.1.0.7 がコンピューターに既にインストールされてを想定します。  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 サポートされていない Oracle クライアント、たとえば 10.2.0.3 というが同じコンピューターにインストールされている場合、パス変数は、次の参照が得られます。  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 サポートされていないクライアントのバージョンがサポートされているバージョンより前に参照されているため BizTalk ホストがクラッシュすることに注意してください。 実行する 1 つ以上の BizTalk ホストがある場合は、アダプターをホストする 1 つがクラッシュします。  
  
 **解決策**  
  
 1 つ以上の Oracle クライアントが同じコンピューターにインストールされている場合は、PATH 変数に、他の Oracle クライアント バージョンの前に、サポートされている Oracle クライアントのバージョンが参照されていることを確認してください。 たとえば、サポートされている Oracle クライアントのバージョンが 11.1.0.7 の場合は、PATH 変数で参照する必要がありますようになります。  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a>操作の実行にオーバーフロー例外をスロー アダプター  
 **問題**  
  
 データセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型を含む操作を実行しようとする場合は、アダプターを使用して、アダプターではオーバーフロー例外がスロー可能性があります。  
  
 **原因**  
  
 これは、データセットまたはそれぞれの .NET 型に収まらない弱い型指定の REF CURSOR の内部 Oracle 数値データ型の大きな値を指定する場合に発生します。  
  
 **解決策**  
  
 データセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型の大きな値を渡す場合は、セーフである入力の値を設定して有効にする必要があります、 **EnableSafeTyping**にプロパティのバインド**true**. 文字列としてデータセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型を公開するセーフである入力の有効化します。  
  
###  <a name="BKMK_Arithmetic"></a>ExecuteScalar 操作の実行に算術オーバーフロー例外をスロー アダプター  
 **問題**  
  
 大きな数を取得する ExecuteScalar 操作で SELECT ステートメントを実行しようとする場合は、アダプターを使用して、アダプターは、次の例外がスローされます"System.OverflowException: 算術演算でオーバーフローが発生しました。"。  
  
 **原因**  
  
 これは、ODP.NET で ExecuteScalar 操作の既知の制限により発生します。 ODP.NET が .NET 10 進数のデータ型へのデータに合わせてしようとし、結果が大きすぎる .NET 10 進数型に収まるように、例外がスローされます。  
  
 **解決策**  
  
 ExecuteScalar 操作で、SELECT ステートメントで TO_CHAR() を使用して、文字列として返されるデータを変換します。  
  
###  <a name="BKMK_AppContext"></a>アダプターのクライアントが操作の実行では、次の例外をスローします。"を取得できませんでしたユーザー id、責任の id、アプリケーション id。確認の正しい値が渡されたかどうか。"  
 **問題**  
  
 Oracle E-business Suite の成果物 (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセット) に対する操作を実行している場合、アダプターのクライアントはこの例外をスロー可能性があります。  
  
 **原因**  
  
 これは、インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセットに対する操作の実行中に Oracle ユーザー名、パスワード、および責任の名前の組み合わせが正しくないを指定する場合に発生します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]これらの成果物のアプリケーション コンテキストを設定するためにこれらの値が必要です。 アプリケーション コンテキストの設定に関する詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
 **解決策**  
  
 正しい Oracle ユーザー名、パスワード、および Oracle E-business Suite の成果物のアプリケーション コンテキストを適切に設定する責任の組み合わせを指定する必要があります。 Oracle ユーザー名とパスワードの値を指定するには、使用する必要があります、 **OracleUserName**と**OraclePassword**プロパティをバインドします。 Oracle 責任の値を指定するには、使用するか、 **OracleEBSResponsibilityName**プロパティまたはメッセージのコンテキスト プロパティをバインドします。  
  
###  <a name="BKMK_RootNode"></a>RootNode TypeName BizTalk プロジェクト内のエラー  
 **問題**  
  
 BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決策**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。  
  
###  <a name="BKMK_InvalidBinding"></a>Visual Studio でのアダプターの使用時の無効なバインドの警告  
 **問題**  
  
 アプリケーションを作成するアダプターを使用すると[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド、`oracleEBSBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。  
  
 **解決策**  
  
 この警告は無視してかまいません。  
  
###  <a name="BKMK_Notify"></a>BizTalk Server が、同じアプリケーションで 1 つ以上の通知スキーマを使用して、同じホスト上の複数のアプリケーション間で通知スキーマを使用するか、例外をスローします。  
 **問題**  
  
 BizTalk Server は、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかのため発生します。  
  
-   1 つ以上を生成する、BizTalk Server プロジェクトでの通知スキーマを BizTalk Server アプリケーションに展開し、Oracle データベースから通知を受け取るアプリケーションを実行します。 競合が通知スキーマは、一般的なであるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
-   複数のプロジェクトが発生した場合、BizTalk Server が配置されたプロジェクトの各プロジェクトの場合、同じホスト上の別の BizTalk Server アプリケーションの各通知スキーマを生成したし、し、実行、アプリケーションまたはアプリケーションからの通知を受信するにはOracle データベースです。 スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるため競合があるさまざまな BizTalk Server アプリケーションおよびアセンブリの下でデプロイされる共通のスキーマ間でします。  
  
 **解決策**  
  
 BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションからの通知スキーマを使用します。  
  
###  <a name="BKMK_Timeout"></a>Visual Studio での Oracle E-business Suite 成果物の参照中にタイムアウト例外  
 **問題**  
  
 Oracle E-business Suite のアイテムの閲覧中に、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクトを使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]タイムアウト例外が発生する可能性があります。  
  
 **原因**  
  
 これは、Oracle E-business Suite をホストしているサーバーが低速なサーバーがリモートの場所にある、または 検索するスキーマが成果物の数が多い場合に発生する可能性があります。  
  
 **解決策**  
  
 値を大きくかを選択できます、 **SendTimeout**に検索式を入力、またはプロパティのバインド、**カテゴリで検索**を成果物の数を減らすためにテキスト ボックスをアダプター取得します。  
  
 バインドのプロパティを指定する方法の詳細については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。 Oracle E-business Suite でアイテムを検索する方法に関する詳細については、次を参照してください。[参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
###  <a name="BKMK_MemUsage"></a>メモリ使用量とスレッド数の増加トランザクション受信操作で、アダプターを使用する場合  
 **問題**  
  
 ポーリングなどのトランザクション受信操作で**かどうかはデータをポーリングするテーブルで使用できる**アダプターがポーリングを継続しは、メモリ使用量とスレッド数の増加が発生する期間にわたっています。  
  
 **原因**  
  
 **かどうかはデータをポーリングするテーブルで使用できる**の後にすべて受信タイムアウト サイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。 そのため、時間の期間にわたって、スレッドの数とメモリの使用量が増加します。 ただし、一部のデータをポーリングするテーブルには、同じスレッドが継続後続のすべてのポーリングを実行します。  
  
 **解決策**  
  
 設定を推奨、 **ReceiveTimeout**に最大の可能な値は 24.20:31:23.6470000 (24 日)、新しいスレッドが 24 日間にのみを生成できるようにします。 これにより、メモリ使用量とスレッド数が大きくならないが多すぎるが早すぎます。  
  
 詳細については、 **ReceiveTimeout**バインディング プロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 バインドのプロパティを指定する方法の詳細については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。  
  
> [!NOTE]
>  付いたアダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。  
  
## <a name="see-also"></a>参照  
[Oracle EBS アダプターのトラブルシューティング](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)