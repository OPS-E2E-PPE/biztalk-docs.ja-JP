---
title: "インストールと構成のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, troubleshooting
- configuring, troubleshooting
- troubleshooting, configuring
- troubleshooting, installing
ms.assetid: 25a2f6c5-c049-4042-8e38-4f7a2556e066
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62cb7d6181c7be44f7095a6c1d1149132df4e21e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="installation-and-configuration-troubleshooting"></a><span data-ttu-id="6faa1-102">インストールと構成のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6faa1-102">Installation and Configuration Troubleshooting</span></span>
## <a name="setup-is-unable-to-deploy-the-runtimeschemas-assembly"></a><span data-ttu-id="6faa1-103">RuntimeSchemas アセンブリを配置できません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-103">Setup is unable to deploy the RuntimeSchemas assembly</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-104">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-104">Symptom</span></span>  
 <span data-ttu-id="6faa1-105">A4SWIFT セットアップ プログラムは、RuntimeSchemas.dll を展開できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6faa1-105">The A4SWIFT Setup program was unable to deploy RuntimeSchemas.dll.</span></span> <span data-ttu-id="6faa1-106">アセンブリはセットアップ後に手動で展開されず、A4SWIFT 構成ウィザードは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-106">If the assembly is not deployed manually after setup, the A4SWIFT Configuration Wizard fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-107">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-107">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-108">次の条件のいずれかが存在する場合します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-108">One of the following conditions exists:</span></span>  
  
-   <span data-ttu-id="6faa1-109">実行時のスキーマ アセンブリは、A4SWIFT の最初のインストールを実行しようとしたときに既に展開されていた。</span><span class="sxs-lookup"><span data-stu-id="6faa1-109">The Runtime Schemas assembly was already deployed when you tried to perform an initial installation of A4SWIFT.</span></span>  
  
-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="6faa1-110">[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] A4SWIFT をインストールしようとするコンピューターで開始されませんでした。</span><span class="sxs-lookup"><span data-stu-id="6faa1-110"> [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was not started on the computer on which you tried to install A4SWIFT.</span></span>  
  
-   <span data-ttu-id="6faa1-111">実行時のスキーマ アセンブリは、A4SWIFT をアップグレードしようとしています。 別のアセンブリが参照したするとに既に展開されていた。</span><span class="sxs-lookup"><span data-stu-id="6faa1-111">The Runtime Schemas assembly was already deployed when you tried to upgrade A4SWIFT, and was referenced by another assembly.</span></span> <span data-ttu-id="6faa1-112">このされませんでしたの展開解除、A4SWIFT によって実行時のスキーマ アセンブリのでは、プログラムをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-112">This prevented undeployment of the Runtime Schemas assembly by the A4SWIFT upgrade program.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-113">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-113">Solution</span></span>  
 <span data-ttu-id="6faa1-114">問題の性質に応じて、次のように、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6faa1-114">Proceed as follows, depending upon the nature of the problem:</span></span>  
  
-   <span data-ttu-id="6faa1-115">BizTalk エクスプ ローラーを開く場合は、実行時のスキーマ アセンブリは、A4SWIFT の最初のインストールを実行しようとしたときに既に展開されていた、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]、アセンブリを右クリックして[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.FinancialServices.SWIFT.RuntimeSchemas をクリックして展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-115">If the Runtime Schemas assembly was already deployed when you attempted to run an initial installation of A4SWIFT, open BizTalk Explorer in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)], right-click the assembly [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.FinancialServices.SWIFT.RuntimeSchemas, and then click Undeploy.</span></span> <span data-ttu-id="6faa1-116">RuntimeSchemas.dll の最新バージョンを展開する BizTalk 展開ウィザードを使用して*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-116">Use the BizTalk Deployment Wizard to deploy the latest version of RuntimeSchemas.dll from *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies.</span></span>  
  
-   <span data-ttu-id="6faa1-117">場合[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]が開始されませんが、開始[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]サービス マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="6faa1-117">If [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was not started, start [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] in the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Service Manager.</span></span> <span data-ttu-id="6faa1-118">RuntimeSchemas.dll の最新バージョンを展開する BizTalk 展開ウィザードを使用して*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-118">Use the BizTalk Deployment Wizard to deploy the latest version of RuntimeSchemas.dll from *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies.</span></span>  
  
-   <span data-ttu-id="6faa1-119">A4SWIFT をアップグレードしようとしています。 してによって参照されたときに、実行時のスキーマ アセンブリが既に展開されている場合、別のアセンブリは BizTalk エクスプローラで、参照元のアセンブリを展開解除し、RuntimeSchemas.dll BizTalk エクスプ ローラーでの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-119">If the Runtime Schemas assembly was already deployed when you tried to upgrade A4SWIFT, and was referenced by another assembly, undeploy the referencing assembly in BizTalk Explorer, and undeploy RuntimeSchemas.dll in BizTalk Explorer.</span></span> <span data-ttu-id="6faa1-120">RuntimeSchemas.dll の最新バージョンを展開する BizTalk 展開ウィザードを使用して*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-120">Use the BizTalk Deployment Wizard to deploy the latest version of RuntimeSchemas.dll from *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Assemblies.</span></span>  
  
## <a name="after-the-web-components-feature-is-removed-message-repair-and-reconciliation-is-incorrectly-shown-as-uninstalled"></a><span data-ttu-id="6faa1-121">Web コンポーネントの機能が削除されると、Message Repair and 調整が不適切にアンインストール</span><span class="sxs-lookup"><span data-stu-id="6faa1-121">After the Web Components feature is removed, Message Repair and Reconciliation is incorrectly shown as uninstalled</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-122">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-122">Symptom</span></span>  
 <span data-ttu-id="6faa1-123">A4SWIFT の機能を Message Repair and New Submission の Web コンポーネントを削除した後は、アンインストールをインストールするまたは Message Repair および調整機能 (または A4SWIFT のコンポーネント) を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-123">After you remove the Web Components for Message Repair and New Submission feature of A4SWIFT, you cannot uninstall, install, or configure the Message Repair and Reconciliation feature (or A4SWIFT Components).</span></span> <span data-ttu-id="6faa1-124">Message Repair and 調整がインストールされている場合は、A4SWIFT には、機能がインストールされていることは認識されません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-124">If Message Repair and Reconciliation is installed, A4SWIFT does not recognize that the feature is installed.</span></span> <span data-ttu-id="6faa1-125">インストール、変更、または Message Repair and プログラムの追加/削除 (コントロール パネルから表示される) 内からの調整を削除しようとすると、プログラムの追加/削除は、機能がインストールされていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-125">If you attempt to install, modify, or remove Message Repair and Reconciliation from within Add/Remove Programs (displayed from Control Panel), Add/Remove Programs will indicate that the feature is not installed.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-126">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-126">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-127">削除された、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Message Repair and New Submission の機能および Message Repair and 調整の機能の Web コンポーネントをインストールした後、管理者がグループ化します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-127">You were removed from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group after you had installed the Web Components for Message Repair and New Submission feature and the Message Repair and Reconciliation feature.</span></span> <span data-ttu-id="6faa1-128">Web コンポーネント機能を削除する場合 (のメンバーでなくて行うことができる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators グループ)、A4SWIFT セットアップ プログラムがメッセージを修復するファイルを削除して、調整機能に依存しています。</span><span class="sxs-lookup"><span data-stu-id="6faa1-128">If you then remove the Web Components feature (which you can do without being a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group), the A4SWIFT setup program will remove files that the Message Repair and Reconciliation feature has a dependency on.</span></span> <span data-ttu-id="6faa1-129">これらのファイルには、ConfigFramework.exe が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6faa1-129">These files include ConfigFramework.exe.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-130">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-130">Solution</span></span>  
 <span data-ttu-id="6faa1-131">この問題が発生した場合は、次の手順します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-131">If you encounter this problem, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="6faa1-132">追加に自分でコンピューターの管理 ウィンドウで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループが、コンピューターからログオフし、再度ログオンします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-132">In the Computer Management window, add yourself back into the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrator group, log off the computer, and then log back on.</span></span>  
  
2.  <span data-ttu-id="6faa1-133">Message Repair and New Submission の機能の Web コンポーネントを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-133">Re-install the Web Components for Message Repair and New Submission feature.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6faa1-134">手順 2 では、A4SWIFT インストールに戻す ConfigFramework.exe を追加します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-134">Step 2 adds ConfigFramework.exe back into the A4SWIFT installation.</span></span>  
  
3.  <span data-ttu-id="6faa1-135">MRSR 機能を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-135">Re-install the MRSR feature.</span></span>  
  
4.  <span data-ttu-id="6faa1-136">まだたくない Web コンポーネント Message Repair and New Submission 機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-136">If you still do not want the Web Components for Message Repair and New Submission feature, remove it.</span></span>  
  
## <a name="repairing-a4swift-to-add-the-service-folder-can-result-in-improper-access-permissions-for-that-folder"></a><span data-ttu-id="6faa1-137">Service フォルダーを追加する A4SWIFT を修復することができますと、そのフォルダーの不適切なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6faa1-137">Repairing A4SWIFT to add the Service folder can result in improper access permissions for that folder</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-138">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-138">Symptom</span></span>  
 <span data-ttu-id="6faa1-139">フォルダーを削除する場合*%programfiles%*サーバー フォルダーを追加する A4SWIFT セットアップの修復機能は、A4SWIFT に戻します、A4SWIFT インストール環境適切に構成してから実行してから \Microsoft BizTalk Accelerator for SWIFT\Serviceインストールの場合、サービスのフォルダーのアクセス許可は正しいされません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-139">If you delete the folder *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service from a properly configured A4SWIFT installation, and then run the Repair feature of A4SWIFT setup to add the Server folder back in the A4SWIFT installation, the access permissions for the Service folder will not be correct.</span></span> <span data-ttu-id="6faa1-140">適切なアクセス許可は、A4SWIFT 管理者および読み取りのフル コントロールと A4SWIFT ユーザーに対して実行します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-140">The correct permissions are Full Control for A4SWIFT Administrators and Read & Execute for A4SWIFT Users.</span></span>  
  
 <span data-ttu-id="6faa1-141">これは、サービスのフォルダーが存在する場合に、A4SWIFT セットアップの修復機能を実行する場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-141">This also occurs if you run the Repair feature of A4SWIFT setup when the Service folder exists.</span></span> <span data-ttu-id="6faa1-142">アクセス許可、A4SWIFT 構成ウィザードによって設定で上書きされます不適切な値です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-142">The access permissions, as set by the A4SWIFT Configuration Wizard, will be overwritten with incorrect values.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-143">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-143">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-144">Message Repair and New Submission の Web コンポーネントをインストールする機能は、サービスのフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-144">Installing the Web Components for Message Repair and New Submission feature adds the Service folder.</span></span> <span data-ttu-id="6faa1-145">フォルダーを削除し、Message Repair and New Submission の Web コンポーネントを追加する A4SWIFT セットアップの修復 オプションを実行すると、A4SWIFT セットアップはフォルダーのアクセス許可を設定するには、(ConfigFramework.exe) の構成ウィザードを実行できません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-145">If you delete the folder and then run the Repair option of A4SWIFT setup to add the Web Components for Message Repair and New Submission, A4SWIFT setup does not run the configuration wizard (ConfigFramework.exe) to set the permissions for the folder.</span></span> <span data-ttu-id="6faa1-146">構成ウィザードが既に実行されていないため、構成をリセットするには、もう一度ウィザードを実行する非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-146">Because the configuration wizard has already been run, it is very difficult to run the wizard again to reset the configuration.</span></span> <span data-ttu-id="6faa1-147">その結果、削除されたファイルおよびフォルダーのすべての修復オプションが再作成が、アクセス許可が正しく設定ことはできません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-147">As a result, the Repair option will re-create all deleted files and folders, but it will not set access permissions correctly.</span></span>  
  
 <span data-ttu-id="6faa1-148">修復プロセスは、修復を実行すると、フォルダーが存在する場合にも、サービスのフォルダーのアクセス許可を上書きします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-148">The repair process also overwrites permissions for the Service folder if the folder exists when repair is run.</span></span> <span data-ttu-id="6faa1-149">として、ケースの修復を実行する前に、サービスのフォルダーを削除すると、非常に難しくなります、アクセス許可を設定、構成プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-149">As with the case of deleting the Service folder before running repair, it will be very difficult to run the configuration program to set the permissions.</span></span> <span data-ttu-id="6faa1-150">このインスタンスで同様に、アクセス許可が正しくないあり、それらを手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6faa1-150">In this instance, as well, the permissions will be incorrect and you will have to manually set them.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-151">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-151">Solution</span></span>  
 <span data-ttu-id="6faa1-152">この問題が発生した場合、サービスのフォルダーの次のアクセス許可を手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-152">If you encounter this problem, manually set the following access permissions for the Service folder:</span></span>  
  
|<span data-ttu-id="6faa1-153">[グループ名またはユーザー名]</span><span class="sxs-lookup"><span data-stu-id="6faa1-153">Group or User Name</span></span>|<span data-ttu-id="6faa1-154">権限</span><span class="sxs-lookup"><span data-stu-id="6faa1-154">Permission</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="6faa1-155">A4SWIFT の管理者</span><span class="sxs-lookup"><span data-stu-id="6faa1-155">A4SWIFT Administrators</span></span>|<span data-ttu-id="6faa1-156">フル コントロール</span><span class="sxs-lookup"><span data-stu-id="6faa1-156">Full Control</span></span>|  
|<span data-ttu-id="6faa1-157">A4SWIFT のユーザー</span><span class="sxs-lookup"><span data-stu-id="6faa1-157">A4SWIFT Users</span></span>|<span data-ttu-id="6faa1-158">読み取りと実行</span><span class="sxs-lookup"><span data-stu-id="6faa1-158">Read & Execute</span></span>|  
  
 <span data-ttu-id="6faa1-159">これらのアクセス許可を設定するには、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6faa1-159">To set these permissions, proceed as follows:</span></span>  
  
 <span data-ttu-id="6faa1-160">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-160">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service.</span></span>  
  
1.  <span data-ttu-id="6faa1-161">Service フォルダーを右クリックし、をクリックして**プロパティ**、をクリックし、**セキュリティ**タブです。</span><span class="sxs-lookup"><span data-stu-id="6faa1-161">Right-click the Service folder, click **Properties**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="6faa1-162">クリックして、グループまたはユーザー名のウィンドウで、サービスのプロパティ ダイアログ ボックス、**追加**、入力 ***\<サーバー名\>*\A4SWIFT 管理者**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-162">In the Group or user names pane of the Service Properties dialog box, click **Add**, enter ***\<server name\>*\A4SWIFT Administrators**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6faa1-163">A4SWIFT の Administrators グループがドメイン グループである場合は、入力 ***\<ドメイン名\>*\A4SWIFT 管理者**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-163">If the A4SWIFT Administrators group is a domain group, enter ***\<domain name\>*\A4SWIFT Administrators**.</span></span>  
  
3.  <span data-ttu-id="6faa1-164">手順 2. を繰り返します ***\<サーバー名\>*\A4SWIFT ユーザー**、または  **\<*ドメイン名*\>\A4SWIFT ユーザー * *、A4SWIFT Users グループがドメイン グループの場合。</span><span class="sxs-lookup"><span data-stu-id="6faa1-164">Repeat step 2 for ***\<server name\>*\A4SWIFT Users**, or **\<*domain name*\>\A4SWIFT Users** if the A4SWIFT Users group is a domain group.</span></span>  
  
4.  <span data-ttu-id="6faa1-165">グループまたはユーザー名ペインで選択**A4SWIFT 管理者**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-165">In the Group or user names pane, select **A4SWIFT Administrators**.</span></span> <span data-ttu-id="6faa1-166">アクセス許可 ウィンドウで、次のように選択します。**許可**の**フルコントロール**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-166">In the Permissions pane, select **Allow** for **Full Control**.</span></span>  
  
5.  <span data-ttu-id="6faa1-167">グループまたはユーザー名ペインで選択**A4SWIFT ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-167">In the Group or user names pane, select **A4SWIFT Users**.</span></span> <span data-ttu-id="6faa1-168">アクセス許可 ウィンドウで、をクリックして**許可**の**読み取りと実行**、**フォルダー内容の一覧**、および**読み取り**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-168">In the Permissions pane, click **Allow** for **Read & Execute**, **List Folder Contents**, and **Read**.</span></span>  
  
6.  <span data-ttu-id="6faa1-169">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-169">Click **OK**.</span></span>  
  
## <a name="upgrade-results-in-a-side-by-side-installation-of-two-versions-of-a4swift"></a><span data-ttu-id="6faa1-170">A4SWIFT の 2 つのバージョンのサイド バイ サイド インストールでのアップグレード結果</span><span class="sxs-lookup"><span data-stu-id="6faa1-170">Upgrade results in a side-by-side installation of two versions of A4SWIFT</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-171">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-171">Symptom</span></span>  
 <span data-ttu-id="6faa1-172">アップグレードしようとする[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]A4SWIFT の以前のバージョンは完全に削除できません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-172">When you attempt to upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], previous versions of A4SWIFT may not be fully removed.</span></span> <span data-ttu-id="6faa1-173">コントロール パネルの プログラムの追加/削除を実行する場合、現在インストールされているプログラムの一覧は、現在と以前のバージョンを表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6faa1-173">If you run Add/Remove Programs from the Control Panel, the list of Currently Installed Programs might show the current and the previous versions.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-174">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-174">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-175">次の条件のいずれかは、上記が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6faa1-175">Any of the following conditions can cause the above to occur:</span></span>  
  
-   <span data-ttu-id="6faa1-176">アップグレードしようとしています。 ユーザーがのメンバーではない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="6faa1-176">The user attempting to upgrade is not a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
-   <span data-ttu-id="6faa1-177">[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] (MSSQLSERVER) サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-177">The [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] service (MSSQLSERVER) is stopped.</span></span>  
  
-   <span data-ttu-id="6faa1-178">サイレント アップグレードを使用して、実行して、 **setup.exe/addlocal**コマンド。</span><span class="sxs-lookup"><span data-stu-id="6faa1-178">You performed a silent upgrade using the **setup.exe /addlocal** command.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-179">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-179">Solution</span></span>  
 <span data-ttu-id="6faa1-180">サイド バイ サイド インストールされないようにする[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]と[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]アップグレード中に発生していることを確認 (ログオン ユーザー) のメンバー、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループ、およびを[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)](MSSQLSERVER) サービスが開始します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-180">To prevent a side-by-side installation of [!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)] and [!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)] occurring during upgrade, ensure that you (the logged-on user) are a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group, and that the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] service (MSSQLSERVER) is started.</span></span>  
  
 <span data-ttu-id="6faa1-181">サイド バイ サイド インストール終了するかどうかは[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]または[!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)]と[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]、次の手順します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-181">If you end up with a side-by-side installation of [!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)] or [!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)] and [!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)], proceed as follows:</span></span>  
  
1.  <span data-ttu-id="6faa1-182">SWIFT メッセージ フォルダー内のデータをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-182">Back up the data in the SWIFT Messages folder.</span></span>  
  
2.  <span data-ttu-id="6faa1-183">ログオン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BTS Administrators のメンバーとしてグループ化、および MSSQLSERVER サービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6faa1-183">Log on to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a member of the BTS Administrators group, and ensure that the MSSQLSERVER service is running.</span></span>  
  
3.  <span data-ttu-id="6faa1-184">A4SWIFT の以前のバージョンを削除します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-184">Remove the previous version of A4SWIFT.</span></span>  
  
4.  <span data-ttu-id="6faa1-185">もう一度 A4SWIFT の最新バージョンにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-185">Upgrade to the latest version of A4SWIFT again.</span></span> <span data-ttu-id="6faa1-186">今度は、アップグレードを使用し、サイド バイ サイド インストールは作成されません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-186">This time the upgrade will work, and no side-by-side installation will be created.</span></span>  
  
5.  <span data-ttu-id="6faa1-187">BizTalk 展開ユーティリティを使用して手動で解除[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll、A4SWIFT インストールの場所の Assemblies フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-187">Using the BizTalk Deployment Utility, manually undeploy [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll, and then redeploy it from the Assemblies folder of your A4SWIFT installation location.</span></span> <span data-ttu-id="6faa1-188">このツールの詳細については、次を参照してください。 [BRE 配置ユーティリティ](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-188">For more information about this tool, see [BRE Deployment Utility](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md).</span></span>  
  
## <a name="the-uninstall-or-upgrade-process-may-not-complete-correctly-if-you-do-not-restart-when-prompted"></a><span data-ttu-id="6faa1-189">表示されたら再起動しない場合、アンインストールまたはアップグレードの処理が正しく完了しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6faa1-189">The uninstall or upgrade process may not complete correctly if you do not restart when prompted</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-190">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-190">Symptom</span></span>  
 <span data-ttu-id="6faa1-191">アンインストールまたはアップグレードのプロセスが正常に完了しません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-191">Uninstall or upgrade processes do not complete correctly.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-192">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-192">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-193">プロジェクトを展開解除がない場合は、既存の展開済みアセンブリを参照する、A4SWIFT 構成の変更を有効にするには、システムを再起動する必要があることを示すメッセージが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6faa1-193">If you have not undeployed a project that references an existing deployed assembly, you may receive a prompt indicating that you must restart your system for A4SWIFT configuration changes to take effect.</span></span> <span data-ttu-id="6faa1-194">クリックしない場合**はい**をすぐに再起動すると、グローバル アセンブリ キャッシュ内の削除の割り当てられている一部のアセンブリは削除できません、追加のアンインストールまたはアップグレードのプロセスが正常に完了しない原因です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-194">If you do not click **Yes** to restart immediately, some assemblies that were assigned for removal in the global assembly cache may not be removed, causing additional uninstall or upgrade processes to not complete correctly.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-195">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-195">Solution</span></span>  
 <span data-ttu-id="6faa1-196">既存の展開済みアセンブリを参照する他のプロジェクトを展開解除し、もう一度アンインストールまたはアップグレードの処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-196">Undeploy any project that references an existing deployed assembly, and then run the uninstall or upgrade process again.</span></span>  
  
## <a name="if-the-iis-admin-service-is-stopped-during-setup-you-must-reconfigure-the-webservice-feature"></a><span data-ttu-id="6faa1-197">セットアップ中に、IIS Admin サービスを停止すると場合、は、web サービス機能を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6faa1-197">If the IIS Admin Service is stopped during setup, you must reconfigure the WebService feature</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-198">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-198">Symptom</span></span>  
 <span data-ttu-id="6faa1-199">[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードが web サービス機能を正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-199">The [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration Wizard does not configure the WebService feature correctly.</span></span> <span data-ttu-id="6faa1-200">次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6faa1-200">You receive the following error:</span></span>  
  
 <span data-ttu-id="6faa1-201">"MRSR アーティファクトを作成できませんリモート サーバーに接続できません。"。</span><span class="sxs-lookup"><span data-stu-id="6faa1-201">"Unable to create MRSR artifacts: Unable to connect to the remote server."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-202">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-202">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-203">実行したときに、IIS 管理サービスが停止されました、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザード。</span><span class="sxs-lookup"><span data-stu-id="6faa1-203">The IIS Admin Service was stopped when you ran the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration Wizard.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-204">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-204">Solution</span></span>  
 <span data-ttu-id="6faa1-205">構成プロセスを正常に完了するには、次の手順します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-205">To complete the configuration process successfully, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="6faa1-206">閉じる、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6faa1-206">Close the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console.</span></span>  
  
2.  <span data-ttu-id="6faa1-207">IIS 管理サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-207">Restart the IIS Admin Service.</span></span>  
  
3.  <span data-ttu-id="6faa1-208">実行*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Configuration.exe です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-208">Execute *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Configuration.exe.</span></span>  
  
4.  <span data-ttu-id="6faa1-209">[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、**機能の構成解除**し、 **WebService**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-209">In the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, select **Unconfigure Features** and then select **WebService**.</span></span>  
  
5.  <span data-ttu-id="6faa1-210">未使用の領域として、構成コンソールで web サービス機能の状態が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-210">Ensure that the status of the WebService feature in the Configuration console is shown as unconfigured.</span></span>  
  
6.  <span data-ttu-id="6faa1-211">選択**構成を適用**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-211">Select **Apply Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6faa1-212">A4SWIFT 構成ウィザードは、web サービス機能を正しく構成してようになりました。</span><span class="sxs-lookup"><span data-stu-id="6faa1-212">The A4SWIFT Configuration Wizard will now configure the WebService feature correctly.</span></span>  
  
## <a name="a4swift-configuration-will-fail-if-the-biztalkserverapplication-host-was-not-created-in-biztalk-server-configuration"></a><span data-ttu-id="6faa1-213">BizTalk Server の構成では、BizTalkServerApplication ホストは作成されていない場合は、A4SWIFT 構成は失敗します</span><span class="sxs-lookup"><span data-stu-id="6faa1-213">A4SWIFT configuration will fail if the BizTalkServerApplication host was not created in BizTalk Server configuration</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-214">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-214">Symptom</span></span>  
 <span data-ttu-id="6faa1-215">[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードが web サービス機能を正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-215">The [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration Wizard does not configure the WebService feature correctly.</span></span> <span data-ttu-id="6faa1-216">次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6faa1-216">You receive the following error:</span></span>  
  
 <span data-ttu-id="6faa1-217">"MRSR アーティファクトを作成できません: オブジェクトの参照オブジェクトのインスタンスに設定されていません"。</span><span class="sxs-lookup"><span data-stu-id="6faa1-217">"Unable to create MRSR artifacts: Object reference not set to an instance of an object."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-218">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-218">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-219">インプロセス ホストとホスト インスタンスは、BizTalk Server ランタイムの構成時に作成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="6faa1-219">An In-Process Host and a Host Instance were not created during BizTalk Server Runtime configuration.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-220">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-220">Solution</span></span>  
 <span data-ttu-id="6faa1-221">A4SWIFT 構成を修復するには、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6faa1-221">To repair the A4SWIFT configuration, proceed as follows:</span></span>  
  
-   <span data-ttu-id="6faa1-222">BizTalk Server 管理コンソールで、ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-222">Create a host in BizTalk Server Administration.</span></span> <span data-ttu-id="6faa1-223">今すぐ実行中のインスタンスを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6faa1-223">There is no need to have a running instance now.</span></span>  
  
-   <span data-ttu-id="6faa1-224">RepairBAS ツールを実行、 *%programfiles%*\Microsoft BizTalk Accelerator for swift \sdk\tools フォルダーに、A4SWIFT インストール環境のです。</span><span class="sxs-lookup"><span data-stu-id="6faa1-224">Run the RepairBAS tool in the *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools folder of the A4SWIFT installation.</span></span>  
  
 <span data-ttu-id="6faa1-225">これを行うには、次の手順します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-225">To do so, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="6faa1-226">開始**BizTalk Server 管理コンソール**コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6faa1-226">Start **BizTalk Server Administration** console.</span></span>  
  
2.  <span data-ttu-id="6faa1-227">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**の順に展開**BizTalk グループ**、順に展開**プラットフォームの設定。**</span><span class="sxs-lookup"><span data-stu-id="6faa1-227">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, then expand **BizTalk Group**, and then expand **Platform Settings.**</span></span>  
  
3.  <span data-ttu-id="6faa1-228">右クリック**ホスト**、指す**新規**、し、**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-228">Right-click **Hosts**, point to **New**, and then select **Host**.</span></span>  
  
4.  <span data-ttu-id="6faa1-229">[ホストのプロパティ] 画面で、[全般] ペインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-229">In the Host Properties screen, in the General pane, enter the following:</span></span>  
  
    -   <span data-ttu-id="6faa1-230">ホスト名: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="6faa1-230">Host name: **BizTalkServerApplication**</span></span>  
  
    -   <span data-ttu-id="6faa1-231">型:**インプロセス**</span><span class="sxs-lookup"><span data-stu-id="6faa1-231">Type: **In-Process**</span></span>  
  
    -   <span data-ttu-id="6faa1-232">Windows グループ:   **\<*ドメイン*\>\BizTalk アプリケーション ユーザー * * (またはアカウントを BizTalk プロセスを実行するための BizTalk Server の構成時に設定することアプリケーションの)</span><span class="sxs-lookup"><span data-stu-id="6faa1-232">Windows group: **\<*domain*\>\BizTalk Application Users** (or the account that you set up during BizTalk Server configuration for running BizTalk In-Process applications)</span></span>  
  
    -   <span data-ttu-id="6faa1-233">[オプション] の両方を選択**ホストの追跡を許可する**と**しやすいように、既定のホスト グループに**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-233">In the Options section, select both **Allow Host Tracking** and **Make this the default host in the group**.</span></span>  
  
5.  <span data-ttu-id="6faa1-234">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-234">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="6faa1-235">をクリックして**開始**し、[実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-235">Click **Start** and then click Run.</span></span> <span data-ttu-id="6faa1-236">型**cmd**  をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-236">Type **cmd** and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="6faa1-237">コマンド プロンプトに移動*%programfiles%***\Microsoft BizTalk Accelerator for swift \sdk\tools**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-237">At the command prompt, navigate to *%programfiles%***\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools**.</span></span>  
  
8.  <span data-ttu-id="6faa1-238">型**RepairBAS.exe**キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="6faa1-238">Type **RepairBAS.exe** and then press **Enter**.</span></span>  
  
## <a name="you-must-change-the-bre-deployment-configuration-file-when-running-the-bre-deployment-utility-on-a-64-bit-computer"></a><span data-ttu-id="6faa1-239">64 ビット コンピューターで BRE 配置ユーティリティを実行する場合は、BRE 配置構成ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6faa1-239">You must change the BRE Deployment configuration file when running the BRE Deployment Utility on a 64-bit computer</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6faa1-240">現象</span><span class="sxs-lookup"><span data-stu-id="6faa1-240">Symptom</span></span>  
 <span data-ttu-id="6faa1-241">BRE 配置ユーティリティが正しく機能しないまたは実行すると、64 ビット コンピューターで既定以外のディレクトリ (C:\Program files \microsoft BizTalk Accelerator 用 SWIFT) 以外で 32 ビット コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="6faa1-241">The BRE Deployment Utility does not work correctly when you run it on a 64-bit computer or in a non-default directory (other than C:\Program Files\Microsoft BizTalk Accelerator for SWIFT) on a 32-bit computer.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6faa1-242">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="6faa1-242">Possible Cause</span></span>  
 <span data-ttu-id="6faa1-243">BRE 配置ユーティリティは正しく動きませんにある BREDeployment.exe.config ファイル内のパスを変更するまで、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for swift \sdk\tools フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6faa1-243">The BRE Deployment Utility will not work correctly until you change the paths in the BREDeployment.exe.config file located in the \<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools folder.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6faa1-244">解決方法</span><span class="sxs-lookup"><span data-stu-id="6faa1-244">Solution</span></span>  
 <span data-ttu-id="6faa1-245">ユーティリティの構成を更新するには、メモ帳で、BREDeployment.exe.config を開き、基本ポリシー、スキーマ、およびボキャブラリのディレクトリのフォルダーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6faa1-245">Update the utility's configuration by opening BREDeployment.exe.config in Notepad, and changing the folders for the base policies, schemas, and vocabulary directories.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6faa1-246">参照</span><span class="sxs-lookup"><span data-stu-id="6faa1-246">See Also</span></span>  
 [<span data-ttu-id="6faa1-247">トラブルシューティング: 問題と解決策</span><span class="sxs-lookup"><span data-stu-id="6faa1-247">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)