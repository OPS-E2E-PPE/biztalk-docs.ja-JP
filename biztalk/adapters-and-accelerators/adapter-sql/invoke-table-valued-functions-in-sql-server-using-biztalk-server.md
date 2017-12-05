---
title: "BizTalk Server を使用して SQL Server でのテーブル値関数を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d360c15-699e-4859-8143-798c1de821db
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4729d62d52f8624eef766cf928b5232d4a669673
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-table-valued-functions-in-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server でのテーブル値関数を呼び出す
使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を SQL Server でのテーブル値関数を呼び出します。 アダプターは、SQL サーバー上で直接呼び出すことができる操作として、テーブル値関数を公開します。 アダプターでテーブル値関数をサポートする方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL Server で Executing Table-Valued 関数](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)です。 テーブル値関数を呼び出すため、SOAP メッセージの構造については、次を参照してください。[プロシージャと関数のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   作成、[厳密な名前キー ファイルを開き、ツールの説明](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
  
-   [MSDTC を構成して](configure-msdtc-on-sql-server-and-adapter-client.md)を実行しているコンピューターで、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL Server。
  
## <a name="invoke-table-valued-functions-on-a-sql-server-database"></a>SQL Server データベースでテーブル値関数を呼び出す  
 使用して、SQL Server データベースでの操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 SQL Server でのテーブル値関数を呼び出すには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、SQL Server で、呼び出し先のテーブル値関数のスキーマを生成します。  
  
2.  SQL Server からメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SQL Server で操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generate-schema"></a>スキーマを生成します。  
 このトピックは、SQL Server を使用してテーブル値関数を呼び出す方法を示します、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 この操作を示すためにこのトピックでは、TVF_EMPLOYEE 関数を実行します。 この関数は、パラメーターとして、従業員の表記を取得し、テーブル型として、指定があるすべての従業員レコードを返します。 Employee テーブルと、関数は、サンプルに用意されているスクリプトを実行して作成されます。 スクリプトの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。  
  
 テーブル値関数を呼び出す方法を示すためには、TVF_EMPLOYEE テーブル値関数のスキーマが生成されます。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。  
  
## <a name="define-messages-and-message-types"></a>メッセージおよびメッセージの定義の種類  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは通常、対応するスキーマによって定義された型の変数です。 ここで、オーケストレーションのメッセージを作成し、前の手順で生成されたスキーマにそれをリンクします。  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *TableFunctions.TableValuedFunction_dbo です。TVF_EMPLOYEE*TableFunctions は、BizTalk プロジェクトの名前。 TableValuedFunction_dbo は、TVF_EMPLOYEE 関数に対して生成されたスキーマでは。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *TableFunctions.TableValuedFunction_dbo です。TVF_EMPLOYEEResponse*です。|  
  
## <a name="set-up-the-orchestration"></a>オーケストレーションをセットアップします。  
 使用する BizTalk オーケストレーションを作成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server で操作を実行するためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]このメッセージを消費し、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形の SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。 テーブル値関数を呼び出すためのサンプル オーケストレーションには、次のようになります。  
  
 ![テーブル &#45; を呼び出すためのオーケストレーション関数の値を持つ](../../adapters-and-accelerators/adapter-sql/media/28ca3930-7ce8-423a-9edd-cb2888eebaac.gif "28ca3930-7ce8-423a-9edd-cb2888eebaac")  
  
### <a name="add-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形の列ごとには、次のプロパティを入力します。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="add-ports"></a>ポートを追加します。  
 論理ポートの列ごとには、次のプロパティを入力します。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを入力し、それらのポートを接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.TVF.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.TVF.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.TVF.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.TVF.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートを接続しているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドし、BizTalk Server に展開します。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configure-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。 
 
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SQL Server データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。
  
## <a name="start-the-application"></a>アプリケーションを開始します。  
 SQL Server データベースでテーブル値関数を呼び出すための BizTalk アプリケーションを起動します。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="execute-the-operation"></a>操作を実行します。  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマは、以前に生成した TVF_EMPLOYEE テーブル値関数用のスキーマに準拠している必要があります。 たとえば、TVF_EMPLOYEE 関数を呼び出すための要求メッセージには。  
  
```  
<TVF_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/dbo">  
  <emp_desig>Tester</emp_desig>  
</TVF_EMPLOYEE>  
```  
  
 この要求メッセージは、"Tester"として指定を持つ従業員レコードを取得する TVF_EMPLOYEE 関数を呼び出します。 参照してください[プロシージャと関数のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)SQL Server を使用してテーブル値関数を呼び出すための要求メッセージ スキーマの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
> [!NOTE]
>  アダプターが内部的に使用可能な場合、アダプターが、パラメーターの既定値を渡すことによって関数を実行することを意味する DEFAULT キーワードを使用して関数を実行して、パラメーターの値を指定しない場合、関数定義の一部として。  
  
 オーケストレーションはメッセージを処理して、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<TVF_EMPLOYEEResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/dbo">  
  <TVF_EMPLOYEEResult>  
    <TVF_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/TableFunctionReturnTables/dbo">  
      <Employee_ID>10499</Employee_ID>   
      <Name>John</Name>   
      <Designation>Tester</Designation>   
      <Salary>999999.00</Salary>   
      <Last_Modified>AAAAAAAAJBM=</Last_Modified>   
    </TVF_EMPLOYEE>  
    <TVF_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/TableFunctionReturnTables/dbo">  
      ......  
      ......  
    </TVF_EMPLOYEE>  
    ......  
    ......  
  </TVF_EMPLOYEEResult>  
</TVF_EMPLOYEEResponse>  
```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)