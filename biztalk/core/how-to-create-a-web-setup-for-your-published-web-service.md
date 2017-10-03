---
title: "公開された Web サービスの Web 設定を作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87c5ec4fe61c8649fe951460917cfde8788f2e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a><span data-ttu-id="05ef0-102">公開する Web サービスの Web セットアップを作成する方法</span><span class="sxs-lookup"><span data-stu-id="05ef0-102">How to Create a Web Setup for Your Published Web Service</span></span>
<span data-ttu-id="05ef0-103">インストール パッケージを作成すると、実稼働環境での Web サービスの設定が容易になります。</span><span class="sxs-lookup"><span data-stu-id="05ef0-103">You can create an installation package to facilitate setting up your Web service in a production environment.</span></span> <span data-ttu-id="05ef0-104">この結果、.MSI ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="05ef0-104">This produces an .MSI file.</span></span>  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a><span data-ttu-id="05ef0-105">Visual Studio を使用して .MSI ファイルを作成するためにインストール パッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="05ef0-105">To create an installation package to produce an .MSI file using Visual Studio</span></span>  
  
1.  <span data-ttu-id="05ef0-106">公開する ASP.NET Web サービス プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="05ef0-106">Open your published ASP.NET Web service project.</span></span>  
  
2.  <span data-ttu-id="05ef0-107">ソリューション エクスプ ローラーでソリューション ノードを右クリックし、をクリックして**追加**、クリックして**新しいプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-107">In Solution Explorer, right-click the solution node, click **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="05ef0-108">**新しいプロジェクトの追加**] ダイアログ ボックスで、**プロジェクトの種類**領域で、展開**その他のプロジェクトの種類**、展開**セットアップ/配置プロジェクト**、し、[ **Visual Studio インストーラー**です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-108">In the **Add New Project** dialog box, in the **Project Types** area, expand **Other Project Types**, expand **Setup and Deployment Projects**, and then select **Visual Studio Installer**.</span></span> <span data-ttu-id="05ef0-109">**テンプレート**領域で、 **Web セットアップ プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-109">In the **Templates** area, select **Web Setup Project**.</span></span>  
  
4.  <span data-ttu-id="05ef0-110">**名前**テキスト ボックス、Web セットアップ プロジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="05ef0-110">In the **Name** text box, type a name for the Web Setup Project.</span></span> <span data-ttu-id="05ef0-111">ASP.NET Web サービス プロジェクトと同じ名前を使用してとをサフィックスとして"_Setup"を追加してをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-111">You can use the same name as the ASP.NET Web Service project and add "_Setup" as a suffix and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="05ef0-112">ソリューション エクスプ ローラーで、新しく作成された Web セットアップ プロジェクト ノードを右クリックし、順にポイント**ビュー**、クリックして**ファイル システム**です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-112">In Solution Explorer, right-click the newly created Web setup project node, and point to **View**, and then click **File System**.</span></span>  
  
6.  <span data-ttu-id="05ef0-113">**ファイル システム**ウィンドウを右クリックし、 **Web アプリケーション フォルダー**ノードをポイントして**追加**をクリックし、**プロジェクト出力**です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-113">In the **File System** window, right-click the **Web Application Folder** node and point to **Add**, then click **Project Output**.</span></span>  
  
7.  <span data-ttu-id="05ef0-114">**プロジェクト出力グループの追加**ダイアログ ボックスで、**プライマリ出力**と**コンテンツ ファイル**プロジェクトから ASP.NET Web サービスと、をクリックして**OK**.</span><span class="sxs-lookup"><span data-stu-id="05ef0-114">In the **Add Project Output Group** dialog box, select **Primary Output** and **Content Files** from the ASP.NET Web Service project and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="05ef0-115">ソリューション エクスプ ローラーで、展開、**依存関係の検出**Web セットアップ プロジェクトの下にあるノード。</span><span class="sxs-lookup"><span data-stu-id="05ef0-115">In Solution Explorer, expand the **Detected Dependencies** node under the Web setup project.</span></span>  
  
9. <span data-ttu-id="05ef0-116">すべての依存関係を選択します。</span><span class="sxs-lookup"><span data-stu-id="05ef0-116">Select all dependencies.</span></span> <span data-ttu-id="05ef0-117">**プロパティ**ウィンドウで、設定、**除外**プロパティを**True**です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-117">In the **Properties** window, set the **Exclude** property to **True**.</span></span>  
  
10. <span data-ttu-id="05ef0-118">Web セットアップ プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="05ef0-118">Build your Web setup project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05ef0-119">Web セットアップ プロジェクトの作成の詳細についてを参照してください「方法を作成または追加 Web セットアップ プロジェクト」、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268)です。</span><span class="sxs-lookup"><span data-stu-id="05ef0-119">For more information about creating Web setup projects, see "How to Create or Add a Web Setup Project" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ef0-120">参照</span><span class="sxs-lookup"><span data-stu-id="05ef0-120">See Also</span></span>  
 [<span data-ttu-id="05ef0-121">非 Visual Studio コンピューターに公開された Web サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="05ef0-121">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)