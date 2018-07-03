---
title: BizTalk Server 2016 のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f5ac913-0734-45b2-8e25-1db146d81858
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f6c6868302554aa14d80c296955e657c9f171d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003739"
---
# <a name="install-biztalk-server-2016"></a><span data-ttu-id="40d27-102">BizTalk Server 2016 のインストール</span><span class="sxs-lookup"><span data-stu-id="40d27-102">Install BizTalk Server 2016</span></span>
<span data-ttu-id="40d27-103">BizTalk Server を単一のサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="40d27-103">Install BizTalk Server on a single computer.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="40d27-104">始める前に</span><span class="sxs-lookup"><span data-stu-id="40d27-104">Before you get started</span></span>

* <span data-ttu-id="40d27-105">**システム管理者** – SQL Server をインストールすると、セットアップによりサインイン アカウントにシステム管理者権限が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="40d27-105">**System Administrator** – When you install SQL Server, setup automatically grants your signed-in account System Administrator rights.</span></span> <span data-ttu-id="40d27-106">BizTalk Server のインストールにもこれらの権限が必要なため、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="40d27-106">Since these rights are also required to install BizTalk Server, do one of the following:</span></span>
  * <span data-ttu-id="40d27-107">SQL Server のインストール時に使用した同じアカウントを使用する。</span><span class="sxs-lookup"><span data-stu-id="40d27-107">Use the same account you used when you installed SQL Server.</span></span>
  * <span data-ttu-id="40d27-108">サインイン アカウントにシステム管理者の権限を付与する。</span><span class="sxs-lookup"><span data-stu-id="40d27-108">Give the signed-in account System Administrator rights.</span></span>
  * <span data-ttu-id="40d27-109">サインイン アカウントがローカルの Administrators グループのメンバーであることを確認する。</span><span class="sxs-lookup"><span data-stu-id="40d27-109">Confirm the signed-in account is a member of the local administrators group.</span></span>
* <span data-ttu-id="40d27-110">**アカウント名** – 可能な場合は常に既定のアカウント名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="40d27-110">**Account names** – Use the default account names whenever possible.</span></span> <span data-ttu-id="40d27-111">BizTalk Server のセットアップでは自動的に既定のアカウントが入力されます。</span><span class="sxs-lookup"><span data-stu-id="40d27-111">The BizTalk Server setup automatically enters the default accounts.</span></span> <span data-ttu-id="40d27-112">ドメイン内に複数の BizTalk Server グループがある場合は、競合を防ぐためアカウント名を変更してください。</span><span class="sxs-lookup"><span data-stu-id="40d27-112">If there are multiple BizTalk Server groups within the Domain, change the account names to avoid conflicts.</span></span> <span data-ttu-id="40d27-113">名前を変更する場合は、BizTalk Server では、サービス アカウントおよび Windows グループに対しては *<NetBIOS ドメイン名>\<ユーザー>* だけがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="40d27-113">If you change the names, BizTalk Server supports only *NetBIOS domain name\user* for service accounts and Windows groups.</span></span>
* <span data-ttu-id="40d27-114">**アカウント名と BAM 管理 Web サービス**: BizTalk Server では、ビルトイン アカウントまたはパスワードなしのアカウントを BAM 管理 Web サービス ユーザーに使用することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40d27-114">**Account names with BAM Management Web Service** – BizTalk Server does not support built-in accounts or accounts without passwords for the BAM Management Web Service User.</span></span> <span data-ttu-id="40d27-115">Web サービスが BizTalk Server データベースにアクセスする際、これらのアカウントでセキュリティの脅威が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40d27-115">The web service accesses the BizTalk Server database and these accounts may suggest a security threat.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="40d27-116">これらの種類のアカウントで BizTalk Server を構成すると成功する場合がありますが、BAM 管理 Web サービスは失敗します。</span><span class="sxs-lookup"><span data-stu-id="40d27-116">Configuring BizTalk Server with these typs of accounts may succeed, but the BAM Management Web Service fails.</span></span> <span data-ttu-id="40d27-117">ビルトイン アカウントまたはパスワードなしのアカウントは、BAM アプリケーション プールに使用できます。</span><span class="sxs-lookup"><span data-stu-id="40d27-117">Built-in accounts or accounts without passwords can be used for the BAM Application pool.</span></span>

* <span data-ttu-id="40d27-118">**BizTalk アセンブリ ビューアー** – 64 ビットのプラットフォームではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="40d27-118">**BizTalk Assembly Viewer** – Not supported on a 64-bit platform.</span></span> 
* <span data-ttu-id="40d27-119">**インストールとアンインストール** – BizTalk Server をアンインストールするには、手動で BizTalk Server データベースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40d27-119">**Install and Uninstall** – Uninstalling BizTalk Server requires manually deleting the BizTalk Server databases.</span></span> <span data-ttu-id="40d27-120">BizTalk Server を開発者または評価担当者としてインストールする場合は、仮想マシンを使用します。</span><span class="sxs-lookup"><span data-stu-id="40d27-120">If you are installing BizTalk Server as a developer or evaluator, use a virtual machine.</span></span> <span data-ttu-id="40d27-121">再インストールが必要になった場合は、アンインストールやデータベースを削除することなく、仮想マシンを簡単にロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="40d27-121">If you need to reinstall, you can easily roll back the virtual machine without having to uninstall and delete the databases.</span></span>
* <span data-ttu-id="40d27-122">**32 ビットおよび 64 ビットのコンピューター** – 32 ビットまたは 64ビットのコンピューターへの BizTalk Server のインストールに大きな違いはありません。</span><span class="sxs-lookup"><span data-stu-id="40d27-122">**32-bit and 64-bit computers** – There are few differences when installing BizTalk Server on 32-bit or 64-bit computer.</span></span> <span data-ttu-id="40d27-123">インストールと構成は 32 ビットおよび 64 ビットのコンピューターに対応しています。</span><span class="sxs-lookup"><span data-stu-id="40d27-123">The installation and configuration covers 32-bit and 64-bit computers.</span></span> <span data-ttu-id="40d27-124">特に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="40d27-124">Any differences are noted.</span></span>
* <span data-ttu-id="40d27-125">**ワークグループ** - 単一コンピューター上のワークグループ環境に BizTalk Server をインストールして構成できます。</span><span class="sxs-lookup"><span data-stu-id="40d27-125">**Workgroups** - Installing and configuring BizTalk Server in the workgroup environment on a single computer is supported.</span></span> <span data-ttu-id="40d27-126">SQL Server と BizTalk Server の機能とコンポーネントは、同じコンピューターにインストールされて構成されます。</span><span class="sxs-lookup"><span data-stu-id="40d27-126">SQL Server and BizTalk Server features and components are installed and configured on the same computer.</span></span>


## <a name="install-biztalk-server"></a><span data-ttu-id="40d27-127">BizTalk Server のインストール</span><span class="sxs-lookup"><span data-stu-id="40d27-127">Install BizTalk Server</span></span>
1. <span data-ttu-id="40d27-128">開いているプログラムをすべて閉じます。</span><span class="sxs-lookup"><span data-stu-id="40d27-128">Close any open programs.</span></span> <span data-ttu-id="40d27-129">BizTalk Server のセットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="40d27-129">Run the BizTalk Server setup as an Administrator.</span></span>
2. <span data-ttu-id="40d27-130">**[Microsoft BizTalk Server 2016 のインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-130">Select **Install Microsoft BizTalk Server 2016**.</span></span>
3. <span data-ttu-id="40d27-131">**[ユーザー名]**、**[組織]**、およびプロダクト キーを入力します。</span><span class="sxs-lookup"><span data-stu-id="40d27-131">Enter your **User name**, your **Organization**, and your product key.</span></span> <span data-ttu-id="40d27-132">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-132">Select **Next**.</span></span>
4. <span data-ttu-id="40d27-133">ライセンス契約に同意して、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-133">Accept the license agreement, and select **Next**.</span></span>
5. <span data-ttu-id="40d27-134">カスタマー エクスペリエンス向上プログラムへの参加を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-134">Choose to participate in the Customer Experience Improvement Program, and select **Next**.</span></span>
6. <span data-ttu-id="40d27-135">インストールするコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-135">Choose which components you want to install:</span></span>

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    <span data-ttu-id="40d27-137">必ず **[追加ソフトウェア]** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="40d27-137">Be sure to select **Additional Software**.</span></span> <span data-ttu-id="40d27-138">インストール場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="40d27-138">You can also change the installation location:</span></span> 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    <span data-ttu-id="40d27-140">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-140">Select **Next**.</span></span>   
  
   7. <span data-ttu-id="40d27-141">選択したコンポーネントによっては、追加の前提条件がある場合があります (ADOMD.NET など)。</span><span class="sxs-lookup"><span data-stu-id="40d27-141">Depending on the components you choose, there may be some additional prerequisites, such as ADOMD.NET.</span></span> <span data-ttu-id="40d27-142">セットアップは、再配布可能なすべての前提条件を自動的にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="40d27-142">The setup can install all the redistributable prerequisites automatically for you.</span></span> <span data-ttu-id="40d27-143">次のような方法があります。</span><span class="sxs-lookup"><span data-stu-id="40d27-143">Your options include:</span></span>
7. <span data-ttu-id="40d27-144">**[必要な再配布可能コンポーネントを手動でインストールする]**: インストール ウィザードが閉じ、不足しているコンポーネントを手動でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="40d27-144">**Manually install the redistributable prerequisites** : The installation wizard closes so you can manually install the missing prerequisites.</span></span>
8. <span data-ttu-id="40d27-145">**[必要な再配布可能コンポーネントを Web から自動的にインストールする]**: 既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="40d27-145">**Automatically install the redistributable prerequisites from the web** : Default.</span></span> <span data-ttu-id="40d27-146">インターネットへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="40d27-146">Requires internet access.</span></span>
9. <span data-ttu-id="40d27-147">**[必要な再配付可能コンポーネントの CAB ファイルをダウンロードする]**: CAB ファイルをダウンロードして後でインストールします。</span><span class="sxs-lookup"><span data-stu-id="40d27-147">**Download the redistributable prerequisites CAB file** : Downloads a CAB file, which you can install later.</span></span>
10. <span data-ttu-id="40d27-148">**[必要な再配布可能コンポーネントを CAB ファイルから自動的にインストールする]**: 前に CAB ファイルをダウンロードしてある場合、このオプションを選択してその CAB ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40d27-148">**Automatically install the redistributable prerequisites from a CAB file**: If you previously downloaded the CAB files, you can select this option to use those CAB files.</span></span> 

    <span data-ttu-id="40d27-149">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-149">Select **Next**.</span></span>
  
11. <span data-ttu-id="40d27-150">概要ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="40d27-150">Review the summary page.</span></span> <span data-ttu-id="40d27-151">変更する場合は、**[戻る]** を選択してコンポーネントをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="40d27-151">To make any changes, select **Back** to check or uncheck any components.</span></span> 

      <span data-ttu-id="40d27-152">システム再起動後に自動的にログオンするには、**[設定]** を選択して、サインイン アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="40d27-152">To enable auto-logon after a system reboot, select **Set**, and enter the sign-in account.</span></span> <span data-ttu-id="40d27-153">これは、BizTalk のセットアップ中にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="40d27-153">This is only enabled during the BizTalk setup.</span></span> <span data-ttu-id="40d27-154">セットアップが完了すると、この設定は無効になります。</span><span class="sxs-lookup"><span data-stu-id="40d27-154">When setup is complete, this setting is disabled.</span></span> 

     <span data-ttu-id="40d27-155">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40d27-155">Select **Install**.</span></span>
  
12. <span data-ttu-id="40d27-156">BizTalk をすぐに構成するには、**[BizTalk Server 構成の開始]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="40d27-156">To configure BizTalk now, check **Launch BizTalk Server Configuration**.</span></span> <span data-ttu-id="40d27-157">BizTalk をすぐに構成しない場合は、このオプションをオフにし、**[完了]** を選択してインストール ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="40d27-157">If you don't want to configure BizTalk now, then uncheck this option, and select **Finish** to close the installation wizard.</span></span> 

<span data-ttu-id="40d27-158">セットアップ ログ ファイルが `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm` などの一時フォルダーに生成されます。</span><span class="sxs-lookup"><span data-stu-id="40d27-158">A setup log file is generated in a temp folder, similar to: `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`</span></span>
  
## <a name="check-the-installation"></a><span data-ttu-id="40d27-159">インストールを確認する</span><span class="sxs-lookup"><span data-stu-id="40d27-159">Check the installation</span></span>

* <span data-ttu-id="40d27-160">BizTalk Server が **[プログラムと機能]** の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="40d27-160">BizTalk Server is listed in **Programs and Features**.</span></span>
* <span data-ttu-id="40d27-161">レジストリ キー `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` に、BizTalk Server のバージョン、インストール パス、エディション、その他の詳細が列記されます。</span><span class="sxs-lookup"><span data-stu-id="40d27-161">The `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` registry key lists the BizTalk Server version, the install path, the edition, and other details.</span></span>
* <span data-ttu-id="40d27-162">BizTalk Server の管理、構成、その他のコンポーネントが、アプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="40d27-162">BizTalk Server Administration, Configuration, and other components are listed in your Apps.</span></span> 

## <a name="next-step"></a><span data-ttu-id="40d27-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="40d27-163">Next step</span></span>
[<span data-ttu-id="40d27-164">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="40d27-164">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)