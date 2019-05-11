---
title: WCF チャネル モデルを使用した SQL でのテーブルに対する挿入操作の実行 |Microsoft Docs
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
ms.openlocfilehash: 0be345ab33e12068b9b5eb52fd75c65ff15361be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367982"
---
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して SQL テーブルで挿入操作を実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]一連の SQL Server データベースのテーブルおよびビューに対する Insert、Select、Update、および Delete の基本的な操作を検出します。 これらの操作を使用すると、実行の単純な SQL Insert、Select、Update、および Delete ステートメントで Where 修飾対象のテーブルまたはビューの句。 このトピックでは、WCF チャネル モデルを使用して SQL Server データベース テーブルに対して挿入操作を実行する方法について説明します。  
  
 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルとビューを SQL アダプターを使用した操作の選択](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)します。 WCF チャネル モデルを使用して SQL Server での操作を実行する方法の詳細については、次を参照してください。 [SQL アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)します。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルに対する操作を実行します。 サンプルで提供される SQL スクリプトを実行して、従業員テーブルが作成されます。 サンプルの詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。 サンプルについては、 **EmployeeInsertOp**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。  
  
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
  
 メッセージは、InsertRequest.xml など、ファイルをコピーする必要があります。 このファイルは、SQL Server を使用する要求メッセージを送信するこの例で使用されます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 テーブルに対する操作のメッセージ スキーマの詳細については、次を参照してください。[挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)します。  
  
## <a name="creating-a-wcf-channel-application"></a>WCF チャネル アプリケーションの作成  
 このセクションでは、Employee テーブルに対して挿入操作を実行する WCF チャネル アプリケーションを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a>Employee テーブルにレコードを挿入するための WCF チャネル アプリケーションを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`します。  
  
3.  Program.cs ファイルを開き、次の名前空間を追加します。  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  バインディングとエンドポイントを作成します。  
  
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
  
6.  作成して、チャネルを開きます。  
  
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
  
     要求メッセージを作成するときに、SQL Server テーブルをアダプターを実行するアクションを示すメッセージのアクションを指定する必要があります。 メッセージのアクションは、Employee テーブルに対して挿入操作を実行する`TableOp/Insert/dbo/Employee`します。 テーブルに対するさまざまな操作のメッセージ アクションを決定する方法については、次を参照してください。[挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)します。  
  
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
  
    -   要求メッセージ、InsertRequest.xml、実行可能ファイル、プロジェクトと同じ場所にコピーします。 通常、この場所は、プロジェクト ディレクトリ以下に \bin\Debug\ です。  
  
    -   この例で使用される"Employee"テーブルには、ポイントのユーザー定義型 (UDT) の列があります。 そのため、プロジェクトを実行する前に作成する必要がある Point UDT のアセンブリの説明に従って[ユーザー定義型](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types)します。 DLL プロジェクトの実行可能ファイルと同じ場所にあるアセンブリをコピーすることも必要があります。 通常、この場所は、プロジェクト ディレクトリ以下に \bin\Debug\ です。  
  
11. アプリケーションを実行します。 Response.xml、応答メッセージは、アプリケーションで指定した場所に保存されます。 応答メッセージは、新しく追加された従業員の ID を格納し、次のような。  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     Employee テーブルには、id 列として Employee_ID 列があるために、挿入操作は、新しく挿入されたレコードの id 列の値を返します。 テーブル内に id 列がない場合、戻り値は NULL です。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)