---
title: 展開して、BizTalk アプリケーションの管理に必要なアクセス許可 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], security
- permissions, EDI adapters
- deploying, security
- security, applications
- security, EDI adapters
- assemblies, permissions
- permissions, deploying
- EDI adapters, security
- permissions, assemblies
- security, assemblies
- permissions, applications
- deploying, permissions
- applications, importing
- applications, exporting
- permissions, exporting
- installing, permissions
- applications, security
- security, permissions
- applications, installing
- assemblies, security
- managing, security
ms.assetid: 4a459ff1-661d-403a-99e0-d54b82e008d0
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4dcf35fb7975e878e6603712d5a56d2bd89a89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019653"
---
# <a name="permissions-required-for-deploying-and-managing-a-biztalk-application"></a><span data-ttu-id="ac189-102">BizTalk アプリケーションの展開と管理に必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-102">Permissions Required for Deploying and Managing a BizTalk Application</span></span>
<span data-ttu-id="ac189-103">アプリケーションの展開には、BizTalk アプリケーションのインポート、エクスポート、およびインストールの他に、Visual Studio から BizTalk アセンブリを展開することが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac189-103">Application deployment includes deploying BizTalk assemblies from Visual Studio as well as importing, exporting, and installing BizTalk applications.</span></span> <span data-ttu-id="ac189-104">これらの作業を実行するために必要な基本的なアクセス許可は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac189-104">The basic permissions you need to perform these tasks are as follows:</span></span>  
  
- <span data-ttu-id="ac189-105">BizTalk Server 管理者グループのメンバーには、Visual Studio から BizTalk アセンブリを展開するために必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-105">As a member of the BizTalk Server Administrators group, you are granted the permissions required to deploy BizTalk assemblies from Visual Studio.</span></span>  
  
- <span data-ttu-id="ac189-106">BizTalk Server 管理者グループのメンバーには、BizTalk アプリケーションを BizTalk グループにインポートするために必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-106">As a member of the BizTalk Server Administrators group, you are granted the permissions required to import BizTalk applications into a BizTalk group.</span></span> <span data-ttu-id="ac189-107">インポート時に、アプリケーション内のアセンブリをグローバル アセンブリ キャッシュ (GAC) に追加するオプションを指定する場合、アセンブリ フォルダーに対する書き込みアクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-107">If the option to add an assembly included in the application to the global assembly cache (GAC) on import has been specified, you must also have Write permissions on the assembly folder.</span></span> <span data-ttu-id="ac189-108">このアクセス許可は、ローカルの Administrators グループのメンバーとして付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-108">As a member of the local Administrators group, you have this permission.</span></span>  
  
- <span data-ttu-id="ac189-109">BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバーとして、次の作業を行うために必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-109">As a member of the BizTalk Server Administrators or BizTalk Server Operators group, you are granted the permissions required to:</span></span>  
  
  -   <span data-ttu-id="ac189-110">BizTalk アプリケーションをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ac189-110">Export BizTalk applications</span></span>  
  
  -   <span data-ttu-id="ac189-111">送信ポート、送信ポート グループ、およびオーケストレーションの開始と停止</span><span class="sxs-lookup"><span data-stu-id="ac189-111">Start and stop send ports, send port groups, and orchestrations</span></span>  
  
  -   <span data-ttu-id="ac189-112">受信場所の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="ac189-112">Enable and disable receive locations</span></span>  
  
  -   <span data-ttu-id="ac189-113">インスタンスの中断、再開、および終了</span><span class="sxs-lookup"><span data-stu-id="ac189-113">Suspend, resume, and terminate instances</span></span>  
  
  -   <span data-ttu-id="ac189-114">起動し、アプリケーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="ac189-114">Start and stop applications</span></span>  
  
- <span data-ttu-id="ac189-115">ローカルの Administrators グループのメンバーには、ローカル コンピューターに BizTalk アプリケーションをインポートするためのアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-115">As a member of the local Administrators group you are granted permissions to install BizTalk applications on the local computer.</span></span>  
  
  <span data-ttu-id="ac189-116">ユーザーがこれらの作業を実行する際には、最も制限されたアクセス許可を提供する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac189-116">You may want to provide the most restrictive permissions for users to perform these tasks.</span></span> <span data-ttu-id="ac189-117">このトピックの残りの部分では、必要なアクセス許可の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac189-117">The remainder of this topic provides more details on the required permissions, as follows.</span></span>  
  
- [<span data-ttu-id="ac189-118">Visual Studio から BizTalk アセンブリを展開するためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-118">Permissions for deploying BizTalk assemblies from Visual Studio</span></span>](#BKMK_Permissions_for_deploying)  
  
- [<span data-ttu-id="ac189-119">アプリケーションをインポートするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-119">Permissions for importing an application</span></span>](#BKMK_Permissions_for_importing)  
  
- [<span data-ttu-id="ac189-120">アプリケーションをエクスポートするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-120">Permissions for exporting an application</span></span>](#BKMK_Permissions_for_exporting)  
  
- [<span data-ttu-id="ac189-121">アプリケーションをインストールするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-121">Permissions for installing an application</span></span>](#BKMK_Permissions_for_installing_an_application)  
  
##  <a name="BKMK_Permissions_for_deploying"></a> <span data-ttu-id="ac189-122">Visual Studio から BizTalk アセンブリを展開するためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-122">Permissions for deploying BizTalk assemblies from Visual Studio</span></span>  
 <span data-ttu-id="ac189-123">Visual Studio から BizTalk アセンブリを展開するには、少なくとも BizTalk 管理データベースに対する書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-123">To deploy BizTalk assemblies from within Visual Studio, you must have Write permission on the BizTalk Management database, at a minimum.</span></span> <span data-ttu-id="ac189-124">このアクセス許可は、BizTalk Server 管理者グループのメンバーとして付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-124">You are granted this permission as a member of the BizTalk Server Administrators group.</span></span>  
  
##  <a name="BKMK_Permissions_for_importing"></a> <span data-ttu-id="ac189-125">アプリケーションをインポートするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-125">Permissions for importing an application</span></span>  
 <span data-ttu-id="ac189-126">BizTalk アプリケーションをインポートするには、少なくとも次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-126">To import a BizTalk application, you must have the following permissions, at a minimum.</span></span> <span data-ttu-id="ac189-127">必要なすべてのアクセス許可は、BizTalk Server 管理者グループのメンバーに付与されますが、アセンブリを GAC にインストールする場合は、アセンブリ フォルダーに対する書き込みアクセス許可も必要になります。</span><span class="sxs-lookup"><span data-stu-id="ac189-127">You are granted all of the required permissions as a member of the BizTalk Server Administrators group, except that if you want to install any assemblies to the GAC, you must also have Write permissions on the assembly folder.</span></span>  
  
|<span data-ttu-id="ac189-128">アイテム</span><span class="sxs-lookup"><span data-stu-id="ac189-128">Item</span></span>|<span data-ttu-id="ac189-129">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-129">Permissions</span></span>|<span data-ttu-id="ac189-130">必要な場合</span><span class="sxs-lookup"><span data-stu-id="ac189-130">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="ac189-131">BizTalk 管理データベース</span><span class="sxs-lookup"><span data-stu-id="ac189-131">BizTalk Management database</span></span>|<span data-ttu-id="ac189-132">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-132">Read/Write</span></span>|<span data-ttu-id="ac189-133">常に必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-133">Always required.</span></span>|  
|<span data-ttu-id="ac189-134">BizTalk ルール エンジン データベース</span><span class="sxs-lookup"><span data-stu-id="ac189-134">BizTalk Rule Engine database</span></span>|<span data-ttu-id="ac189-135">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-135">Read/Write</span></span>|<span data-ttu-id="ac189-136">アプリケーションにルール リソースが含まれている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-136">Required only if the application includes rules resources.</span></span>|  
|<span data-ttu-id="ac189-137">BAM データベース</span><span class="sxs-lookup"><span data-stu-id="ac189-137">BAM database</span></span>|<span data-ttu-id="ac189-138">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-138">Read/Write</span></span>|<span data-ttu-id="ac189-139">アプリケーションに BAM リソースが含まれている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-139">Required only if the application includes BAM resources</span></span>|  
|<span data-ttu-id="ac189-140">グローバル アセンブリ キャッシュ (GAC)</span><span class="sxs-lookup"><span data-stu-id="ac189-140">Global assembly cache (GAC)</span></span>|<span data-ttu-id="ac189-141">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-141">Read/Write</span></span>|<span data-ttu-id="ac189-142">アプリケーションにアセンブリ リソースが含まれている場合、およびアセンブリがインポート時に GAC に追加されていることを指定する場合のみ必要です </span><span class="sxs-lookup"><span data-stu-id="ac189-142">Required only if the application includes assembly resources, and you specify that the assemblies are added to the GAC on import.</span></span> <span data-ttu-id="ac189-143">(以下の「メモ」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ac189-143">(See Note.)</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ac189-144">インポート ウィザードを使用してアセンブリをインポートする場合、アセンブリをグローバル アセンブリ キャッシュ (GAC) に追加するオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac189-144">When importing an assembly by using the Import Wizard, you can specify the option to add the assembly to the global assembly cache (GAC).</span></span> <span data-ttu-id="ac189-145">この場合、アセンブリ フォルダーに対する書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-145">In this case, you must have write permission on the assembly folder.</span></span> <span data-ttu-id="ac189-146">アセンブリ フォルダーの詳細については、[アプリケーションをインストールするためのアクセス許可](#BKMK_Permissions_for_installing_an_application)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac189-146">For more information about the assembly folder, see [Permissions for installing an application](#BKMK_Permissions_for_installing_an_application).</span></span>  
>   
>  <span data-ttu-id="ac189-147">前の一覧に示されていない項目を展開するスクリプトがアプリケーションに含まれている場合、それらの項目を展開するための適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-147">If your application includes a script that deploys any items in addition to those listed, you must have appropriate permissions to deploy the additional items.</span></span>  
  
##  <a name="BKMK_Permissions_for_exporting"></a> <span data-ttu-id="ac189-148">アプリケーションをエクスポートするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-148">Permissions for exporting an application</span></span>  
 <span data-ttu-id="ac189-149">BizTalk アプリケーションをエクスポートするには、少なくとも次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-149">To export a BizTalk application, you must have the following permissions, at a minimum.</span></span> <span data-ttu-id="ac189-150">必要なアクセス許可は、BizTalk Operators グループのメンバーとして付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-150">You are granted the required permissions as a member of the BizTalk Operators group.</span></span>  
  
|<span data-ttu-id="ac189-151">アイテム</span><span class="sxs-lookup"><span data-stu-id="ac189-151">Item</span></span>|<span data-ttu-id="ac189-152">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-152">Permissions</span></span>|<span data-ttu-id="ac189-153">必要な場合</span><span class="sxs-lookup"><span data-stu-id="ac189-153">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="ac189-154">BizTalk 管理データベース</span><span class="sxs-lookup"><span data-stu-id="ac189-154">BizTalk Management database</span></span>|<span data-ttu-id="ac189-155">Read</span><span class="sxs-lookup"><span data-stu-id="ac189-155">Read</span></span>|<span data-ttu-id="ac189-156">常に必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-156">Always required.</span></span>|  
|<span data-ttu-id="ac189-157">BizTalk ルール エンジン データベース</span><span class="sxs-lookup"><span data-stu-id="ac189-157">BizTalk Rule Engine database</span></span>|<span data-ttu-id="ac189-158">Read</span><span class="sxs-lookup"><span data-stu-id="ac189-158">Read</span></span>|<span data-ttu-id="ac189-159">アプリケーションにルール リソースが含まれている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-159">Required only if the application includes rules resources.</span></span>|  
|<span data-ttu-id="ac189-160">証明書ストア</span><span class="sxs-lookup"><span data-stu-id="ac189-160">Certificate store</span></span>|<span data-ttu-id="ac189-161">Read</span><span class="sxs-lookup"><span data-stu-id="ac189-161">Read</span></span>|<span data-ttu-id="ac189-162">アプリケーションに証明書リソースが含まれている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-162">Required only if the application includes certificate resources.</span></span>|  
|<span data-ttu-id="ac189-163">[インターネット インフォメーション サービス]</span><span class="sxs-lookup"><span data-stu-id="ac189-163">Internet Information Services</span></span>|<span data-ttu-id="ac189-164">Read</span><span class="sxs-lookup"><span data-stu-id="ac189-164">Read</span></span>|<span data-ttu-id="ac189-165">アプリケーションに仮想ディレクトリ リソースが含まれている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-165">Required only if the application includes virtual directory resources.</span></span>|  
  
##  <a name="BKMK_Permissions_for_installing_an_application"></a> <span data-ttu-id="ac189-166">アプリケーションをインストールするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-166">Permissions for installing an application</span></span>  
 <span data-ttu-id="ac189-167">既定では、ローカルの Administrators グループのメンバーには、ローカル コンピューターに BizTalk アプリケーションをインポートするために必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="ac189-167">By default, members of the local Administrators group have the permissions required to install BizTalk applications on the local computer.</span></span> <span data-ttu-id="ac189-168">アプリケーションをインストールするユーザーに対して、制限の厳しいアクセス許可を付与する場合は、次の表に示す最低限のアクセス許可を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac189-168">If you want to provide more restricted permissions to users who need to install applications, the following table provides the minimum permissions that you must configure.</span></span> <span data-ttu-id="ac189-169">次に示すアクセス許可以外にも、インストール時に追加のアクセス許可 (新しいデータベースやデータベース テーブルを作成するアクセス許可など) が必要となるリソースがアプリケーションに含まれている場合、それらのアクセス許可も保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac189-169">In addition to these permissions, if your application has resources that require additional permissions to install, such as to create a new database or database table, you must also have these permissions.</span></span>  
  
|<span data-ttu-id="ac189-170">アイテム</span><span class="sxs-lookup"><span data-stu-id="ac189-170">Item</span></span>|<span data-ttu-id="ac189-171">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac189-171">Permissions</span></span>|<span data-ttu-id="ac189-172">必要な場合</span><span class="sxs-lookup"><span data-stu-id="ac189-172">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="ac189-173">証明書ストア</span><span class="sxs-lookup"><span data-stu-id="ac189-173">Certificate store</span></span>|<span data-ttu-id="ac189-174">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-174">Read/Write</span></span>|<span data-ttu-id="ac189-175">アプリケーションに証明書リソースが含まれている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-175">Required only if the application includes certificate resources.</span></span>|  
|<span data-ttu-id="ac189-176">[インターネット インフォメーション サービス]</span><span class="sxs-lookup"><span data-stu-id="ac189-176">Internet Information Services</span></span>|<span data-ttu-id="ac189-177">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-177">Read/Write</span></span>|<span data-ttu-id="ac189-178">アプリケーションに仮想ディレクトリ リソースが含まれている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-178">Required only if the application includes virtual directory resources.</span></span>|  
|<span data-ttu-id="ac189-179">GAC (GAC)</span><span class="sxs-lookup"><span data-stu-id="ac189-179">GAC</span></span>|<span data-ttu-id="ac189-180">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-180">Read/Write</span></span>|<span data-ttu-id="ac189-181">アプリケーションにアセンブリ リソースが含まれている場合、およびアセンブリがインストール時に GAC に追加されるように指定する場合のみ必要です </span><span class="sxs-lookup"><span data-stu-id="ac189-181">Required only if the application includes assembly resources, and you specify that the assemblies are added to the GAC on install.</span></span> <span data-ttu-id="ac189-182">(以下のメモを参照)。</span><span class="sxs-lookup"><span data-stu-id="ac189-182">(See Note, below.)</span></span>|  
|<span data-ttu-id="ac189-183">ファイル システム</span><span class="sxs-lookup"><span data-stu-id="ac189-183">File system</span></span>|<span data-ttu-id="ac189-184">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-184">Read/Write</span></span>|<span data-ttu-id="ac189-185">リソースの対象のプロパティが設定されている場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-185">Required only if a destination property has been set for a resource.</span></span>|  
|<span data-ttu-id="ac189-186">レジストリ</span><span class="sxs-lookup"><span data-stu-id="ac189-186">Registry</span></span>|<span data-ttu-id="ac189-187">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-187">Read/Write</span></span>|<span data-ttu-id="ac189-188">必要な場合、 **regsvcs**または**regasm**マネージ COM または COM + のコンポーネントを含んでいるアセンブリ リソースのプロパティが True に設定します。</span><span class="sxs-lookup"><span data-stu-id="ac189-188">Required if the **regsvcs** or **regasm**property is set to True for an assembly resource containing managed COM or COM+ components.</span></span>|  
|<span data-ttu-id="ac189-189">レジストリ</span><span class="sxs-lookup"><span data-stu-id="ac189-189">Registry</span></span>|<span data-ttu-id="ac189-190">[読み取り/書き込み]</span><span class="sxs-lookup"><span data-stu-id="ac189-190">Read/Write</span></span>|<span data-ttu-id="ac189-191">アプリケーションにアンマネージ COM リソースが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-191">Required if the application includes unmanaged COM resources</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ac189-192">BizTalk Server 管理コンソールで、アセンブリのインストール時に GAC に追加するように指定できます (この操作を行うには、リソース フォルダー内のアセンブリを右クリックし、[変更] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="ac189-192">From the BizTalk Server Administration console, you can specify that an assembly be added to the GAC on installation (right-click the assembly in the resources folder and then click Modify).</span></span> <span data-ttu-id="ac189-193">このオプションを指定した場合、BizTalk アプリケーションのインストールには GAC が含まれているアセンブリ フォルダーに対する書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac189-193">If this option is specified, then installing the BizTalk application requires Write permission on the assembly folder, which contains the GAC.</span></span> <span data-ttu-id="ac189-194">アセンブリ フォルダーのパスは %SystemRoot%\assembly です。</span><span class="sxs-lookup"><span data-stu-id="ac189-194">The path of the assembly folder is %SystemRoot%\assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac189-195">参照</span><span class="sxs-lookup"><span data-stu-id="ac189-195">See Also</span></span>  
 [<span data-ttu-id="ac189-196">アプリケーションの展開のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ac189-196">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)