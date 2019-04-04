---
title: BizTalk Server を使用して SQL Server のスカラー関数を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70bb7be9-ae31-4505-9406-f9d4744b65e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7ad0d193f3445fd751c7893277588348342802
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979051"
---
# <a name="invoke-scalar-functions-in-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server のスカラー関数を呼び出す
使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server のスカラー関数を呼び出します。 アダプターは、SQL サーバー上で直接呼び出すことができる操作として、スカラー関数を公開します。 アダプターがスカラー関数をサポートする方法の詳細については、[SQL アダプターを使用して SQL server のスカラー関数の実行](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)を参照してください。 スカラー関数を呼び出すため、SOAP メッセージの構造については、[プロシージャと関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
  
- 作成、[厳密な名前キー ファイルを開き、ツールの説明](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
  
- [MSDTC を構成する](configure-msdtc-on-sql-server-and-adapter-client.md)実行するコンピューターで、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL Server。
  
## <a name="invoke-scalar-functions-on-sql-server-database"></a>SQL Server データベースのスカラー関数を呼び出す  
 使用して SQL Server データベースでの操作を実行する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。 これらのタスクは SQL Server のスカラー関数を呼び出すには。  
  
1. BizTalk プロジェクトを作成し、SQL server を起動するスカラー関数のスキーマを生成します。  
  
2. SQL Server からメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. SQL Server で操作を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generate-schema"></a>スキーマを生成します。  
 このトピックでは、SQL Server を使用してスカラー関数を呼び出す方法を示します、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 この操作を説明するためにこのトピックでは、GET_EMP_ID 関数を実行します。 この関数は、パラメーターとして、従業員の指定を受け取り、その従業員の従業員テーブルから ID を返します。 テーブルと、関数は、サンプルに付属のスクリプトを実行して作成されます。 スクリプトの詳細については、[SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)を参照してください。  
  
 スカラー関数を呼び出す方法を示すためには、GET_EMP_ID スカラー関数のスキーマが生成されます。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。  
  
## <a name="define-messages-and-message-types"></a>メッセージとメッセージ定義の種類  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 ここでは、オーケストレーションでは、メッセージを作成し、前の手順で生成したスキーマにリンクします。    
 
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *ScalarFunction.ScalarFunction_dbo します。GET_EMP_ID*ScalarFunction は、BizTalk プロジェクトの名前です。 ScalarFunction_dbo は GET_EMP_ID 関数に対して生成されたスキーマを示します。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *ScalarFunction.ScalarFunction_dbo します。GET_EMP_IDResponse*します。|  
  
## <a name="set-up-the-orchestration"></a>オーケストレーションをセットアップします。  
 BizTalk オーケストレーションを使用する作成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server で操作を実行します。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がこのメッセージを使用して、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形とそれぞれに、応答を受信する SQL Server にメッセージを送信する必要があります。 スカラー関数を呼び出すためのサンプル オーケストレーションには、次のようになります。  
  
 ![スカラー関数を呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/9f69c9b9-2466-46d5-8423-1ccdc37a93fb.gif "9f69c9b9-2466-46d5-8423-1ccdc37a93fb")  
  
### <a name="add-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="add-ports"></a>ポートを追加します。  
 各論理ポートには、次のプロパティを入力します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.ScalarFunction.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.ScalarFunction.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.ScalarFunction.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.ScalarFunction.Request*|  
  
 これらのプロパティを入力した後、メッセージの構築図形とポートを接続すると、し、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドし、BizTalk サーバーに配置します。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。  
  
## <a name="configure-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。
   
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが SQL Server データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)を参照してください。
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。
  
## <a name="start-the-application"></a>アプリケーションを起動します  
 SQL Server データベースのスカラー関数を呼び出すための BizTalk アプリケーションを起動します。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="execute-the-operation"></a>操作を実行します  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、以前に生成した GET_EMP_ID 関数のスキーマに準拠する必要があります。 たとえば、GET_EMP_ID 関数の呼び出しに要求メッセージには。  
  
```  
<GET_EMP_ID xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/dbo">  
  <emp_desig>Manager</emp_desig>  
</GET_EMP_ID>  
```  
  
 この要求メッセージは、"Manager"の表記で従業員の ID を取得する GET_EMP_ID 関数を呼び出します。 参照してください[プロシージャと関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)要求メッセージ スキーマを使用して SQL Server のスカラー関数を呼び出すための詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
 オーケストレーションはメッセージを使用し、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_EMP_IDResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/dbo">  
  <GET_EMP_IDResult>10072</GET_EMP_IDResult>  
</GET_EMP_IDResponse>  
```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)を参照してください。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)