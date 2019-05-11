---
title: WCF チャネル モデルを使用して Oracle E-business Suite でのインターフェイス テーブルで挿入操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a2e5ee3-552b-40a2-aaa6-5391347f1146
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2f52284e3d4fb08c7dafae9f1a761346fd56351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375480"
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle E-business Suite でのインターフェイス テーブルで挿入操作を実行します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite のインターフェイス テーブルに対する Insert、Select、Update、および削除の操作のセットを検出します。 これらの操作を使用すると、実行の単純な Insert、Select、Update、および Delete ステートメントで Where 修飾対象のインターフェイス テーブルで句。 このトピックでは、WCF チャネル モデルを使用して、インターフェイス テーブルに対する挿入操作を実行する方法について説明します。  
  
 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)します。 WCF チャネル モデルを使用して Oracle E-business Suite での操作を実行する方法の詳細については、次を参照してください。 [Oracle E-business Suite アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)します。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルの操作を実行します。 サンプルに付属のスクリプトを実行して、テーブルが作成されます。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。 サンプルについては、 **InsertOperation**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。  
  
## <a name="the-insert-message"></a>挿入メッセージ  
 WCF チャネル モデルを使用して Oracle E-business Suite での操作を実行するには、操作に固有の要求メッセージが必要です。 MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対して挿入操作を実行する要求メッセージには、次のようになります。  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">  
      <EMP_NO>10050</EMP_NO>  
      <NAME>John Smith</NAME>  
      <DESIGNATION>Manager</DESIGNATION>  
      <SALARY>500000</SALARY>  
      <JOIN_DATE>1999-05-31</JOIN_DATE>  
    </InsertRecord>  
  </RECORDSET>  
</Insert>  
```  
  
 この要求メッセージは、次の詳細情報を持つレコードを挿入します。  
  
```  
Employee Number = 10050  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 メッセージは、InsertRequest.xml など、ファイルをコピーする必要があります。 Oracle E-business Suite を使用する要求メッセージを送信するこの例ではこのファイルが使用される、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 テーブルに対する操作のメッセージ スキーマの詳細については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)します。  
  
## <a name="creating-a-wcf-channel-application"></a>WCF チャネル アプリケーションの作成  
 このセクションでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対して挿入操作を実行する WCF チャネル アプリケーションを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a>テーブルにレコードを挿入するための WCF チャネル アプリケーションを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`します。  
  
3.  Program.cs ファイルを開き、次の名前空間を追加します。  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  バインディングとエンドポイントを作成します。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  インターフェイス テーブルで操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。 この例で、アプリケーションのコンテキストの設定を指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーションのコンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  作成し、チャネル ファクトリを開きます。 このアプリケーションが Oracle E-business Suite への要求メッセージの送信し、応答を受信、そのため、IRequestChannel インターフェイスを実装する必要があります。  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  作成して、チャネルを開きます。  
  
    ```  
    IRequestChannel channel;  
    try  
    {  
       channel = factory.CreateChannel();  
       channel.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception :" + ex.Message);  
       throw;  
    }  
    ```  
  
8.  作成し、要求メッセージを送信します。  
  
    ```  
    XmlReader readerIn;  
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
    Message messageIn;  
    Message messageOut;  
    try  
    {  
       messageIn = Message.CreateMessage(MessageVersion.Default, "InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE", readerIn);  
       messageOut = channel.Request(messageIn);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    ```  
  
     要求メッセージを作成するときに、インターフェイス テーブルで、アダプターを実行するアクションを示すメッセージ操作を指定する必要があります。 メッセージのアクションは、MS_SAMPLE_EMPLOYEE テーブルに対する挿入操作を実行する`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`します。 テーブルに対するさまざまな操作のメッセージ アクションを決定する方法については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)します。  
  
9. 応答メッセージを取得します。  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
10. メッセージ、チャネル、およびチャネル ファクトリを閉じます。  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
11. プロジェクトをビルドする。 プロジェクトをビルドした後に、要求メッセージ、実行可能ファイル、プロジェクトと同じ場所にある、InsertRequest.xml をコピーする必要があります。 通常、この場所は、プロジェクト ディレクトリ以下に \bin\Debug\ です。  
  
12. アプリケーションを実行します。 Response.xml、応答メッセージは、アプリケーションで指定した場所に保存されます。 応答メッセージは、数または挿入されたレコードを格納し、次のような。  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     値「1」では、MS_SAMPLE_EMPLOYEE テーブルに 1 つのレコードが挿入されることを示します。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)