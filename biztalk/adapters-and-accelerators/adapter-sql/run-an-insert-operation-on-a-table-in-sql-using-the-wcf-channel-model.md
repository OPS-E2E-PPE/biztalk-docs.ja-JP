---
title: WCF チャネル モデルを使用して SQL でテーブルに対して挿入操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3df95d78-3a9c-48c0-81ab-1f3206c5e3f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bceb236b660b80c1e46cb0410d799d994516c40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224410"
---
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して SQL でのテーブルに対して挿入操作の実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]一連の SQL Server データベース テーブルおよびビューの基本的な Insert、Select、Update、および削除操作を検出します。 これらの操作を使用することができますを実行して単純な SQL Insert、Select、Update、Delete ステートメントで Where 修飾対象のテーブルまたはビューの句。 このトピックでは、WCF チャネル モデルを使用して SQL Server データベース テーブルに対して挿入操作を実行する方法について説明します。  
  
 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルおよび SQL アダプターとビューの選択操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)です。 WCF チャネル モデルを使用して SQL Server での操作を実行する方法に関する詳細については、次を参照してください。 [SQL アダプタを使用して WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルでの操作を実行します。 サンプルに用意されている SQL スクリプトを実行して、従業員テーブルが作成されます。 サンプルの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。 サンプルは、 **EmployeeInsertOp**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。  
  
## <a name="the-insert-message"></a>挿入メッセージ  
 WCF チャネル モデルを使用して SQL Server データベースで操作を実行するには、操作に固有の要求メッセージが必要です。 SQL Server データベースの Employee テーブルに対して挿入操作を実行する要求メッセージには、次のようになります。  
  
```  
<Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Rows>  
    <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
      <Name>Tom Smith</Name>  
      <Designation>Manager</Designation>  
      <Salary>500000</Salary>  
   </Employee>  
  </Rows>  
</Insert>  
```  
  
 この要求メッセージは、次の詳細情報を持つレコードを挿入します。  
  
```  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 例: InsertRequest.xml ファイルにメッセージをコピーする必要があります。 このファイルは、SQL Server を使用する要求メッセージを送信するこの例では使用、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 テーブルに対する操作のメッセージ スキーマの詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。  
  
## <a name="creating-a-wcf-channel-application"></a>WCF チャネル アプリケーションを作成します。  
 このセクションでは、Employee テーブルに対して挿入操作を実行する WCF チャネル アプリケーションを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a>Employee テーブルにレコードを挿入するための WCF チャネル アプリケーションを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`です。  
  
3.  Program.cs ファイルを開き、次の名前空間を追加します。  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  バインドとエンドポイントを作成します。  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
    ```  
  
5.  作成し、チャネル ファクトリを開きます。 このアプリケーションが SQL Server に要求メッセージを送信し、応答を受信、そのため、IRequestChannel インターフェイスを実装する必要があります。  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
6.  作成し、チャネルを開きます。  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
7.  作成し、要求メッセージを送信します。  
  
    ```  
    XmlReader readerIn;  
    Console.WriteLine("Creating the message");  
    try  
    {  
       readerIn = XmlReader.Create("InsertRequest.xml");  
       Console.WriteLine("Reader created");  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Message messageIn = Message.CreateMessage(MessageVersion.Default, "TableOp/Insert/dbo/Employee", readerIn);  
    Message messageOut = channel.Request(messageIn);  
  
    ```  
  
     要求メッセージを作成中に SQL Server のテーブルについて、アダプターを実行するアクションを示すメッセージのアクションを指定する必要があります。 メッセージのアクションは、Employee テーブルに対して挿入操作を実行する`TableOp/Insert/dbo/Employee`です。 テーブルに対するさまざまな操作のメッセージのアクションを判断する方法については、次を参照してください。 [Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。  
  
8.  応答メッセージを取得します。  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
9. メッセージ、チャネル、およびチャネル ファクトリを閉じます。  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
10. プロジェクトをビルドする。 プロジェクトをビルドしたら、次のタスクを実行する必要があります。  
  
    -   要求メッセージ、InsertRequest.xml、実行可能プロジェクトと同じ場所にコピーします。 通常、この場所は、プロジェクト ディレクトリ下にある \bin\Debug\ です。  
  
    -   この例で使用される"Employee"テーブルには、ポイントのユーザー定義型 (UDT) の列があります。 そのため、プロジェクトを実行する前に作成する必要がある Point UDT のアセンブリの説明に従って[ユーザー定義型](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types)です。 アセンブリの実行可能ファイルのプロジェクトと同じ場所にある DLL をコピーすることも必要があります。 通常、この場所は、プロジェクト ディレクトリ下にある \bin\Debug\ です。  
  
11. アプリケーションを実行します。 応答メッセージ、Response.xml は、アプリケーションで指定した場所に保存されます。 応答メッセージは、新しく追加した従業員の ID を格納し、次のようになります。  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     Employee テーブルには、id 列として Employee_ID 列があるために、挿入操作は、新しく挿入したレコードの id 列の値を返します。 テーブル内に id 列がない場合、戻り値は NULL です。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)