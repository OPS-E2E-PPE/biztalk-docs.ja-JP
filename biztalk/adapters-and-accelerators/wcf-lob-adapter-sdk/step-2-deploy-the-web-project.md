---
title: "手順 2: Web プロジェクトを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85cef88de4e8fa05bb50840002a0f344b1f0b350
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="step-2-deploy-the-web-project"></a><span data-ttu-id="a8b9c-102">手順 2: Web プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-102">Step 2: Deploy the Web Project</span></span>
<span data-ttu-id="a8b9c-103">![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="a8b9c-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="a8b9c-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="a8b9c-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="a8b9c-105">この手順で生成された Web プロジェクトをパブリッシュします[手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)インターネット インフォメーション サービス (IIS) にします。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-105">In this step you will publish the Web project generated in [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md) to Internet Information Services (IIS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8b9c-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="a8b9c-106">Prerequisites</span></span>  
 <span data-ttu-id="a8b9c-107">この手順を完了する必要がありますを行った[手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-107">To complete this step, you should have completed [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md).</span></span> <span data-ttu-id="a8b9c-108">Web サーバーは、HTTPS 通信を有効にインストールされている SSL 証明書も必要です。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-108">Your Web server must also have an SSL certificate installed to enable HTTPS communication.</span></span>  
  
## <a name="compile-and-deploy-the-web-project"></a><span data-ttu-id="a8b9c-109">コンパイルして、Web プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="a8b9c-109">Compile and deploy the Web project</span></span>  
  
1.  <span data-ttu-id="a8b9c-110">Visual Studio では、以前に作成された EchoWeb プロジェクトを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-110">In Visual Studio, load the EchoWeb project created previously.</span></span>  
  
2.  <span data-ttu-id="a8b9c-111">Visual Studio コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-111">Open a Visual Studio command prompt.</span></span>  
  
3.  <span data-ttu-id="a8b9c-112">C:\tutorials\echoweb フォルダーから、コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-112">At the command prompt, from the C:\tutorials\echoweb folder, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="a8b9c-113">**sn/k EchoWebKey.snk**</span><span class="sxs-lookup"><span data-stu-id="a8b9c-113">**sn /k EchoWebKey.snk**</span></span>  
  
     <span data-ttu-id="a8b9c-114">確認メッセージを**キー ペア EchoWebKey.snk に書き込まれる**、コマンド ラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-114">A confirmation message, **Key pair written to EchoWebKey.snk**, displays on the command line.</span></span>  
  
4.  <span data-ttu-id="a8b9c-115">コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-115">Close the command prompt.</span></span>  
  
5.  <span data-ttu-id="a8b9c-116">**ソリューション エクスプ ローラー**EchoWeb プロジェクトを右クリックし、、 **Web サイトの発行**です。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-116">In **Solution Explorer**, right click the EchoWeb project, and then select **Publish Web Site**.</span></span>  
  
6.  <span data-ttu-id="a8b9c-117">**Web サイトの発行** ダイアログ ボックスの**ターゲットの場所**、入力**http://machinename/EchoWeb**です。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-117">In the **Publish Web Site** dialog box, for **Target location**, enter **http://machinename/EchoWeb**.</span></span> <span data-ttu-id="a8b9c-118">選択**このプリコンパイル済みサイトを更新できるように**、**固定名およびシングル ページ アセンブリを使用する**、および**プリコンパイル済みアセンブリに厳密な名前を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-118">Select **Allow this precompiled site to be updatable**, **Use fixed naming and single page assemblies**, and **Enable strong naming on precompiled assemblies**.</span></span> <span data-ttu-id="a8b9c-119">**ファイルの場所をキー**フィールドで省略記号ボタンをクリックして**([...])**ボタンをクリックし、以前作成した EchoWebKey.snk ファイルを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-119">In the **Key file location** field, click the ellipsis **(…)** button, select the EchoWebKey.snk file created previously, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a8b9c-120">Web サイトが正しく作成されたことを確認するには、Internet Explorer を起動、入力**"http://localhost/EchoWeb/EchoOutboundContract.svc"**でアドレス バー、および、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-120">To verify that the Web site was correctly created, start Internet Explorer, enter  **"http://localhost/EchoWeb/EchoOutboundContract.svc"** in the address bar, and then press ENTER.</span></span> <span data-ttu-id="a8b9c-121">EchoOutboundContractClient を説明する Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-121">A Web page that describes the EchoOutboundContractClient should appear.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="a8b9c-122">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-122">What did I just do?</span></span>  
 <span data-ttu-id="a8b9c-123">IIS に Web プロジェクトをパブリッシュしただけです。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-123">You have just published your Web project to IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a8b9c-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="a8b9c-124">Next Steps</span></span>  
 <span data-ttu-id="a8b9c-125">進むことができますをコンパイルし、プロジェクトを展開した、[手順 3: アプリケーション定義ファイルの作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span><span class="sxs-lookup"><span data-stu-id="a8b9c-125">Now that you have compiled and deployed the project, you can proceed to [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b9c-126">参照</span><span class="sxs-lookup"><span data-stu-id="a8b9c-126">See Also</span></span>  
 [<span data-ttu-id="a8b9c-127">チュートリアル 3: IIS でエコー アダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="a8b9c-127">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)