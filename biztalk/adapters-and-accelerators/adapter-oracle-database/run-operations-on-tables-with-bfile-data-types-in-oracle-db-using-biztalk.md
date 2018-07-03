---
title: BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルに対する操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations on tables with BFILE data types, performing by using BizTalk Server
- BFILE data types
ms.assetid: 2e4af5a9-acde-419b-a99c-3eaa0c72daa8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6d70bcee5ccea0c6906c434d64981888576f4a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987451"
---
# <a name="run-operations-on-tables-with-bfile-data-types-in-oracle-database-using-biztalk-server"></a>BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルに対する操作を実行します。
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] BFILE データ型をテーブルとストアド プロシージャでサポートしています。 このセクションでは、BFILE データ型の列があるテーブルに対して操作を実行する方法について説明します。 方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サポート BFILE を参照してください[テーブルに BFILE データ型に対する演算 Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-with-bfile-data-types-in-oracle-database.md)します。  
  
## <a name="setting-up-your-oracle-database-server-for-operations-on-bfile"></a>BFILE に対する操作の Oracle データベース サーバーの設定  
 このセクションでは、SCOTT にレコードを挿入するプロシージャを呼び出す方法を示します。CUSTOMERDOC テーブルです。 このテーブルは BFILE データ型の列を保持し、付属の SQL スクリプトを実行して作成、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。 サンプルとの SQL スクリプトの詳細については、次を参照してください。 [Oracle データベース アダプターのサンプル](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md)します。  
  
 CUSTOMERDOC テーブルを作成するスクリプトを実行した後、BFILE データ型に対する演算を有効にする Oracle データベースを実行するコンピューターでの操作を実行する必要があります。 Oracle データベースのために必要なタスクは次のとおりです。  
  
1.  Oracle データベースを実行するコンピューターで C:\MYDIR ディレクトリを作成します。  
  
2.  Oracle データベースでは、論理ディレクトリを作成します。 これには、SYSDBA 特権を持つユーザーは、通常必要があります。 以下に例を示します。  
  
    ```  
    CREATE OR REPLACE DIRECTORY MYDIR AS 'C:\MYDIR';  
    ```  
  
3.  Oracle では、論理ディレクトリにアクセスするユーザーに権限を追加します。 以下に例を示します。  
  
    ```  
    GRANT READ, WRITE ON DIRECTORY MYDIR to SCOTT;  
    ```  
  
4.  Oracle database、Oracle では、論理ディレクトリに関連付けられているを実行するコンピューターで、物理ディレクトリの場所にアクセスするファイルをコピーします。 このディレクトリは、手順 1. で作成します。  
  
     上記の例に基づいて、customer_profile.txt C:\MYDIR ディレクトリにファイルをコピーします。 このファイルは BFILE 操作に使用できるようになりました。 操作の実行の詳細については、次を参照してください。 [Oracle データベースでの BizTalk Server を使用して大規模なオブジェクトの種類のデータ テーブルで操作を実行する](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-object-data-types-in-oracle-database.md)します。  
  
    > [!IMPORTANT]
    >  ReadLOB 操作は、BFILE データ型を持つテーブルでサポートされます。 UpdateLOB 操作がサポートされていません。 ただし、ユーザーは、更新操作を代わりに使用できます。  
  
## <a name="how-to-perform-operations-using-bfile-data-types"></a>BFILE データ型を使用して操作を実行する方法  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。 SCOTT にレコードを挿入するプロシージャを呼び出します。CUSTOMERDOC テーブルでは、これらのタスクは。  
  
1. BizTalk プロジェクトを作成し、CREATE_CUSTOMERDOC ストアド プロシージャのスキーマを生成します。  
  
2. Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. Oracle データベースのテーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル Operate_BFILE、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。 [Oracle データベース アダプターのサンプル](../../adapters-and-accelerators/adapter-oracle-database/samples-for-the-oracle-database-adapter.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックで、BFILE 列を持つテーブルに対する操作を実行する方法を示すを呼び出す CREATE_CUSTOMERDOC プロシージャ。 このプロシージャは、サンプルで提供される SQL スクリプトを実行して SCOTT\Package\ACCOUNT_PKG スキーマの下に作成されます。 このプロシージャは、BFILE レコード型を受け取り、CUSTOMERDOC テーブルにレコードを追加します。 SQL スクリプトの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。  
  
 参照してください[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: Oracle データベースとその他の応答を受信する要求を送信する 1 つ。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
2.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
3.  新しく作成されたメッセージを右クリックし、[**プロパティ] ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOC*ここで、 *BFILE_Operations*の名前を指定します。BizTalk プロジェクト。 *OracleDBBindingSchema* CREATE_CUSTOMERDOC プロシージャに対して生成されるスキーマです。|  
  
5.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *BFILE_Operations.OracleDBBindingSchema.CREATE_CUSTOMERDOCResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロシージャを実行します。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がこのメッセージを使用して、ODP を使用して Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 Oracle database テーブルに BFILE 列に対する操作を実行するための一般的なオーケストレーションが含まれます。  
  
- Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
- Oracle データベースに送信する要求メッセージを受信するポートは一方向の受信します。  
  
- 双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
- フォルダーに Oracle データベースからの応答を送信する一方向の送信ポート。  
  
  サンプル オーケストレーションには、次のようになります。  
  
  ![BFILE を使用した操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/5902cf48-0555-4d9a-b902-5208949b6c87.gif "5902cf48-0555-4d9a-b902-5208949b6c87")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.Create_BFILE します。要求*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Create_BFILE します。要求*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Create_BFILE します。応答*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.Create_BFILE します。要求*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Oracle データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、次を参照してください。 [、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 CUSTOMERDOC テーブルにレコードを作成するプロシージャを呼び出すための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb の送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、以前に作成したプロシージャのスキーマに準拠する必要があります。 参照してください[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)要求メッセージ スキーマを使用してプロシージャを呼び出すための詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
 たとえば、CREATE_CUSTOMERDOC プロシージャを呼び出す要求メッセージには。  
  
```  
<CREATE_CUSTOMERDOC xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CNAME>John Smith</CNAME>  
  <CDOC>MYDIR/John_Smith_profile.txt</CDOC>  
</CREATE_CUSTOMERDOC>  
```  
  
> [!NOTE]
>  テキスト ファイル、John_Smith_profile.txt は Oracle では、論理ディレクトリに関連付けられている物理ディレクトリの場所に存在である必要があります。 この例では、テキスト ファイルは C:\MYDIR 内に存在する必要があります。  
  
 オーケストレーションはメッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の Oracle データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<CREATE_CUSTOMERDOCResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"></CREATE_CUSTOMERDOCResponse>  
```  
  
> [!NOTE]
>  BFILE 型フィールドがテーブルからデータを読み取るようなオーケストレーションを作成することができます。 SQL スクリプトが付属、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] GET_CUSTOMERDOC プロシージャを含む、ACCOUNT_PKG を作成します。 この手順を使用するには、SCOTT から BFILE データを取得します。CUSTOMERDOC テーブルです。  
> 
>  サンプルについては、Operate_BFILE はのサンプルに含まれているも[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 このサンプルは、SCOTT にレコードを挿入する方法を示します。CUSTOMERDOC テーブルが、CREATE_CUSTOMERDOC を使用してストアド プロシージャ (このトピックで説明します。)BFILE データを SCOTT から読み取る方法も示します。GET_CUSTOMERDOC を使用して CUSTOMERDOC テーブルはストアド プロシージャです。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報を使用して、DML 操作の実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)します。  
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)