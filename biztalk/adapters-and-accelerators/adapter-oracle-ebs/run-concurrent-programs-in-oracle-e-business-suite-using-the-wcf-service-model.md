---
title: WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを起動 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9ff6b37f2e18c03a364e3f584ea9f79b547f1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964632"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを呼び出す
Oracle E-business Suite では、Oracle アプリケーションで特定の操作を実行する実行可能な同時実行プログラムを公開します。 各 Oracle アプリケーションでは、一連の標準的な同時実行プログラム (同じすべての操作で) と Oracle アプリケーションに固有の特定の同時実行プログラムがあります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが呼び出すことのできる操作としてすべての同時実行プログラムを公開します。 アダプターで同時実行プログラムをサポートする方法の詳細については、次を参照してください。[同時実行プログラムで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)です。  
  
> [!NOTE]
>  そのメタデータを公開しない同時実行プログラム、については、Oracle E-business アダプターは、これらの同時実行プログラムごとに 100 の省略可能なパラメーターを公開します。 これらの同時実行プログラムを正常に呼び出すには、ユーザーは、値を必要とする同時実行プログラムのパラメーターを確認する Oracle E-business Suite のマニュアルを参照され、それらを指定する必要があります。 このような同時実行プログラムの例は**Journal インポート**(実際の名前: **GLLEZL**) で、**元帳**アプリケーションです。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例を呼び出す、 **MS_SAMPLE_COPY_EMP_DATA**続くプログラムが同時、 **Get_Status**同時実行プログラムを最初の同時実行プログラムの状態を確認します。 これらの同時実行プログラムが呼び出されて、**アプリケーション オブジェクト ライブラリ**アプリケーションです。 **MS_SAMPLE_COPY_EMP_DATA**は、サンプルの値が指定されたスクリプトを実行して作成します。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。 サンプルは、 **ConcurrentProgram_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 同時実行プログラムを起動するために生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。  
  
|成果物|WCF クライアント名|  
|--------------|---------------------|  
|同時実行プログラム|ConcurrentPrograms_ [APP_NAME] クライアント|  
  
 [構成]、Oracle E-business Suite アプリケーションの実際の名前を =たとえばのヘルプ。  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a>同時実行プログラムを起動するためのメソッド シグネチャ  
 次の表は、同時実行プログラムのメソッドのシグネチャを示します。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|同時実行プログラム|パブリック\<型を返す\>< Concurrent_program_name > (param 1、param 2、...)|  
  
 たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラムです。  
  
```  
public partial class ConcurrentPrograms_FNDClient : System.ServiceModel.ClientBase<ConcurrentPrograms_FND>, ConcurrentPrograms_FND {      
  
    public string MS_SAMPLE_COPY_EMP_DATA(schemas.microsoft.com.OracleEBS._2008._05.Options.SetOptions SetOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,  
      string Description, string StartTime);  
  
    public bool GetStatusForConcurrentProgram(string RequestId, out string Phase, out string Status,  
      out string DevPhase, out string DevStatus, out string Message);  
}  
```  
  
 このスニペットで**ConcurrentPrograms_FNDClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 **MS_SAMPLE_COPY_EMP_DATA**プログラムを同時に呼び出すメソッドの名前を指定します。 **GetStatusForConcurrentProgram**最初の同時実行プログラムの状態を取得するプログラムを同時に呼び出すメソッドの名前を指定します。  
  
> [!NOTE]
>  **GetStatusForConcurrentProgram**の実際の名前、 **Get_Status**同時実行プログラムです。  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a>同時実行プログラムを起動する WCF クライアントを作成します。  
 WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)です。 このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラムです。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  WCF クライアント クラスを生成、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラムです。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
    > [!IMPORTANT]
    >  WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`です。  
  
4.  Program.cs ファイルを開き、次の名前空間を追加します。  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
    ```  
  
     このスニペットで`ConcurrentPrograms_FNDClient`OracleEBSBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!NOTE]
    >  このスニペットでは、アプリケーション コードで明示的にバインドとエンドポイント アドレスを指定するだけです。 アプリケーション構成ファイルから、app.config、によって生成されるも、これらの値を使用することも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。  
  
6.  クライアントの資格情報を設定します。  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  Oracle E-business Suite アプリケーションで同時実行プログラムを起動するため、アプリケーションのコンテキストを設定する必要があります。 この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  次のスニペット」の説明に従って、クライアントを開きます。  
  
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
  
9. 呼び出す、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラムです。  
  
    ```  
    string RequestID;  
    bool Result;  
    string Phase;  
    string Status;  
    string DevPhase;  
    string DevStatus;  
    string Message;  
  
    try  
    {  
        Console.WriteLine("Invoking the MS_SAMPLE_COPY_EMP_DATA concurrent program");  
        RequestID = client.MS_SAMPLE_COPY_EMP_DATA(null, null, null, null, null);  
        Console.WriteLine("The request ID generated for the concurrent program is : " + RequestID);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nWaiting for 60 seconds for the concurrent program to be complete");  
        System.Threading.Thread.Sleep(60000);  
        Console.WriteLine("\nInvoking the Get_Status concurrent program");  
        Result = client.GetStatusForConcurrentProgram(RequestID, out Phase, out Status, out DevPhase, out DevStatus, out Message);  
        Console.WriteLine("\nResult is  : " + Result);  
        Console.WriteLine("Phase is     : " + Phase);  
        Console.WriteLine("Status is    : " + Status);  
        Console.WriteLine("DevPhase is  : " + DevPhase);  
        Console.WriteLine("DevStatus is : " + DevStatus);  
        Console.WriteLine("Message is   : " + Message);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;                 
    }  
    ```  
  
10. 次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    ```  
  
11. プロジェクトをビルドし、それを実行します。 アプリケーションを起動、 **MS_SAMPLE_COPY_EMP_DATA**し、要求 ID を返します。 渡されたし、ID、 **Get_Status**プログラムの状態が最後に表示される同時、 **MS_SAMPLE_COPY_EMP_DATA**列プログラムです。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)