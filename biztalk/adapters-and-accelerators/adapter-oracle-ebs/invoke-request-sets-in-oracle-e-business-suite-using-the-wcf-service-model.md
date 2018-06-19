---
title: WCF サービス モデルを使用して Oracle E-business Suite での要求のセットを呼び出す |Microsoft ドキュメント
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
ms.openlocfilehash: ec243c1d1ed1093241e4dc6120c3703fbf2e4542
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965184"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite での要求のセットをを呼び出す
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite で要求のセットを実行できます。 セットは、1 つまたは複数の段階的に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 を要求します。 アダプターが要求のセットをサポートする方法の詳細については、次を参照してください。[要求設定に対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 要求の呼び出し設定用に生成、WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。  
  
|成果物|WCF クライアント名|  
|--------------|---------------------|  
|要求のセット|RequestSets_ [APP_NAME] クライアント|  
  
 [構成]、Oracle E-business Suite アプリケーションの実際の名前を =たとえば、SQLAP です。  
  
### <a name="method-signature-for-invoking-request-sets"></a>要求のセットを呼び出すためのメソッド シグネチャ  
 次の表は、要求のセットに対してメソッド署名を示します。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|要求のセット|パブリック\<型を返す\>\<要求セット名\>(param 1、param 2、...)|  
  
 たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **reqset_singlestage**セットを要求します。  
  
> [!NOTE]
>  これにより、カスタム要求セットはあり、Oracle E-business ソリューション インスタンスで使用可能なことができない可能性があります。  
  
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
  
 このスニペットで**RequestSets_SQLAPClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 **REQSTG**要求セットに呼び出すメソッドの名前を指定します。  
  
## <a name="creating-a-wcf-client-to-invoke-request-sets"></a>要求セットを呼び出す、WCF クライアントを作成します。  
 WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)です。 このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **reqset_singlestage**セットを要求します。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  WCF クライアント クラスを生成、 **reqset_singlestage**セットを要求します。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
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
    RequestSets_SQLAPClient client = new RequestSets_SQLAPClient(binding, address);  
    ```  
  
     このスニペットで`RequestSets_SQLAPClient`OracleEBSBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!NOTE]
    >  このスニペットでは、アプリケーション コードで明示的にバインドとエンドポイント アドレスを指定するだけです。 アプリケーション構成ファイルから、app.config、によって生成されるも、これらの値を使用することも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。  
  
6.  クライアントの資格情報を設定します。  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  Oracle E-business Suite アプリケーションで要求のセットを起動するため、アプリケーションのコンテキストを設定する必要があります。 この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
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
  
10. 次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    ```  
  
11. プロジェクトをビルドし、それを実行します。 アプリケーションを起動、 **reqset_singlestage**要求が設定され、コンソールに書き込まれますが、要求の ID を返します。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)