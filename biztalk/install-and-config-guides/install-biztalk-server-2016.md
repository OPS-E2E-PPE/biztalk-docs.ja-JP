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
ms.openlocfilehash: 97ea71a309d5073f0c1a00adeff5a94ea62cb958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266221"
---
# <a name="install-biztalk-server-2016"></a><span data-ttu-id="aba09-102">BizTalk Server 2016 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aba09-102">Install BizTalk Server 2016</span></span>
<span data-ttu-id="aba09-103">1 台のコンピューターで BizTalk Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aba09-103">Install BizTalk Server on a single computer.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="aba09-104">始める前に</span><span class="sxs-lookup"><span data-stu-id="aba09-104">Before you get started</span></span>

* <span data-ttu-id="aba09-105">**システム管理者**– SQL Server をインストールすると、セットアップがシステム管理者の権限に自動的に、サインイン済みのアカウントに付与されます。</span><span class="sxs-lookup"><span data-stu-id="aba09-105">**System Administrator** – When you install SQL Server, setup automatically grants your signed-in account System Administrator rights.</span></span> <span data-ttu-id="aba09-106">これらの権限は BizTalk Server をインストールする必要であるため、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="aba09-106">Since these rights are also required to install BizTalk Server, do one of the following:</span></span>
  * <span data-ttu-id="aba09-107">SQL Server をインストールしたときに使用した同じアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="aba09-107">Use the same account you used when you installed SQL Server.</span></span>
  * <span data-ttu-id="aba09-108">サインイン アカウントにシステム管理者の権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="aba09-108">Give the signed-in account System Administrator rights.</span></span>
  * <span data-ttu-id="aba09-109">サインイン アカウントがローカルの administrators グループのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aba09-109">Confirm the signed-in account is a member of the local administrators group.</span></span>
* <span data-ttu-id="aba09-110">**アカウント名**– 可能な限り、既定のアカウント名を使用します。</span><span class="sxs-lookup"><span data-stu-id="aba09-110">**Account names** – Use the default account names whenever possible.</span></span> <span data-ttu-id="aba09-111">BizTalk Server のセットアップでは、既定のアカウントが自動的に入力します。</span><span class="sxs-lookup"><span data-stu-id="aba09-111">The BizTalk Server setup automatically enters the default accounts.</span></span> <span data-ttu-id="aba09-112">ドメイン内の複数の BizTalk Server グループがある場合は、競合を回避するために、アカウント名を変更します。</span><span class="sxs-lookup"><span data-stu-id="aba09-112">If there are multiple BizTalk Server groups within the Domain, change the account names to avoid conflicts.</span></span> <span data-ttu-id="aba09-113">名前を変更する場合は、BizTalk Server のみをサポート*NetBIOS ドメイン名 \ ユーザー*のサービス アカウントと Windows グループ。</span><span class="sxs-lookup"><span data-stu-id="aba09-113">If you change the names, BizTalk Server supports only *NetBIOS domain name\user* for service accounts and Windows groups.</span></span>
* <span data-ttu-id="aba09-114">**アカウント名と BAM 管理 Web サービス**– BizTalk Server はサポートされませんビルトイン アカウントまたはパスワードなしのアカウントを BAM 管理 Web サービス ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="aba09-114">**Account names with BAM Management Web Service** – BizTalk Server does not support built-in accounts or accounts without passwords for the BAM Management Web Service User.</span></span> <span data-ttu-id="aba09-115">BizTalk Server データベースを web サービスにアクセスし、これらのアカウントがセキュリティの脅威をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aba09-115">The web service accesses the BizTalk Server database and these accounts may suggest a security threat.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="aba09-116">これらの種類のアカウントを BizTalk Server の構成が成功しないが、BAM 管理 Web サービスが失敗します。</span><span class="sxs-lookup"><span data-stu-id="aba09-116">Configuring BizTalk Server with these typs of accounts may succeed, but the BAM Management Web Service fails.</span></span> <span data-ttu-id="aba09-117">BAM アプリケーション プールのビルトイン アカウントまたはパスワードなしのアカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aba09-117">Built-in accounts or accounts without passwords can be used for the BAM Application pool.</span></span>

* <span data-ttu-id="aba09-118">**BizTalk アセンブリ ビューアー** – 64 ビット プラットフォームでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aba09-118">**BizTalk Assembly Viewer** – Not supported on a 64-bit platform.</span></span> 
* <span data-ttu-id="aba09-119">**インストールし、アンインストール**– BizTalk Server のアンインストールでは、BizTalk Server データベースを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aba09-119">**Install and Uninstall** – Uninstalling BizTalk Server requires manually deleting the BizTalk Server databases.</span></span> <span data-ttu-id="aba09-120">開発者またはエバリュエーターとして BizTalk Server をインストールする場合は、仮想マシンを使用します。</span><span class="sxs-lookup"><span data-stu-id="aba09-120">If you are installing BizTalk Server as a developer or evaluator, use a virtual machine.</span></span> <span data-ttu-id="aba09-121">再インストールする必要がある場合に簡単にロールバックできます仮想マシンをアンインストールし、データベースを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aba09-121">If you need to reinstall, you can easily roll back the virtual machine without having to uninstall and delete the databases.</span></span>
* <span data-ttu-id="aba09-122">**32 ビットおよび 64 ビット コンピューター** – 32 ビットまたは 64 ビット コンピューターで BizTalk Server をインストールするときにいくつか違いがあります。</span><span class="sxs-lookup"><span data-stu-id="aba09-122">**32-bit and 64-bit computers** – There are few differences when installing BizTalk Server on 32-bit or 64-bit computer.</span></span> <span data-ttu-id="aba09-123">インストールと構成は、32 ビットおよび 64 ビット コンピューターをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aba09-123">The installation and configuration covers 32-bit and 64-bit computers.</span></span> <span data-ttu-id="aba09-124">相違点が記載されています。</span><span class="sxs-lookup"><span data-stu-id="aba09-124">Any differences are noted.</span></span>
* <span data-ttu-id="aba09-125">**ワークグループ**-をインストールして、1 台のコンピューター上のワークグループ環境での BizTalk Server の構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aba09-125">**Workgroups** - Installing and configuring BizTalk Server in the workgroup environment on a single computer is supported.</span></span> <span data-ttu-id="aba09-126">SQL Server と BizTalk Server の機能とコンポーネントがインストールされ、同じコンピューター上で構成します。</span><span class="sxs-lookup"><span data-stu-id="aba09-126">SQL Server and BizTalk Server features and components are installed and configured on the same computer.</span></span>


## <a name="install-biztalk-server"></a><span data-ttu-id="aba09-127">BizTalk Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aba09-127">Install BizTalk Server</span></span>
1. <span data-ttu-id="aba09-128">開いているプログラムを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aba09-128">Close any open programs.</span></span> <span data-ttu-id="aba09-129">BizTalk Server のセットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="aba09-129">Run the BizTalk Server setup as an Administrator.</span></span>
2. <span data-ttu-id="aba09-130">選択**Microsoft BizTalk Server 2016 のインストール**します。</span><span class="sxs-lookup"><span data-stu-id="aba09-130">Select **Install Microsoft BizTalk Server 2016**.</span></span>
3. <span data-ttu-id="aba09-131">入力、**ユーザー名**、**組織**、およびプロダクト キー。</span><span class="sxs-lookup"><span data-stu-id="aba09-131">Enter your **User name**, your **Organization**, and your product key.</span></span> <span data-ttu-id="aba09-132">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aba09-132">Select **Next**.</span></span>
4. <span data-ttu-id="aba09-133">ライセンス条項に同意し、選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="aba09-133">Accept the license agreement, and select **Next**.</span></span>
5. <span data-ttu-id="aba09-134">顧客のエクスペリエンス向上プログラムに参加し、選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="aba09-134">Choose to participate in the Customer Experience Improvement Program, and select **Next**.</span></span>
6. <span data-ttu-id="aba09-135">インストールするコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="aba09-135">Choose which components you want to install:</span></span>

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    <span data-ttu-id="aba09-137">必ず選択**追加ソフトウェア**します。</span><span class="sxs-lookup"><span data-stu-id="aba09-137">Be sure to select **Additional Software**.</span></span> <span data-ttu-id="aba09-138">インストール場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="aba09-138">You can also change the installation location:</span></span> 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    <span data-ttu-id="aba09-140">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aba09-140">Select **Next**.</span></span>   
  
   7. <span data-ttu-id="aba09-141">選択したコンポーネント、によっていくつか追加の前提条件、ADOMD.NET などがあります。</span><span class="sxs-lookup"><span data-stu-id="aba09-141">Depending on the components you choose, there may be some additional prerequisites, such as ADOMD.NET.</span></span> <span data-ttu-id="aba09-142">自動的に再配布可能なすべての前提条件をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aba09-142">The setup can install all the redistributable prerequisites automatically for you.</span></span> <span data-ttu-id="aba09-143">次のような方法があります。</span><span class="sxs-lookup"><span data-stu-id="aba09-143">Your options include:</span></span>
7. <span data-ttu-id="aba09-144">**再頒布可能パッケージの前提条件を手動でインストール**:前提条件を手動でインストールできるようにインストール ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aba09-144">**Manually install the redistributable prerequisites** : The installation wizard closes so you can manually install the missing prerequisites.</span></span>
8. <span data-ttu-id="aba09-145">**Web サイトから再頒布可能パッケージのコンポーネントを自動的にインストール**:既定値です。</span><span class="sxs-lookup"><span data-stu-id="aba09-145">**Automatically install the redistributable prerequisites from the web** : Default.</span></span> <span data-ttu-id="aba09-146">インターネットへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="aba09-146">Requires internet access.</span></span>
9. <span data-ttu-id="aba09-147">**再頒布可能コンポーネントの CAB ファイルをダウンロード**:後でインストールすることができる CAB ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aba09-147">**Download the redistributable prerequisites CAB file** : Downloads a CAB file, which you can install later.</span></span>
10. <span data-ttu-id="aba09-148">**再頒布可能パッケージの必須コンポーネントを CAB ファイルから自動的にインストール**:以前に CAB ファイルをダウンロードした場合は、その CAB ファイルを使用するには、このオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="aba09-148">**Automatically install the redistributable prerequisites from a CAB file**: If you previously downloaded the CAB files, you can select this option to use those CAB files.</span></span> 

    <span data-ttu-id="aba09-149">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aba09-149">Select **Next**.</span></span>
  
11. <span data-ttu-id="aba09-150">[概要] ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="aba09-150">Review the summary page.</span></span> <span data-ttu-id="aba09-151">変更を加えるには、次のように選択します。**戻る**チェックまたはすべてのコンポーネントをオフにします。</span><span class="sxs-lookup"><span data-stu-id="aba09-151">To make any changes, select **Back** to check or uncheck any components.</span></span> 

      <span data-ttu-id="aba09-152">自動ログオンをできるように、システムの再起動後、次のように選択します。**設定**、サインイン アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="aba09-152">To enable auto-logon after a system reboot, select **Set**, and enter the sign-in account.</span></span> <span data-ttu-id="aba09-153">これは、BizTalk セットアップ中にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="aba09-153">This is only enabled during the BizTalk setup.</span></span> <span data-ttu-id="aba09-154">セットアップが完了したら、この設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="aba09-154">When setup is complete, this setting is disabled.</span></span> 

     <span data-ttu-id="aba09-155">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aba09-155">Select **Install**.</span></span>
  
12. <span data-ttu-id="aba09-156">確認すると、BizTalk を構成するには、 **BizTalk Server 構成**します。</span><span class="sxs-lookup"><span data-stu-id="aba09-156">To configure BizTalk now, check **Launch BizTalk Server Configuration**.</span></span> <span data-ttu-id="aba09-157">BizTalk をすぐに構成しない場合は、このオプションをオフにし、選択**完了**インストール ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="aba09-157">If you don't want to configure BizTalk now, then uncheck this option, and select **Finish** to close the installation wizard.</span></span> 

<span data-ttu-id="aba09-158">ような一時フォルダーには、セットアップ ログ ファイルが生成されます。 `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`</span><span class="sxs-lookup"><span data-stu-id="aba09-158">A setup log file is generated in a temp folder, similar to: `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`</span></span>
  
## <a name="check-the-installation"></a><span data-ttu-id="aba09-159">インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="aba09-159">Check the installation</span></span>

* <span data-ttu-id="aba09-160">BizTalk Server が記載**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="aba09-160">BizTalk Server is listed in **Programs and Features**.</span></span>
* <span data-ttu-id="aba09-161">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0`レジストリ キーには、BizTalk Server のバージョン、インストール パス、エディション、およびその他の詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="aba09-161">The `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` registry key lists the BizTalk Server version, the install path, the edition, and other details.</span></span>
* <span data-ttu-id="aba09-162">BizTalk Server 管理、構成、およびその他のコンポーネントは、アプリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aba09-162">BizTalk Server Administration, Configuration, and other components are listed in your Apps.</span></span> 

## <a name="next-step"></a><span data-ttu-id="aba09-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="aba09-163">Next step</span></span>
[<span data-ttu-id="aba09-164">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="aba09-164">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)