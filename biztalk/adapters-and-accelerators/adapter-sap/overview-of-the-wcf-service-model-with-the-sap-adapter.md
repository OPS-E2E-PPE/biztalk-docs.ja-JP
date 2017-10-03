---
title: "SAP アダプターで WCF サービス モデルの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF service model, overview of using
ms.assetid: 02a4b43e-ade0-4dba-b8f6-074bca7cbe5c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da5b2f7cc8e38eb8afd211a2008c0f740760cd4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-sap-adapter"></a>SAP アダプターで WCF サービス モデルの概要
操作を使用する際にする、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サーフェスは、コードは、機能、クライアントと、アダプターにサービスのどちらかです。  
  
 コードは、次のような SAP システムの操作を呼び出すクライアントとして機能します。  
  
-   リモート関数呼び出し (RFC) を呼び出します。  
  
-   トランザクション リモート関数呼び出し (tRFC) を呼び出します。  
  
-   プログラミング インターフェイス (BAPI) ビジネス アプリケーションを起動します。  
  
-   中間ドキュメント (IDOC) を送信します。  
  
 コードは、次のような操作を受信するサービスとして動作します。  
  
-   RFC (RFC サーバー) が表示されます。  
  
-   TRFC (tRFC サーバー) が表示されます。  
  
-   IDOC を受信します。  
  
> [!NOTE]
>  Bapi のビジネス オブジェクト リポジトリ (どれ) に配置されているビジネス オブジェクト上の SAP システムで公開されたメソッドであるために、Bapi を受信できません。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。 これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。 操作を受信するサービスを実装する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ターゲットの操作に対して生成されたインターフェイスを実装します。  
  
 次のセクションでは、モデルを使用して、WCF サービスのクライアントとサービスのコードを作成する方法を説明する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="creating-a-wcf-client-and-invoking-operations-on-sap"></a>WCF クライアントを作成して、SAP で操作を呼び出すこと  
 モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。 このクラスでは、WCF クライアントのインスタンスを作成し、SAP システムでの操作を実行するには、そのメソッドを呼び出すことができます。  
  
#### <a name="to-invoke-operations-on-the-sap-adapter"></a>SAP アダプターの操作を呼び出す  
  
1.  WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を SAP システムの成果物を対象と WCF クライアント クラスを生成する作業します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
2.  クライアントのバインディングを指定することによって、WCF クライアントのインスタンスを作成します。 クライアントのバインディングを指定するには、バインドと WCF クライアントが使用するエンドポイント アドレスを指定する必要があります。 これは、コードで命令として記述または構成で宣言によって行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。[クライアントを、SAP システムのバインド構成](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)です。 次のコードでは、SAP システムで RFC を呼び出すために使用できる WCF クライアントを作成します。 また、SAP システムの資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
    ```  
    RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  WCF クライアントを開きます。  
  
    ```  
    rfcClient.Open();  
    ```  
  
4.  SAP システムでの操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 次のコードを呼び出す、 **SD_RFC_CUSTOMER_GET**を SAP システムで RFC を呼び出す、WCF クライアントのメソッドです。  
  
    ```  
    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
        new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
    ```  
  
5.  WCF クライアントを閉じます。  
  
    ```  
    rfcClient.Close();  
  
    ```  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-sap-adapter"></a>作成して、SAP アダプターを使用して WCF サービスの実装  
 モデルを使用して、WCF サービスからの操作を受信する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、最初に、.NET (WCF サービス コントラクトとも呼ばれます) を表すインターフェイスによって公開されるサービス コントラクトを生成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作します。 これを行う方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
 WCF サービスを実装するには、生成されたインターフェイスを実装することで。 このクラスには、操作を処理して、アダプターに応答を返すビジネス ロジックが含まれています。 サービス ホストを使用して (**System.ServiceModel.ServiceHost**) をこのサービスのインスタンスをホストします。  
  
#### <a name="to-create-and-implement-a-wcf-service"></a>作成して、WCF サービスを実装するには  
  
1.  WCF サービス コントラクトとヘルパー クラスを生成します。 使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または svcutil.exe を操作する SAP システムのアイテムを対象とした WCF サービス コントラクト (インターフェイス) を生成します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
2.  手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 その操作を処理するメソッドがエラーを返す、SAP システムに例外をスローできます操作のデータの処理エラーが発生した場合それ以外の場合、メソッドは、操作を適切な応答が (生成) クラスのインスタンスを返す必要があります。 次のように、WCF サービス クラスを属性する必要があります。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
    1.  使用した場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]インターフェイスを生成するには、直接、適切なメソッドで、生成されたロジックを実装できる**SAPBindingService**クラスです。 このクラスは、SAPBindingService.cs で確認できます。 次のコードでサブ クラス、 **SAPBindingService**クラスです。  
  
        ```  
        [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
        class RfcServerClass : SAPBindingNamespace.SAPBindingService  
        {  
            public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
            {  
                // If either parameter is null throw an exception   
                if (request.X == null || request.Y == null)  
                    throw new System.ArgumentNullException();  
  
                // Add the two operands  
                int result = (int) (request.X + request.Y);  
  
                return new Z_RFC_MKD_ADDResponse(result);  
            }  
        }  
        ```  
  
    2.  Svcutil.exe を使用して、インターフェイスを生成した場合は、インターフェイスを実装するクラスを作成し、このクラスの appropriatemethod で、ロジックを実装する必要があります。  
  
3.  手順 2 で作成した WCF サービスのインスタンスを作成します。  
  
    ```  
    // create service instance  
    RfcServerClass rfcServerInstance = new RfcServerClass();  
    ```  
  
4.  インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。 基本の接続 URI には、userinfoparams またはクエリ文字列を含めることはできません。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("sap://a/YourSAPHost/00") };  
    ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
    ```  
  
5.  作成、 **SAPBinding**し、バインドのプロパティを設定して、操作のように構成します。 これは、コードで明示的にまたは構成で宣言によって行うことができます。 設定する必要がありますには、少なくとも**AcceptCredentialsInUri**に**true**です。  
  
    ```  
    // Create and configure a binding for the service endpoint. NOTE: binding  
    // parameters are set here for clarity, but these are already set in the  
    // the generated configuration file  
    SAPBinding binding = new SAPBinding();  
  
    // The credentials are included in the connection URI, so set this property to true  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
6.  サービス ホストにサービス エンドポイントを追加します。 これを行うには :  
  
    -   手順 5. で作成したバインディングを使用します。  
  
    -   接続の資格情報が含まれており、リスナーの接続を指定する URI を指定して (SAP のゲートウェイ、ゲートウェイ サービスとプログラム ID)、query_string にします。 SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
    -   サービス コントラクトを指定します。 これは、WCF サービス コントラクトを表すインターフェイスの名前です。 Rfc、"Rfc"です。  
  
    ```  
    // Add service endpoint   
    // NOTE: The contract for the service endpoint is "Rfc".  
    //       This is the generated WCF service contract (interface) -- see SAPBindingInterface.cs.  
    Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGW00&ListenerGwHost=YourSapHost&ListenerProgramId=SAPAdapter");  
    srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
    ```  
  
7.  SAP システムから、操作を受信するには、サービス ホストを開きます。 SAP システムにプログラムの ID と手順 6. で、サービス URI で指定されたシステム上の操作が呼び出されるたびに、WCF サービスが呼び出されます。  
  
    ```  
    // Open the service host to begin receiving the operation.  
    srvHost.Open();  
    ```  
  
8.  操作の受信を停止するには、サービス ホストを閉じます。  
  
    > [!IMPORTANT]
    >  アダプターは、サービス ホストが閉じられるまで、操作を受信し続けます。 操作を受信する必要がなくなったときに常に、サービス ホストを閉じる必要があります。  
  
    ```  
    srvHost.Close();  
    ```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)