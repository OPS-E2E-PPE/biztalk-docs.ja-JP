---
title: "手順 2: Fabrikam LOBWebApplication の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed64aac8ea0cf4073f3085f4491f607373d721b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a><span data-ttu-id="896af-102">手順 2: Fabrikam LOBWebApplication の作成</span><span class="sxs-lookup"><span data-stu-id="896af-102">Step 2: Creating the Fabrikam LOBWebApplication</span></span>
<span data-ttu-id="896af-103">ここでは、Fabrikam が 3A2 PIP 要求を Contoso に送信するために使用する LOB アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="896af-103">In this step, you create the LOB application that Fabrikam uses to submit a 3A2 PIP request to Contoso.</span></span> <span data-ttu-id="896af-104">LOBWebApplication プロジェクトは、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="896af-104">The LOBWebApplication project is installed in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="896af-105">Web アプリケーションを実行するためには、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] インターネット インフォメーション サービス (IIS) 仮想ディレクトリを作成し、LOBWebApplication プロジェクトをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="896af-105">To run the Web application, you have to create a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) virtual directory and build the LOBWebApplication project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="896af-106">ダブル アクション チュートリアルを完了済みであれば、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="896af-106">If you completed the DoubleAction tutorial, you do not need to perform this step.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="896af-107">LOBWebApplication 仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="896af-107">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="896af-108">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="896af-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services Manager**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="896af-109">ダブル アクション チュートリアルを完了済みであれば、このチュートリアルで LOBWebApplication 仮想ディレクトリを作成しています。</span><span class="sxs-lookup"><span data-stu-id="896af-109">If you have already done the Double Action tutorial, you will already have created the LOBWebApplication virtual directory for that tutorial.</span></span> <span data-ttu-id="896af-110">その場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="896af-110">If so, you do not have to perform these steps.</span></span> <span data-ttu-id="896af-111">仮想ディレクトリのアクセス許可を変更する必要が、ただし、**スクリプトを実行する**に**読み取り**です。</span><span class="sxs-lookup"><span data-stu-id="896af-111">You will, however, have to change the permissions for the virtual directory from **Run scripts** to **Read**.</span></span>  
  
2.  <span data-ttu-id="896af-112">インターネット インフォメーション サービス マネージャーで  **< computer_name > (ローカル コンピューター)**、順に展開**Websites**です。</span><span class="sxs-lookup"><span data-stu-id="896af-112">In Internet Information Services Manager, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="896af-113">右クリック**既定の Web サイト**、 をポイント**新規**、クリックして**仮想ディレクトリ**です。</span><span class="sxs-lookup"><span data-stu-id="896af-113">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="896af-114">**Welcometo 仮想ディレクトリの作成ウィザード ページ**、 をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="896af-114">On the **Welcometo the Virtual Directory Creation Wizard page**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="896af-115">**仮想ディレクトリ エイリアス**] ページの [、**エイリアス**ボックスに、入力**LOBWebApplication**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="896af-115">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="896af-116">**Web サイトのコンテンツのディレクトリ**] ページで [**参照**を選択、 **\<ドライブ >: \Program Files\Microsoft BizTalk\<バージョン > Accelerator forRosettanet \sdk\lobwebapplication**フォルダー、およびクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="896af-116">On the **Web Site Content Directory** page, click **Browse**, select the **\<drive>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\LOBWebApplication** folder, and then click **OK**.</span></span> <span data-ttu-id="896af-117">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="896af-117">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="896af-118">**仮想ディレクトリのアクセス許可**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="896af-118">On the **Virtual Directory Access Permissions** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="896af-119">をクリックして**完了**仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="896af-119">Click **Finish** to create the virtual directory.</span></span>  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a><span data-ttu-id="896af-120">SharePoint からの LOBWebApplication の除外</span><span class="sxs-lookup"><span data-stu-id="896af-120">Excluding LOBWebApplication from SharePoint</span></span>  
  
1.  <span data-ttu-id="896af-121">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="896af-121">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="896af-122">ダブル アクション チュートリアルを完了済みであれば、チュートリアルで LOBWebApplication 仮想ディレクトリを SharePoint から除外しています。</span><span class="sxs-lookup"><span data-stu-id="896af-122">If you have already done the Double Action tutorial, you will already have excluded the LOBWebApplication virtual directory from SharePoint for that tutorial.</span></span> <span data-ttu-id="896af-123">その場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="896af-123">If so, you do not have to perform these steps.</span></span>  
  
2.  <span data-ttu-id="896af-124">**サーバーの全体管理**] ページの [、**仮想サーバーの構成**セクションで、**拡張またはアップグレードの virtual server**です。</span><span class="sxs-lookup"><span data-stu-id="896af-124">On the **Central Administration** page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="896af-125">コンピューターで構成されている URL が表示されない場合にクリックして**完全な一覧**です。</span><span class="sxs-lookup"><span data-stu-id="896af-125">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="896af-126">選択**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="896af-126">Select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="896af-127">**仮想サーバーの管理**セクションで、**管理パスの定義**です。</span><span class="sxs-lookup"><span data-stu-id="896af-127">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="896af-128">**新しいパスの追加**セクションで、**パス**ボックスに、入力"/LOBWebApplication"。</span><span class="sxs-lookup"><span data-stu-id="896af-128">In the **Add New Path** section, in the **Path** box, type "/LOBWebApplication".</span></span> <span data-ttu-id="896af-129">**型**を選択**エクスクルード パス**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="896af-129">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="896af-130">LOBWebApplication プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="896af-130">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="896af-131">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="896af-131">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="896af-132">**ファイル** メニューのをポイント**開く**、クリックして**Project\Solution**です。</span><span class="sxs-lookup"><span data-stu-id="896af-132">From the **File** menu, point to **Open**, and then click **Project\Solution**.</span></span>  
  
3.  <span data-ttu-id="896af-133">プロジェクトを開く ダイアログ ボックスで**検索対象の**に移動**\<ドライブ >: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for RosettaNet\ SDK\LOBWebApplication**、選択、 **LOBWebApplication.sln**ソリューション、およびクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="896af-133">In the Open Project dialog box, in **Look In**, move to **\<drive>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\ SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="896af-134">ソリューション エクスプ ローラーで、最上位ノード (http://localhost/LOBWebApplication) を右クリックし、をクリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="896af-134">In Solution Explorer, right-click the top node (http://localhost/LOBWebApplication), and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="896af-135">[参照の追加] ダイアログ ボックスで、**参照**に移動する**\<ドライブ >: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \bin**です。</span><span class="sxs-lookup"><span data-stu-id="896af-135">In the Add Reference dialog box, click **Browse** and move to **\<drive>:\Program Files\Microsoft  BizTalk \<version> Accelerator for RosettaNet\bin**.</span></span>  
  
6.  <span data-ttu-id="896af-136">**選択、Microsoft.Solutions.BTARN.ConfigurationManager.dll および Microsoft.Solutions.BTARN.Shared.dll**アセンブリ**し、[OK] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="896af-136">**Select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll** assemblies **and then click OK.**</span></span>  
  
7.  <span data-ttu-id="896af-137">**ビルド** メニューのをクリックして**Web サイトのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="896af-137">On the **Build** menu, click **Build Web Site**.</span></span>  
  
### <a name="to-run-the-lobwebapplication-project"></a><span data-ttu-id="896af-138">LOBWebApplication プロジェクトを実行するには</span><span class="sxs-lookup"><span data-stu-id="896af-138">To run the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="896af-139">ソリューション エクスプ ローラーで右クリック**default.aspx**、し、**スタート ページとして設定**です。</span><span class="sxs-lookup"><span data-stu-id="896af-139">In Solution Explorer, right-click **default.aspx**, and then select **Set As Start Page**.</span></span>  
  
2.  <span data-ttu-id="896af-140">**デバッグ** メニューのをクリックして**デバッグなしで開始**です。</span><span class="sxs-lookup"><span data-stu-id="896af-140">On the **Debug** menu, click **Start Without Debugging**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896af-141">参照</span><span class="sxs-lookup"><span data-stu-id="896af-141">See Also</span></span>  
 [<span data-ttu-id="896af-142">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="896af-142">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)