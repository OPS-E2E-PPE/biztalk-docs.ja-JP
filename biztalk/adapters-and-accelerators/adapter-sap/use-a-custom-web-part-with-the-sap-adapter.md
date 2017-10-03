---
title: "SAP アダプタでカスタム Web パーツを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b7fecd2-a385-4b2d-a01b-3bfd65ecff3a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5712376abaa24d998f13612a3b74e11f2487e514
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-a-custom-web-part-with-the-sap-adapter"></a><span data-ttu-id="45c74-102">SAP アダプターでカスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="45c74-102">Use a Custom Web Part with the SAP adapter</span></span>
<span data-ttu-id="45c74-103">このセクションでは、Microsoft Office SharePoint Server でカスタム Web パーツの使用に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="45c74-103">This section provides information about using a custom Web Part with Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="45c74-104">カスタム Web パーツを使用するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="45c74-104">To use a custom Web Part, you must do the following:</span></span>  
  
1.  <span data-ttu-id="45c74-105">カスタム Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="45c74-105">Create a custom Web Part</span></span>  
  
2.  <span data-ttu-id="45c74-106">SharePoint ポータルにカスタム Web パーツを展開します。</span><span class="sxs-lookup"><span data-stu-id="45c74-106">Deploy the custom Web Part to a SharePoint portal</span></span>  
  
3.  <span data-ttu-id="45c74-107">カスタム Web パーツを使用する SharePoint ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="45c74-107">Configure the SharePoint portal to use the custom Web Part</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="45c74-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="45c74-108">Before You Begin</span></span>  
 <span data-ttu-id="45c74-109">カスタム Web パーツを作成する前に。</span><span class="sxs-lookup"><span data-stu-id="45c74-109">Before you create a custom Web Part:</span></span>  
  
-   <span data-ttu-id="45c74-110">WCF サービスとして SAP アイテムをパブリッシュします。</span><span class="sxs-lookup"><span data-stu-id="45c74-110">Publish the SAP artifacts as a  WCF service.</span></span> <span data-ttu-id="45c74-111">詳細については、次を参照してください。[手順 1: WCF サービスとして SAP アイテムをパブリッシュ](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)で[チュートリアル 1: SharePoint サイト上の SAP システムからデータを表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)です。</span><span class="sxs-lookup"><span data-stu-id="45c74-111">For more information, see [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
-   <span data-ttu-id="45c74-112">Microsoft Office SharePoint Server でビジネス データ カタログを使用して SAP アイテム用のアプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="45c74-112">Create an application definition file for the SAP artifacts using the Business Data Catalog in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="45c74-113">詳細については、次を参照してください。[手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)で[チュートリアル 1: SharePoint サイト上の SAP システムからデータを表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)です。</span><span class="sxs-lookup"><span data-stu-id="45c74-113">For more information, see [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
##  <span data-ttu-id="45c74-114"><a name="Create_a_Custom_Web_Part"></a>手順 1: がカスタム Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="45c74-114"><a name="Create_a_Custom_Web_Part"></a> Step 1: Create a custom Web Part</span></span>  
 <span data-ttu-id="45c74-115">Visual Studio を使用してカスタム Web パーツを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="45c74-115">To create a custom Web Part using Visual Studio, do the following:</span></span>  
  
1.  <span data-ttu-id="45c74-116">Visual Studio を起動し、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="45c74-116">Start Visual Studio, and then create a project.</span></span>  
  
2.  <span data-ttu-id="45c74-117">**新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#**です。</span><span class="sxs-lookup"><span data-stu-id="45c74-117">In the **New Project** dialog box, from the **Project types** pane, select **Visual C#**.</span></span> <span data-ttu-id="45c74-118">**テンプレート**ペインで、**クラス ライブラリ**です。</span><span class="sxs-lookup"><span data-stu-id="45c74-118">From the **Templates** pane, select **Class Library**.</span></span>  
  
3.  <span data-ttu-id="45c74-119">ソリューションの場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="45c74-119">Specify a name and location for the solution.</span></span> <span data-ttu-id="45c74-120">このトピックでは、指定`CustomWebPart`で、**名前**と**ソリューション名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="45c74-120">For this topic, specify `CustomWebPart` in the **Name** and **Solution Name** boxes.</span></span> <span data-ttu-id="45c74-121">場所を指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="45c74-121">Specify a location, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="45c74-122">System.Web コンポーネントへの参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="45c74-122">Add a reference to the System.Web component into the project.</span></span> <span data-ttu-id="45c74-123">プロジェクト名を右クリックして**ソリューション エクスプ ローラー**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="45c74-123">Right-click the project name in **Solution Explorer**, and then click **Add Reference**.</span></span> <span data-ttu-id="45c74-124">**参照の追加**ダイアログ ボックスで、 **System.Web**で、 **.NET**  タブをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="45c74-124">In the **Add Reference** dialog box, select **System.Web** in the **.NET** tab, and then click **OK**.</span></span> <span data-ttu-id="45c74-125">System.Web コンポーネントには、System.Web.UI.WebControls.WebParts の必要な名前空間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45c74-125">The System.Web component contains the required namespace of System.Web.UI.WebControls.WebParts.</span></span>  
  
5.  <span data-ttu-id="45c74-126">プロジェクトで、問題に基づく、必要なコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="45c74-126">Add the required code based on your issue in the project.</span></span> <span data-ttu-id="45c74-127">特定の問題に関連するコード サンプルを参照してください「の問題に関連する追加の Web パーツ」 [SharePoint での SAP アダプターの使用時の考慮事項](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md)です。</span><span class="sxs-lookup"><span data-stu-id="45c74-127">For the code sample that is relevant to a certain issue, see “Issues Involving Custom Web Parts” in [Considerations when using the SAP adapter with SharePoint](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md).</span></span>  
  
6.  <span data-ttu-id="45c74-128">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="45c74-128">Build the project.</span></span> <span data-ttu-id="45c74-129">プロジェクトの成功したビルドで CustomWebPart.dll、.dll ファイルが生成されます、\<プロジェクト フォルダー > bin/デバッグ フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="45c74-129">On successful build of the project, a .dll file, CustomWebPart.dll, will be generated in the \<project folder>/bin/Debug folder.</span></span>  
  
7.  <span data-ttu-id="45c74-130">**64 ビット コンピューターに対してのみ**: 次の手順を実行する前に厳密な名前で CustomWebPart.dll ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="45c74-130">**Only for 64-bit computer**: Sign the CustomWebPart.dll file with a strong name before performing the following steps.</span></span> <span data-ttu-id="45c74-131">それ以外の場合、することはできません、インポート、CustomWebPart.dll では、SharePoint サイトで使用する"手順 3: カスタムの Web パーツを使用する SharePoint ポータルを構成します"。</span><span class="sxs-lookup"><span data-stu-id="45c74-131">Otherwise, you will not be able to import, and hence use the CustomWebPart.dll in the SharePoint portal in “Step 3: Configure the SharePoint Portal to use the custom Web Part.”</span></span> <span data-ttu-id="45c74-132">参照してください[する方法: 厳密な名前でアセンブリに署名](https://msdn.microsoft.com/library/xc31ft41.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="45c74-132">See [How to: Sign an Assembly with a Strong Name](https://msdn.microsoft.com/library/xc31ft41.aspx).</span></span>
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a><span data-ttu-id="45c74-133">手順 2: カスタム Web パーツを SharePoint ポータルを展開します。</span><span class="sxs-lookup"><span data-stu-id="45c74-133">Step 2: Deploy the custom Web Part to a SharePoint Portal</span></span>  
 <span data-ttu-id="45c74-134">CustomWebPart.dll ファイル (カスタム Web パーツ) で作成されるようにする、次を実行する必要があります"手順 1: カスタム Web パーツを作成する"このトピックは SharePoint ポータル上で使用。</span><span class="sxs-lookup"><span data-stu-id="45c74-134">You must do the following to make the CustomWebPart.dll file (custom Web Part) that is created in “Step 1: Create a custom Web Part” of this topic usable on the SharePoint portal:</span></span>  
  
-   <span data-ttu-id="45c74-135">**CustomWebPart.dll ファイルを SharePoint Portal の bin フォルダーにコピー**: Microsoft Office SharePoint Server は、ポータルを作成、\<ルート ドライブ >: \Inetpub\wwwroot\wss\VirtualDirectories フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="45c74-135">**Copy the CustomWebPart.dll file to the bin folder of the SharePoint Portal**: Microsoft Office SharePoint Server creates portals under the \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories folder.</span></span> <span data-ttu-id="45c74-136">フォルダーは、各ポータルが作成され、ポート番号で識別できます。</span><span class="sxs-lookup"><span data-stu-id="45c74-136">A folder is created for each portal, and can be identified with the port number.</span></span> <span data-ttu-id="45c74-137">作成した CustomWebPart.dll ファイルをコピーする必要があります"手順 1: カスタム Web パーツを作成する"に、このトピックの\<ルート ドライブ >: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number > \bin フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="45c74-137">You must copy the CustomWebPart.dll file created in “Step 1: Create a custom Web Part” of this topic to the \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number>\bin folder.</span></span> <span data-ttu-id="45c74-138">たとえば、SharePoint portal のポート番号が 13614 の場合に CustomWebPart.dll ファイルをコピーする必要があります、\<ドライブのルート >: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="45c74-138">For example, if the port number of your SharePoint portal is 13614, you must copy the CustomWebPart.dll file to the \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories\13614\bin folder.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="45c74-139">使用して、SharePoint portal のフォルダーの場所を検索する別の方法は、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ (**開始** > **実行** >  **inetmgr**)。</span><span class="sxs-lookup"><span data-stu-id="45c74-139">Another way to find the folder location of your SharePoint portal is by using the **Internet Information Services (IIS) Manager** window (**Start** > **Run** > **inetmgr**).</span></span> <span data-ttu-id="45c74-140">検索で、SharePoint portal、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ ([コンピューター名] > の Web サイト > [ポータル名])、右クリックし、クリック**プロパティ**で、ショートカット メニューです。</span><span class="sxs-lookup"><span data-stu-id="45c74-140">Locate your SharePoint portal in the **Internet Information Services (IIS) Manager** window ([computer_name] > Web Sites > [Portal-Name]), right-click, and then click **Properties** in the shortcut menu.</span></span> <span data-ttu-id="45c74-141">SharePoint portal の [プロパティ] ダイアログ ボックスをクリックして、**ホーム ディレクトリ**、タブをクリックし、**ローカル パス**ボックス。</span><span class="sxs-lookup"><span data-stu-id="45c74-141">In the properties dialog box of the SharePoint portal, click the **Home Directory** tab, and then select the **Local path** box.</span></span>  
  
-   <span data-ttu-id="45c74-142">**Web.config ファイルに安全なコントロール エントリを追加**: CustomWebPart.dll ファイルを使用する別のコンピューターに、複数のユーザーが、ために、ファイルを"safe"としてを宣言する必要があります</span><span class="sxs-lookup"><span data-stu-id="45c74-142">**Add the Safe Control Entry in the web.config File**: Because the CustomWebPart.dll file will be used on different computers and by multiple users, you must declare the file as “safe.”</span></span> <span data-ttu-id="45c74-143">SharePoint portal フォルダーにある web.config ファイルを開くためには、\<ルート ドライブ >: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number >。</span><span class="sxs-lookup"><span data-stu-id="45c74-143">To do so, open the web.config file located in the SharePoint portal folder at \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number>.</span></span> <span data-ttu-id="45c74-144">下にある、`<SafeControls>`セクションで、web.config ファイルの次の安全なコントロール エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="45c74-144">Under the `<SafeControls>` section of the web.config file, add the following safe control entry:</span></span>  
  
    -   <span data-ttu-id="45c74-145">**32 ビット コンピューターで。**</span><span class="sxs-lookup"><span data-stu-id="45c74-145">**On 32-bit computer:**</span></span>  
  
        ```  
        <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
    -   <span data-ttu-id="45c74-146">**64 ビット コンピューターで。**</span><span class="sxs-lookup"><span data-stu-id="45c74-146">**On 64-bit computer:**</span></span>  
  
        ```  
        <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
     <span data-ttu-id="45c74-147">Web.config ファイルを保存し、閉じます。</span><span class="sxs-lookup"><span data-stu-id="45c74-147">Save the web.config file, and then close it.</span></span>  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a><span data-ttu-id="45c74-148">手順 3: カスタムの Web パーツを使用する SharePoint ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="45c74-148">Step 3: Configure the SharePoint portal to use the custom Web Part</span></span>  
 <span data-ttu-id="45c74-149">SharePoint ポータルで使用できるようにする、Microsoft Office SharePoint Server Web パーツ ギャラリー、カスタムの Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45c74-149">You need to add the custom Web Part to the Microsoft Office SharePoint Server Web Part Gallery, so that you can use it on your SharePoint portal.</span></span> <span data-ttu-id="45c74-150">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="45c74-150">To do so:</span></span>  
  
1.  <span data-ttu-id="45c74-151">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="45c74-151">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="45c74-152">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="45c74-152">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="45c74-153">左側のナビゲーション ウィンドウでの共有サービス プロバイダー (SSP) カスタム Web パーツを追加する名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45c74-153">In the left navigation pane, click the name of the Shared Service Provider (SSP) to which you want to add the custom Web Part.</span></span>  
  
3.  <span data-ttu-id="45c74-154">共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="45c74-154">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
4.  <span data-ttu-id="45c74-155">[サイト設定] ページで、をクリックして**Web パーツ**下にある、**ギャラリー**列です。</span><span class="sxs-lookup"><span data-stu-id="45c74-155">On the Site Settings page, click **Web Parts** under the **Galleries** column.</span></span>  
  
5.  <span data-ttu-id="45c74-156">Web パーツ ギャラリー ページで、カスタム Web パーツをギャラリーを追加する をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="45c74-156">On the Web Part Gallery page, to add the custom Web Part to the gallery,  click **New**.</span></span> <span data-ttu-id="45c74-157">この時点でカスタム Web パーツでは、Web パーツ ギャラリー ページで使用できません。</span><span class="sxs-lookup"><span data-stu-id="45c74-157">At this point the custom Web Part is not available in the Web Part Gallery page.</span></span>  
  
6.  <span data-ttu-id="45c74-158">[新しい Web パーツ] ページで、検索**CustomWebPart** (カスタムの Web パーツの名前) の一覧で、左側のチェック ボックスをオンにし、をクリックして**ギャラリー**ページの上部です。</span><span class="sxs-lookup"><span data-stu-id="45c74-158">On the New Web Parts page, locate **CustomWebPart** (name of the custom Web Part) in the list, select the check box on the left, and then click **Populate Gallery** on the top of the page.</span></span> <span data-ttu-id="45c74-159">これが追加されます、 **CustomWebPart** Web パーツ ギャラリー ページで入力します。</span><span class="sxs-lookup"><span data-stu-id="45c74-159">This will add the **CustomWebPart** entry in the Web Part Gallery page.</span></span>  
  
 <span data-ttu-id="45c74-160">これで、カスタム Web パーツを使用することができます (**CustomWebPart**) ポータルの SharePoint Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="45c74-160">Now you can use the custom Web Part (**CustomWebPart**) to create Web Parts in your SharePoint portal.</span></span> <span data-ttu-id="45c74-161">カスタム Web パーツ (**CustomWebPart**) 下に表示されます、 **その他** Web パーツの追加 ページのセクションです。</span><span class="sxs-lookup"><span data-stu-id="45c74-161">The custom Web Part (**CustomWebPart**) will appear under the **Miscellaneous** section in the Add Web Parts page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c74-162">参照</span><span class="sxs-lookup"><span data-stu-id="45c74-162">See Also</span></span>  
[<span data-ttu-id="45c74-163">SharePoint での SAP アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="45c74-163">Use the SAP adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)