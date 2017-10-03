---
title: "BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルでの操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations on tables with BFILE data types, performing by using BizTalk Server
- BFILE data types
ms.assetid: 2e4af5a9-acde-419b-a99c-3eaa0c72daa8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2219b93bfcc767af4eec6d433074a013dba0cca2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-tables-with-bfile-data-types-in-oracle-database-using-biztalk-server"></a>BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルでの操作を実行します。
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルやストアド プロシージャで BFILE データ型をサポートしています。 このセクションでは、BFILE データ型の列があるテーブルに対する操作を実行する方法について説明します。 方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サポート BFILE を参照してください[テーブルに BFILE データ型の演算 Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-with-bfile-data-types-in-oracle-database.md)です。  
  
## <a name="setting-up-your-oracle-database-server-for-operations-on-bfile"></a>BFILE に対する操作の Oracle データベース サーバーのセットアップ  
 このセクションでは、SCOTT にレコードを挿入するプロシージャを呼び出す方法を示します。CUSTOMERDOC テーブルです。 このテーブルは BFILE データ型の列に含まれており、付属の SQL スクリプトを実行することによって作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプルです。 サンプルおよび SQL スクリプトの詳細を知るには、次を参照してください。 [Oracle データベース アダプターのサンプル](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md)です。  
  
 CUSTOMERDOC テーブルを作成するスクリプトを実行した後は、BFILE データ型に対する操作を有効にする Oracle データベースを実行しているコンピューターで特定の操作を行う必要があります。 Oracle データベースで行う必要があります、タスクは次のとおりです。  
  
1.  Oracle データベースを実行しているコンピューターにディレクトリ C:\MYDIR を作成します。  
  
2.  Oracle データベースでは、論理ディレクトリを作成します。 これにより、SYSDBA 特権を持つユーザーが通常必要です。 例:  
  
    ```  
    CREATE OR REPLACE DIRECTORY MYDIR AS 'C:\MYDIR';  
    ```  
  
3.  Oracle では、論理ディレクトリにアクセスするユーザーに権限を追加します。 例:  
  
    ```  
    GRANT READ, WRITE ON DIRECTORY MYDIR to SCOTT;  
    ```  
  
4.  Oracle では、論理ディレクトリに関連付けられている Oracle データベースを実行するコンピューター上の物理ディレクトリ場所にアクセスするファイルをコピーします。 手順 1 では、このディレクトリを作成します。  
  
     上記の例に基づいて、ファイル、ディレクトリ C:\MYDIR customer_profile.txt をコピーします。 このファイルは、BFILE 操作に使用できるようになりました。 操作の実行の詳細については、次を参照してください。[大規模な Oracle データベースでの BizTalk Server を使用してデータ オブジェクト型を持つテーブルでの操作の実行](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-object-data-types-in-oracle-database.md)です。  
  
    > [!IMPORTANT]
    >  ReadLOB 操作は、BFILE データ型を持つテーブルでサポートされています。 UpdateLOB 操作はサポートされていません。 ただし、ユーザーは、更新操作を代わりに使用できます。  
  
## <a name="how-to-perform-operations-using-bfile-data-types"></a>BFILE データ型を使用して操作を実行する方法  
 Oracle データベースを使用して、操作を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、[の Oracle データベースと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)です。 SCOTT にレコードを挿入するプロシージャを呼び出します。CUSTOMERDOC 表では、これらのタスクに示します。  
  
1.  BizTalk プロジェクトを作成し、CREATE_CUSTOMERDOC ストアド プロシージャのスキーマを生成します。  
  
2.  Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  Oracle データベース テーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、Operate_BFILE、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [Oracle データベース アダプターのサンプル](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは BFILE 列を含むテーブルに対して操作を実行する方法を示すことが、CREATE_CUSTOMERDOC プロシージャを呼び出します。 この手順は、サンプルに用意されている SQL スクリプトを実行して SCOTT\Package\ACCOUNT_PKG スキーマで作成されます。 この手順では、BFILE レコード型を受け取りし、CUSTOMERDOC テーブルにレコードを追加します。 SQL スクリプトの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。  
  
 参照してください[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: Oracle データベースと他の応答を受信する要求を送信する 1 つです。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
2.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  新しく作成されたメッセージを右クリックし、[**プロパティ] ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOC*ここで、 *BFILE_Operations*の名前を指定します。BizTalk プロジェクトです。 *OracleDBBindingSchema* CREATE_CUSTOMERDOC プロシージャに対して生成されるスキーマです。|  
  
5.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOCResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロシージャを実行します。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]このメッセージを消費し、ODP を使用して Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 Oracle データベースのテーブルに BFILE 列に対する操作を実行するための一般的なオーケストレーションにが含まれます。  
  
-   Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを Oracle データベースに送信する要求メッセージを受信します。  
  
-   双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
-   フォルダーに Oracle データベースからの応答を送信する一方向の送信ポートです。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![BFILE で操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/5902cf48-0555-4d9a-b902-5208949b6c87.gif "5902cf48-0555-4d9a-b902-5208949b6c87")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを指定して、ポートへの接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.Create_BFILE です。要求*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Create_BFILE です。要求*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Create_BFILE です。応答*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.Create_BFILE です。要求*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、次を参照してください。 [Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk Server 管理コンソールから、このバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 CUSTOMERDOC テーブルにレコードを作成するプロシージャを呼び出すための BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマは、以前に作成したプロシージャのスキーマに準拠する必要があります。 参照してください[関数およびプロシージャのメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)、要求メッセージ スキーマを使用してプロシージャを呼び出すための詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 たとえば、CREATE_CUSTOMERDOC プロシージャを呼び出す要求メッセージには。  
  
```  
<CREATE_CUSTOMERDOC xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CNAME>John Smith</CNAME>  
  <CDOC>MYDIR/John_Smith_profile.txt</CDOC>  
</CREATE_CUSTOMERDOC>  
```  
  
> [!NOTE]
>  テキスト ファイル、John_Smith_profile.txt は、Oracle では、論理ディレクトリに関連付けられている物理ディレクトリの場所に存在する必要があります。 この例では、テキスト ファイルは C:\MYDIR 内に存在する必要があります。  
  
 オーケストレーションはメッセージを使用して、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の Oracle データベースからの応答には。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<CREATE_CUSTOMERDOCResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"></CREATE_CUSTOMERDOCResponse>  
```  
  
> [!NOTE]
>  BFILE 種類フィールドのあるテーブルからデータを読み取るようなオーケストレーションを作成することができます。 付属の SQL スクリプト、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] GET_CUSTOMERDOC プロシージャを含む ACCOUNT_PKG を作成します。 この手順を使用するには、SCOTT から BFILE データを取得します。CUSTOMERDOC テーブルです。  
>   
>  サンプルについては、Operate_BFILE も含まれていますのサンプルを使って[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 このサンプルは、SCOTT にレコードを挿入する方法を示します。CUSTOMERDOC テーブル、CREATE_CUSTOMERDOC を使用してストアド プロシージャ (このトピックで説明します。)このサンプルでは、SCOTT から BFILE データを読み取る方法も示します。GET_CUSTOMERDOC を使用して CUSTOMERDOC テーブルはストアド プロシージャです。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報を使用して、DML 操作の実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)