---
title: 更新または、BizTalk Adapter Pack 2016 のアンインストール |Microsoft Docs
description: セットアップ ウィザードまたは msiexec を使用して、変更または BizTalk Server に含まれている BAP 2016 のアンインストールなど、バインドを削除し、カスタム Rfc の削除
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eef0252a2907287c3197d40558d605f5c9f5660e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981867"
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="9eac4-103">更新または、BizTalk Adapter Pack 2016 のアンインストール</span><span class="sxs-lookup"><span data-stu-id="9eac4-103">Update or uninstall the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="9eac4-104">変更またはアンインストールする方法、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-104">How to change or uninstall the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a><span data-ttu-id="9eac4-105">変更または更新のインストール</span><span class="sxs-lookup"><span data-stu-id="9eac4-105">Change or update the installation</span></span>  
<span data-ttu-id="9eac4-106">変更には、セットアップ ウィザードを実行する前に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="9eac4-106">Before you run the setup wizard to modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] is installed.</span></span> 
  
 <span data-ttu-id="9eac4-107">対話モード (セットアップ ウィザード) で、またはサイレント モード (コマンドライン) でのインストールを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-107">You can modify the installation in interactive mode (the setup wizard), or in silent mode (the command line).</span></span>
  
### <a name="use-the-setup-wizard"></a><span data-ttu-id="9eac4-108">セットアップ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-108">Use the setup wizard</span></span>  
  
1. <span data-ttu-id="9eac4-109">BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9eac4-109">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2. <span data-ttu-id="9eac4-110">**プログラムと機能**、**プログラムのアンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-110">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
3. <span data-ttu-id="9eac4-111">右クリックして**Microsoft BizTalk Adapter Pack**、し、**変更**します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-111">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Change**.</span></span>  
  
4. <span data-ttu-id="9eac4-112">[ようこそ] 画面で、次のように選択します。**次**します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-112">On the Welcome screen, select **Next**.</span></span>  
  
5. <span data-ttu-id="9eac4-113">**変更、修復、または削除インストール**:</span><span class="sxs-lookup"><span data-stu-id="9eac4-113">In **Change, repair, or remove installation**:</span></span>  
  
   - <span data-ttu-id="9eac4-114">インストールするコンポーネントを選択する**変更**し、手順 6. に進みます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-114">To select the components you want to install, select **Change** and go to Step 6.</span></span>  
  
   - <span data-ttu-id="9eac4-115">最新のインストールのエラーを修復するには、選択**修復**手順 7. に進みます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-115">To repair errors in the most recent installation, select **Repair** and go to Step 7.</span></span>  
  
   - <span data-ttu-id="9eac4-116">削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、コンピューターから次のように選択します。**削除**し、手順 10 に進みます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-116">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from the computer, select **Remove** and then go to Step 10.</span></span>  
  
6. <span data-ttu-id="9eac4-117">インストールを変更する場合。</span><span class="sxs-lookup"><span data-stu-id="9eac4-117">If you chose to modify the installation:</span></span>  
  
   -   <span data-ttu-id="9eac4-118">展開、 **Microsoft BizTalk Adapter Pack**ノード ベース アダプター、.NET Framework データ プロバイダー、またはその両方をインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-118">Expand the **Microsoft BizTalk Adapter Pack** node to choose to install the base adapters, the .NET Framework Data Providers, or both.</span></span>  
  
   -   <span data-ttu-id="9eac4-119">展開、**ベース アダプター**ノードをすべてのアダプターまたは特定のアダプターのインストールを選択します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-119">Expand the **Base Adapters** node to choose to install all the adapters or specific adapters.</span></span>  
  
   -   <span data-ttu-id="9eac4-120">展開、 **ADO プロバイダー**ノードすべてのプロバイダーまたは特定のプロバイダーをインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-120">Expand the **ADO Providers** node to choose to install all the providers or specific providers.</span></span>  
  
   -   <span data-ttu-id="9eac4-121">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-121">Select **Next**.</span></span>  
  
   -   <span data-ttu-id="9eac4-122">選択**変更**、し、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-122">Select **Change**, and then select **Finish**.</span></span>  
  
7. <span data-ttu-id="9eac4-123">インストールを修復することを選んだ場合、 **Microsoft BizTalk Adapter Pack の修復の準備完了**ダイアログ ボックスで、**修復**します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-123">If you chose to repair the installation, in the **Ready to repair Microsoft BizTalk Adapter Pack** dialog box, select **Repair**.</span></span> <span data-ttu-id="9eac4-124">ウィザードでは、インストールの修復を開始します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-124">The wizard starts repairing the installation.</span></span>  
  
8. <span data-ttu-id="9eac4-125">必要な場合、基本設定を変更、CEIP のオプトインに関連し、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="9eac4-125">If required, change your preferences regarding opting for CEIP, and then select **OK**.</span></span> 
  
9. <span data-ttu-id="9eac4-126">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-126">Select **Finish**.</span></span>  
  
10. <span data-ttu-id="9eac4-127">アダプターを削除した場合、 **Microsoft BizTalk Adapter Pack を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**。</span><span class="sxs-lookup"><span data-stu-id="9eac4-127">If you chose to remove the adapters, in the **Ready to remove Microsoft BizTalk Adapter Pack** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
### <a name="use-msiexec-in-silent-mode"></a><span data-ttu-id="9eac4-128">サイレント モードで msiexec を使用します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-128">Use msiexec in silent mode</span></span>  
  
1. <span data-ttu-id="9eac4-129">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラー。</span><span class="sxs-lookup"><span data-stu-id="9eac4-129">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2. <span data-ttu-id="9eac4-130">次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-130">Run a command similar to the following:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9eac4-131">変更する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、次のコマンドでの x64 ベースのプラットフォームでサイレント モードでインストールを交換して`AdaptersSetup.msi`で`AdaptersSetup64.msi`。</span><span class="sxs-lookup"><span data-stu-id="9eac4-131">To modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in a silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
   ```  
  
    <span data-ttu-id="9eac4-132">このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]をインストールし、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-132">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], and installs the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span>  
  
    <span data-ttu-id="9eac4-133">別の値を使用して、`REMOVE`と`ADDLOCAL`プロパティを追加または特定のコンポーネントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-133">By using different values for the `REMOVE` and `ADDLOCAL` properties, you can add or remove specific components.</span></span> <span data-ttu-id="9eac4-134">内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)これらのプロパティを使用できる値についてはします。</span><span class="sxs-lookup"><span data-stu-id="9eac4-134">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for these properties.</span></span>  
  
    <span data-ttu-id="9eac4-135">Msiexec コマンドの一部として、/f オプションを使用して、サイレントの修復を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-135">You can also do a silent repair by using the /f option as part of the msiexec command.</span></span> <span data-ttu-id="9eac4-136">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-136">For example:</span></span>  
  
   ```  
   msiexec /i AdaptersSetup.msi /qn /f  
   ```  
  
    <span data-ttu-id="9eac4-137">/F オプションを使用して、さまざまなさまざまな組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-137">You can use various different combinations with the /f option.</span></span> <span data-ttu-id="9eac4-138">Msiexec コマンドの種類の詳細については`msiexec`コマンドライン、およびキーを押して`ENTER`します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-138">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="9eac4-139">移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-139">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="9eac4-140">変更中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでインストール、または ceip のオプトインの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9eac4-140">While modifying the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="9eac4-141">True または false に、CEIP_OPTIN を明示的に設定した場合でも、インストールは残りの中に選択した環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-141">The preferences you chose during the installation remains, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a><span data-ttu-id="9eac4-142">アンインストールするか、BizTalk Adapter Pack の削除</span><span class="sxs-lookup"><span data-stu-id="9eac4-142">Uninstall or remove the BizTalk Adapter Pack</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9eac4-143">TRFC 機能を使用する SQL Server データベースでテーブルを作成した場合、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、アンインストールする前に削除する必要があります手動で、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-143">If you created tables in the SQL Server database to work with the tRFC feature of the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], you must manually remove them before uninstalling the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="9eac4-144">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールのコピーを`SapAdapter-DbScript-Uninstall.sql`ファイルを通常*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-144">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation copies a `SapAdapter-DbScript-Uninstall.sql` file typically at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="9eac4-145">作成したテーブルを削除するには、このファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-145">Run this file to remove the tables you created.</span></span>  
  
<span data-ttu-id="9eac4-146">削除するには、次の手順を完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]コンピューターから。</span><span class="sxs-lookup"><span data-stu-id="9eac4-146">Complete the following steps to remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from your computer.</span></span> <span data-ttu-id="9eac4-147">必ず、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]セットアップ ウィザードを実行する前にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="9eac4-147">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard.</span></span>  
  
 <span data-ttu-id="9eac4-148">削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード)、またはサイレント モード (コマンドライン)。</span><span class="sxs-lookup"><span data-stu-id="9eac4-148">You can remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode (setup wizard), or in silent mode (command line).</span></span>
  
### <a name="uninstall-using-the-setup-wizard"></a><span data-ttu-id="9eac4-149">セットアップ ウィザードを使用したアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9eac4-149">Uninstall using the setup wizard</span></span>  
  
1.  <span data-ttu-id="9eac4-150">**プログラムと機能**、**プログラムのアンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-150">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
2.  <span data-ttu-id="9eac4-151">右クリックして**Microsoft BizTalk Adapter Pack**、し、**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-151">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Uninstall**.</span></span>  
  
### <a name="uninstall-in-silent-mode"></a><span data-ttu-id="9eac4-152">サイレント モードでアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9eac4-152">Uninstall in silent mode</span></span>  
  
1. <span data-ttu-id="9eac4-153">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラー。</span><span class="sxs-lookup"><span data-stu-id="9eac4-153">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2. <span data-ttu-id="9eac4-154">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-154">Run the following command:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9eac4-155">削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードで、次のコマンドでの x64 ベースのプラットフォームで置き換える`AdaptersSetup.msi`で`AdaptersSetup64.msi`。</span><span class="sxs-lookup"><span data-stu-id="9eac4-155">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
   ```  
  
    <span data-ttu-id="9eac4-156">このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]から、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="9eac4-156">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
    <span data-ttu-id="9eac4-157">さまざまな値を提供することで、`REMOVE`プロパティから特定のコンポーネントを削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="9eac4-157">By providing different values for the `REMOVE` property, you can remove specific components from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="9eac4-158">内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)このプロパティの使用できる値についてはします。</span><span class="sxs-lookup"><span data-stu-id="9eac4-158">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for this property.</span></span>  
  
    <span data-ttu-id="9eac4-159">完全に削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-159">To completely remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], execute the following command:</span></span>  
  
   ```  
   msiexec /x AdaptersSetup.msi /qn  
   ```  
  
    <span data-ttu-id="9eac4-160">Msiexec コマンドの種類の詳細については`msiexec`コマンドライン、およびキーを押して`ENTER`します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-160">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="9eac4-161">移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-161">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
## <a name="remove-the-bindings"></a><span data-ttu-id="9eac4-162">バインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-162">Remove the bindings</span></span>  
 <span data-ttu-id="9eac4-163">次の手順を完了*のみ*アダプター バインドまたは .NET Framework データ プロバイダーの登録、machine.config ファイルから削除するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="9eac4-163">Complete these steps *only* if the setup wizard fails to remove the adapter bindings or .NET Framework Data Provider registration from the machine.config file.</span></span>  
  
1. <span data-ttu-id="9eac4-164">コンピューターの machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-164">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="9eac4-165">たとえば、32 ビット プラットフォームで、machine.config はで使用可能な*\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG*します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-165">For example, on a 32-bit platform, the machine.config is available under *\<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  
  
2. <span data-ttu-id="9eac4-166">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-166">Open the file using a text editor.</span></span>  
  
3. <span data-ttu-id="9eac4-167">アダプターのバインドの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-167">Remove the adapter binding registration:</span></span>  
  
   1. <span data-ttu-id="9eac4-168">検索、`system.serviceModel`要素、および次の要素の下から削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-168">Search for the `system.serviceModel` element, and remove the following from under the element:</span></span>  
  
      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
  
      ```  
  
   2. <span data-ttu-id="9eac4-169">検索、 `bindingElementExtensions` system.serviceModel\extensions の下の要素。</span><span class="sxs-lookup"><span data-stu-id="9eac4-169">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
   3. <span data-ttu-id="9eac4-170">次のセクションでは、削除、`bindingElementExtensions`ノードで、使用可能なアダプターのバインドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9eac4-170">Remove the following sections under the `bindingElementExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="9eac4-171">セットアップ ウィザードは、削除が失敗した場合、すべてのバインドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eac4-171">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
       <span data-ttu-id="9eac4-172">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-172">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-173">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-173">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-174">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-174">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-175">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-175">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-176">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-176">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
   4. <span data-ttu-id="9eac4-177">検索、 `bindingExtensions` system.serviceModel\extensions の下の要素。</span><span class="sxs-lookup"><span data-stu-id="9eac4-177">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
   5. <span data-ttu-id="9eac4-178">次のセクションでは、削除、`bindingExtensions`ノードで、使用可能なアダプターのバインドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9eac4-178">Remove the following sections under the `bindingExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="9eac4-179">セットアップ ウィザードは、削除が失敗した場合、すべてのバインドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eac4-179">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
       <span data-ttu-id="9eac4-180">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-180">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-181">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-181">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-182">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-182">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-183">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-183">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
       <span data-ttu-id="9eac4-184">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-184">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  
  
4. <span data-ttu-id="9eac4-185">.NET Framework Data Provider の登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-185">Remove the .NET Framework Data Provider registration:</span></span>  
  
   - <span data-ttu-id="9eac4-186">検索、 `DbProviderFactories` system.data ノードの下の要素。</span><span class="sxs-lookup"><span data-stu-id="9eac4-186">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
   - <span data-ttu-id="9eac4-187">まだ登録されている .NET Framework データ プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-187">Look for the .NET Framework Data Providers that are still registered.</span></span> <span data-ttu-id="9eac4-188">次のセクションでは、削除、`DbProviderFactories`によっては、既存の .NET Framework データ プロバイダーのノード。</span><span class="sxs-lookup"><span data-stu-id="9eac4-188">Remove the following sections under the `DbProviderFactories` node, depending on the existing .NET Framework Data Providers.</span></span> <span data-ttu-id="9eac4-189">存在する場合は、すべてのプロバイダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eac4-189">You must remove all the providers if they exist.</span></span>  
  
      <span data-ttu-id="9eac4-190">[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-190">For [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], remove:</span></span>  
  
     ```  
     <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
         description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
     ```  
  
      <span data-ttu-id="9eac4-191">[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-191">For [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], remove:</span></span>  
  
     ```  
     <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
         description=".NET Framework Data Provider for Siebel eBusiness Applications"  
         type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
     ```  
  
5. <span data-ttu-id="9eac4-192">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="9eac4-192">Save and close the machine.config file.</span></span>  
  
## <a name="remove-the-custom-rfcs"></a><span data-ttu-id="9eac4-193">カスタム Rfc を削除します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-193">Remove the custom RFCs</span></span>  
<span data-ttu-id="9eac4-194">SAP システムがインストールされているカスタム Rfc を削除するには、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-194">Complete this step to remove the custom RFCs that you installed in the SAP system.</span></span> <span data-ttu-id="9eac4-195">参照してください[インストールまたは削除のカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="9eac4-195">See [Install or remove custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
