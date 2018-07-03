---
title: WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作の完了 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9869cd49ed09d80a866f3dcbb6f4b9429788339b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982563"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型を持つインターフェイス テーブルとビューで操作を実行できるようにします。  

- 型の列の BLOB、CLOB、NCLOB、アダプターにより、クライアントは、読み取り、データを更新します。 アダプター公開 Read_\<*LOBColName* \>と Update_\<*LOBColName* \>を読み取って、データを更新する操作、 \<*LOBColName* \>大量のデータ型の列の名前を指定します。 大規模なデータ型は、1 つのインターフェイス テーブルでは、複数の列がある場合、アダプターは、多くの読み取りし、そのインターフェイス テーブルに対して操作を更新を公開します。  

- BFILE の型の列は、アダプター クライアントは、データを読み取るだけことができます。 アダプター公開 Read_\<*LOBColName* \> BFILE 型の列からデータを読み取る操作。 大規模なデータ型は、1 つのインターフェイス テーブルでは、複数の列がある場合、アダプターは、インターフェイス テーブルに対する操作の読み取りの多くを公開します。  

  これらの操作の詳細については、次を参照してください。[インターフェイス テーブル、インターフェイス ビュー、テーブル、ビューを含む LOB データを操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)します。  

## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、顧客のデータベース テーブル内の BLOB 列 (写真) を更新し、同じ列からデータを取得します。 サンプルに付属のスクリプトを実行して、テーブルが作成されます。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。 サンプルについては、 **LargeDataTypes_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。  

> [!NOTE]
>  このトピックでは、更新とベース データベース テーブル内の大規模なデータ型の列を読み取り用の詳細なタスクを使用します。 更新とのインターフェイス テーブルに大量のデータ型の列を読み取り用同じ一連のタスクを実行する必要があります。  

## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 によって大量のデータ型では、テーブルでの操作に対して生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に示すように、テーブルの名前に基づきます。  


|     成果物     |                     WCF クライアント名                      |
|------------------|----------------------------------------------------------|
| インターフェイス テーブル | [APP_NAME] InterfaceTables_*[SCHEMA]\\*[TABLE_NAME] のクライアント |

 [構成] は、Oracle E-business Suite のアプリケーションの実際の名前を =たとえば、ヘルプです。  

 [スキーマ] のアイテムのコレクションを =たとえば、アプリです。  

 [TABLE_NAME] テーブルの名前を =たとえば、MS_SAMPLE_EMPLOYEE です。  

 [VIEW_NAME] ビューの名前を =たとえば、MS_SAMPLE_EMPLOYEE_View です。  

### <a name="method-signature-for-invoking-operations-on-tables"></a>テーブルに対する操作を呼び出すためのメソッド シグネチャ  
 次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。  

|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|Update_\<*column_name*\>|public void Update_\<*column_name*\>(フィルター、byte[] のデータを文字列)。|  
|Read_\<*column_name*\>|パブリック System.IO.Stream Read_\<*column_name*\>(フィルターの文字列)。|  

 例としては、次のコードは、アプリ スキーマの下で顧客データベースのテーブルに対する Update_PHOTO と Read_PHOTO 操作に対して生成された WCF クライアント クラスのメソッド シグネチャを示します。  

```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      

    public void Update_PHOTO(string FILTER, byte[] DATA);  

    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  

 このスニペットで**Tables_APPS_CUSTOMERClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 Update_PHOTO と Read_PHOTO はの更新および読み取るテーブル内の大規模なデータ型の列を呼び出すことができるメソッドを実行します。  

### <a name="parameters-for-table-operations"></a>テーブル操作のパラメーター  
 このセクションでは、Update_ に必要なパラメーターを提供します。\<*column_name* \>と Read_\<*column_name* \>操作。  

|操作名|パラメーター|  
|--------------------|----------------|  
|Update_\<*column_name*\>|次のパラメーターが必要です。<br /><br /> -   `string FILTER`. このパラメーターは、場所を含める必要があります句を更新するデータを持っているレコードを表します。 たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。<br />-   `byte[] DATA`. 大規模なデータ型の列で更新するデータのバイト配列が含まれています。|  
|Read_\<*column_name*\>|次のパラメーターが必要です。<br /><br /> -   `string FILTER`. このパラメーターは、場所を含める必要があります句を元のデータが読み取られるレコードを表します。 たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。|  

## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a>大規模なデータ型の列を持つテーブルに対する操作の呼び出しに WCF クライアントを作成します。  
 汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)します。 このセクションでは、顧客のデータベース テーブルでも Update_PHOTO と Read_PHOTO の操作を呼び出すための WCF クライアントを作成する方法について説明します。  

#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  

1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  

2. 顧客のデータベース テーブルでも Update_PHOTO と Read_PHOTO の操作のための WCF クライアント クラスを生成します。 WCF クライアント クラスを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。  

   > [!IMPORTANT]
   >  WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  

3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`、`System.Transactions`します。  

4. Program.cs ファイルを開き、次の名前空間を追加します。  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

   -   `System.Transactions`  

   -   `System.IO`  

5. Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  

   ```  

             Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  

   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    このスニペットで`Tables_APPS_CUSTOMERClient`OracleEBSBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

   > [!NOTE]
   >  このスニペットでは、バインディングと構成ファイル app.config ファイルからエンドポイント アドレスを使用します。これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)します。  

6. クライアントの資格情報を設定します。  

   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  

   > [!IMPORTANT]
   >  この例では、データベース テーブルの操作を実行します。 ただし、インターフェイス テーブルでの操作を実行する場合は、する必要がありますコンテキストを設定するアプリケーションの適切な値を指定することによって、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 クライアントを開く前に、これらのバインドのプロパティを指定する必要があります。 アプリケーションのコンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

7. 次のスニペットで説明されているように、クライアントを開きます。  

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

8. 顧客テーブルに Update_PHOTO 操作を呼び出します。  

    Update_PHOTO 操作には、更新するデータのバイト配列が必要です。 このコード スニペットでは、FileStream クラスを使用しての写真を SamplePhoto.jpg バイト配列を作成します。 このアプリケーションを操作するには、プロジェクトの bin ディレクトリにファイルをコピーする必要があります。  

   > [!IMPORTANT]
   >  トランザクションでは、Update_PHOTO 操作を実行する必要がありますので、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**true**内 Update_PHOTO 操作を実行する必要があります、トランザクションのスコープ。 設定することができます、 **UseAmbientTransaction** app.config 内、または、アプリケーションで明示的に設定することで、プロパティをバインド`binding.UseAmbientTransaction = true`します。 場合は、コードでバインディングのプロパティを明示的に指定は、設定する必要がありますようにクライアントを開く前に注意してください。  

   ```  
   byte[] photo;  

   using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
   {  
       try  
       {  
           Console.WriteLine("Reading the photo");  
           int count = 0;  
           photo = new byte[fs.Length];  
           while ((count += fs.Read(photo, count, (int)(((fs.Length - count) > 4096) ? 4096 : fs.Length - count))) < fs.Length) ;  
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

9. 顧客テーブルに Read_PHOTO 操作を呼び出します。  

     Read_PHOTO、System.IO.Stream の形式で出力を示します。 アダプターのクライアントでは、Read_PHOTO 操作からのデータの読み取りに FileStream クラスを実装する必要があります。 Read_PHOTO 操作が完了した後、プロジェクトの bin ディレクトリの下で PhotoCopy.jpg ファイルがコピーされます。  

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

10. 次のスニペットの説明に従って、クライアントを閉じます。  

    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  

11. プロジェクトをビルドし、それを実行します。 アプリケーションでは、CUSTOMER テーブルの PHOTO 列を更新し、PHOTO 列の内容を読み取ります。  

## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)