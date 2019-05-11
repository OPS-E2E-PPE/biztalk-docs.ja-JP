---
title: WCF サービス モデルを使用して Oracle E-business Suite での要求のセットを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb6ec551-c069-4133-add5-2ba83d20405d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09eb5e16e45d97e4035f2f16639773f9fbaaa39f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375445"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite での要求のセットを呼び出す
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite での要求セットを実行できます。 要求セットは 1 つまたは複数の段階に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 します。 アダプターが要求のセットをサポートする方法の詳細については、次を参照してください。[に対する要求の設定操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)します。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 要求の呼び出し設定するために生成される WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。  
  
|成果物|WCF クライアント名|  
|--------------|---------------------|  
|要求セット|[APP_NAME] RequestSets_ クライアント|  
  
 [構成] は、Oracle E-business Suite のアプリケーションの実際の名前を =たとえば、SQLAP です。  
  
### <a name="method-signature-for-invoking-request-sets"></a>要求セットを呼び出すためのメソッド シグネチャ  
 要求セットのメソッド シグネチャを次の表に示します。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|要求セット|パブリック\<型を返す\>\<要求セット名\>(param 1、param 2、...)|  
  
 WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **reqset_singlestage**セットを要求します。  
  
> [!NOTE]
>  カスタムの要求セットは、この Oracle E-business ソリューション インスタンスで使用可能なことができない可能性があります。  
  
```  
public partial class RequestSets_SQLAPClient : System.ServiceModel.ClientBase<RequestSets_SQLAP>, RequestSets_SQLAP{      
  
    public string REQSTG(  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRelClassOptions SetRelClassOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetNlsOptions SetNlsOptions,  
      string StartTime,  
      schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 set1_set1);  
}  
```  
  
 このスニペットで**RequestSets_SQLAPClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 **REQSTG**要求セットを呼び出すメソッドの名前を指定します。  
  
## <a name="creating-a-wcf-client-to-invoke-request-sets"></a>要求セットを呼び出す、WCF クライアントを作成します。  
 汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)します。 このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **reqset_singlestage**セットを要求します。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. WCF クライアント クラスを生成、 **reqset_singlestage**セットを要求します。 WCF クライアント クラスを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。  
  
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
   RequestSets_SQLAPClient client = new RequestSets_SQLAPClient(binding, address);  
   ```  
  
    このスニペットで`RequestSets_SQLAPClient`OracleEBSBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
   > [!NOTE]
   >  このスニペットでは、アプリケーション コードで明示的にバインディングとエンドポイント アドレスを指定するだけ。 アプリケーション構成ファイルから、app.config、によって生成されることも、これらの値を使用することも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)します。  
  
6. クライアントの資格情報を設定します。  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. Oracle E-business Suite アプリケーションで要求のセットを呼び出すため、アプリケーションのコンテキストを設定する必要があります。 この例で、アプリケーションのコンテキストの設定を指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーションのコンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
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
  
9. 呼び出す、 **reqset_singlestage**セットを要求します。  
  
    ```  
    string RequestID;  
  
    schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 param =  
        new schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1();  
  
    param.INSPARAMPROG = new schemas.microsoft.com.OracleEBS._2008._05.RequestSetConcurrentProgram.SQLAP.REQSTG.set1.SQLAP1.INSPARAMPROG();  
    param.INSPARAMPROG.p_id = "123";  
    param.INSPARAMPROG.p_name = "MyName";  
  
    try  
    {  
        Console.WriteLine("Invoking the reqset_singlestage request set");  
        RequestID = client.REQSTG(null, null, null, null, null, param);  
        Console.WriteLine("The request ID generated for the request set is : " + RequestID);  
        Console.WriteLine("*****************************************************************");  
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
  
11. プロジェクトをビルドし、それを実行します。 アプリケーションの起動、 **reqset_singlestage**要求の設定し、コンソールに書き込まれる要求 ID を返します。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)