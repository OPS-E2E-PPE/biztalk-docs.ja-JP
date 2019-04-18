---
title: BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストするための .NET アプリケーションを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, .NET applications
- WCF services, WCF Service Publishing Wizard
- creating, .NET applications [WCF services]
- WCF Service Publishing Wizard
ms.assetid: 17e39db2-8471-4f6f-a7f1-833023cdbc39
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d390b54a79ca883b53ff5088638ba2804fa2640
ms.sourcegitcommit: 85e827c42f193e44ca8b5b8d78d6f8b8ac686f1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58867556"
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a><span data-ttu-id="be7dc-102">BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストするための .NET アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="be7dc-102">How to Create a .NET Application to Test a WCF Service Published with the BizTalk WCF Service Publishing Wizard</span></span>
<span data-ttu-id="be7dc-103">を、公開済み WCF サービスをテストするには、公開済み WCF サービスを使用する .NET アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="be7dc-103">To test your published WCF service, you can create a .NET application that consumes your published WCF service.</span></span> <span data-ttu-id="be7dc-104">このトピックでは、公開した WCF サービスをテストするための .NET アプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-104">This topic describes how to create a .NET application to test a published WCF service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be7dc-105">Visual Studio ヘルプ コレクションには、WCF サービスを使用する .NET アプリケーションを作成するため貴重なチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="be7dc-105">The Visual Studio Help Collection contains a valuable walkthrough for creating a .NET application that consumes WCF services.</span></span> <span data-ttu-id="be7dc-106">このチュートリアルを使用して、公開済み WCF サービスをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="be7dc-106">You can use the walkthrough to test your published WCF service.</span></span> <span data-ttu-id="be7dc-107">情報と WCF クライアント プロジェクトの作成方法の手順では、次を参照してください。"チュートリアル。Visual Basic または Visual を使用して XML Web サービスへのアクセスC#"で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-107">For information and procedures about creating a WCF client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="be7dc-108">このトピックでは、Service Model メタデータ ユーティリティ ツール (SvcUtil.exe)、WCF プロキシ クラスを作成してアプリケーション構成ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-108">This topic uses the Service Model Metadata Utility tool (SvcUtil.exe) to create the WCF proxy classes and application configuration file.</span></span> <span data-ttu-id="be7dc-109">SvcUtil.exe で、Microsoft Windows ソフトウェア開発キット (SDK) の Windows Vista と .NET Framework のランタイム コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="be7dc-109">SvcUtil.exe is included in the Microsoft Windows Software Development Kit (SDK) of Windows Vista and .NET Framework Runtime Components.</span></span>  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a><span data-ttu-id="be7dc-110">単純な WCF プロキシ クラスおよびアプリケーション構成ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="be7dc-110">To create a simple WCF proxy class and application configuration file</span></span>  
  
1.  <span data-ttu-id="be7dc-111">次のように CMD シェルを開きます: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Windows SDK**、順にクリックします**CMD シェル**します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-111">Open CMD Shell as follows: click **Start**, point to **All Programs**, point to **Microsoft Windows SDK**, and then click **CMD Shell**.</span></span>  
  
2.  <span data-ttu-id="be7dc-112">CMD シェルで、プロキシ クラスおよびアプリケーション構成ファイルを配置するディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-112">In CMD Shell, go to the directory where you want to place the proxy class and application configuration file.</span></span>  
  
3.  <span data-ttu-id="be7dc-113">CMD シェルで次のように、ServiceModel メタデータ ユーティリティ ツール (SvcUtil.exe) WCF プロキシ クラスを作成して、公開済み WCF サービスのアプリケーション構成ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-113">In CMD Shell, run the ServiceModel Metadata Utility Tool (SvcUtil.exe) to create the WCF proxy class and application configuration file for the published WCF service as follows:</span></span>  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="be7dc-114">このコマンドラインは、アプリケーションの構成のプロキシ クラスと App.config の BizTalkServiceInstance.cs を生成します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-114">This command line generates BizTalkServiceInstance.cs for the proxy class and App.config for the application configuration.</span></span> <span data-ttu-id="be7dc-115">Svcutil.exe の詳細についてを参照してください「サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)」 [ http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696)します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-115">For more information about Svcutil.exe, see "Service Model Metadata Utility Tool (Svcutil.exe)" at [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696).</span></span>  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a><span data-ttu-id="be7dc-116">.NET アプリケーションをコンパイルするには、公開した WCF サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-116">To compile your .NET application that consumes the published WCF service</span></span>  
  
1. <span data-ttu-id="be7dc-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、SvcUtil.exe が作成した BizTalkServiceInstance および App.config ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, add the files that SvcUtil.exe creates, BizTalkServiceInstance and App.config, to your project.</span></span>  
  
2. <span data-ttu-id="be7dc-118">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロキシ コードをコンパイルするには、ソリューション エクスプ ローラー、System.ServiceModel.dll への参照を追加することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="be7dc-118">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, make sure to add a reference to the System.ServiceModel.dll to compile the proxy code.</span></span>  
  
3. <span data-ttu-id="be7dc-119">生成されたプロキシ コードを使用するコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-119">Create the code to use the generated proxy code.</span></span> <span data-ttu-id="be7dc-120">次のコードでは、生成されたプロキシを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-120">The following code shows how to use the generated proxy:</span></span>  
  
   ```  
   DeliveryNotification deliveryNotification= new DeliveryNotification();  
   deliveryNotification.TrackingNumber = "001";  
               Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
   service.Submit(deliveryNotification);  
   ```  
  
4. <span data-ttu-id="be7dc-121">公開した WCF サービスにメッセージを送信する .NET アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="be7dc-121">Run your .NET application to send messages to the published WCF service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be7dc-122">参照</span><span class="sxs-lookup"><span data-stu-id="be7dc-122">See Also</span></span>  
 [<span data-ttu-id="be7dc-123">WCF 受信アダプターで WCF サービスを公開する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="be7dc-123">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)