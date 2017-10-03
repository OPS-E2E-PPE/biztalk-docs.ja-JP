---
title: "BizTalk Server を使用して SQL Server での複合操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86fd2aa1-20c7-4b58-9f35-83ba0c959cf1
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa84ee4a4c1964db090cc48b7229558c9ee86114
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-composite-operations-on-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server での複合操作を実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントが、SQL Server データベースでの複合操作を実行できるようにします。 複合操作を含めることができます。  
  
-   Insert、Update、および削除操作です。 複合操作の一部としては、Select 操作がサポートされていません。  
  
-   操作として実行されるストアド プロシージャです。  
  
 1 つの複合操作は、任意の順序でこれらの操作の任意の数を持つことができます。 たとえば、次の 2 つの挿入操作の後に、削除操作と最後に、ストアド プロシージャの実行を持つことができます。 また、さまざまな操作が別のデータベース テーブルまたはビューを対象とすることができます。 アダプターが複合操作をサポートする方法の詳細については、次を参照してください。 [SQL アダプタを使用して SQL Server で複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)です。 複合操作用の SOAP メッセージの構造については、次を参照してください。[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)です。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="how-to-perform-composite-operations-on-sql-server"></a>SQL Server で合成の操作を実行する方法  
 SQL Server を使用して操作を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発するビルド ブロック](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 これらのタスクは、SQL Server データベースでの複合操作を行うには。  
  
1.  BizTalk プロジェクトを作成し、呼び出し先のすべての操作のスキーマを生成します。  
  
2.  前の手順で生成したすべてのスキーマへの参照を含むスキーマ ファイルを手動で作成します。  
  
3.  SQL Server データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。 これらのメッセージは、前の手順で作成した要求と応答のスキーマに準拠する必要があります。  
  
4.  SQL Server データベースで複合操作を呼び出すオーケストレーションを作成します。  
  
5.  構築し、BizTalk プロジェクトを展開します。  
  
6.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
7.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する方法についてを説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、CompositeOperations、このトピックの内容に基づいてが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、複合操作を実行する方法を示す、次のタスクが実行されます指定の順序で。  
  
-   EMPLOYEE テーブルにレコードを挿入します。  
  
-   GET_LAST_EMP_DATA ストアド プロシージャを呼び出すことによって、最後に挿入されたレコードのすべての列を取得します。  
  
-   EMPLOYEE テーブルからレコードを削除します。  
  
 EMPLOYEE テーブルを作成するサンプルに用意されているスクリプトを実行します。 サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。  
  
 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]をこれらの操作のスキーマを生成します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。  
  
## <a name="creating-a-composite-schema-definition"></a>複合のスキーマ定義を作成します。  
 個々 の操作用に作成したスキーマを参照する複合スキーマを作成する必要がありますようになりました。 複合のスキーマ定義を作成する次の手順を実行します。  
  
#### <a name="to-add-a-composite-schema-definition"></a>複合のスキーマ定義を追加するには  
  
1.  スキーマ ファイルを BizTalk プロジェクトに追加します。 プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 **新しい項目の追加** ダイアログ ボックスから、**カテゴリ**ボックスで、クリックして**スキーマ ファイル**です。 **テンプレート**ボックスで、クリックして**スキーマ**です。 スキーマ ファイルの名前を指定し、クリックして**OK**です。  
  
     この例で、ファイルとスキーマ名を指定`CompositeSchema.xsd`です。  
  
2.  実行する別の操作の生成スキーマへの参照を追加します。 この例では操作に対して生成されるさまざまなスキーマには。  
  
    -   TableOperation.dbo.Employee.xsd、挿入および削除操作です。  
  
    -   Procedure.dbo.xsd、GET_LAST_EMP_DATA のストアド プロシージャです。  
  
     参照を追加します。  
  
    1.  ルートを右クリックして**\<スキーマ >** CompositeSchema.xsd、およびクリック ノード**プロパティ**です。  
  
    2.  **プロパティ**ボックスで、省略記号ボタンをクリックして**([...])**に対して、 **Imports**プロパティです。  
  
         ![スキーマ定義をインポート](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")  
  
    3.  **Imports** ] ダイアログ ボックスから、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、順にクリック**追加**です。  
  
    4.  **BizTalk 型の選択** ダイアログ ボックスで、BizTalk プロジェクト名 ノードを展開し、展開**スキーマ**、し、インポートするスキーマを選択します。 この例では、< BizTalk_project_name > を選択します。TableOperation_dbo_Employee です。 **[OK]**をクリックします。  
  
         < BizTalk_project_name > をインポートするには、この手順を繰り返します。Procedure_dbo すぎます。  
  
    5.  **Imports**ダイアログ ボックスで、をクリックして**OK**です。  
  
3.  ルート スキーマ ノードに 2 つの子ノードを追加します。 1 つの子ノードは、複合操作を実行するため、要求スキーマに対応します。 その他の子ノードは、応答スキーマに対応します。 Request スキーマに対応するノードには、任意の名前を持つことができます。 応答スキーマに対応するノードには、< request_schema_node > 応答を呼び出す必要があります。 この例として、要求スキーマのノードを呼び出しては**要求**です。 そのため、応答スキーマのノードと呼びます**RequestResponse**です。  
  
    > [!NOTE]
    >  既定では、**ルート**ノードが新しいスキーマ ファイルにも追加します。 名前を変更することができます、**ルート**ノード**要求**です。 ノードの名前を変更するノード名を右クリックし、をクリックして**の名前を変更**です。  
  
     下のノードを追加する、 **\<スキーマ >**ノード。  
  
    1.  右クリックし、 **\<スキーマ >**に**スキーマ ノードの挿入**、 をクリック**子レコード**です。  
  
    2.  新しいノードの名前を**RequestResponse**です。  
  
4.  下に子ノードを追加、**要求**複合操作の一部として実行する各操作の要求スキーマに対応するノードです。 この例では、次に対応する子ノードを追加する必要があります。  
  
    -   挿入し、従業員テーブルに対する操作を削除します。  
  
    -   GET_LAST_EMP_DATA はストアド プロシージャです。  
  
    > [!IMPORTANT]
    >  操作を実行する同じ順序でのノードを追加する必要があります。 たとえば、レコードを挿入し、ストアド プロシージャを実行し、挿入操作のノードを追加する必要があります最初のレコードを削除する場合は、後に、ストアド プロシージャのノードと最後に、削除操作のノード。  
  
     子ノードを追加する、**要求**ノード。  
  
    1.  右クリックし、**要求**に**スキーマ ノードの挿入**、順にクリック**子レコード**です。  
  
         ![スキーマの子ノードの挿入](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")  
  
    2.  複合操作の一部として実行する操作の要求スキーマに対応するレコードの名前を変更します。 たとえば、"Insert"するノードの名前を変更します。  
  
    3.  マップ、**挿入**の EMPLOYEE テーブルに対する挿入操作の要求スキーマのノードです。 これを行うを右クリックし、**挿入** ノードをクリック**プロパティ**です。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[**挿入 (参照)**です。  
  
         ![要求スキーマへの子ノードをマップ](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")  
  
    4.  GET_LAST_EMP_DATA ストアド プロシージャおよび削除操作の要求スキーマのノードを追加する手順を繰り返します。 ノード名を指定し、次の表で説明したように、対応するスキーマにマップします。  
  
        |ノード名|スキーマにマップされています。|  
        |---------------|----------------------|  
        |GET_LAST_EMP_DATA|GET_LAST_EMP_DATA (参照)|  
        |DELETE|削除 (参照)|  
  
5.  下に子ノードを追加、 **RequestResponse**複合操作の一部として実行する各操作の応答スキーマに対応するノードです。 この例では、次に対応する子ノードを追加する必要があります。  
  
    -   挿入し、従業員テーブルに対する操作を削除します。  
  
    -   GET_LAST_EMP_DATA はストアド プロシージャです。  
  
    > [!IMPORTANT]
    >  下の子ノードと同じ順序で子ノードを追加する必要があります、**要求**ノード。  
  
     子ノードを追加する、 **RequestResponse**ノード。  
  
    1.  右クリックし、 **RequestResponse**に**スキーマ ノードの挿入**、 をクリック**子レコード**です。  
  
    2.  複合操作の一部として実行する操作の応答スキーマに対応するレコードの名前を変更します。 たとえば、"InsertResponse"するノードの名前を変更します。  
  
    3.  マップ、 **InsertResponse**を EMPLOYEE テーブルに対する挿入操作の応答スキーマのノードです。 これを行うを右クリックし、 **InsertResponse**ノード、およびクリック**プロパティ**です。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **InsertResponse (参照)**です。  
  
    4.  GET_LAST_EMP_DATA ストアド プロシージャおよび削除操作の応答スキーマのノードを追加する手順を繰り返します。 ノード名を指定し、次の表で説明したように、対応するスキーマにマップします。  
  
        |ノード名|スキーマにマップされています。|  
        |---------------|----------------------|  
        |GET_LAST_EMP_DATAResponse|GET_LAST_EMP_DATAResponse (参照)|  
        |DeleteResponse|DeleteResponse (参照)|  
  
6.  保存、 **CompositeSchema.xsd**ファイル。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 最後の手順で作成した複合スキーマでは、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションのメッセージを作成し、それらを前の手順で作成したスキーマにリンクする必要がありますようになりました。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *CompositeOp.CompositeSchema.Request*CompositeOp は、BizTalk プロジェクトの名前。 CompositeSchema は、複合操作用に手動で作成したスキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *CompositeOp.CompositeSchema.RequestResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server で合成の操作を実行します。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 要求メッセージは、先ほど作成した複合スキーマに準拠する必要があります。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]このメッセージを消費し、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形を SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。 複合操作を実行するための基本的なオーケストレーションには、次のようになります。  
  
 ![複合操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")  
  
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
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを指定して、ポートへの接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.CompositeOp.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.CompositeOp.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.CompositeOp.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.CompositeOp.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SQL Server データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 操作の場合は、単一のトランザクションで複合操作の一部が実行されるとしていることを確認するため、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**です。  
  
         送信ポートでアクションを指定することもあります。 複合操作のアクションが"**CompositeOperation**"です。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。 ポートのアクションを指定する方法の詳細については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)です。
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。 Wcf-custom または WCF-SQL 送信ポートのアクションがで選択したすべての操作に関連する動的なアクションに設定されているこのバインド ファイルをインポートする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中にします。 複合操作では、"CompositeOperation"がある動的アクションを置き換える必要があります。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースでの複合操作を実行する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマは、先ほど作成した複合操作のスキーマに準拠する必要があります。 たとえば、EMPLOYEE テーブルにレコードを挿入、GET_LAST_EMP_DATA ストアド プロシージャを呼び出すし、EMPLOYEE テーブルからレコードを削除する要求メッセージには。  
  
```  
<Request xmlns="http://CompositeTest.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
        <Designation>Manager</Designation>  
        <Salary>100000</Salary>  
      </Employee>  
    </Rows>  
  </Insert>  
  <GET_LAST_EMP_DATA xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo" />  
  <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
      </Employee>  
    </Rows>  
  </Delete>  
</Request>  
```  
  
 参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)を使用して、データベースの SQL Server で合成の操作を実行する要求メッセージ スキーマの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
 オーケストレーションはメッセージを処理して、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://CompositeTest.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <InsertResult>  
      <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10080</long>   
    </InsertResult>  
  </InsertResponse>  
  <GET_LAST_EMP_DATAResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
    <GET_LAST_EMP_DATAResult>  
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
        \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
            \<xs:complexType>  
              \<xs:sequence>  
                \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  \<xs:complexType>  
                    \<xs:sequence>  
                      \<xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      \<xs:element minOccurs="0" name="Name" type="xs:string" />   
                      \<xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                      \<xs:element minOccurs="0" name="Designation" type="xs:string" />   
                      \<xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                      \<xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                      \<xs:element minOccurs="0" name="Rating" type="xs:string" />   
                      \<xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
                    \</xs:sequence>  
                  \</xs:complexType>  
                \</xs:element>  
              \</xs:sequence>  
            \</xs:complexType>  
          \</xs:element>  
        \</xs:schema>  
        \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="">  
            <NewTable>  
              <Employee_ID>10080</Employee_ID>   
              <Name>John</Name>   
              <Designation>Manager</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF40=</Last_Modified>   
            </NewTable>  
          </NewDataSet>  
        \</diffgr:diffgram>  
      </DataSet>  
    </GET_LAST_EMP_DATAResult>  
    <ReturnValue>0</ReturnValue>   
  </GET_LAST_EMP_DATAResponse>  
  <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 前の応答には、複合操作の一部として実行されるさまざまな操作を対応する複数の結果セットが含まれています。 たとえば、`InsertResult`要素 10080 は含まれています、新しく追加されたレコードの一意の識別子。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)