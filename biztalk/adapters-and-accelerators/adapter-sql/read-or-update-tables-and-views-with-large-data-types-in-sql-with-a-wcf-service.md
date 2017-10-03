---
title: "WCF サービス モデルを使用して SQL の大規模なデータ型を持つテーブルとビューの操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d33e17c-e09e-4a57-9acc-43095e67ed8c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c673e5c31c0498bb82fe7979d2855765f4c9bf35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL の大規模なデータ型を持つテーブルとビューの操作を実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントの読み取りし、は、大規模なデータ型の列のデータを更新する、varchar (max)、nvarchar (max)、または varbinary (max) を有効にします。 このような列からデータを読み取る、アダプターのクライアントは、Select 操作を使用できます。 アダプターの一連の公開を挿入またはこのような列にデータを更新、\<*column_name*> 操作、場所\< *column_name*> の型 varchar (列の名前を指定しますmax)、nvarchar (max)、または varbinary (max)。  
  
 さらに、SQL Server でテキスト ドキュメントやイメージなどの非構造化データを格納 varbinay(max) 列を持つことができます。 このような非構造化データには、FILESTREAM データは呼び出されます。 FILESTREAM データは、ファイル システム上のファイルとして格納することができます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Varbinary (max) 型の列に FILESTREAM データを入力するクライアントを有効にします。 [FILESTREAM ストレージ](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server)の詳細についてはします。 
  
 このトピックの内容が行う必要があります、特定のタスクに関する情報を提供、コンピューター上には、SQL Server とを挿入または FILESTREAM データを更新できるアダプターのクライアントを実行しているコンピューターを実行しています。 このトピックの内容についても説明セットを実行する\<*column_name*> FILESTREAM データを挿入する操作。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server を実行しているコンピューターと、アダプターのクライアントを実行しているコンピューターで、次のタスクを行う必要があります。  
  
-   **SQL Server を実行するコンピューター**  
  
    -   SQL Server インスタンスで FILESTREAM を有効にする必要があります。 参照してください[を有効にして、FILESTREAM を構成する](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream)です。
  
    -   FILESTREAM が有効なデータベースを作成する必要があります。 参照してください[FILESTREAM が有効なデータベースを作成する](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database)です。
  
    -   FILESTREAM データを格納するテーブルが必要です。 参照してください[FILESTREAM データを格納するテーブルを作成する](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data)、
  
-   **アダプターのクライアントを実行するコンピューター**  
  
    -   SQL クライアント接続 SDK がインストールされている可能性があります。 SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。 アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。  
  
 これらのタスクを完了するがすべて設定するを挿入または SQL Server データベース テーブル内の FILESTREAM データを更新します。  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>このトピックの内容が大量のデータ型に対する操作を示しています  
 セットを実行する方法をデモンストレーションする\<*column_name*> ラージ データ型とテーブルでの操作にあるテーブルを見て**レコード**、列を持つ**Id**と**ドキュメント**:  
  
-   **レコード**サンプルに用意されている SQL スクリプトを実行してすべてのデータのテーブルを作成します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
-   **Id**列型は uniqueidentifier は、GUID を取得します。 あると想定、 **Id**列は既に GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`' です。  
  
-   **ドキュメント**列が varbinary (max) 型です。 更新する、**ドキュメント**列で、アダプターを公開、 **SetDocument**操作します。  
  
> [!NOTE]
>  SQL Server の FILESTREAM 操作を示すためには、あると想定、**ドキュメント**列が FILESTREAM データを格納できます。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例で操作を実行する、**レコード**テーブル。 **レコード**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。 サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。 サンプルは、 **Records_FILESTREAM_Op**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 大規模なデータでの操作の生成、WCF クライアントの名前の種類を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]検出、次の表に示すように、テーブルまたはビューの名前に基づきます。  
  
|SQL Server のデータベース成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|テーブル|TableOp_ [Schema] _ [TABLE_NAME] のクライアント|  
|表示|ViewOp_ [Schema] _ [VIEW_NAME] のクライアント|  
  
 [スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a>大規模なデータ型の列に対する操作を呼び出すためのメソッド シグネチャ  
 次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|設定\<*column_name*>|public void セット\<*column_name*> (フィルター、byte[] データを文字列) です。|  
  
 \<*column_name*> ラージ データ型の列の名前を = です。  
  
 たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **SetDocument**で操作、**レコード**既定の"dbo"スキーマの下の表。  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 このスニペットで**TableOp_dbo_RecordsClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a>大規模なデータ型の列に対する操作のパラメーター  
 このセクションでは、セットに必要なパラメーター\<*column_name*> 操作します。  
  
|[パラメーター名]|Description|  
|--------------------|-----------------|  
|文字列フィルター|アダプターが大量のデータ型の列のレコードを更新を基に WHERE 句を指定します。|  
|byte[] データ|大規模なデータ型の列を更新する必要があります値を指定します。|  
  
 セット\<*column_name*> 操作は任意の値を返しません。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a>大規模なデータ型の列に対する操作を呼び出すに WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。 このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **SetDocument**での操作、**レコード**テーブル。 アダプターを公開、 **SetDocument**ラージ データ型の列のデータを更新する操作。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  WCF クライアント クラスを生成、 **SetDocument**での操作、**レコード**テーブル。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
3.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、および`System.Transactions`です。  
  
4.  Program.cs ファイルを開き、追加、`System.Transactions`名前空間。  
  
5.  Program.cs では、次のスニペット」の説明に従って、クライアントを作成します。  
  
    ```  
  
              TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
    client.ClientCredentials.UserName.UserName = "";  
    client.ClientCredentials.UserName.Password = "";  
  
    ```  
  
     このスニペットで`TableOp_dbo_RecordsClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 `SqlAdapterBinding_TableOp_dbo_Records`クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。  
  
    > [!CAUTION]
    >  FILESTREAM データでの操作を行うには、常に Windows 認証を使用して SQL Server に接続する必要があります。 Windows 認証を使用して接続するに、前のスニペットに示すように、空のユーザー名とパスワードを提供する必要があります。 また、SQL Server への接続に Windows 認証を使用する前に行うことが必要で説明する手順[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    > [!NOTE]
    >  このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。  
  
6.  次のスニペット」の説明に従って、クライアントを開きます。  
  
    ```  
    try  
    {  
       Console.WriteLine("Opening Client...");  
       client.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    ```  
  
7.  呼び出す、 **SetDocument**での操作、**レコード**テーブル。  
  
    > [!CAUTION]
    >  セット*< column_name >*操作は、トランザクションで常に実行する必要があります。 、これを実現するセット*< column_name >*トランザクション スコープ内で操作を呼び出す必要があります、 **UseAmbientTransaction** binding プロパティを設定する必要があります**true**app.config です。  
  
    ```  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
        byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
        client.SetDocument(filter, data);  
        tx.Complete();  
    }  
    ```  
  
     ここでは、文字列「サンプル データ」を base64 でエンコードされた文字列に変換、アプリケーションとフィルター条件を満たすレコードに更新します。  
  
8.  次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
9. プロジェクトをビルドし、それを実行します。 アプリケーションの更新プログラム、**ドキュメント**内の列、**レコード**テーブル。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)