---
title: "チュートリアル: データベースおよび .NET のファクトを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 676d6e46-d9f8-477e-979e-1ac051ad4451
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca754e84d07718a3656aa9a6f27d3a54f831c25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-using-database-and-net-facts"></a>チュートリアル: データベースおよび .NET のファクトの使用
ここでは、ビジネス ルール作成ツールを使用して、データベースおよび .NET のファクトを使用するポリシーを作成する手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 値を設定する必要があります、 **StaticSupport**を 1 または 2、チュートリアルを実行する前にレジストリ キー。 これによって、クライアントにクラスのインスタンスをアサートするように要求しなくても、ポリシーで .NET クラスの静的メソッドを呼び出すことができるようになります。 詳細については、次を参照してください。[クラスの静的メンバーの呼び出し](../core/invoking-static-members-of-a-class.md)です。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 5 つの手順が含まれています。  
  
|手順のタイトル|手順の説明|  
|---------------------|---------------------------|  
|TestDB データベースと PO テーブルを作成するには|作成するための手順をわかりやすく説明、 **TestDB**データベースおよび**PO**テーブル。|  
|POUtility コンポーネントを作成するには|作成するための手順をわかりやすく説明、 **POUtility**コンポーネントです。|  
|ProcessPurchaseOrderDbNet ビジネス ポリシーを作成するには|作成するための手順をわかりやすく説明、 **ProcessPurchaseOrderDbNet**ポリシー。|  
|ビジネス ルール作成ツールを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには|ビジネス ルール作成ツールを使用してテストするための手順をわかりやすく説明、 **ProcessPurchaseOrderDbNet**ポリシー。|  
|Policy.Execute メソッドを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには|テストするための手順をわかりやすく説明、 **ProcessPurchaseOrderDbNet**ポリシーを使用して、 **Policy.Execute**メソッドです。|  
  
### <a name="to-create-the-testdb-database-and-the-po-table"></a>TestDB データベースと PO テーブルを作成するには  
  
1.  開いている**SQL Server Management Studio**です。  
  
2.  サーバー名と認証を確認し、をクリックして**接続**です。  
  
3.  左側の [オブジェクト エクスプ ローラー] ウィンドウでコンピューター名を右クリックし、をクリックして**新しいクエリ**です。  
  
4.  次の SQL ステートメントをクエリ ウィンドウにコピーします。  
  
    ```  
    CREATE DATABASE [TestDB]  
    GO  
  
    Use TestDB  
    CREATE TABLE [dbo].[PO]([PONumber] [nvarchar](50) NOT NULL,  
    [Quantity] [int] NOT NULL,  
    [Status] [nchar](10) NULL  
    CONSTRAINT [PK_PO] PRIMARY KEY CLUSTERED ([PONumber] ASC))   
    GO  
  
    INSERT INTO PO VALUES ('PO1', 400, NULL)  
    INSERT INTO PO VALUES ('PO2', 700, NULL)  
    GO  
    ```  
  
5.  F5 キーを押して、SQL クエリを実行します。  
  
6.  オブジェクト エクスプ ローラー ウィンドウで、コンピューター名を展開し、**データベース**、ことを確認および**TestDB**が存在します。  
  
7.  展開**TestDB**、展開**テーブル**、ことを確認および**dbo します。PO**が存在します。  
  
8.  右クリック**dbo します。PO**、クリックして**テーブルを開く**表に、次のデータが存在することを確認します。  
  
    |PONumber|Quantity|[状態]|  
    |--------------|--------------|------------|  
    |PO1|400|NULL|  
    |PO2|700|NULL|  
  
### <a name="to-create-the-poutility-component"></a>POUtility コンポーネントを作成するには  
  
1.  開始**Microsoft Visual Studio**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|をクリックして**Visual c#**です。|  
    |**[テンプレート]**|をクリックして**クラス ライブラリ**です。|  
    |**名前**|型**POUtilityLib**です。|  
    |**場所**|指定**C:\BRE-Walkthroughs**場所として。|  
    |**[ソリューション名]**|型**POUtilitySol**です。|  
    |**ソリューションのディレクトリを作成します。**|ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。|  
  
4.  **[OK]**をクリックします。 **POUtilityLib**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  
  
5.  [プロパティ] ウィンドウで、ファイルの名前変更**Class1.cs**を**POUtility.cs**です。  
  
6.  次のコードに示すように、パブリック コンストラクターをクラスに追加します。  
  
    ```  
    public POUtility()  
    {  
    }  
    ```  
  
7.  という名前の静的メソッドを追加**GetMaxAllowed**を**POUtility**クラスに次のコードに示すようにします。  
  
    ```  
    public static int GetMaxAllowed()  
    {  
    return 500;  
    }   
    ```  
  
8.  開始**Visual Studio コマンド プロンプト**です。  
  
9. ディレクトリに移動**C:\BRE-Walkthroughs\POUtilitySol**、次のコマンドを実行します。  
  
     **Sn-k POUtility.snk**  
  
10. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、**プロパティ**、順にダブルクリック**AssemblyInfo.cs**です。  
  
11. 次のステートメントを追加、 **AssemblyInfo.cs**最後のファイル。  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POUtilitySol\POUtility.snk")]  
    ```  
  
12. ソリューション エクスプ ローラー ウィンドウで右クリック**POUtilityLib**、クリックして**ビルド**です。  
  
13. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動**C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**、しを GAC (グローバル POUtility コンポーネントを登録するには、次のコマンドを実行アセンブリ キャッシュ)。 場合は、コマンド プロンプトを開き、次の手順を開くには、8 ではありません。  
  
     **Gacutil-i POUtilityLib.dll**  
  
### <a name="to-create-the-processpurchaseorderdbnet-business-policy"></a>ProcessPurchaseOrderDbNet ビジネス ポリシーを作成するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。 ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  [ファクト エクスプ ローラー] ウィンドウ**データベース**です。  
  
3.  右クリック**サーバー**、クリックして**参照**です。  
  
4.  サーバーと認証情報を確認し、をクリックして**OK**です。  
  
5.  展開**TestDB**の順に展開および**PO**です。  
  
6.  [ファクト エクスプ ローラー] ウィンドウ**.NET クラス**です。  
  
7.  右クリック**です。NETAssemblies**、クリックして**参照**です。  
  
8.  選択**POUtility**、順にクリック**OK**です。  
  
9. 展開**Class1**です。  
  
10. ポリシー エクスプ ローラー ウィンドウで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。  
  
11. ポリシーの名前を変更**"policy1"**に**ProcessPurchaseOrderDbNet**し、ENTER キーを押します。 ポリシーの名前は [プロパティ] ウィンドウで変更することもできます。  
  
12. 右クリック**バージョン 1.0**、クリックして**新しいルールの追加**です。  
  
13. ルールの名前を変更**Rule1**に**ApprovalRule**し、ENTER キーを押します。 ルールの名前は [プロパティ] ウィンドウで変更することもできます。  
  
14. IF ペイン (上部) の右側を右クリックし**条件**をクリックして**述語**、順にクリック**以下**です。  
  
15. [ファクト エクスプ ローラー] ウィンドウ**データベース**です。  
  
16. ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**argument1** IF ペイン。  
  
17. [ファクト エクスプ ローラー] ウィンドウ**.NET クラス**です。  
  
18. ドラッグ**GetMaxAllowed**ノードを ファクト エクスプ ローラー ウィンドウから**argument2** IF ペイン。  
  
19. [ファクト エクスプ ローラー] ウィンドウ**データベース**です。  
  
20. ドラッグ、**ステータス**ノード、ファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右下の THEN ペインにします。  
  
21. [THEN] ペインでをクリックして**\<値を入力 >**し入力**Approved**です。  
  
22. ファクト エクスプ ローラー ウィンドウで右クリック**バージョン 1.0**で**ProcessPurchaseOrderDbNet**、クリックして**新しいルールの追加**です。  
  
23. ルールの名前を変更**Rule1**に**DeniedRule**し、ENTER キーを押します。 ルールの名前は [プロパティ] ウィンドウで変更することもできます。  
  
24. IF ペイン (上部) の右側を右クリックし**条件**をクリックして**述語**、順にクリック**GreaterThan**です。  
  
25. [ファクト エクスプ ローラー] ウィンドウ**データベース**です。  
  
26. ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**argument1** IF ペイン。  
  
27. [ファクト エクスプ ローラー] ウィンドウ**.NET クラス**です。  
  
28. ドラッグ、 **GetMaxAllowed**ノードを ファクト エクスプ ローラー ウィンドウから**argument2** IF ペイン。  
  
29. [ファクト エクスプ ローラー] ウィンドウ**データベース**です。  
  
30. ドラッグ、**ステータス**ノード、ファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右下の THEN ペインにします。  
  
31. [THEN] ペインでをクリックして**\<値を入力 >**し入力**Denied**です。  
  
32. ポリシー エクスプ ローラー ウィンドウで右クリック**バージョン 1.0 (未保存)**、クリックして**保存**です。  
  
### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-business-rule-composer"></a>ビジネス ルール作成ツールを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。 ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrderDbNet**を右クリックして**バージョン 1.0**、クリックして**ポリシーのテスト**.  
  
3.  をクリックして**TestDB:PO (Data Connection)**、クリックして**インスタンスの追加**です。  
  
4.  **SQL Server への接続**ダイアログ ボックスでは、サーバー名と認証情報を確認し、をクリックして**OK**です。  
  
5.  **バインドの選択** ダイアログ ボックスで、展開**TestDB**、 をクリックして**PO**、順にクリック**OK**です。  
  
6.  をクリックして**テスト**です。  
  
7.  [出力] ウィンドウであることを確認両方、 **ApprovalRule**と**DeniedRule**が起動します。  
  
8.  SQL Server Management Studio で、右クリック**dbo します。PO**、クリックして**テーブルを開く**です。  
  
9. いることを確認の値、**ステータス**にフィールドが設定されている**Approved**最初のレコードです。  
  
10. いることを確認の値、**ステータス**にフィールドが設定されている**Denied** 2 番目のレコードです。  
  
    > [!NOTE]
    >  値が解消されない場合、**ステータス**NULL としてフィールドをデータを含むリストを右クリックし、をクリックして**SQL 実行**ビューを更新します。  
  
11. SQL Server Management Studio は開いたままにしておきます。  
  
### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-policyexecute-method"></a>Policy.Execute メソッドを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには  
  
1.  開始**Microsoft Visual Studio**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|をクリックして**Visual c#**です。|  
    |**[テンプレート]**|をクリックして**コンソール アプリケーション**です。|  
    |**名前**|型**TestProcessPODbNet**です。|  
    |**場所**|指定**C:\BRE-Walkthroughs**場所として。|  
    |**[ソリューション名]**|型**TestProcessPODbNetSol**です。|  
    |**ソリューションのディレクトリを作成します。**|ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。|  
  
4.  **[OK]**をクリックします。 **TestProcessPODbNet**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  
  
5.  ソリューション エクスプ ローラーで右クリック**参照**、クリックして**参照の追加**です。  
  
6.  をクリックして**参照**を参照**\program files \microsoft BizTalk**、順にダブルクリック**[microsoft.ruleengine.dll]**です。  
  
7.  先頭に次のコードを追加、 **Program.cs**後、既存のファイル`using`ステートメント。  
  
    ```  
    //To use the SQLConnection class  
    using System.Data.SqlClient;  
  
    //To use the Policy and DataConnection classes  
    using Microsoft.RuleEngine;  
    ```  
  
8.  次のコードを追加、 **Main**関数を作成し、開く、 **SQLConnection**オブジェクト。  
  
    ```  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    ```  
  
9. 次のコードを追加、 **Main**関数の末尾を作成する、 **DataConnection**オブジェクトに基づいて、 **SQLConnection**前の手順で作成したオブジェクトします。  
  
    ```  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    ```  
  
10. 次のコードを追加、 **Main**関数の末尾を作成する、**ポリシー**オブジェクトし、ポリシーを実行します。  
  
    ```  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    ```  
  
11. 次のコードを追加、 **Main**関数の末尾のデータベースを更新します。  
  
    ```  
    dc.Update();  
    ```  
  
12. 次のコードを追加、 **Main**関数の末尾をデータベースへの接続を閉じます。  
  
    ```  
    cn.Close();  
    ```  
  
13. 生成された例外をキャッチする try-catch ブロックを追加、 **Main**メソッドです。  
  
14. いることを確認の完全なコード、 **Main**関数は、次のコードに示すようにします。  
  
    ```  
    try  
    {  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    dc.Update();  
    cn.Close();  
    }  
    catch (Exception ex)  
    {  
    Console.WriteLine(ex.Message);  
    }  
    ```  
  
15. **ビルド** メニューのをクリックして**ビルド TestProcessPODbNet**です。  
  
16. ビジネス ルール作成ツールで、次のように展開します**ポリシー**、展開**ProcessPurchaseOrderDbNet**、を右クリック**バージョン 1.0**、順にクリック**発行。**.  
  
17. 右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。  
  
18. SQL Server Management Studio での値を設定、**ステータス**フィールドを**NULL**の両方の PO レコード。  
  
19. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を実行するには、CTRL + F5 キーを押して、 **TestProcessPODbNet**アプリケーションです。  
  
20. 任意のキーを押してコマンド プロンプト ウィンドウを閉じます。  
  
21. SQL Server Management Studio で PO レコードを含むテーブルを右クリックし、をクリックして**SQL 実行**です。  
  
22. いることを確認の値、**ステータス**にフィールドが設定されている**Approved**最初のレコードです。  
  
23. いることを確認の値、**ステータス**にフィールドが設定されている**Denied** 2 番目のレコードです。  
  
## <a name="comments"></a>コメント  
  
-   ポリシーで .NET クラスの非静的メソッドを使用する場合は、ポリシーをビジネス ルール作成ツールでテストするために .NET クラスのインスタンスをアサートするファクト作成コンポーネントを使用する必要があります。  
  
-   ビジネス ルール作成ツールがのインスタンスを作成することに注意してください、 **DataConnection**オブジェクトし、するルール エンジンの作業メモリに自動的にアサートことです。 ただし、クライアント (BizTalk または BizTalk 以外) アプリケーションからポリシーを呼び出すと、 **DataConnection**のオブジェクトが自動的に作成されません。 クライアントを作成する必要があります、 **DataConnection**オブジェクトをパラメーターまたはファクトとしてポリシーを実行するルール エンジンに渡すことです。  
  
-   使用することができます、 **DebugTrackingInterceptor**ポリシー実行の詳細を追跡するクラス。 次のサンプル コードは、のインスタンスを作成する方法を示します、 **DebugTrackingInterceptor**クラス、およびポリシーを実行するときに使用します。  
  
    ```  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    ```  
  
-   使用することができます、 **SqlTransaction**からデータベースを更新するクラス、 **ProcessPODbNet**トランザクション的な方法でポリシー。 次のコードは、するには、トランザクションを開始、トランザクションをパラメーターとして渡す方法を示しています、 **DataConnection**オブジェクト、およびデータベースの変更をコミットします。 詳細については、次を参照してください。[トランザクション サポート](../core/transaction-support.md)です。  
  
    ```  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    //Begin the transaction  
    SqlTransaction  tn = cn.BeginTransaction();  
    //Pass the transaction object to the DataConnection constructor  
    DataConnection dc = new DataConnection("TestDB", "PO", cn, tn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    dc.Update();  
    //Commit the database transaction  
    tn.Commit();  
    cn.Close();  
    ```  
  
## <a name="see-also"></a>参照  
 [ファクトの選択](../core/selecting-facts.md)