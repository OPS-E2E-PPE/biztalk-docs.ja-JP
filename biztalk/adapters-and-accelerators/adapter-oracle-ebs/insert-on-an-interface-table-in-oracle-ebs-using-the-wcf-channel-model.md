---
title: "WCF チャネル モデルを使用して Oracle E-business Suite のインターフェイス テーブルに対して挿入操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a2e5ee3-552b-40a2-aaa6-5391347f1146
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703b00adeb373fe66c4a96c324f13f9c3c5ec655
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-on-an-interface-table-in-oracle-e-business-suite-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle E-business suite のインターフェイス テーブルに対して挿入操作を実行します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite のインターフェイス テーブルに対する Insert、Select、Update、および Delete の操作のセットを検出します。 これらの操作を使用することができますを実行して単純な Insert、Select、Update、Delete ステートメントで修飾して、Where 句は、対象のインターフェイス テーブルにします。 このトピックでは、WCF チャネル モデルを使用してインターフェイス テーブルに対する挿入操作を実行する方法について説明します。  
  
 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとのインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)です。 WCF チャネル モデルを使用して Oracle E-business Suite での操作を実行する方法に関する詳細については、次を参照してください。 [Oracle E-business Suite アダプターで WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの操作を実行します。 サンプルに用意されているスクリプトを実行して、テーブルが作成されます。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。 サンプルは、 **InsertOperation**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。  
  
## <a name="the-insert-message"></a>挿入メッセージ  
 WCF チャネル モデルを使用して Oracle E-business Suite での操作を実行するには、操作に固有の要求メッセージが必要です。 MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する挿入操作を実行する要求メッセージには、次のようになります。  
  
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
  
 例: InsertRequest.xml ファイルにメッセージをコピーする必要があります。 このファイルは、Oracle E-business Suite を使用する要求メッセージを送信するこの例では使用、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 テーブルに対する操作のメッセージ スキーマの詳細については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)です。  
  
## <a name="creating-a-wcf-channel-application"></a>WCF チャネル アプリケーションを作成します。  
 このセクションでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対して挿入操作を実行する WCF チャネル アプリケーションを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-table"></a>テーブルにレコードを挿入するための WCF チャネル アプリケーションを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`です。  
  
3.  Program.cs ファイルを開き、次の名前空間を追加します。  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  バインドとエンドポイントを作成します。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
  
    ```  
  
5.  インターフェイス テーブルに対する操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。 この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  作成し、チャネル ファクトリを開きます。 このアプリケーションは、Oracle E-business Suite に要求メッセージを送信し、応答を受信する、そのため、IRequestChannel インターフェイスを実装する必要があります。  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
7.  作成し、チャネルを開きます。  
  
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
  
     要求メッセージを作成中にインターフェイス テーブルについて、アダプターを実行するアクションを示すメッセージのアクションを指定する必要があります。 メッセージのアクションは、MS_SAMPLE_EMPLOYEE テーブルに対して挿入操作を実行する`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`です。 テーブルに対するさまざまな操作のメッセージのアクションを判断する方法については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)です。  
  
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
  
11. プロジェクトをビルドする。 プロジェクトをビルドしたら、InsertRequest.xml、実行可能プロジェクトと同じ場所に、要求メッセージをコピーする必要があります。 通常、この場所は、プロジェクト ディレクトリ下にある \bin\Debug\ です。  
  
12. アプリケーションを実行します。 応答メッセージ、Response.xml は、アプリケーションで指定した場所に保存されます。 応答メッセージは、番号または挿入されたレコードが含まれ、次のようになります。  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">  
      <InsertResult>1</InsertResult>  
    </InsertResponse>  
    ```  
  
     値「1」では、1 つのレコードが MS_SAMPLE_EMPLOYEE テーブルに挿入されるを示します。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)