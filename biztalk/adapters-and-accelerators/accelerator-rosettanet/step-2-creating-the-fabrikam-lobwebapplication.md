---
title: '手順 2: Fabrikam LOBWebApplication の作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c55234d8ee9c123c9efe9e7ec66b7c0db590b54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966627"
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a><span data-ttu-id="4b649-102">手順 2: Fabrikam LOBWebApplication の作成</span><span class="sxs-lookup"><span data-stu-id="4b649-102">Step 2: Creating the Fabrikam LOBWebApplication</span></span>
<span data-ttu-id="4b649-103">ここでは、Fabrikam が 3A2 PIP 要求を Contoso に送信するために使用する LOB アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b649-103">In this step, you create the LOB application that Fabrikam uses to submit a 3A2 PIP request to Contoso.</span></span> <span data-ttu-id="4b649-104">LOBWebApplication プロジェクトは、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="4b649-104">The LOBWebApplication project is installed in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="4b649-105">Web アプリケーションを実行するには、Microsoft インターネット インフォメーション サービス (IIS) 仮想ディレクトリを作成し、LOBWebApplication プロジェクトをビルドがあります。</span><span class="sxs-lookup"><span data-stu-id="4b649-105">To run the Web application, you have to create a Microsoft Internet Information Services (IIS) virtual directory and build the LOBWebApplication project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b649-106">ダブル アクション チュートリアルを完了済みであれば、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4b649-106">If you completed the DoubleAction tutorial, you do not need to perform this step.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="4b649-107">LOBWebApplication 仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="4b649-107">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="4b649-108">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services Manager**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b649-109">ダブル アクション チュートリアルを完了済みであれば、このチュートリアルで LOBWebApplication 仮想ディレクトリを作成しています。</span><span class="sxs-lookup"><span data-stu-id="4b649-109">If you have already done the Double Action tutorial, you will already have created the LOBWebApplication virtual directory for that tutorial.</span></span> <span data-ttu-id="4b649-110">その場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4b649-110">If so, you do not have to perform these steps.</span></span> <span data-ttu-id="4b649-111">仮想ディレクトリからのアクセス許可を変更する必要が、ただし、**スクリプトを実行する**に**読み取り**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-111">You will, however, have to change the permissions for the virtual directory from **Run scripts** to **Read**.</span></span>  
  
2.  <span data-ttu-id="4b649-112">インターネット インフォメーション サービス マネージャーで  **< computer_name > (ローカル コンピューター)**、順に展開**Websites**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-112">In Internet Information Services Manager, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="4b649-113">右クリック**既定の Web サイト**、 をポイント**新規**、 をクリックし、**仮想ディレクトリ**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-113">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="4b649-114">**Welcometo 仮想ディレクトリの作成ウィザードのページ**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-114">On the **Welcometo the Virtual Directory Creation Wizard page**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="4b649-115">**仮想ディレクトリ エイリアス**] ページの [、**エイリアス**ボックスに「 **LOBWebApplication**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-115">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="4b649-116">**Web サイトのコンテンツ ディレクトリ**] ページで [**参照**を選択、 **\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication**フォルダー、およびクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-116">On the **Web Site Content Directory** page, click **Browse**, select the **\<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication** folder, and then click **OK**.</span></span> <span data-ttu-id="4b649-117">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b649-117">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="4b649-118">**仮想ディレクトリのアクセス許可**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-118">On the **Virtual Directory Access Permissions** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="4b649-119">クリックして**完了**仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b649-119">Click **Finish** to create the virtual directory.</span></span>  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a><span data-ttu-id="4b649-120">SharePoint からの LOBWebApplication の除外</span><span class="sxs-lookup"><span data-stu-id="4b649-120">Excluding LOBWebApplication from SharePoint</span></span>  
  
1.  <span data-ttu-id="4b649-121">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint Central Administration**。</span><span class="sxs-lookup"><span data-stu-id="4b649-121">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b649-122">ダブル アクション チュートリアルを完了済みであれば、チュートリアルで LOBWebApplication 仮想ディレクトリを SharePoint から除外しています。</span><span class="sxs-lookup"><span data-stu-id="4b649-122">If you have already done the Double Action tutorial, you will already have excluded the LOBWebApplication virtual directory from SharePoint for that tutorial.</span></span> <span data-ttu-id="4b649-123">その場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4b649-123">If so, you do not have to perform these steps.</span></span>  
  
2.  <span data-ttu-id="4b649-124">**サーバーの全体管理**] ページの [、**仮想サーバーの構成**セクションで、**アップグレード仮想サーバーの拡張または**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-124">On the **Central Administration** page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="4b649-125">コンピューターで構成されている URL が表示されない場合はクリックして**完全な一覧**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-125">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="4b649-126">選択**Default Web Site**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-126">Select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="4b649-127">**仮想サーバーの管理**セクションで、**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-127">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="4b649-128">**新しいパスの追加**セクションで、**パス**ボックスに「"/LOBWebApplication".</span><span class="sxs-lookup"><span data-stu-id="4b649-128">In the **Add New Path** section, in the **Path** box, type "/LOBWebApplication".</span></span> <span data-ttu-id="4b649-129">**型**を選択します**エクスクルード パス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-129">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="4b649-130">LOBWebApplication プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="4b649-130">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="4b649-131">開始**Microsoft Visual Studio 2012**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-131">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="4b649-132">**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト \ ソリューション**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-132">From the **File** menu, point to **Open**, and then click **Project\Solution**.</span></span>  
  
3.  <span data-ttu-id="4b649-133">プロジェクトを開く ダイアログ ボックスで**検索対象の**に移動**\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>して sdk \ のアクセラレータLOBWebApplication**を選択、 **LOBWebApplication.sln**ソリューション、およびクリック**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-133">In the Open Project dialog box, in **Look In**, move to **\<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\ SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="4b649-134">ソリューション エクスプ ローラーで最上位ノードを右クリックし (http://localhost/LOBWebApplication)、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-134">In Solution Explorer, right-click the top node (http://localhost/LOBWebApplication), and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="4b649-135">[参照の追加] ダイアログ ボックスで、**参照**に移動し、 **\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin**.</span><span class="sxs-lookup"><span data-stu-id="4b649-135">In the Add Reference dialog box, click **Browse** and move to **\<drive\>:\Program Files\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\bin**.</span></span>  
  
6.  <span data-ttu-id="4b649-136">**選択 Microsoft.Solutions.BTARN.ConfigurationManager.dll および Microsoft.Solutions.BTARN.Shared.dll**アセンブリ**し、[ok] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="4b649-136">**Select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll** assemblies **and then click OK.**</span></span>  
  
7.  <span data-ttu-id="4b649-137">**ビルド** メニューのをクリックして**Web サイトのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-137">On the **Build** menu, click **Build Web Site**.</span></span>  
  
### <a name="to-run-the-lobwebapplication-project"></a><span data-ttu-id="4b649-138">LOBWebApplication プロジェクトを実行するには</span><span class="sxs-lookup"><span data-stu-id="4b649-138">To run the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="4b649-139">ソリューション エクスプ ローラーで右クリックして**default.aspx**、し、**スタート ページとして設定**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-139">In Solution Explorer, right-click **default.aspx**, and then select **Set As Start Page**.</span></span>  
  
2.  <span data-ttu-id="4b649-140">**デバッグ** メニューのをクリックして**デバッグなしで開始**します。</span><span class="sxs-lookup"><span data-stu-id="4b649-140">On the **Debug** menu, click **Start Without Debugging**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b649-141">参照</span><span class="sxs-lookup"><span data-stu-id="4b649-141">See Also</span></span>  
 [<span data-ttu-id="4b649-142">ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="4b649-142">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)