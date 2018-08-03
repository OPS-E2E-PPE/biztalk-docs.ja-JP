---
title: '手順 2: Web プロジェクトをデプロイする |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a99defc18cd38dc6f88a16b8c3fd0db2a8168426
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013123"
---
# <a name="step-2-deploy-the-web-project"></a><span data-ttu-id="7caa1-102">手順 2: Web プロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="7caa1-102">Step 2: Deploy the Web Project</span></span>
<span data-ttu-id="7caa1-103">![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="7caa1-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="7caa1-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="7caa1-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="7caa1-105">この手順で生成された Web プロジェクトをパブリッシュします[手順 1: アダプター サービス開発ウィザードを使用して Web プロジェクトを作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)インターネット インフォメーション サービス (IIS) にします。</span><span class="sxs-lookup"><span data-stu-id="7caa1-105">In this step you will publish the Web project generated in [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md) to Internet Information Services (IIS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7caa1-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="7caa1-106">Prerequisites</span></span>  
 <span data-ttu-id="7caa1-107">作成したこの手順を完了する[手順 1: アダプター サービス開発ウィザードを使用して、Web プロジェクトを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="7caa1-107">To complete this step, you should have completed [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md).</span></span> <span data-ttu-id="7caa1-108">Web サーバーは、HTTPS 通信を有効にインストールされている SSL 証明書も必要です。</span><span class="sxs-lookup"><span data-stu-id="7caa1-108">Your Web server must also have an SSL certificate installed to enable HTTPS communication.</span></span>  
  
## <a name="compile-and-deploy-the-web-project"></a><span data-ttu-id="7caa1-109">コンパイルして、Web プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="7caa1-109">Compile and deploy the Web project</span></span>  
  
1. <span data-ttu-id="7caa1-110">Visual Studio では、以前に作成 EchoWeb プロジェクトを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="7caa1-110">In Visual Studio, load the EchoWeb project created previously.</span></span>  
  
2. <span data-ttu-id="7caa1-111">Visual Studio コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7caa1-111">Open a Visual Studio command prompt.</span></span>  
  
3. <span data-ttu-id="7caa1-112">C:\tutorials\echoweb フォルダーから、コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7caa1-112">At the command prompt, from the C:\tutorials\echoweb folder, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="7caa1-113">**sn/k EchoWebKey.snk**</span><span class="sxs-lookup"><span data-stu-id="7caa1-113">**sn /k EchoWebKey.snk**</span></span>  
  
    <span data-ttu-id="7caa1-114">確認のメッセージでは、**キーのペア EchoWebKey.snk に書き込まれる**コマンドラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="7caa1-114">A confirmation message, **Key pair written to EchoWebKey.snk**, displays on the command line.</span></span>  
  
4. <span data-ttu-id="7caa1-115">コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7caa1-115">Close the command prompt.</span></span>  
  
5. <span data-ttu-id="7caa1-116">**ソリューション エクスプ ローラー**EchoWeb プロジェクトを右クリックして選択し、 **Web サイトの発行**します。</span><span class="sxs-lookup"><span data-stu-id="7caa1-116">In **Solution Explorer**, right click the EchoWeb project, and then select **Publish Web Site**.</span></span>  
  
6. <span data-ttu-id="7caa1-117">**Web サイトの発行** ダイアログ ボックスの**ターゲットの場所**、入力 **http://machinename/EchoWeb**します。</span><span class="sxs-lookup"><span data-stu-id="7caa1-117">In the **Publish Web Site** dialog box, for **Target location**, enter **http://machinename/EchoWeb**.</span></span> <span data-ttu-id="7caa1-118">選択**このプリコンパイル済みサイトを更新可能**、**固定名およびシングル ページ アセンブリを使用する**、および**プリコンパイル済みアセンブリで厳密な名前を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="7caa1-118">Select **Allow this precompiled site to be updatable**, **Use fixed naming and single page assemblies**, and **Enable strong naming on precompiled assemblies**.</span></span> <span data-ttu-id="7caa1-119">**ファイルの場所をキー**フィールドで省略記号をクリックします **([...])。** ボタンをクリックし、以前は、作成 EchoWebKey.snk ファイルを選択し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7caa1-119">In the **Key file location** field, click the ellipsis **(…)** button, select the EchoWebKey.snk file created previously, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="7caa1-120">Web サイトが正しく作成されたことを確認するには、Internet Explorer を起動、入力 **"<http://localhost/EchoWeb/EchoOutboundContract.svc>"** でアドレス バー、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7caa1-120">To verify that the Web site was correctly created, start Internet Explorer, enter  **"<http://localhost/EchoWeb/EchoOutboundContract.svc>"** in the address bar, and then press ENTER.</span></span> <span data-ttu-id="7caa1-121">EchoOutboundContractClient を説明する Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7caa1-121">A Web page that describes the EchoOutboundContractClient should appear.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="7caa1-122">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="7caa1-122">What did I just do?</span></span>  
 <span data-ttu-id="7caa1-123">IIS に Web プロジェクトを発行するだけです。</span><span class="sxs-lookup"><span data-stu-id="7caa1-123">You have just published your Web project to IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7caa1-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="7caa1-124">Next Steps</span></span>  
 <span data-ttu-id="7caa1-125">これでコンパイルされ、プロジェクトのデプロイに進んで[手順 3: アプリケーション定義ファイルの作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span><span class="sxs-lookup"><span data-stu-id="7caa1-125">Now that you have compiled and deployed the project, you can proceed to [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7caa1-126">参照</span><span class="sxs-lookup"><span data-stu-id="7caa1-126">See Also</span></span>  
 [<span data-ttu-id="7caa1-127">チュートリアル 3: IIS でエコー アダプターをホストする</span><span class="sxs-lookup"><span data-stu-id="7caa1-127">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)