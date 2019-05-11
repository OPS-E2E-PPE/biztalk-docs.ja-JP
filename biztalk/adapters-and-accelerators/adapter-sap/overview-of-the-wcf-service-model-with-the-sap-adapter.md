---
title: SAP アダプターを使用した WCF サービス モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview of using
ms.assetid: 02a4b43e-ade0-4dba-b8f6-074bca7cbe5c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ce25d78b40763f78d214276bb9311898653389
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373135"
---
# <a name="overview-of-the-wcf-service-model-with-the-sap-adapter"></a>SAP アダプターを使用した WCF サービス モデルの概要
操作を使用するが、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サーフェスは、クライアントまたはアダプターにサービスとして、コードが機能します。  
  
 コードは、次のような SAP システムの操作を呼び出すクライアントとして機能します。  
  
- リモート関数呼び出し (RFC) を呼び出します。  
  
- トランザクション リモート関数呼び出し (tRFC) を呼び出します。  
  
- プログラミング インターフェイス (BAPI)、ビジネス アプリケーションを起動します。  
  
- 中間ドキュメント (IDOC) を送信します。  
  
  コードは、次のような操作を受信するサービスとして動作します。  
  
- 受信 RFC (RFC サーバー)  
  
- 受信 tRFC (tRFC server)  
  
- IDOC を受信します。  
  
> [!NOTE]
>  Bapi はビジネス オブジェクト リポジトリ (BOR) であるビジネス オブジェクト上の SAP システムによって公開されるメソッドであるために、Bapi を受信できません。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作はこのインターフェイスのメソッドとして表されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF アダプターを公開するメタデータからの対象となる操作には、このインターフェイスを生成するためのツールを提供するとします。 これらのツールでは、サービス インターフェイスで公開されている操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションでは、アダプターの操作を呼び出すための WCF クライアント クラスのメソッドを呼び出すことができます。 操作を受信するサービスを実装するために、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]対象の操作に対して生成されたインターフェイスを実装します。  
  
 次のセクションでは、WCF サービス モデルを使用して、クライアントとサービスのコードを作成する方法を説明します、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="creating-a-wcf-client-and-invoking-operations-on-sap"></a>WCF クライアントを作成して、SAP での操作を呼び出す  
 WCF サービス モデルを使用して、操作を呼び出してする、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、まずターゲットの WCF クライアント クラスを生成する必要があります。 WCF クライアントでは、このクラスのインスタンスを作成し、SAP システムの操作を実行するには、そのメソッドを呼び出すことができます。  
  
#### <a name="to-invoke-operations-on-the-sap-adapter"></a>SAP アダプターの操作を呼び出す  
  
1. WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) SAP システムの成果物を対象とした WCF クライアント クラスを生成する作業します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
2. クライアントのバインディングを指定することで、WCF クライアントのインスタンスを作成します。 クライアントのバインディングを指定するには、バインドと WCF クライアントを使用するエンドポイント アドレスを指定する必要があります。 コードで強制的に、または構成で宣言的に、これを行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。[のバインド、SAP システムのクライアントを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)します。 次のコードでは、SAP システムの RFC を呼び出すために使用できる WCF クライアントを作成します。 また、SAP システムの資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
   ```  
   RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
   rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. WCF クライアントを開きます。  
  
   ```  
   rfcClient.Open();  
   ```  
  
4. SAP システムの操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 次のコードを呼び出す、 **SD_RFC_CUSTOMER_GET**を SAP システムでの RFC を呼び出す、WCF クライアントのメソッド。  
  
   ```  
   microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
       new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
   rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
   ```  
  
5. WCF クライアントを閉じます。  
  
   ```  
   rfcClient.Close();  
  
   ```  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-sap-adapter"></a>作成して、SAP アダプターを使用して WCF サービスを実装します。  
 操作を受信する WCF サービス モデルを使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、(WCF サービス コントラクトとも呼ばれます) によって公開されるサービス コントラクトを表す .NET インターフェイスを生成する必要があります最初、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作。 これを行う方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
 WCF サービスを実装するには、生成されたインターフェイスを実装します。 このクラスには、操作を処理し、アダプターに応答を返すビジネス ロジックが含まれています。 サービス ホストを使用して (**System.ServiceModel.ServiceHost**) このサービスのインスタンスをホストします。  
  
#### <a name="to-create-and-implement-a-wcf-service"></a>作成して WCF サービスの実装  
  
1. WCF サービス コントラクトとヘルパー クラスを生成します。 使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または svcutil.exe を使用する SAP システムの成果物を対象とした WCF サービス コントラクト (インターフェイス) を生成します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
2. 手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 その操作を処理するメソッドが、SAP システムに、エラーを返す例外をスローできますデータ操作の処理エラーが発生した場合それ以外の場合、メソッドは、操作の適切な応答が (生成) クラスのインスタンスを返す必要があります。 次のように、WCF サービス クラスを属性する必要があります。  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
   1. 使用した場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]インターフェイスを生成するには、生成された適切なメソッドに直接ロジックを実装できる**SAPBindingService**クラス。 このクラスは、SAPBindingService.cs で確認できます。 次のコード サブクラス、 **SAPBindingService**クラス。  
  
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
  
   2. Svcutil.exe を使用してインターフェイスを生成した場合は、インターフェイスを実装するクラスを作成し、このクラスの appropriatemethod で、ロジックを実装する必要があります。  
  
3. 手順 2 で作成した WCF サービスのインスタンスを作成します。  
  
   ```  
   // create service instance  
   RfcServerClass rfcServerInstance = new RfcServerClass();  
   ```  
  
4. インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。 基本の接続 URI には、userinfoparams またはクエリ文字列を含めることはできません。  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("sap://a/YourSAPHost/00") };  
   ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
   ```  
  
5. 作成、 **SAPBinding**そのバインドのプロパティを設定して、操作用に構成します。 コードで明示的に、または構成で宣言的に、これを行うことができます。 設定する必要がありますには、少なくとも**AcceptCredentialsInUri**に**true**します。  
  
   ```  
   // Create and configure a binding for the service endpoint. NOTE: binding  
   // parameters are set here for clarity, but these are already set in the  
   // the generated configuration file  
   SAPBinding binding = new SAPBinding();  
  
   // The credentials are included in the connection URI, so set this property to true  
   binding.AcceptCredentialsInUri = true;  
   ```  
  
6. サービス ホストにサービス エンドポイントを追加します。 これを行うには :  
  
   -   手順 5. で作成したバインドを使用します。  
  
   -   接続の資格情報を含み、リスナーの接続を指定する URI を指定して (SAP ゲートウェイ、ゲートウェイ サービスとプログラム ID)、クエリ文字列にします。 SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
   -   サービス コントラクトを指定します。 これは、WCF サービス コントラクトを表すインターフェイスの名前です。 Rfc、"Rfc"です。  
  
   ```  
   // Add service endpoint   
   // NOTE: The contract for the service endpoint is "Rfc".  
   //       This is the generated WCF service contract (interface) -- see SAPBindingInterface.cs.  
   Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGW00&ListenerGwHost=YourSapHost&ListenerProgramId=SAPAdapter");  
   srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
   ```  
  
7. SAP システムから、操作を受信するには、サービス ホストを開きます。 WCF サービスは、SAP システムにプログラムの ID と手順 6. で、サービス URI で指定されたシステム上の操作が呼び出されるたびに呼び出されます。  
  
   ```  
   // Open the service host to begin receiving the operation.  
   srvHost.Open();  
   ```  
  
8. 操作の受信を停止するには、サービス ホストを閉じます。  
  
   > [!IMPORTANT]
   >  アダプターは、サービス ホストが閉じられるまで、操作を受信する続行します。 操作を受信する必要がなくなったときに常に、サービス ホストを閉じる必要があります。  
  
   ```  
   srvHost.Close();  
   ```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)