---
title: 挿入、更新、削除、または SQL アダプターを使用した BizTalk Server を使用して操作を選択します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d411b1a-a36d-4e3e-a56a-91804a5d69b9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8e7ee1ca1f19f07033cf94a460978d9597645aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369379"
---
# <a name="insert-update-delete-or-select-operations-using-biztalk-server-with-the-sql-adapter"></a>挿入、更新、削除、または SQL アダプターを使用した BizTalk Server を使用して操作を選択します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]一連の標準的な操作で SQL Server データベースのテーブルおよびビューを表示します。 データ操作言語 (DML) 操作といいます。 DML 操作を使用すると、単純な Insert、Update、Select を実行し、テーブルとビューで操作を削除できます。 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルとビューを SQL アダプターを使用した操作の選択](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)します。 これらの操作用の SOAP メッセージの構造については、次を参照してください。[挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)します。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="how-to-perform-basic-operations-on-a-sql-server-database"></a>SQL Server データベースに対する基本操作を実行する方法  
 使用して SQL Server データベースでの操作を実行する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。 これらのタスクは SQL Server では、Insert、Update、Delete、またはテーブルとビューに対する Select 操作を実行には。  
  
1. BizTalk プロジェクトを作成し、SQL Server データベース テーブルまたはビューを起動する操作のスキーマを生成します。  
  
2. SQL Server データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. SQL Server データベース テーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル SelectTable、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、SQL Server データベースの EMPLOYEE テーブルからレコードを選択して基本的な DML 操作を実行する方法を示します。 EMPLOYEE テーブルを作成するサンプルに付属のスクリプトを実行します。 サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。  
  
 レコードを選択する方法を示すためには、EMPLOYEE テーブルに対して Select 操作のスキーマが生成されます。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。  
  
> [!IMPORTANT]
>  ユーザー定義型 (Udt) 列を持つテーブルに対する操作のメタデータを生成する場合と同じ場所にある、Udt のそれぞれのアセンブリが使用できるように、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]実行可能ファイル devenv.exe します。 実行可能ファイルは通常、`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`します。 この例では、UDT (ポイント) 列が EMPLOYEE テーブルにあります。 同じ場所にあるそれぞれのアセンブリをコピーするかどうかを確認、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]実行可能ファイルです。  
> 
>  UDT を作成する方法については、次を参照してください。[ユーザー定義型を作成する](https://msdn.microsoft.com/library/ms131106.aspx)します。 SQL Server で UDT を登録する方法については、次を参照してください。 [SQL Server で Registering User-Defined 型](https://msdn.microsoft.com/library/eybzcxe6(v=vs.85).aspx)します。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは通常、対応するスキーマによって定義された型の変数です。 オーケストレーションのメッセージを作成し、前の手順で生成したスキーマにリンクする必要がありますようになりました。  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *SelectTable.TableOperation_dbo_Employee.Select*SelectTable は、BizTalk プロジェクトの名前です。 TableOperation_dbo_Employee は、EMPLOYEE テーブルの選択操作で生成されたスキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *SelectTable.TableOperation_dbo_Employee.SelectResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server で操作を実行します。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がこのメッセージを使用して、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形とそれぞれに、応答を受信する SQL Server にメッセージを送信する必要があります。 選択操作のサンプルのオーケストレーションには、次のようになります。  
  
 ![SQL Server 上の Select 操作のオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/e74e342f-ba66-41fe-bd34-d45cd8767ef8.gif "e74e342f-ba66-41fe-bd34-d45cd8767ef8")  
  
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
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.Select.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Select.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Select.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.Select.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートを接続すると、し、オーケストレーションが完了します。  
  
 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースのテーブルからレコードを選択するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを起動する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
> [!IMPORTANT]
>  ユーザー定義型 (Udt) 列を持つテーブルに対する操作を実行する場合と同じ場所にある、Udt のそれぞれのアセンブリが使用できるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]実行可能ファイル、btsntsvc.exe します。 実行可能ファイルは通常、`<installation drive>:\Program Files\Microsoft BizTalk Server <version>`します。 この例では、UDT (ポイント) 列が EMPLOYEE テーブルにあります。 同じ場所にあるそれぞれのアセンブリをコピーするかどうかを確認、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]実行可能ファイルです。  
> 
>  UDT を作成する方法については、次を参照してください。[ユーザー定義型を作成する](https://msdn.microsoft.com/library/ms131106.aspx)します。 SQL Server で UDT を登録する方法については、次を参照してください。 [SQL Server で Register User-Defined 型](https://msdn.microsoft.com/library/ms131079.aspx)します。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、先に生成した Select 操作のスキーマに準拠する必要があります。 たとえば、EMPLOYEE テーブルからすべてのレコードを選択する要求メッセージには。  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>*</Columns>  
  <Query>where Employee_ID=10001</Query>  
</Select>  
```  
  
 この要求メッセージはで指定された条件を満たす従業員テーブルからレコードを取得、`<Query>`要素。 テーブルから特定の列を取得する場合は、それらを指定する必要があります、< 列\>テーブルの定義に表示されるように、同じ順序で、コンマで区切られた要素。 データの取得でそのまま使用する条件を指定しないかどうか、`<Query>`要素が空です。 参照してください[挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)SQL Server での基本的な DML 操作を実行するための要求メッセージ スキーマの詳細については、データベースはテーブルし、ビューを使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 オーケストレーションはメッセージを使用し、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
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
  
-   展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[再利用の SQL アダプター バインド](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。
  
-   場合は、更新、挿入、または削除する大量のデータ確認して値を設定する適切なタイムアウト、WCF アダプターを MSDTC トランザクション。 詳細については、「、アダプターが挿入、更新、または大量のデータを BizTalk Server を使用して 1 つの操作の削除に失敗」の問題を参照してください。 [SQL アダプターでの運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)します。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)