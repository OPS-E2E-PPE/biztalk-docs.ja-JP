---
title: "挿入、更新、削除、または BizTalk Server アダプターを使用して、SQL 操作の選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d411b1a-a36d-4e3e-a56a-91804a5d69b9
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2216116e00e587d8da0d69cea8cd1c364e5786b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-or-select-operations-using-biztalk-server-with-the-sql-adapter"></a>挿入、更新、削除、または BizTalk Server アダプターを使用して、SQL 操作の選択
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server データベース テーブルやビュー上の標準的な操作のセットを表示します。 これらは、データ操作言語 (DML) 操作と呼ばれます。 DML 操作を使用すると、単純な Insert、Update、Select を実行し、テーブルおよびビューの操作を削除できます。 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルおよび SQL アダプターとビューの選択操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)です。 これらの操作用の SOAP メッセージの構造については、次を参照してください。 [Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="how-to-perform-basic-operations-on-a-sql-server-database"></a>SQL Server データベースの基本的な操作を実行する方法  
 使用して、SQL Server データベースでの操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 SQL Server では、Insert、Update、Delete、またはテーブルとビューに対する Select 操作を実行、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、SQL Server データベース テーブルまたはビューを起動する操作のスキーマを生成します。  
  
2.  SQL Server データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SQL Server データベース テーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、SelectTable、このトピックの内容に基づいてが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、SQL Server データベースの EMPLOYEE テーブルからレコードを選択して基本的な DML 操作を実行する方法を示します。 EMPLOYEE テーブルを作成するサンプルに用意されているスクリプトを実行します。 サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。  
  
 レコードを選択する方法を示すためには、EMPLOYEE テーブルに対して Select 操作のスキーマが生成されます。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。  
  
> [!IMPORTANT]
>  ユーザー定義型 (Udt) 列を持つテーブルに対する操作のメタデータを生成する場合と同じ場所に、Udt のそれぞれのアセンブリを利用できるように、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]実行可能ファイル devenv.exe です。 実行可能ファイルは通常`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`です。 EMPLOYEE テーブルでは、この例では、UDT (ポイント) 列があります。 同じ場所にあるそれぞれのアセンブリをコピーするかどうかを確認、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]実行可能ファイルです。  
>   
>  UDT を作成する方法については、次を参照してください。[ユーザー定義型を作成する](https://msdn.microsoft.com/library/ms131106.aspx)です。 SQL Server で UDT を登録する方法については、次を参照してください。 [SQL Server で Registering User-Defined 型](https://msdn.microsoft.com/library/eybzcxe6(v=vs.85).aspx)です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは通常、対応するスキーマによって定義された型の変数です。 オーケストレーションのメッセージを作成し、それらを前の手順で生成されたスキーマにリンクする必要がありますようになりました。  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *SelectTable.TableOperation_dbo_Employee.Select*SelectTable は、BizTalk プロジェクトの名前。 TableOperation_dbo_Employee は、EMPLOYEE テーブルでの Select 操作に対して生成されるスキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *SelectTable.TableOperation_dbo_Employee.SelectResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server で操作を実行するためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]このメッセージを消費し、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形の SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。 Select 操作のサンプルのオーケストレーションには、次のようになります。  
  
 ![SQL Server 上の Select 操作のオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/e74e342f-ba66-41fe-bd34-d45cd8767ef8.gif "e74e342f-ba66-41fe-bd34-d45cd8767ef8")  
  
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
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.Select.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Select.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Select.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.Select.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートを接続しているし、オーケストレーションが完了します。  
  
 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SQL Server データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベース テーブルからレコードを選択する場合、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションを起動する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
> [!IMPORTANT]
>  ユーザー定義型 (Udt) 列を持つテーブルでの操作を実行する場合と同じ場所に、Udt のそれぞれのアセンブリを利用できるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]実行可能ファイル、btsntsvc.exe です。 実行可能ファイルは通常`<installation drive>:\Program Files\Microsoft BizTalk Server <version>`です。 EMPLOYEE テーブルでは、この例では、UDT (ポイント) 列があります。 同じ場所にあるそれぞれのアセンブリをコピーするかどうかを確認、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]実行可能ファイルです。  
>   
>  UDT を作成する方法については、次を参照してください。[ユーザー定義型を作成する](https://msdn.microsoft.com/library/ms131106.aspx)です。 SQL Server で UDT を登録する方法については、次を参照してください。 [SQL Server で Register User-Defined 型](https://msdn.microsoft.com/library/ms131079.aspx)です。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマは、先に生成した Select 操作のスキーマに準拠する必要があります。 たとえば、EMPLOYEE テーブルからすべてのレコードを選択する要求メッセージには。  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>*</Columns>  
  <Query>where Employee_ID=10001</Query>  
</Select>  
```  
  
 この要求メッセージで指定された条件に適合する Employee テーブルからレコードを取得、`<Query>`要素。 テーブルから特定の列を取得する場合でそれらを指定する必要があります、< 列\>要素、テーブルの定義に示すように同じ順序で、コンマで区切って指定します。 データの取得でそのまま使用する条件を指定しないかどうか、`<Query>`要素が空です。 参照してください[Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)基本の DML 操作では、SQL Server を実行するための要求メッセージ スキーマの詳細についてはデータベース テーブルし、ビューを使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 オーケストレーションはメッセージを使用して、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<SelectResponse xmlns="mssql://Microsoft.LobServices.Sql/2008/01/TVOp/dbo/Employee">  
  <SelectResult>  
    <Employee xmlns="mssql://Microsoft.LobServices.Sql/2008/01/Types/Tables/dbo">  
      <Employee_ID>10001</Employee_ID>  
      <Name>John</Name>  
      <DOJ>1983-12-31T00:00:00Z</DOJ>  
      <Designation>Manager</Designation>  
      <Job_Description>Management</Job_Description>  
      <Photo>EjRVYzRFVQ==</Photo>  
      <Rating>1,2</Rating>  
      <Salary>100000.00</Salary>  
      <Last_Modified>AAAAAAAAD6I=</Last_Modified>  
    </Employee>  
  </SelectResult>  
</SelectResponse>  
```  
  
## <a name="best-practices"></a>ベスト プラクティス  
  
-   展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドが SQL の再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
-   挿入する場合は、更新、または削除する大量のデータを確認して値を設定する右のタイムアウトの WCF アダプタと、MSDTC トランザクションのです。 詳細については、「アダプターは、挿入、更新、または大量の BizTalk Server を使用して単一の操作でデータの削除に失敗」の問題を参照してください。 [SQL アダプタでの運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)です。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)