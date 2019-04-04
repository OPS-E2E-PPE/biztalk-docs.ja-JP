---
title: Oracle E-business Suite アダプターを使用した運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的な問題と Oracle EBS アダプターの BizTalk アダプター パック (BAP) の解決策
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119afaea2382e1ede6c780a40bbe2bf4329860f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989992"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターを使用した運用上の問題のトラブルシューティングします。
このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。  
  
## <a name="enabling-tracing"></a>トレースを有効にします。  
 トレースのサポートの詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、[診断トレースとメッセージ ログの Oracle E-business Suite アダプターで](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md)します。  
  
## <a name="known-issues"></a>既知の問題  
 使用する場合に発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]と共に、考えられる原因と解決します。  
  
  
  
###  <a name="BKMK_LoadBindings"></a> アダプターのバインドを読み込み中にエラー  
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
  
- 必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 サポートされているクライアントのバージョンについてで使用可能なインストール ガイドを参照してください。\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
  
- 必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。  
  
###  <a name="BKMK_Display"></a> Oracle E-business Suite アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。  
 **問題**  
  
 付属のアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]でアダプターの一覧が表示されない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 **原因**  
  
 最新[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]WCF カスタム バインドします。 そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
 **解決方法**  
  
 明示的に追加することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。  
  
###  <a name="BKMK_MissingAction"></a> Oracle E-business suite 操作の実行中のエラー  
 **問題**  
  
 Oracle E-business Suite を使用して、操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
- **BizTalk Server 用**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  メッセージの WCF アクションが指定されていません。 WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。  
  
  **解決方法**  
  
  送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。 手順については、[for Oracle E-business Suite の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)を参照してください。 参照してください[メッセージと Oracle EBS アダプターのメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)各操作のアクションの一覧を表示します。  
  
###  <a name="BKMK_WrongClient"></a> 要求メッセージが受信場所で削除されるとき、BizTalk プロセスが不適切な Oracle クライアントのバージョンのためクラッシュ  
 **問題**  
  
 要求メッセージを削除した後には、BizTalk オーケストレーションで定義されている受信場所で、オーケストレーションはメッセージを使用し、BizTalk ホスト (BTSNTSvc.exe) がクラッシュしたし、再起動します。  
  
 **原因**  
  
 Oracle クライアントをインストールすると、PATH 変数に最新のクライアント アセンブリへの参照が追加されます。 また、Oracle クライアント アセンブリの最新のインストールへの参照の前に、既存のクライアント アセンブリへの参照。 そのため、サポートされているクライアントのバージョンの最新の Oracle クライアントのインストールでない場合、BizTalk ホストがクラッシュし、し再起動します。  
  
 たとえば、11.1.0.7、サポートされている Oracle クライアントがコンピューターに既にインストールされていること、および PATH 変数は、次の参照。  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 場合は、次のようにサポートされていない Oracle クライアント、10.2.0.3 という例は、同じコンピューターにインストールされて、PATH 変数は、次の参照になります。  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 サポートされていないクライアントのバージョンがサポートされているバージョンの前に参照されていることと、BizTalk ホストがクラッシュするために注意してください。 実行している 1 つ以上の BizTalk ホストがある場合は、アダプターをホストする 1 つがクラッシュします。  
  
 **解決方法**  
  
 1 つ以上の Oracle クライアントが同じコンピューターにインストールされているの場合は、PATH 変数に、他の Oracle クライアント バージョンの前にサポートされている Oracle クライアントのバージョンが参照されていることを確認してください。 たとえば、サポートされている Oracle クライアントのバージョンが 11.1.0.7 の場合は、PATH 変数に参照する必要がありますようになります。  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a> アダプター操作の実行にオーバーフロー例外をスロー  
 **問題**  
  
 データセットまたは厳密に型指定の REF CURSOR の内部で Oracle の数値データ型を格納している操作を実行しようとする場合、アダプターを使用して、アダプターは、オーバーフロー例外をスロー可能性があります。  
  
 **原因**  
  
 これは、大規模なデータセットや、それぞれの .NET 型に収まらない厳密に型指定の REF CURSOR の内部で Oracle の数値データ型の値を指定する場合に発生します。  
  
 **解決方法**  
  
 データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型の大きな値を渡す場合は、安全な」と入力の値を設定して有効にする必要があります、 **EnableSafeTyping**プロパティをバインド**true**. 安全な入力を有効にすると、データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型が文字列として公開します。  
  
###  <a name="BKMK_Arithmetic"></a> アダプター、ExecuteScalar 操作の実行に算術オーバーフロー例外をスロー  
 **問題**  
  
 大きな数を取得、ExecuteScalar 操作で SELECT ステートメントを実行しようとする場合、アダプターを使用して、アダプターは、次の例外がスローされます"System.overflowexception:: 算術演算結果オーバーフローが発生します。"。  
  
 **原因**  
  
 これは、ODP.NET ExecuteScalar 操作の既知の制限のため発生します。 ODP.NET が .NET の 10 進数のデータ型へのデータに合わせてしようとし、結果が大きすぎて、.NET の Decimal 型に収まるように、例外がスローされます。  
  
 **解決方法**  
  
 ExecuteScalar 操作で SELECT ステートメントで TO_CHAR() を使用して、文字列として返されるデータを変換します。  
  
###  <a name="BKMK_AppContext"></a> アダプター クライアントの操作の実行では、次の例外がスロー:"を取得できませんでしたユーザー id、責任の id、アプリケーション id。確認の正しい値が渡されたかどうか。"  
 **問題**  
  
 アダプターのクライアントは、Oracle E-business Suite アーティファクト (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセット) に対する操作を実行している場合、この例外をスロー可能性があります。  
  
 **原因**  
  
 これは、インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セットに対する操作の実行中に Oracle ユーザー名、パスワード、および責任の名前の組み合わせが正しくないを指定する場合に発生します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]これらの成果物のアプリケーションのコンテキストを設定するにはこれらの値が必要です。 アプリケーション コンテキストの設定の詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  
  
 **解決方法**  
  
 Oracle ユーザー名、パスワード、および Oracle E-business Suite の成果物のアプリケーションのコンテキストを適切に設定する必要がありますの適切な組み合わせを指定する必要があります。 Oracle ユーザー名とパスワードの値を指定するに使用する必要があります、 **OracleUserName**と**OraclePassword**プロパティをバインドします。 Oracle 責任の値を指定するには、使用できます、 **OracleEBSResponsibilityName**プロパティまたはメッセージのコンテキスト プロパティをバインドします。  
  
###  <a name="BKMK_RootNode"></a> BizTalk プロジェクト内の RootNode TypeName とエラー  
 **問題**  
  
 BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解決方法**  
  
1.  クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。  
  
2.  **RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。  
  
###  <a name="BKMK_InvalidBinding"></a> Visual Studio で、アダプターを使用する際に無効なバインド警告  
 **問題**  
  
 アプリケーションを作成するアダプターを使用すると[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]とアダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 この警告が表示されます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド、`oracleEBSBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。  
  
 **解決方法**  
  
 この警告は無視してかまいません。  
  
###  <a name="BKMK_Notify"></a> 同じアプリケーション内で 1 つ以上の通知スキーマを使用するか、同じホスト上の複数のアプリケーションで通知スキーマを使用している場合、BizTalk Server は例外をスローします。  
 **問題**  
  
 BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。  
  
 **原因**  
  
 これは、次のいずれかの原因で発生します。  
  
- 1 つ以上を生成した通知スキーマを BizTalk Server プロジェクトで、BizTalk Server アプリケーションに展開し、Oracle データベースから通知を受け取るアプリケーションを実行します。 競合が通知のスキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。  
  
- 複数のプロジェクトが発生した場合、同じホスト上の別の BizTalk Server アプリケーションを各プロジェクト配置されたプロジェクト、BizTalk Server の各通知スキーマを生成したから通知を受信するアプリケーションを実行し、Oracle データベース。 競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。  
  
  **解決方法**  
  
  BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。 同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから通知スキーマを使用します。  
  
###  <a name="BKMK_Timeout"></a> Visual Studio での Oracle E-business Suite の成果物の閲覧中にタイムアウトの例外  
 **問題**  
  
 Oracle E-business Suite のアイテムの閲覧中に、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクトを使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]タイムアウト例外が発生する可能性があります。  
  
 **原因**  
  
 これは、Oracle E-business Suite をホストするサーバーが遅い、サーバーがリモートの場所にある、または 検索するスキーマに含まれる成果物の数が多い場合に発生する可能性があります。  
  
 **解決方法**  
  
 値を大きくかを選択できます、 **SendTimeout**に検索式を入力、またはプロパティのバインド、**カテゴリで検索**成果物の数を削減するテキスト ボックスをアダプター取得します。  
  
 バインドのプロパティを指定する方法については、[for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)を参照してください。 Oracle E-business Suite でアーティファクトの検索に関する詳細については、[参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)を参照してください。  
  
###  <a name="BKMK_MemUsage"></a> メモリ使用量とスレッド数の増加、トランザクション受信操作で、アダプターを使用する場合  
 **問題**  
  
 ポーリングなどのトランザクション受信操作で**かどうかデータがないポーリングされるテーブルで使用できる**アダプターがポーリングを継続しは、時間の期間にわたってメモリ使用量とスレッド数の増加が発生します。  
  
 **原因**  
  
 **かどうかはデータがないポーリングされるテーブルで使用できる**後にすべて受信タイムアウトのサイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。 そのため、期間のスレッドの数とメモリ使用量が増加します。 ただし、ポーリングされるテーブルにいくつかのデータがある場合、同じスレッドは、すべての後続のポーリングを実行する継続します。  
  
 **解決方法**  
  
 設定をお勧め、 **ReceiveTimeout**に最大の可能な値である 24.20:31:23.6470000 (24 日)、新しいスレッドは 24 日間にのみを生成できるようにします。 メモリ使用量とスレッドの数が大きくが多すぎるが早すぎるようになります。  
  
 詳細については、 **ReceiveTimeout**プロパティ、バインドを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 バインドのプロパティを指定する方法の詳細については、[for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)を参照してください。  
  
> [!NOTE]
>  アダプターを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。  
  
## <a name="see-also"></a>参照  
[Oracle EBS アダプターのトラブルシューティング](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)