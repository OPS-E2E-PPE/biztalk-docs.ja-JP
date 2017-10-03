---
title: "WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルでの操作を完了 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b671f8fc124875eb5eadf119188d0ffe4c1a2a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型とのインターフェイス テーブルやビューでの操作を実行できるようにします。  
  
-   型の列を読み取るできるだけでなく、データ更新のクライアントにより、アダプター、BLOB、CLOB、NCLOB、します。 アダプター公開 Read_\<*LOBColName*> と Update_\<*LOBColName*> の読み取りし、それぞれのデータを更新する操作、 \< *LOBColName*> 大量のデータ型の列の名前を指定します。 大規模なデータ型は、1 つのインターフェイス テーブルで 1 つ以上の列がある場合、アダプターは、多くの読み取りし、そのインターフェイス テーブルに対して操作を更新を公開します。  
  
-   BFILE 型の列は、アダプターのクライアントは、データを読み取るだけことができます。 アダプター公開 Read_\<*LOBColName*> BFILE 型の列からデータを操作します。 大規模なデータ型は、1 つのインターフェイス テーブルで 1 つ以上の列がある場合、アダプターは、多くの読み取り操作インターフェイス テーブルとしてを公開します。  
  
 これらの操作の詳細については、次を参照してください。[インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビューを含む LOB データに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、顧客データベース テーブル内の BLOB 列 (写真) を更新し、同じ列からデータを取得します。 サンプルに用意されているスクリプトを実行して、テーブルが作成されます。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。 サンプルは、 **LargeDataTypes_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。  
  
> [!NOTE]
>  このトピックでは、ベース データベース テーブルに大量のデータ型の列を読み取ったり更新に関する詳細なタスクを示します。 更新とのインターフェイス テーブルに大量のデータ型の列を読み取り、同じ一連のタスクを行う必要があります。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 大量のデータ型とは、テーブルでの操作に対して生成される WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に示すように、テーブルの名前に基づきます。  
  
|成果物|WCF クライアント名|  
|--------------|---------------------|  
|インターフェイス テーブル|InterfaceTables_ [APP_NAME] _ [SCHEMA]\_[TABLE_NAME] クライアント|  
  
 [構成]、Oracle E-business Suite アプリケーションの実際の名前を =たとえばのヘルプ。  
  
 [スキーマ]; の成果物のコレクションを =たとえば、アプリです。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、MS_SAMPLE_EMPLOYEE です。  
  
 [VIEW_NAME] ビューの名前を =たとえば、MS_SAMPLE_EMPLOYEE_View です。  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>テーブルに対する操作を呼び出すためのメソッド シグネチャ  
 次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|Update_\<*column_name*>|public void Update_\<*column_name*> (フィルター、byte[] データを文字列) です。|  
|Read_\<*column_name*>|パブリック System.IO.Stream Read_\<*column_name*>(string FILTER) です。|  
  
 例としては、次のコードは、アプリケーション スキーマの下にある顧客データベース テーブルに Update_PHOTO および Read_PHOTO 操作に対して生成される WCF クライアント クラスのメソッドのシグニチャを示します。  
  
```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      
  
    public void Update_PHOTO(string FILTER, byte[] DATA);  
  
    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  
  
 このスニペットで**Tables_APPS_CUSTOMERClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 Update_PHOTO と Read_PHOTO は、更新し、テーブル内の大規模なデータ型の列を表示するに呼び出せるようにする方法です。  
  
### <a name="parameters-for-table-operations"></a>テーブル操作のパラメーター  
 このセクションでは、Update_ に必要なパラメーター\<*column_name*> と Read_\<*column_name*> 操作します。  
  
|操作名|パラメーター|  
|--------------------|----------------|  
|Update_\<*column_name*>|次のパラメーターが必要です。<br /><br /> -   `string FILTER`. このパラメーターは、where を含める必要があります句を更新するデータを持っているレコードを表します。 たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。<br />-   `byte[] DATA`. 大規模なデータ型の列で更新するデータのバイト配列が含まれています。|  
|Read_\<*column_name*>|次のパラメーターが必要です。<br /><br /> -   `string FILTER`. このパラメーターは、where を含める必要がありますを元のデータが読み取られるレコードを示す句。 たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。|  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a>大規模なデータ型の列を持つテーブルの操作の呼び出しに WCF クライアントを作成します。  
 WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)です。 このセクションでは、顧客データベース テーブルに Update_PHOTO と Read_PHOTO 操作の呼び出しに WCF クライアントを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  顧客データベース テーブルに Update_PHOTO および Read_PHOTO 操作の WCF クライアント クラスを生成します。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
    > [!IMPORTANT]
    >  WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`、`System.Transactions`です。  
  
4.  Program.cs ファイルを開き、次の名前空間を追加します。  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.Transactions`  
  
    -   `System.IO`  
  
5.  Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  
  
    ```  
  
              Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  
  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     このスニペットで`Tables_APPS_CUSTOMERClient`OracleEBSBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!NOTE]
    >  このスニペットでは、バインディングと構成ファイル app.config ファイルからエンドポイント アドレスを使用します。これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。  
  
6.  クライアントの資格情報を設定します。  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!IMPORTANT]
    >  この例では、データベースのテーブルに対する操作を実行します。 ただし場合インターフェイス テーブルに対する操作を実行する場合は、する必要があります設定、アプリケーションのコンテキストの適切な値を指定することによって、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 クライアントを開く前にこれらのバインディング プロパティを指定する必要があります。 アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
7.  次のスニペット」の説明に従って、クライアントを開きます。  
  
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
  
8.  操作を呼び出し、Update_PHOTO 顧客テーブルにします。  
  
     Update_PHOTO 操作には、更新するデータのバイト配列が必要です。 このコード スニペットでは、写真、SamplePhoto.jpg のバイト配列を作成するのに FileStream クラスを使用します。 このアプリケーションが動作するには、ため、プロジェクトの bin ディレクトリにファイルをコピーする必要があります。  
  
    > [!IMPORTANT]
    >  トランザクションでは、Update_PHOTO 操作を実行する必要がありますので、 **UseAmbientTransaction** binding プロパティを設定する必要があります**true** Update_PHOTO 操作を内で実行する必要があります、トランザクションのスコープです。 設定することができます、 **UseAmbientTransaction**として、アプリケーションで明示的に設定することによってまたは app.config では、プロパティをバインド`binding.UseAmbientTransaction = true`です。 ある場合は、コードでは、バインディング プロパティを明示的に指定は、行う必要があります、クライアントを開く前に注意してください。  
  
    ```  
    byte[] photo;  
  
    using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
    {  
        try  
        {  
            Console.WriteLine("Reading the photo");  
            int count = 0;  
            photo = new byte[fs.Length];  
            while ((count += fs.Read(photo, count, (int)(((fs.Length - count) > 4096) ? 4096 : fs.Length - count))) \< fs.Length) ;  
        }  
        catch(Exception ex)  
        {  
            Console.WriteLine("Exception: " + ex.Message);  
            throw;  
        }  
    }  
  
    Console.WriteLine("Updating data for the 'PHOTO' column");  
    // Invoking the Update_PHOTO operation inside a transaction scope  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Name='Mindy Martin'";  
        client.Update_PHOTO(filter, photo);  
        tx.Complete();  
    }  
  
    ```  
  
9. 操作を呼び出し、Read_PHOTO 顧客テーブルにします。  
  
     Read_PHOTO は、System.IO.Stream の形式で出力を示します。 アダプターのクライアントは、Read_PHOTO 操作からのデータを読み取る FileStream クラスを実装する必要があります。 Read_PHOTO 操作が完了したら、プロジェクトの bin ディレクトリの下にある PhotoCopy.jpg ファイルがコピーされます。  
  
    ```  
    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
    {  
        Console.WriteLine("Reading photo data");  
        String ReadFilter = "WHERE NAME='Mindy Martin'";  
        Stream photoStream = client.Read_PHOTO(ReadFilter);  
        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  
  
        int count;  
        int length = 0;  
        byte[] buffer = new byte[4096];  
        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
        {  
            fs.Write(buffer, 0, count);  
            length+=count;  
        }  
        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
    }  
  
    Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
    Console.ReadLine();  
    ```  
  
10. 次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. プロジェクトをビルドし、それを実行します。 アプリケーションでは、CUSTOMER テーブルの PHOTO 列を更新し、PHOTO 列の内容を読み取ります。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)