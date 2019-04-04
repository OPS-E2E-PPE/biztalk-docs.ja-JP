---
title: WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを呼び出す |Microsoft Docs
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
ms.openlocfilehash: 81f181cfad40c31abc0d5b3517f0d7f8d9c32d7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002355"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを起動します。
Oracle E-business Suite では、Oracle のアプリケーションで特定の操作を実行する実行可能な同時実行プログラムを公開します。 各 Oracle アプリケーションでは、標準の同時実行プログラム (つまり同じすべての操作では) と Oracle アプリケーションに固有の特定の同時実行プログラムのセットがあります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが呼び出すことができる操作としてすべての同時実行プログラムを公開します。 アダプターが同時実行プログラムをサポートする方法の詳細については、[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)を参照してください。  
  
> [!NOTE]
>  そのメタデータを公開しない同時実行プログラム、については、Oracle E-business アダプターは、これらの同時実行プログラムごとに 100 の省略可能なパラメーターを公開します。 これらの同時実行プログラムを正常に呼び出すは、ユーザーは、値を必要とする同時実行プログラムのパラメーターを把握する Oracle E-business Suite のドキュメントを参照して、それらを指定する必要があります。 このような同時実行プログラムの例は、 **Journal インポート**(実際の名前: **GLLEZL**) で、**総勘定元帳**アプリケーション。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、起動、 **MS_SAMPLE_COPY_EMP_DATA**後に、同時実行プログラム、 **Get_Status**同時実行プログラム、最初の同時実行プログラムの状態を確認します。 これらの同時実行プログラムがから呼び出される、**アプリケーション オブジェクト ライブラリ**アプリケーション。 **MS_SAMPLE_COPY_EMP_DATA**サンプルに付属のスクリプトを実行して作成されます。 サンプルの詳細については、[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)を参照してください。 サンプルについては、 **ConcurrentProgram_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 同時実行プログラムを起動するために生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。  
  
|成果物|WCF クライアント名|  
|--------------|---------------------|  
|同時実行プログラム|[APP_NAME] ConcurrentPrograms_ クライアント|  
  
 [構成] は、Oracle E-business Suite のアプリケーションの実際の名前を =たとえば、ヘルプです。  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a>同時実行プログラムを呼び出すためのメソッド シグネチャ  
 次の表では、同時実行プログラムにメソッド シグネチャを示します。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|同時実行プログラム|パブリック\<型を返す\>< Concurrent_program_name > (param 1、param 2、...)|  
  
 WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。  
  
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
  
 このスニペットで**ConcurrentPrograms_FNDClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 **MS_SAMPLE_COPY_EMP_DATA**同時実行プログラムを呼び出すメソッドの名前を指定します。 **GetStatusForConcurrentProgram**最初の同時実行プログラムの状態を取得する同時実行プログラムを呼び出すメソッドの名前を指定します。  
  
> [!NOTE]
>  **GetStatusForConcurrentProgram**の実際の名前を指定、 **Get_Status**同時実行プログラム。  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a>同時実行プログラムを呼び出す、WCF クライアントを作成します。  
 汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)します。 このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. WCF クライアント クラスを生成、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。 WCF クライアント クラスを生成する詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。  
  
   > [!IMPORTANT]
   >  WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`します。  
  
4. Program.cs ファイルを開き、次の名前空間を追加します。  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
   ```  
  
    このスニペットで`ConcurrentPrograms_FNDClient`OracleEBSBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
   > [!NOTE]
   >  このスニペットでは、アプリケーション コードで明示的にバインディングとエンドポイント アドレスを指定するだけ。 アプリケーション構成ファイルから、app.config、によって生成されることも、これらの値を使用することも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 クライアント バインディングを指定する、さまざまな方法の詳細については、[Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)を参照してください。  
  
6. クライアントの資格情報を設定します。  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. Oracle E-business Suite アプリケーションで同時実行プログラムを起動するため、アプリケーションのコンテキストを設定する必要があります。 この例で、アプリケーションのコンテキストの設定を指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーションのコンテキストの詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  
  
   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  
  
8. 次のスニペットで説明されているように、クライアントを開きます。  
  
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
  
9. 呼び出す、 **MS_SAMPLE_COPY_EMP_DATA**と**Get_Status**同時実行プログラム。  
  
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
  
10. 次のスニペットの説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    ```  
  
11. プロジェクトをビルドし、それを実行します。 アプリケーションの起動、 **MS_SAMPLE_COPY_EMP_DATA**と要求 ID を返します。 渡されたし、ID、 **Get_Status**同時実行プログラムの状態が最後に提供する、 **MS_SAMPLE_COPY_EMP_DATA**列プログラム。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)