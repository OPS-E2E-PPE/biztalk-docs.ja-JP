---
title: "更新または BizTalk アダプター パック 2016 のアンインストール |Microsoft ドキュメント"
description: "セットアップ ウィザードまたは msiexec を使用して、変更または BizTalk Server に含まれている BAP 2016 のアンインストールなど、バインドを削除して、カスタムの Rfc を削除"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c30fa3b107113991a8b4893fa2626a53d67159
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="a573f-103">更新または BizTalk アダプター パック 2016 のアンインストール</span><span class="sxs-lookup"><span data-stu-id="a573f-103">Update or uninstall the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="a573f-104">変更またはアンインストールする方法、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a573f-104">How to change or uninstall the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a><span data-ttu-id="a573f-105">変更または更新のインストール</span><span class="sxs-lookup"><span data-stu-id="a573f-105">Change or update the installation</span></span>  
<span data-ttu-id="a573f-106">変更するセットアップ ウィザードを実行する前に、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、インストールを確認してください、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a573f-106">Before you run the setup wizard to modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] is installed.</span></span> 
  
 <span data-ttu-id="a573f-107">対話モード (セットアップ ウィザード) で、またはサイレント モード (コマンド ライン) で、インストールを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a573f-107">You can modify the installation in interactive mode (the setup wizard), or in silent mode (the command line).</span></span>
  
### <a name="use-the-setup-wizard"></a><span data-ttu-id="a573f-108">セットアップ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a573f-108">Use the setup wizard</span></span>  
  
1.  <span data-ttu-id="a573f-109">BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a573f-109">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="a573f-110">**プログラムと機能****プログラムのアンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-110">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
3.  <span data-ttu-id="a573f-111">右クリック**Microsoft BizTalk Adapter Pack**、し、**変更**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-111">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Change**.</span></span>  
  
4.  <span data-ttu-id="a573f-112">[ようこそ] 画面で、次のように選択します。**次**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-112">On the Welcome screen, select **Next**.</span></span>  
  
5.  <span data-ttu-id="a573f-113">**変更、修復、または削除インストール**:</span><span class="sxs-lookup"><span data-stu-id="a573f-113">In **Change, repair, or remove installation**:</span></span>  
  
    -   <span data-ttu-id="a573f-114">インストールするコンポーネントを選択する**変更**し、手順 6. に進みます。</span><span class="sxs-lookup"><span data-stu-id="a573f-114">To select the components you want to install, select **Change** and go to Step 6.</span></span>  
  
    -   <span data-ttu-id="a573f-115">最新のインストールのエラーを修復するには、次のように選択します。**修復**手順 7. に進みます。</span><span class="sxs-lookup"><span data-stu-id="a573f-115">To repair errors in the most recent installation, select **Repair** and go to Step 7.</span></span>  
  
    -   <span data-ttu-id="a573f-116">削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、コンピューターから選択**削除**し、手順 10 に進みます。</span><span class="sxs-lookup"><span data-stu-id="a573f-116">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from the computer, select **Remove** and then go to Step 10.</span></span>  
  
6.  <span data-ttu-id="a573f-117">場合は、インストールを変更することを選択します。</span><span class="sxs-lookup"><span data-stu-id="a573f-117">If you chose to modify the installation:</span></span>  
  
    -   <span data-ttu-id="a573f-118">展開して、 **Microsoft BizTalk Adapter Pack**ノード ベース アダプター、.NET Framework データ プロバイダー、またはその両方をインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a573f-118">Expand the **Microsoft BizTalk Adapter Pack** node to choose to install the base adapters, the .NET Framework Data Providers, or both.</span></span>  
  
    -   <span data-ttu-id="a573f-119">展開して、**ベース アダプター**ノードすべてのアダプターまたは特定のアダプターをインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a573f-119">Expand the **Base Adapters** node to choose to install all the adapters or specific adapters.</span></span>  
  
    -   <span data-ttu-id="a573f-120">展開して、 **ADO プロバイダー**ノードすべてのプロバイダーまたは特定のプロバイダーをインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a573f-120">Expand the **ADO Providers** node to choose to install all the providers or specific providers.</span></span>  
  
    -   <span data-ttu-id="a573f-121">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a573f-121">Select **Next**.</span></span>  
  
    -   <span data-ttu-id="a573f-122">選択**変更**、し、**完了**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-122">Select **Change**, and then select **Finish**.</span></span>  
  
7.  <span data-ttu-id="a573f-123">インストールを修復して、選択した場合、 **Microsoft BizTalk Adapter Pack の修復の準備完了**ダイアログ ボックスで、**修復**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-123">If you chose to repair the installation, in the **Ready to repair Microsoft BizTalk Adapter Pack** dialog box, select **Repair**.</span></span> <span data-ttu-id="a573f-124">ウィザードでは、インストールの修復を開始します。</span><span class="sxs-lookup"><span data-stu-id="a573f-124">The wizard starts repairing the installation.</span></span>  
  
8.  <span data-ttu-id="a573f-125">必要に応じて、ユーザーの設定を変更、CEIP のオプトインに関連し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-125">If required, change your preferences regarding opting for CEIP, and then select **OK**.</span></span> 
  
9. <span data-ttu-id="a573f-126">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a573f-126">Select **Finish**.</span></span>  
  
10. <span data-ttu-id="a573f-127">アダプターを削除した場合、 **Microsoft BizTalk Adapter Pack を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-127">If you chose to remove the adapters, in the **Ready to remove Microsoft BizTalk Adapter Pack** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
### <a name="use-msiexec-in-silent-mode"></a><span data-ttu-id="a573f-128">サイレント モードで msiexec を使用します。</span><span class="sxs-lookup"><span data-stu-id="a573f-128">Use msiexec in silent mode</span></span>  
  
1.  <span data-ttu-id="a573f-129">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="a573f-129">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="a573f-130">次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a573f-130">Run a command similar to the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a573f-131">変更する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次のコマンドでの x64 ベースのプラットフォームにサイレント モードでインストールを交換して`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。</span><span class="sxs-lookup"><span data-stu-id="a573f-131">To modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in a silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     <span data-ttu-id="a573f-132">このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]をインストールし、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a573f-132">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], and installs the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span>  
  
     <span data-ttu-id="a573f-133">別の値を使用して、`REMOVE`と`ADDLOCAL`プロパティを追加または特定のコンポーネントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a573f-133">By using different values for the `REMOVE` and `ADDLOCAL` properties, you can add or remove specific components.</span></span> <span data-ttu-id="a573f-134">内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)これらのプロパティを使用できる値についてはします。</span><span class="sxs-lookup"><span data-stu-id="a573f-134">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for these properties.</span></span>  
  
     <span data-ttu-id="a573f-135">Msiexec コマンドの一部として、/f オプションを使用して、サイレントの修復を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a573f-135">You can also do a silent repair by using the /f option as part of the msiexec command.</span></span> <span data-ttu-id="a573f-136">例:</span><span class="sxs-lookup"><span data-stu-id="a573f-136">For example:</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     <span data-ttu-id="a573f-137">さまざまなさまざまな組み合わせを使用するには、/f オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a573f-137">You can use various different combinations with the /f option.</span></span> <span data-ttu-id="a573f-138">Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。</span><span class="sxs-lookup"><span data-stu-id="a573f-138">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="a573f-139">移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。</span><span class="sxs-lookup"><span data-stu-id="a573f-139">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a573f-140">変更中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでインストールで CEIP を有効または無効にするための設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a573f-140">While modifying the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="a573f-141">True または false に、CEIP_OPTIN を明示的に設定した場合でも、インストールは残りの中に選択した環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="a573f-141">The preferences you chose during the installation remains, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a><span data-ttu-id="a573f-142">アンインストールするか、BizTalk Adapter Pack を削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-142">Uninstall or remove the BizTalk Adapter Pack</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a573f-143">TRFC 機能を使用する SQL Server データベースでテーブルを作成した場合、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、アンインストールする前に手動で削除する必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a573f-143">If you created tables in the SQL Server database to work with the tRFC feature of the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], you must manually remove them before uninstalling the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="a573f-144">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールのコピー、`SapAdapter-DbScript-Uninstall.sql`ファイルを通常*\<インストール ドライブ >: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*です。</span><span class="sxs-lookup"><span data-stu-id="a573f-144">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation copies a `SapAdapter-DbScript-Uninstall.sql` file typically at *\<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="a573f-145">作成したテーブルを削除するには、このファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="a573f-145">Run this file to remove the tables you created.</span></span>  
  
<span data-ttu-id="a573f-146">次の手順を削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]コンピューターからです。</span><span class="sxs-lookup"><span data-stu-id="a573f-146">Complete the following steps to remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from your computer.</span></span> <span data-ttu-id="a573f-147">あるかどうかを確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]セットアップ ウィザードを実行する前にインストールします。</span><span class="sxs-lookup"><span data-stu-id="a573f-147">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard.</span></span>  
  
 <span data-ttu-id="a573f-148">削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード) またはサイレント モード (コマンド ライン)。</span><span class="sxs-lookup"><span data-stu-id="a573f-148">You can remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode (setup wizard), or in silent mode (command line).</span></span>
  
### <a name="uninstall-using-the-setup-wizard"></a><span data-ttu-id="a573f-149">セットアップ ウィザードを使用してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a573f-149">Uninstall using the setup wizard</span></span>  
  
1.  <span data-ttu-id="a573f-150">**プログラムと機能****プログラムのアンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-150">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
2.  <span data-ttu-id="a573f-151">右クリック**Microsoft BizTalk Adapter Pack**、し、**アンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="a573f-151">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Uninstall**.</span></span>  
  
### <a name="uninstall-in-silent-mode"></a><span data-ttu-id="a573f-152">サイレント モードでアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a573f-152">Uninstall in silent mode</span></span>  
  
1.  <span data-ttu-id="a573f-153">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="a573f-153">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="a573f-154">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a573f-154">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a573f-155">削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードで、次のコマンドの x64 ベースのプラットフォーム上で置き換える`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。</span><span class="sxs-lookup"><span data-stu-id="a573f-155">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     <span data-ttu-id="a573f-156">このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]から、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="a573f-156">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
     <span data-ttu-id="a573f-157">異なる値を提供することによって、`REMOVE`プロパティから特定のコンポーネントを削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="a573f-157">By providing different values for the `REMOVE` property, you can remove specific components from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="a573f-158">内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)このプロパティの使用できる値についてはします。</span><span class="sxs-lookup"><span data-stu-id="a573f-158">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for this property.</span></span>  
  
     <span data-ttu-id="a573f-159">完全に削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a573f-159">To completely remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], execute the following command:</span></span>  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     <span data-ttu-id="a573f-160">Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。</span><span class="sxs-lookup"><span data-stu-id="a573f-160">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="a573f-161">移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。</span><span class="sxs-lookup"><span data-stu-id="a573f-161">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
## <a name="remove-the-bindings"></a><span data-ttu-id="a573f-162">バインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-162">Remove the bindings</span></span>  
 <span data-ttu-id="a573f-163">次の手順を完了*のみ*machine.config ファイルから、アダプターのバインドまたは .NET Framework Data Provider の登録を削除するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="a573f-163">Complete these steps *only* if the setup wizard fails to remove the adapter bindings or .NET Framework Data Provider registration from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="a573f-164">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="a573f-164">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="a573f-165">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な*\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG*です。</span><span class="sxs-lookup"><span data-stu-id="a573f-165">For example, on a 32-bit platform, the machine.config is available under *\<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  
  
2.  <span data-ttu-id="a573f-166">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a573f-166">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="a573f-167">アダプターのバインドの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-167">Remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="a573f-168">検索、`system.serviceModel`要素、および要素の下には、次の削除。</span><span class="sxs-lookup"><span data-stu-id="a573f-168">Search for the `system.serviceModel` element, and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="a573f-169">検索、 `bindingElementExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="a573f-169">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="a573f-170">次のセクションでは、削除、`bindingElementExtensions`バインドに応じて、使用可能なアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="a573f-170">Remove the following sections under the `bindingElementExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="a573f-171">セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a573f-171">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="a573f-172">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-172">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-173">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-173">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-174">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-174">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-175">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-175">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-176">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-176">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="a573f-177">検索、 `bindingExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="a573f-177">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="a573f-178">次のセクションでは、削除、`bindingExtensions`バインドに応じて、使用可能なアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="a573f-178">Remove the following sections under the `bindingExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="a573f-179">セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a573f-179">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="a573f-180">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-180">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-181">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-181">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-182">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-182">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-183">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-183">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-184">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-184">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="a573f-185">.NET Framework データ プロバイダーの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-185">Remove the .NET Framework Data Provider registration:</span></span>  
  
    -   <span data-ttu-id="a573f-186">検索、 `DbProviderFactories` system.data ノードの下の要素。</span><span class="sxs-lookup"><span data-stu-id="a573f-186">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    -   <span data-ttu-id="a573f-187">まだ登録されている .NET Framework データ プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="a573f-187">Look for the .NET Framework Data Providers that are still registered.</span></span> <span data-ttu-id="a573f-188">次のセクションでは、削除、`DbProviderFactories`によっては、既存の .NET Framework データ プロバイダーのノード。</span><span class="sxs-lookup"><span data-stu-id="a573f-188">Remove the following sections under the `DbProviderFactories` node, depending on the existing .NET Framework Data Providers.</span></span> <span data-ttu-id="a573f-189">存在する場合は、すべてのプロバイダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a573f-189">You must remove all the providers if they exist.</span></span>  
  
         <span data-ttu-id="a573f-190">[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-190">For [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="a573f-191">[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-191">For [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="a573f-192">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="a573f-192">Save and close the machine.config file.</span></span>  
  
## <a name="remove-the-custom-rfcs"></a><span data-ttu-id="a573f-193">カスタム Rfc を削除します。</span><span class="sxs-lookup"><span data-stu-id="a573f-193">Remove the custom RFCs</span></span>  
<span data-ttu-id="a573f-194">SAP システムにインストールされているカスタム Rfc を削除するには、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="a573f-194">Complete this step to remove the custom RFCs that you installed in the SAP system.</span></span> <span data-ttu-id="a573f-195">参照してください[インストールまたは削除するカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="a573f-195">See [Install or remove custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
