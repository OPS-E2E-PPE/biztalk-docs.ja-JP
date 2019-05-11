---
title: 手順 7:LOBWebApplication SDK サンプルのビルドと |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bbe4c2bad357f479c337b8f889a4e4ed588dcf4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280633"
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a><span data-ttu-id="8a667-102">手順 7:LOBWebApplication SDK サンプルのビルドと</span><span class="sxs-lookup"><span data-stu-id="8a667-102">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>
<span data-ttu-id="8a667-103">この手順では、Fabrikam が Contoso にプロセス PIP (Partner Interface) 要求を送信に使用する基幹業務 (LOB) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a667-103">In this step, you create the line-of-business (LOB) application that Fabrikam uses to submit Partner Interface Process (PIP) requests to Contoso.</span></span> <span data-ttu-id="8a667-104">LOBWebApplication プロジェクトは、Microsoft® で見つかります[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK フォルダー。</span><span class="sxs-lookup"><span data-stu-id="8a667-104">You can find the LOBWebApplication project in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span> <span data-ttu-id="8a667-105">Web アプリケーションを実行するには、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリを作成し、LOBWebApplication プロジェクトを作成するがあります。</span><span class="sxs-lookup"><span data-stu-id="8a667-105">To run the Web application, you have to create a Microsoft Internet Information Services (IIS) virtual directory, and then build the LOBWebApplication project.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="8a667-106">LOBWebApplication 仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="8a667-106">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="8a667-107">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="8a667-107">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="8a667-108">インターネット インフォメーション サービス マネージャ ウィンドウで、 **< computer_name > (ローカル コンピューター)**、順に展開**Websites**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-108">In the Internet Information Services Manager window, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="8a667-109">右クリック**既定の Web サイト**、 をポイント**新規**、 をクリックし、**仮想ディレクトリ**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-109">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="8a667-110">**Welcometo 仮想ディレクトリの作成ウィザード**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-110">On the **Welcometo the Virtual Directory Creation Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="8a667-111">**仮想ディレクトリ エイリアス**] ページの [、**エイリアス**ボックスに「 **LOBWebApplication**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-111">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="8a667-112">**Web サイトのコンテンツ ディレクトリ**] ページで [**参照**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-112">On the **Web Site Content Directory** page, click **Browse**.</span></span> <span data-ttu-id="8a667-113">フォルダーの参照 ダイアログ ボックスに移動します \***\<ドライブ\>\*:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication**、し、。クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-113">In the Browse For Folder dialog box, move to \***\<drive\>\*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, and then click **OK**.</span></span> <span data-ttu-id="8a667-114">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a667-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="8a667-115">**仮想ディレクトリのアクセス許可** ページで、選択を解除**読み取り**を選択します **(ASP) などのスクリプトを実行する**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="8a667-115">On the **Virtual Directory Access Permissions** page, deselect **Read**, select **Run scripts (such as ASP)**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="8a667-116">**仮想ディレクトリの作成ウィザードを正常に完了しました**] ページで [**完了**仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a667-116">On the **You have successfully completed the Virtual Directory Creation Wizard** page, click **Finish** to create the virtual directory.</span></span>  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a><span data-ttu-id="8a667-117">SharePoint 構成から LOBWebApplication Web サイトを除外するには</span><span class="sxs-lookup"><span data-stu-id="8a667-117">To exclude the LOBWebApplication Web site from the SharePoint configuration</span></span>  
  
1.  <span data-ttu-id="8a667-118">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint Central Administration**。</span><span class="sxs-lookup"><span data-stu-id="8a667-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="8a667-119">**サーバーの全体管理**Web ページの**仮想サーバーの構成**セクションで、**アップグレード仮想サーバーの拡張または**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-119">On the **Central Administration** Web page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="8a667-120">コンピューターで構成されている URL が表示されない場合はクリックして**完全な一覧**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-120">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="8a667-121">**仮想サーバーのリスト**] ページで、[**既定の Web サイト**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-121">On the **Virtual Server List** page, select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="8a667-122">**仮想サーバーの管理**セクションで、**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-122">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="8a667-123">**新しいパスの追加**セクションで、**パス**ボックスに「 **/LOBWebApplication**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-123">In the **Add New Path** section, in the **Path** box, type **/LOBWebApplication**.</span></span>  
  
7.  <span data-ttu-id="8a667-124">**型**を選択します**エクスクルード パス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-124">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="8a667-125">LOBWebApplication プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="8a667-125">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="8a667-126">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Visual Studio 2008**、順にクリックします**Microsoft Visual Studio 2008**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-126">Click **Start**, point to **All Programs**, point to **Microsoft Visual Studio 2008**, and then click **Microsoft Visual Studio 2008**.</span></span>  
  
2.  <span data-ttu-id="8a667-127">**[ファイル]** メニューの **[開く]** をポイントし、 **[プロジェクト/ソリューション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a667-127">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="8a667-128">プロジェクトを開く ダイアログ ボックスに移動します。 \***\<ドライブ\>\*:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication**、、を選択します。**LOBWebApplication.sln**ソリューション ファイル、およびクリック**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-128">In the Open Project dialog box, move to \***\<drive\>\*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="8a667-129">ソリューション エクスプ ローラーで右クリックして**http://localhost/LOBWebApplication**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-129">In Solution Explorer, right-click **http://localhost/LOBWebApplication**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="8a667-130">[参照の追加] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-130">In the Add Reference dialog box, click **Browse**.</span></span> <span data-ttu-id="8a667-131">[参照の追加] ダイアログ ボックスに移動します。 \***\<ドライブ\>\*:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="8a667-131">In the Add Reference dialog box, move to \***\<drive\>\*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin** folder.</span></span>  
  
6.  <span data-ttu-id="8a667-132">Bin フォルダーから次のように選択します。、 **Microsoft.Solutions.BTARN.ConfigurationManager.dll**と**Microsoft.Solutions.BTARN.Shared.dll**アセンブリ、およびクリック**開く。**</span><span class="sxs-lookup"><span data-stu-id="8a667-132">From the Bin folder, select the **Microsoft.Solutions.BTARN.ConfigurationManager.dll** and **Microsoft.Solutions.BTARN.Shared.dll** assemblies, and then click **Open.**</span></span>  
  
7.  <span data-ttu-id="8a667-133">をクリックして**OK**を閉じる、**参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8a667-133">Click **OK** to close the **Add Reference** dialog box.</span></span>  
  
8.  <span data-ttu-id="8a667-134">ソリューション エクスプ ローラーで右クリック**ソリューション 'LOBWebApplication'** し**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-134">In Solution Explorer, right-click **Solution 'LOBWebApplication'** and then click **Build Solution**.</span></span>  
  
9. <span data-ttu-id="8a667-135">右クリックして**default.aspx**、 をクリックし、**スタート ページとして設定**します。</span><span class="sxs-lookup"><span data-stu-id="8a667-135">Right-click **default.aspx**, and then click **Set as Start Page**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a667-136">参照</span><span class="sxs-lookup"><span data-stu-id="8a667-136">See Also</span></span>  
 [<span data-ttu-id="8a667-137">ダブル アクション チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="8a667-137">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)