---
title: 'チュートリアル: データベースおよび .NET のファクトの使用 |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 676d6e46-d9f8-477e-979e-1ac051ad4451
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94eb3f34a529950a7344f6cc4579aa6f6909f813
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966955"
---
# <a name="walkthrough-using-database-and-net-facts"></a>チュートリアル: データベースおよび .NET のファクトの使用
ここでは、ビジネス ルール作成ツールを使用して、データベースおよび .NET のファクトを使用するポリシーを作成する手順について説明します。  

## <a name="prerequisites"></a>前提条件  
 値を設定する必要があります、 **StaticSupport**を 1 または 2 のチュートリアルを実行する前にレジストリ キー。 これによって、クライアントにクラスのインスタンスをアサートするように要求しなくても、ポリシーで .NET クラスの静的メソッドを呼び出すことができるようになります。 詳細については、[クラスの静的メンバーを呼び出す](../core/invoking-static-members-of-a-class.md)を参照してください。  

## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 次の表に示すように、このチュートリアルには 5 つの手順が含まれています。  

|プロシージャ タイトル|手順の説明|  
|---------------------|---------------------------|  
|TestDB データベースと PO テーブルを作成するには|作成するための手順について説明します、 **TestDB**データベースおよび**PO**テーブル。|  
|POUtility コンポーネントを作成するには|作成するための手順について説明します、 **POUtility**コンポーネント。|  
|ProcessPurchaseOrderDbNet ビジネス ポリシーを作成するには|作成するための手順について説明します、 **ProcessPurchaseOrderDbNet**ポリシー。|  
|ビジネス ルール作成ツールを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには|ビジネス ルール作成ツールを使用してテストする手順について説明します、 **ProcessPurchaseOrderDbNet**ポリシー。|  
|Policy.Execute メソッドを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには|テストするための手順について説明します、 **ProcessPurchaseOrderDbNet**ポリシーを使用して、 **Policy.Execute**メソッド。|  

### <a name="to-create-the-testdb-database-and-the-po-table"></a>TestDB データベースと PO テーブルを作成するには  

1.  **SQL Server Management Studio** を開きます。  

2.  サーバー名と認証を確認し、順にクリックします**Connect**します。  

3.  左側の [オブジェクト エクスプ ローラー] ウィンドウで、コンピューター名を右クリックし、**新しいクエリ**します。  

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

6.  オブジェクト エクスプ ローラー ウィンドウで、コンピューター名を展開し、**データベース**、ことを確認および**TestDB**存在します。  

7.  展開**TestDB**、展開**テーブル**、ことを確認および**dbo します。PO**存在します。  

8.  右クリックして**dbo します。PO**、 をクリックし、**テーブルを開く**次のデータがテーブルに存在することを確認します。  

    |PONumber|Quantity|状態|  
    |--------------|--------------|------------|  
    |PO1|400|NULL|  
    |PO2|700|NULL|  

### <a name="to-create-the-poutility-component"></a>POUtility コンポーネントを作成するには  

1. 開始**Microsoft Visual Studio**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  

3. **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  


   |             プロパティ              |                             目的                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **プロジェクトの種類**         |                        クリックして**Visual c#** します。                         |
   |           **[テンプレート]**           |                      クリックして**クラス ライブラリ**します。                       |
   |             **名前**              |                       型**POUtilityLib**します。                        |
   |           **場所**            |          指定**C:\BRE-Walkthroughs**場所として。           |
   |         **[ソリューション名]**         |                       型**POUtilitySol**します。                        |
   | **ソリューションのディレクトリを作成します。** | ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。 |


4. **[OK]** をクリックします。 **POUtilityLib**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  

5. [プロパティ] ウィンドウで、ファイルの名前を変更する**Class1.cs**を**POUtility.cs**します。  

6. 次のコードに示すように、パブリック コンストラクターをクラスに追加します。  

   ```  
   public POUtility()  
   {  
   }  
   ```  

7. という名前の静的メソッドを追加**GetMaxAllowed**を**POUtility**クラスの次のコードに示すようにします。  

   ```  
   public static int GetMaxAllowed()  
   {  
   return 500;  
   }   
   ```  

8. 開始**Visual Studio コマンド プロンプト**します。  

9. ディレクトリに移動します**C:\BRE-Walkthroughs\POUtilitySol**、次のコマンドを実行します。  

     **Sn-k POUtility.snk**  

10. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、**プロパティ**、し、ダブルクリック**AssemblyInfo.cs**します。  

11. 次のステートメントを追加、 **AssemblyInfo.cs**最後にファイル。  

    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POUtilitySol\POUtility.snk")]  
    ```  

12. ソリューション エクスプ ローラー ウィンドウで右クリック**POUtilityLib**、 をクリックし、**ビルド**します。  

13. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動します**C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**、しを GAC (グローバル POUtility コンポーネントを登録するには、次のコマンドを実行アセンブリ キャッシュ)。 場合は、コマンド プロンプトを開き、次の手順 8 に開くことはありません。  

     **Gacutil-i POUtilityLib.dll**  

### <a name="to-create-the-processpurchaseorderdbnet-business-policy"></a>ProcessPurchaseOrderDbNet ビジネス ポリシーを作成するには  

1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。  

    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  

2.  [ファクト エクスプ ローラー] ウィンドウ**データベース**します。  

3.  右クリック**サーバー**、 をクリックし、**参照**します。  

4.  サーバーとの認証情報を確認し、 **OK**します。  

5.  展開**TestDB**、順に展開**PO**します。  

6.  [ファクト エクスプ ローラー] ウィンドウ **.NET クラス**します。  

7.  右クリックして**します。NETAssemblies**、 をクリックし、**参照**します。  

8.  選択**POUtility**、 をクリックし、 **OK**。  

9. 展開**Class1**します。  

10. ポリシー エクスプ ローラー ウィンドウで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。  

11. ポリシーの名前を変更**Policy1**に**ProcessPurchaseOrderDbNet**し、ENTER キーを押します。 ポリシーの名前は [プロパティ] ウィンドウで変更することもできます。  

12. 右クリックして**バージョン 1.0**、 をクリックし、**新しいルールの追加**します。  

13. ルールの名前を変更**Rule1**に**ApprovalRule**し、ENTER キーを押します。 ルールの名前は [プロパティ] ウィンドウで変更することもできます。  

14. 右側の場合にペイン (上部)、右クリック**条件**、 をクリックして**述語**、 をクリックし、 **以下**。  

15. [ファクト エクスプ ローラー] ウィンドウ**データベース**します。  

16. ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**引数 1** IF ペインでします。  

17. [ファクト エクスプ ローラー] ウィンドウ **.NET クラス**します。  

18. ドラッグ**GetMaxAllowed**ノードを ファクト エクスプ ローラー ウィンドウから**引数 2** IF ペインでします。  

19. [ファクト エクスプ ローラー] ウィンドウ**データベース**します。  

20. ドラッグ、**状態**ノードをファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右下にある THEN ペインにします。  

21. [THEN] ペインで、次のようにクリックします。 **\<値を入力します\>** し、入力**Approved**。  

22. ファクト エクスプ ローラー ウィンドウで、右クリック**バージョン 1.0**で**ProcessPurchaseOrderDbNet**、 をクリックし、**新しいルールの追加**します。  

23. ルールの名前を変更**Rule1**に**DeniedRule**し、ENTER キーを押します。 ルールの名前は [プロパティ] ウィンドウで変更することもできます。  

24. 右側の場合にペイン (上部)、右クリック**条件**、 をクリックして**述語**、 をクリックし、 **GreaterThan**。  

25. [ファクト エクスプ ローラー] ウィンドウ**データベース**します。  

26. ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**引数 1** IF ペインでします。  

27. [ファクト エクスプ ローラー] ウィンドウ **.NET クラス**します。  

28. ドラッグ、 **GetMaxAllowed**ノードを ファクト エクスプ ローラー ウィンドウから**引数 2** IF ペインでします。  

29. [ファクト エクスプ ローラー] ウィンドウ**データベース**します。  

30. ドラッグ、**状態**ノードをファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右下にある THEN ペインにします。  

31. THEN ペインで次のようにクリックします。 **\<値を入力します\>** し、入力**Denied**します。  

32. ポリシー エクスプ ローラー ウィンドウで右クリック**バージョン 1.0 (未保存)**、 をクリックし、**保存**します。  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-business-rule-composer"></a>ビジネス ルール作成ツールを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには  

1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。  

2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrderDbNet**、右クリック**バージョン 1.0**、 をクリックし、**ポリシーのテスト**.  

3.  クリックして**TestDB:PO (Data Connection)**、 をクリックし、**インスタンスの追加**します。  

4.  **SQL サーバーへの接続**ダイアログ ボックスで、サーバー名と認証情報を確認し、順にクリックします**OK**します。  

5.  **バインドの選択** ダイアログ ボックスで、展開**TestDB**、 をクリックして**PO**、順にクリックします**OK**します。  

6.  クリックして**テスト**します。  

7.  [出力] ウィンドウであることを確認両方、 **ApprovalRule**と**DeniedRule**が発生します。  

8.  SQL Server Management studio で右クリックして**dbo します。PO**、 をクリックし、**テーブルを開く**します。  

9. いることを確認の値、**状態**にフィールドが設定されている**Approved**最初のレコード。  

10. いることを確認の値、**状態**にフィールドが設定されている**が拒否されました**2 番目のレコード。  

    > [!NOTE]
    >  値が引き続き表示される場合、**状態**NULL としてフィールドをデータを含むリストを右クリックし、をクリックし、 **SQL 実行**ビューが更新されます。  

11. SQL Server Management Studio は開いたままにしておきます。  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-policyexecute-method"></a>Policy.Execute メソッドを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには  

1. 開始**Microsoft Visual Studio**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  

3. **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  


   |             プロパティ              |                             目的                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **プロジェクトの種類**         |                        クリックして**Visual c#** します。                         |
   |           **[テンプレート]**           |                   クリックして**コンソール アプリケーション**します。                    |
   |             **名前**              |                    型**TestProcessPODbNet**します。                     |
   |           **場所**            |          指定**C:\BRE-Walkthroughs**場所として。           |
   |         **[ソリューション名]**         |                   型**TestProcessPODbNetSol**します。                   |
   | **ソリューションのディレクトリを作成します。** | ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。 |


4. **[OK]** をクリックします。 **TestProcessPODbNet**プロジェクトがソリューション エクスプ ローラーで表示されます。 ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  

5. ソリューション エクスプ ローラーで右クリックして**参照**、 をクリックし、**参照の追加**します。  

6. をクリックして**参照**を参照**\Program Files\Common files \microsoft BizTalk**、し、ダブルクリック **[microsoft.ruleengine.dll]** します。  

7. 先頭に次のコードを追加、 **Program.cs**既存の後にファイルを`using`ステートメント。  

   ```  
   //To use the SQLConnection class  
   using System.Data.SqlClient;  

   //To use the Policy and DataConnection classes  
   using Microsoft.RuleEngine;  
   ```  

8. 次のコードを追加、 **Main**関数を作成して開く、 **SQLConnection**オブジェクト。  

   ```  
   SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
   cn.Open();  
   ```  

9. 次のコードを追加、 **Main**関数の末尾を作成する、 **DataConnection**オブジェクトに基づいて、 **SQLConnection**前の手順で作成したオブジェクトします。  

    ```  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    ```  

10. 次のコードを追加、 **Main**関数の末尾を作成する、**ポリシー**オブジェクトし、ポリシーの実行します。  

    ```  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    ```  

11. 次のコードを追加、 **Main**関数の末尾にデータベースを更新します。  

    ```  
    dc.Update();  
    ```  

12. 次のコードを追加、 **Main**関数の末尾をデータベースへの接続を閉じます。  

    ```  
    cn.Close();  
    ```  

13. 生成された例外をキャッチする try/catch ブロックを追加、 **Main**メソッド。  

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

15. **ビルド** メニューのをクリックして**ビルド TestProcessPODbNet**します。  

16. ビジネス ルール作成ツールで、展開**ポリシー**、展開**ProcessPurchaseOrderDbNet**、右クリック**バージョン 1.0**、順にクリックします**発行**.  

17. 右クリック**バージョン 1.0 - 公開済み**、 をクリックし、**デプロイ**します。  

18. SQL Server Management studio での値を設定、**状態**フィールドを**NULL**の両方の PO レコード。  

19. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を実行するには、CTRL + F5 キーを押して、 **TestProcessPODbNet**アプリケーション。  

20. 任意のキーを押してコマンド プロンプト ウィンドウを閉じます。  

21. SQL Server Management studio で、PO レコードのテーブルを右クリックし、 **SQL 実行**します。  

22. いることを確認の値、**状態**にフィールドが設定されている**Approved**最初のレコード。  

23. いることを確認の値、**状態**にフィールドが設定されている**が拒否されました**2 番目のレコード。  

## <a name="comments"></a>コメント  

-   ポリシーで .NET クラスの非静的メソッドを使用する場合は、ポリシーをビジネス ルール作成ツールでテストするために .NET クラスのインスタンスをアサートするファクト作成コンポーネントを使用する必要があります。  

-   ビジネス ルール作成ツールがのインスタンスを作成することに注意してくださいに非常に重要ですが、 **DataConnection**オブジェクトし、するルール エンジンの作業メモリに自動的にアサートが。 ただし、クライアント (BizTalk または BizTalk 以外) アプリケーションからポリシーを呼び出すと、 **DataConnection**のオブジェクトが自動的に作成されません。 クライアントを作成する必要があります、 **DataConnection**オブジェクトし、パラメーターまたはファクトとしてポリシーを実行するルール エンジンに渡します。  

-   使用することができます、 **DebugTrackingInterceptor**ポリシー実行の詳細を追跡するクラス。 次のサンプル コードのインスタンスを作成する方法を示しています、 **DebugTrackingInterceptor**クラスし、ポリシーの実行時に使用します。  

    ```  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    ```  

-   使用することができます、 **SqlTransaction**からデータベースを更新するクラス、 **ProcessPODbNet**をトランザクションでのポリシー。 次のコードは、トランザクションを開始するには、トランザクションをパラメーターとして渡す方法を示しています、 **DataConnection**オブジェクト、およびデータベースの変更をコミットします。 詳細については、[トランザクション サポート](../core/transaction-support.md)を参照してください。  

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