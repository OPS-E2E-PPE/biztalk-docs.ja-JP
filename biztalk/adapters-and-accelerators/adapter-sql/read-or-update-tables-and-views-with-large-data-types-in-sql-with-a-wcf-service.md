---
title: WCF サービス モデルを使用して SQL に大規模なデータ型を持つテーブルとビューで操作を実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d33e17c-e09e-4a57-9acc-43095e67ed8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 031e65cc749de34807993e858c066cfc9438cc7b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368555"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL に大規模なデータ型を持つテーブルとビューで操作を実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントの読み取りし、は、大規模なデータ型の列のデータを更新する、varchar (max)、nvarchar (max)、または varbinary (max) を有効にします。 このような列からデータを読み取る、アダプターのクライアントは、選択操作を使用できます。 アダプターを挿入またはこのような列にデータを更新するには、セットを公開する\<*column_name* \>操作、 \< *column_name* \>名前を指定します型 varchar (max)、nvarchar (max)、または varbinary (max) 列。  
  
 さらに、SQL Server でテキスト ドキュメントやイメージなどの非構造化データを格納 varbinay(max) 列があることができます。 このような非構造化データには、FILESTREAM データが呼び出されます。 FILESTREAM データは、ファイル システム上のファイルとして格納することができます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントは、varbinary (max) 型の列に FILESTREAM データを入力できます。 [FILESTREAM ストレージ](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server)の詳細。 
  
 このトピックでは実行する必要があります、特定のタスクについては、コンピューター上には、SQL Server および挿入または FILESTREAM データを更新できるアダプター クライアントを実行しているコンピューターを実行しています。 このトピックの手順をセットを実行する方法も提供します\<*column_name* \> FILESTREAM データを挿入する操作。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server を実行しているコンピューターと、アダプターのクライアントを実行しているコンピューターでは、次のタスクを実行する必要があります。  
  
- **SQL Server を実行するコンピューター**  
  
  -   SQL Server インスタンスで FILESTREAM を有効にする必要があります。 参照してください[を有効にして、FILESTREAM の構成](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream)します。
  
  -   FILESTREAM が有効なデータベースを作成する必要があります。 参照してください[FILESTREAM が有効なデータベースを作成](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database)です。
  
  -   FILESTREAM データを格納するためのテーブルが必要です。 参照してください[FILESTREAM データを格納するテーブルを作成](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data)、
  
- **アダプターのクライアントを実行するコンピューター**  
  
  -   インストールされている SQL Client Connectivity SDK が必要です。 SQL クライアント接続 SDK をインストールするには、SQL Server セットアップを実行し、選択**SQL Client Connectivity SDK**で、**機能の選択**ウィザードのページ。 アダプターは、FILESTREAM 操作を実行するのに SQL クライアント接続 sdk では、インストールされている、sqlncli10.dll を使用します。  
  
  これらのタスクを完了すると、設定は完了を挿入または SQL Server データベース テーブル内の FILESTREAM データを更新します。  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>ここで大量のデータ型に対する演算をについて説明する方法  
 セットを実行する方法を説明するために\<*column_name* \>大量のデータの型を持つテーブルに対する操作は、テーブルを受け取り**レコード**、列を持つ**Id**と**ドキュメント**:  
  
-   **レコード**サンプルで提供される SQL スクリプトを実行して、すべてのデータのテーブルを作成します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
-   **Id**列の型は uniqueidentifier とは GUID を受け取ります。 ある、 **Id**列は既に GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`'。  
  
-   **ドキュメント**列が varbinary (max) 型。 更新する、**ドキュメント**列で、アダプターを公開、 **SetDocument**操作。  
  
> [!NOTE]
>  SQL server の FILESTREAM 操作を示すためには、前提としていますが、**ドキュメント**列が FILESTREAM データを格納できます。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例で操作を実行する、**レコード**テーブル。 **レコード**サンプルで提供される SQL スクリプトを実行してテーブルを作成します。 サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。 サンプルについては、 **Records_FILESTREAM_Op**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 大規模データに対する操作の生成された WCF クライアントの名前の種類を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はでは、次の表に示すように、テーブルまたはビューの名前に基づきます。  
  
|SQL Server データベースの成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|テーブル|TableOp_ [Schema] _ [TABLE_NAME] のクライアント|  
|表示|ViewOp_ [Schema] _ [VIEW_NAME] のクライアント|  
  
 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a>大規模なデータ型の列に対する操作を呼び出すためのメソッド シグネチャ  
 次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|設定\<*column_name*\>|public void セット\<*column_name*\>(フィルター、byte[] のデータを文字列)。|  
  
 \<*column_name* \> = ラージ データ型の列の名前。  
  
 WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **SetDocument**操作、**レコード**既定の"dbo"スキーマの下のテーブル。  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 このスニペットで**TableOp_dbo_RecordsClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a>大規模なデータ型の列に対する操作のパラメーター  
 このセクションでは、セットに必要なパラメーターを提供します。\<*column_name* \>操作。  
  
|[パラメーター名]|説明|  
|--------------------|-----------------|  
|フィルター文字列|アダプターが大量のデータ型の列のレコードを更新ベースの WHERE 句を指定します。|  
|byte[] データ|大規模なデータ型の列を更新する必要があります値を指定します。|  
  
 セット\<*column_name* \>操作では、任意の値は返されません。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a>大規模なデータ型の列の操作の呼び出しに WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。 このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **SetDocument**での操作、**レコード**テーブル。 アダプターを公開、 **SetDocument**ラージ データ型の列のデータを更新する操作。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. WCF クライアント クラスを生成、 **SetDocument**操作、**レコード**テーブル。 WCF クライアント クラスを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。  
  
3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、および`System.Transactions`します。  
  
4. Program.cs ファイルを開き、追加、`System.Transactions`名前空間。  
  
5. 次のスニペットの説明に従って、program.cs に、クライアントを作成します。  
  
   ```  
  
             TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
   client.ClientCredentials.UserName.UserName = "";  
   client.ClientCredentials.UserName.Password = "";  
  
   ```  
  
    このスニペットで`TableOp_dbo_RecordsClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 `SqlAdapterBinding_TableOp_dbo_Records` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。  
  
   > [!CAUTION]
   >  FILESTREAM データの操作を行うには、常に Windows 認証を使用して SQL Server に接続する必要があります。 を Windows 認証を使用して接続するには、前のスニペットで示すように、空のユーザー名とパスワードを提供する必要があります。 また、SQL Server への接続に Windows 認証を使用する前に行うことが必要で説明されている手順[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
   > [!NOTE]
   >  このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。  
  
6. 次のスニペットで説明されているように、クライアントを開きます。  
  
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
  
7. 呼び出す、 **SetDocument**操作、**レコード**テーブル。  
  
   > [!CAUTION]
   >  セット<em>< column_name ></em>操作は、トランザクションで常に実行する必要があります。 、これを実現するセット<em>< column_name ></em>トランザクション スコープ内で操作を呼び出す必要があると、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**true**app.config でします。  
  
   ```  
   using (TransactionScope tx = new TransactionScope())  
   {  
       string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
       byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
       client.SetDocument(filter, data);  
       tx.Complete();  
   }  
   ```  
  
    ここでは、文字列"サンプル データ を base64 でエンコードされた文字列に変換、アプリケーションと、フィルター条件を満たすレコードの更新プログラムします。  
  
8. 次のスニペットの説明に従って、クライアントを閉じます。  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
9. プロジェクトをビルドし、それを実行します。 アプリケーションの更新プログラム、**ドキュメント**内の列、**レコード**テーブル。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)