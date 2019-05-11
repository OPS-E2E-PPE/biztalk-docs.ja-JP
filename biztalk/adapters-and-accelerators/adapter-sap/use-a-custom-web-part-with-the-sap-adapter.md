---
title: SAP アダプターを使用したカスタム Web パーツを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b7fecd2-a385-4b2d-a01b-3bfd65ecff3a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a521caa483c258fd2bacb8b02a47d15ce666ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372266"
---
# <a name="use-a-custom-web-part-with-the-sap-adapter"></a><span data-ttu-id="e131f-102">SAP アダプターを使用したカスタム Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="e131f-102">Use a Custom Web Part with the SAP adapter</span></span>
<span data-ttu-id="e131f-103">このセクションでは、Microsoft Office SharePoint Server でカスタム Web パーツの使用に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e131f-103">This section provides information about using a custom Web Part with Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="e131f-104">カスタム Web パーツを使用するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e131f-104">To use a custom Web Part, you must do the following:</span></span>  
  
1.  <span data-ttu-id="e131f-105">カスタム Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-105">Create a custom Web Part</span></span>  
  
2.  <span data-ttu-id="e131f-106">SharePoint ポータルにカスタム Web パーツを展開します。</span><span class="sxs-lookup"><span data-stu-id="e131f-106">Deploy the custom Web Part to a SharePoint portal</span></span>  
  
3.  <span data-ttu-id="e131f-107">カスタム Web パーツを使用する SharePoint ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-107">Configure the SharePoint portal to use the custom Web Part</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e131f-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="e131f-108">Before You Begin</span></span>  
 <span data-ttu-id="e131f-109">カスタム Web パーツを作成する前に。</span><span class="sxs-lookup"><span data-stu-id="e131f-109">Before you create a custom Web Part:</span></span>  
  
-   <span data-ttu-id="e131f-110">WCF サービスとしての SAP アイテムを発行します。</span><span class="sxs-lookup"><span data-stu-id="e131f-110">Publish the SAP artifacts as a  WCF service.</span></span> <span data-ttu-id="e131f-111">詳細については、次を参照してください。[手順 1。SAP アイテムを WCF サービスとして発行](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)で[チュートリアル 1。SharePoint サイト上の SAP システムからのデータ表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)します。</span><span class="sxs-lookup"><span data-stu-id="e131f-111">For more information, see [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
-   <span data-ttu-id="e131f-112">Microsoft Office SharePoint Server でビジネス データ カタログを使用して SAP アイテム用のアプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-112">Create an application definition file for the SAP artifacts using the Business Data Catalog in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="e131f-113">詳細については、次を参照してください。[手順 2。SAP アイテム用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)で[チュートリアル 1。SharePoint サイト上の SAP システムからのデータ表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)します。</span><span class="sxs-lookup"><span data-stu-id="e131f-113">For more information, see [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
##  <a name="Create_a_Custom_Web_Part"></a> <span data-ttu-id="e131f-114">ステップ 1:カスタム Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-114">Step 1: Create a custom Web Part</span></span>  
 <span data-ttu-id="e131f-115">Visual Studio を使用して、カスタム Web パーツを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e131f-115">To create a custom Web Part using Visual Studio, do the following:</span></span>  
  
1.  <span data-ttu-id="e131f-116">Visual Studio を起動し、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-116">Start Visual Studio, and then create a project.</span></span>  
  
2.  <span data-ttu-id="e131f-117">**新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#** します。</span><span class="sxs-lookup"><span data-stu-id="e131f-117">In the **New Project** dialog box, from the **Project types** pane, select **Visual C#**.</span></span> <span data-ttu-id="e131f-118">**テンプレート**ペインで、**クラス ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="e131f-118">From the **Templates** pane, select **Class Library**.</span></span>  
  
3.  <span data-ttu-id="e131f-119">ソリューションの場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e131f-119">Specify a name and location for the solution.</span></span> <span data-ttu-id="e131f-120">このトピックでは、次のように指定します。`CustomWebPart`で、**名前**と**ソリューション名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="e131f-120">For this topic, specify `CustomWebPart` in the **Name** and **Solution Name** boxes.</span></span> <span data-ttu-id="e131f-121">場所を指定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e131f-121">Specify a location, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="e131f-122">System.Web コンポーネントへの参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e131f-122">Add a reference to the System.Web component into the project.</span></span> <span data-ttu-id="e131f-123">プロジェクト名を右クリックして**ソリューション エクスプ ローラー**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="e131f-123">Right-click the project name in **Solution Explorer**, and then click **Add Reference**.</span></span> <span data-ttu-id="e131f-124">**参照の追加**ダイアログ ボックスで、 **System.Web**で、 **.NET**  タブをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e131f-124">In the **Add Reference** dialog box, select **System.Web** in the **.NET** tab, and then click **OK**.</span></span> <span data-ttu-id="e131f-125">System.Web コンポーネントには、System.Web.UI.WebControls.WebParts の必要な名前空間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e131f-125">The System.Web component contains the required namespace of System.Web.UI.WebControls.WebParts.</span></span>  
  
5.  <span data-ttu-id="e131f-126">プロジェクトの問題に基づいて、必要なコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e131f-126">Add the required code based on your issue in the project.</span></span> <span data-ttu-id="e131f-127">特定の問題に関連するコード サンプルでは、「問題に関連するカスタム Web パーツ」を参照してください[SharePoint で SAP アダプターの使用時の考慮事項](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md)します。</span><span class="sxs-lookup"><span data-stu-id="e131f-127">For the code sample that is relevant to a certain issue, see “Issues Involving Custom Web Parts” in [Considerations when using the SAP adapter with SharePoint](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md).</span></span>  
  
6.  <span data-ttu-id="e131f-128">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="e131f-128">Build the project.</span></span> <span data-ttu-id="e131f-129">プロジェクトの成功したビルドで CustomWebPart.dll、.dll ファイルが生成されます、\<プロジェクト フォルダー\>bin/デバッグ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e131f-129">On successful build of the project, a .dll file, CustomWebPart.dll, will be generated in the \<project folder\>/bin/Debug folder.</span></span>  
  
7.  <span data-ttu-id="e131f-130">**64 ビット コンピューターに対してのみ**:次の手順を実行する前に厳密な名前で CustomWebPart.dll ファイルを署名します。</span><span class="sxs-lookup"><span data-stu-id="e131f-130">**Only for 64-bit computer**: Sign the CustomWebPart.dll file with a strong name before performing the following steps.</span></span> <span data-ttu-id="e131f-131">それ以外の場合、することができなくインポート、および SharePoint ポータルで、CustomWebPart.dll のため、使用する"手順 3。カスタム Web パーツを使用する SharePoint ポータルを構成します。"</span><span class="sxs-lookup"><span data-stu-id="e131f-131">Otherwise, you will not be able to import, and hence use the CustomWebPart.dll in the SharePoint portal in “Step 3: Configure the SharePoint Portal to use the custom Web Part.”</span></span> <span data-ttu-id="e131f-132">「[厳密な名前でアセンブリに署名](https://msdn.microsoft.com/library/xc31ft41.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="e131f-132">See [How to: Sign an Assembly with a Strong Name](https://msdn.microsoft.com/library/xc31ft41.aspx).</span></span>
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a><span data-ttu-id="e131f-133">手順 2:SharePoint ポータルにカスタム Web パーツを展開します。</span><span class="sxs-lookup"><span data-stu-id="e131f-133">Step 2: Deploy the custom Web Part to a SharePoint Portal</span></span>  
 <span data-ttu-id="e131f-134">作成される CustomWebPart.dll ファイル (カスタム Web パーツ) を作成するには、次を行う必要があります"手順 1。カスタム Web パーツを作成"このトピックでの SharePoint ポータルの使用:</span><span class="sxs-lookup"><span data-stu-id="e131f-134">You must do the following to make the CustomWebPart.dll file (custom Web Part) that is created in “Step 1: Create a custom Web Part” of this topic usable on the SharePoint portal:</span></span>  
  
- <span data-ttu-id="e131f-135">**SharePoint Portal の bin フォルダーに CustomWebPart.dll ファイルをコピー**:Microsoft Office SharePoint Server は、ポータルを作成、\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e131f-135">**Copy the CustomWebPart.dll file to the bin folder of the SharePoint Portal**: Microsoft Office SharePoint Server creates portals under the \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories folder.</span></span> <span data-ttu-id="e131f-136">フォルダーは、それぞれのポータルが作成され、ポート番号で識別できます。</span><span class="sxs-lookup"><span data-stu-id="e131f-136">A folder is created for each portal, and can be identified with the port number.</span></span> <span data-ttu-id="e131f-137">作成した CustomWebPart.dll ファイルをコピーする必要があります"手順 1。カスタム Web パーツの作成"するには、このトピックの\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>\bin フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e131f-137">You must copy the CustomWebPart.dll file created in “Step 1: Create a custom Web Part” of this topic to the \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number\>\bin folder.</span></span> <span data-ttu-id="e131f-138">たとえば、SharePoint ポータルのポート番号が 13614 の場合に CustomWebPart.dll ファイルをコピーする必要があります、\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e131f-138">For example, if the port number of your SharePoint portal is 13614, you must copy the CustomWebPart.dll file to the \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories\13614\bin folder.</span></span>  
  
  > [!TIP]
  >  <span data-ttu-id="e131f-139">使用して、SharePoint ポータルのフォルダーの場所を検索する別の方法は、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ (**開始** > **実行** >  **inetmgr**)。</span><span class="sxs-lookup"><span data-stu-id="e131f-139">Another way to find the folder location of your SharePoint portal is by using the **Internet Information Services (IIS) Manager** window (**Start** > **Run** > **inetmgr**).</span></span> <span data-ttu-id="e131f-140">SharePoint ポータルの検索、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ ([コンピューター名] > の Web サイト > [ポータル-Name])、右クリックしをクリック**プロパティ**で、ショートカット メニュー。</span><span class="sxs-lookup"><span data-stu-id="e131f-140">Locate your SharePoint portal in the **Internet Information Services (IIS) Manager** window ([computer_name] > Web Sites > [Portal-Name]), right-click, and then click **Properties** in the shortcut menu.</span></span> <span data-ttu-id="e131f-141">SharePoint ポータルの [プロパティ] ダイアログ ボックスでをクリックして、**ホーム ディレクトリ**、タブを選び、**ローカル パス**ボックス。</span><span class="sxs-lookup"><span data-stu-id="e131f-141">In the properties dialog box of the SharePoint portal, click the **Home Directory** tab, and then select the **Local path** box.</span></span>  
  
- <span data-ttu-id="e131f-142">**Web.config ファイルに安全なコントロール エントリを追加**:CustomWebPart.dll ファイルを別のコンピューターと、複数のユーザーが使用するため、「安全」としてファイルを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e131f-142">**Add the Safe Control Entry in the web.config File**: Because the CustomWebPart.dll file will be used on different computers and by multiple users, you must declare the file as “safe.”</span></span> <span data-ttu-id="e131f-143">これを行うには、SharePoint portal フォルダーにある web.config ファイルを開く\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>します。</span><span class="sxs-lookup"><span data-stu-id="e131f-143">To do so, open the web.config file located in the SharePoint portal folder at \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number\>.</span></span> <span data-ttu-id="e131f-144">下、`<SafeControls>`セクション、web.config ファイルの次の安全なコントロール エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="e131f-144">Under the `<SafeControls>` section of the web.config file, add the following safe control entry:</span></span>  
  
  - <span data-ttu-id="e131f-145">**32 ビット コンピューター。**</span><span class="sxs-lookup"><span data-stu-id="e131f-145">**On 32-bit computer:**</span></span>  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
  - <span data-ttu-id="e131f-146">**64 ビット コンピューター。**</span><span class="sxs-lookup"><span data-stu-id="e131f-146">**On 64-bit computer:**</span></span>  
  
    ```  
    <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
    <span data-ttu-id="e131f-147">Web.config ファイルを保存して、閉じます。</span><span class="sxs-lookup"><span data-stu-id="e131f-147">Save the web.config file, and then close it.</span></span>  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a><span data-ttu-id="e131f-148">手順 3:カスタム Web パーツを使用する SharePoint ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-148">Step 3: Configure the SharePoint portal to use the custom Web Part</span></span>  
 <span data-ttu-id="e131f-149">これを使用するには、SharePoint ポータルにするために、Microsoft Office SharePoint Server Web パーツ ギャラリーでカスタム Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e131f-149">You need to add the custom Web Part to the Microsoft Office SharePoint Server Web Part Gallery, so that you can use it on your SharePoint portal.</span></span> <span data-ttu-id="e131f-150">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="e131f-150">To do so:</span></span>  
  
1. <span data-ttu-id="e131f-151">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="e131f-151">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="e131f-152">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="e131f-152">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2. <span data-ttu-id="e131f-153">左側のナビゲーション ウィンドウでの共有サービス プロバイダー (SSP) カスタム Web パーツを追加する名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e131f-153">In the left navigation pane, click the name of the Shared Service Provider (SSP) to which you want to add the custom Web Part.</span></span>  
  
3. <span data-ttu-id="e131f-154">共有サービス管理 ページで、右上隅にある**サイトの操作**、 をクリックし、**作成**です。</span><span class="sxs-lookup"><span data-stu-id="e131f-154">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
4. <span data-ttu-id="e131f-155">サイトの設定 ページで、次のようにクリックします。 **Web パーツ**下、**ギャラリー**列。</span><span class="sxs-lookup"><span data-stu-id="e131f-155">On the Site Settings page, click **Web Parts** under the **Galleries** column.</span></span>  
  
5. <span data-ttu-id="e131f-156">Web パーツ ギャラリー ページで、カスタム Web パーツをギャラリーを追加するクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="e131f-156">On the Web Part Gallery page, to add the custom Web Part to the gallery,  click **New**.</span></span> <span data-ttu-id="e131f-157">この時点でカスタム Web パーツでは、Web パーツのギャラリー ページでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e131f-157">At this point the custom Web Part is not available in the Web Part Gallery page.</span></span>  
  
6. <span data-ttu-id="e131f-158">新しい Web パーツ ページで、検索**CustomWebPart** (カスタムの Web パーツの名前) の一覧で、左側のチェック ボックスをオンにし**ギャラリー**ページ上部にあります。</span><span class="sxs-lookup"><span data-stu-id="e131f-158">On the New Web Parts page, locate **CustomWebPart** (name of the custom Web Part) in the list, select the check box on the left, and then click **Populate Gallery** on the top of the page.</span></span> <span data-ttu-id="e131f-159">これは追加、 **CustomWebPart** Web パーツのギャラリー ページのエントリ。</span><span class="sxs-lookup"><span data-stu-id="e131f-159">This will add the **CustomWebPart** entry in the Web Part Gallery page.</span></span>  
  
   <span data-ttu-id="e131f-160">カスタム Web パーツを使用するようになりました (**CustomWebPart**)、SharePoint ポータルで Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-160">Now you can use the custom Web Part (**CustomWebPart**) to create Web Parts in your SharePoint portal.</span></span> <span data-ttu-id="e131f-161">カスタム Web パーツ (**CustomWebPart**) 下に表示されます、 **その他** Web パーツの追加 ページでセクション。</span><span class="sxs-lookup"><span data-stu-id="e131f-161">The custom Web Part (**CustomWebPart**) will appear under the **Miscellaneous** section in the Add Web Parts page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e131f-162">参照</span><span class="sxs-lookup"><span data-stu-id="e131f-162">See Also</span></span>  
[<span data-ttu-id="e131f-163">SharePoint で SAP アダプターを使用する</span><span class="sxs-lookup"><span data-stu-id="e131f-163">Use the SAP adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)