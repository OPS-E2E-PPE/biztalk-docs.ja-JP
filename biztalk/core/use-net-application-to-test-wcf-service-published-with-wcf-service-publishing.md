---
title: "BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストするための .NET アプリケーションを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services, .NET applications
- WCF services, WCF Service Publishing Wizard
- creating, .NET applications [WCF services]
- WCF Service Publishing Wizard
ms.assetid: 17e39db2-8471-4f6f-a7f1-833023cdbc39
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb46847361127a915d06ee74eaed549caf40258a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a><span data-ttu-id="e7b8a-102">.NET アプリケーションを作成して、BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストする方法</span><span class="sxs-lookup"><span data-stu-id="e7b8a-102">How to Create a .NET Application to Test a WCF Service Published with the BizTalk WCF Service Publishing Wizard</span></span>
<span data-ttu-id="e7b8a-103">公開済みの WCF サービスをテストするには、公開済みの WCF サービスを使用する .NET アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-103">To test your published WCF service, you can create a .NET application that consumes your published WCF service.</span></span> <span data-ttu-id="e7b8a-104">このトピックでは、.NET アプリケーションを作成して、公開済みの WCF サービスをテストする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-104">This topic describes how to create a .NET application to test a published WCF service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7b8a-105">Visual Studio ヘルプ コレクションには、WCF サービスを使用する .NET アプリケーションを作成するための有用なチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-105">The Visual Studio Help Collection contains a valuable walkthrough for creating a .NET application that consumes WCF services.</span></span> <span data-ttu-id="e7b8a-106">このチュートリアルを使用して、公開済みの WCF サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-106">You can use the walkthrough to test your published WCF service.</span></span> <span data-ttu-id="e7b8a-107">WCF クライアント プロジェクトの作成に関する情報および手順を参照してください「チュートリアル: へのアクセス、XML Web サービスを使用して Visual Basic または Visual c#」で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)です。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-107">For information and procedures about creating a WCF client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7b8a-108">このトピックでは、ServiceModel メタデータ ユーティリティ ツール (SvcUtil.exe) を使用して、WCF プロキシ クラスおよびアプリケーション構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-108">This topic uses the Service Model Metadata Utility tool (SvcUtil.exe) to create the WCF proxy classes and application configuration file.</span></span> <span data-ttu-id="e7b8a-109">SvcUtil.exe は、Windows Vista の Microsoft Windows ソフトウェア開発キット (SDK) および .NET Framework ランタイム コンポーネントに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-109">SvcUtil.exe is included in the Microsoft Windows Software Development Kit (SDK) of Windows Vista and .NET Framework Runtime Components.</span></span>  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a><span data-ttu-id="e7b8a-110">簡単な WCF プロキシ クラスおよびアプリケーション構成ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="e7b8a-110">To create a simple WCF proxy class and application configuration file</span></span>  
  
1.  <span data-ttu-id="e7b8a-111">次のように CMD シェルを開きます: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Windows SDK**、順にクリック**CMD Shell**です。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-111">Open CMD Shell as follows: click **Start**, point to **All Programs**, point to **Microsoft Windows SDK**, and then click **CMD Shell**.</span></span>  
  
2.  <span data-ttu-id="e7b8a-112">CMD シェルで、プロキシ クラスおよびアプリケーション構成ファイルを配置する先のディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-112">In CMD Shell, go to the directory where you want to place the proxy class and application configuration file.</span></span>  
  
3.  <span data-ttu-id="e7b8a-113">CMD シェルで、以下のように ServiceModel メタデータ ユーティリティ ツール (SvcUtil.exe) を実行して、公開済みの WCF サービスの WCF プロキシ クラスおよびアプリケーション構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-113">In CMD Shell, run the ServiceModel Metadata Utility Tool (SvcUtil.exe) to create the WCF proxy class and application configuration file for the published WCF service as follows:</span></span>  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="e7b8a-114">このコマンド ラインにより、プロキシ クラスである BizTalkServiceInstance.cs とアプリケーション構成ファイルである App.config が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-114">This command line generates BizTalkServiceInstance.cs for the proxy class and App.config for the application configuration.</span></span> <span data-ttu-id="e7b8a-115">Svcutil.exe の詳細についてを参照してください「サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)」 [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696)です。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-115">For more information about Svcutil.exe, see "Service Model Metadata Utility Tool (Svcutil.exe)" at [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696).</span></span>  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a><span data-ttu-id="e7b8a-116">公開済みの WCF サービスを使用する .NET アプリケーションをコンパイルするには</span><span class="sxs-lookup"><span data-stu-id="e7b8a-116">To compile your .NET application that consumes the published WCF service</span></span>  
  
1.  <span data-ttu-id="e7b8a-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューション エクスプローラーで、SvcUtil.exe が作成した BizTalkServiceInstance および App.config の 2 つのファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, add the files that SvcUtil.exe creates, BizTalkServiceInstance and App.config, to your project.</span></span>  
  
2.  <span data-ttu-id="e7b8a-118">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューション エクスプローラーで、プロキシ コードをコンパイルするために System.ServiceModel.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-118">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, make sure to add a reference to the System.ServiceModel.dll to compile the proxy code.</span></span>  
  
3.  <span data-ttu-id="e7b8a-119">生成されたプロキシ コードを使用するコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-119">Create the code to use the generated proxy code.</span></span> <span data-ttu-id="e7b8a-120">次のコードは、生成されたプロキシの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-120">The following code shows how to use the generated proxy:</span></span>  
  
    ```  
    DeliveryNotification deliveryNotification= new DeliveryNotification();  
    deliveryNotification.TrackingNumber = "001";  
                Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
    service.Submit(deliveryNotification);  
    ```  
  
4.  <span data-ttu-id="e7b8a-121">.NET アプリケーションを実行して、公開済みの WCF サービスにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e7b8a-121">Run your .NET application to send messages to the published WCF service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b8a-122">参照</span><span class="sxs-lookup"><span data-stu-id="e7b8a-122">See Also</span></span>  
 [<span data-ttu-id="e7b8a-123">受信アダプターの WCF での WCF サービスを発行するときの考慮事項</span><span class="sxs-lookup"><span data-stu-id="e7b8a-123">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)