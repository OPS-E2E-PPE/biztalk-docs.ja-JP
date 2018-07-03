---
title: 公開する Web サービスの Web セットアップを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d894cba37b85c4f18fe2a05af33eb2f4e6e1981e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984387"
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a><span data-ttu-id="2c7f8-102">公開する Web サービスの Web セットアップを作成する方法</span><span class="sxs-lookup"><span data-stu-id="2c7f8-102">How to Create a Web Setup for Your Published Web Service</span></span>
<span data-ttu-id="2c7f8-103">インストール パッケージを作成すると、実稼働環境での Web サービスの設定が容易になります。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-103">You can create an installation package to facilitate setting up your Web service in a production environment.</span></span> <span data-ttu-id="2c7f8-104">この結果、.MSI ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-104">This produces an .MSI file.</span></span>  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a><span data-ttu-id="2c7f8-105">Visual Studio を使用して .MSI ファイルを作成するためにインストール パッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="2c7f8-105">To create an installation package to produce an .MSI file using Visual Studio</span></span>  
  
1. <span data-ttu-id="2c7f8-106">公開する ASP.NET Web サービス プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-106">Open your published ASP.NET Web service project.</span></span>  
  
2. <span data-ttu-id="2c7f8-107">ソリューション エクスプ ローラーでソリューション ノードを右クリックして**追加**、 をクリックし、**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-107">In Solution Explorer, right-click the solution node, click **Add**, and then click **New Project**.</span></span>  
  
3. <span data-ttu-id="2c7f8-108">**新しいプロジェクトの追加**] ダイアログ ボックスで、**プロジェクトの種類**領域で、展開**その他のプロジェクトの種類**、展開**セットアップ/配置プロジェクト**、し、[ **Visual Studio インストーラー**します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-108">In the **Add New Project** dialog box, in the **Project Types** area, expand **Other Project Types**, expand **Setup and Deployment Projects**, and then select **Visual Studio Installer**.</span></span> <span data-ttu-id="2c7f8-109">**テンプレート**領域で、 **Web セットアップ プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-109">In the **Templates** area, select **Web Setup Project**.</span></span>  
  
4. <span data-ttu-id="2c7f8-110">**名前**テキスト ボックス、Web セットアップ プロジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-110">In the **Name** text box, type a name for the Web Setup Project.</span></span> <span data-ttu-id="2c7f8-111">ASP.NET Web サービス プロジェクトと同じ名前を使用してとをサフィックスとして"_Setup"を追加および をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-111">You can use the same name as the ASP.NET Web Service project and add "_Setup" as a suffix and then click **OK**.</span></span>  
  
5. <span data-ttu-id="2c7f8-112">ソリューション エクスプ ローラーで新しく作成された Web セットアップ プロジェクト ノードを右クリックし をポイント**ビュー**、 をクリックし、**ファイル システム**します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-112">In Solution Explorer, right-click the newly created Web setup project node, and point to **View**, and then click **File System**.</span></span>  
  
6. <span data-ttu-id="2c7f8-113">**ファイル システム**ウィンドウを右クリックし、 **Web アプリケーション フォルダー**ノードとポイント対**追加**、 をクリックし、**プロジェクト出力**します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-113">In the **File System** window, right-click the **Web Application Folder** node and point to **Add**, then click **Project Output**.</span></span>  
  
7. <span data-ttu-id="2c7f8-114">**プロジェクト出力グループの追加**ダイアログ ボックスで、**プライマリ出力**と**コンテンツ ファイル**クリックしてから、ASP.NET Web サービス プロジェクトの **[ok]**.</span><span class="sxs-lookup"><span data-stu-id="2c7f8-114">In the **Add Project Output Group** dialog box, select **Primary Output** and **Content Files** from the ASP.NET Web Service project and then click **OK**.</span></span>  
  
8. <span data-ttu-id="2c7f8-115">ソリューション エクスプ ローラーで、**依存関係の検出**Web セットアップ プロジェクトの下のノード。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-115">In Solution Explorer, expand the **Detected Dependencies** node under the Web setup project.</span></span>  
  
9. <span data-ttu-id="2c7f8-116">すべての依存関係を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-116">Select all dependencies.</span></span> <span data-ttu-id="2c7f8-117">**プロパティ**ウィンドウで、設定、**除外**プロパティを**True**します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-117">In the **Properties** window, set the **Exclude** property to **True**.</span></span>  
  
10. <span data-ttu-id="2c7f8-118">Web セットアップ プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-118">Build your Web setup project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c7f8-119">Web セットアップ プロジェクトの作成に関する詳細については、「どのようにプロジェクトを作成または追加、Web セットアップ」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268)します。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-119">For more information about creating Web setup projects, see "How to Create or Add a Web Setup Project" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c7f8-120">参照</span><span class="sxs-lookup"><span data-stu-id="2c7f8-120">See Also</span></span>  
 [<span data-ttu-id="2c7f8-121">Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開</span><span class="sxs-lookup"><span data-stu-id="2c7f8-121">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)