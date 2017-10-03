---
title: ".NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], deploying
- deploying, virtual directories
- managing [applications], deploying
- managing [applications], modifying
- definition files [BAM], modifying
- modifying, artifacts
- deploying, artifacts
- managing [certificates], deploying
- deploying, .NET assemblies
- COM components, deploying
- definition files [BAM], deploying
- virtual directories, deploying
- deploying, certificates
- modifying, deployment options
- virtual directories, modifying
- deploying, COM components
ms.assetid: 4955d420-d9ff-4d5a-82f4-fb16477a828c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6469f06b7b42ae1f8b45419fa0214682bd9fa67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a><span data-ttu-id="2d7cb-102">.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法</span><span class="sxs-lookup"><span data-stu-id="2d7cb-102">How to Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>
<span data-ttu-id="2d7cb-103">このトピックでは、BizTalk Server 管理コンソールを使用して次のリソース アイテムの展開オプションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of the following resource artifacts:</span></span>  
  
-   <span data-ttu-id="2d7cb-104">.NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="2d7cb-104">.NET assemblies</span></span>  
  
-   <span data-ttu-id="2d7cb-105">COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2d7cb-105">COM components</span></span>  
  
-   <span data-ttu-id="2d7cb-106">アドホック ファイル</span><span class="sxs-lookup"><span data-stu-id="2d7cb-106">Ad hoc files</span></span>  
  
-   <span data-ttu-id="2d7cb-107">BAM アイテム</span><span class="sxs-lookup"><span data-stu-id="2d7cb-107">BAM artifacts</span></span>  
  
 <span data-ttu-id="2d7cb-108">展開プロパティを変更して、アプリケーションをローカル コンピューターにインストールするときにアイテム ファイルがコピーされるコピー先の場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-108">You might want to modify the deployment properties to change the destination location to which the artifact file will be copied when the application is installed on the local computer.</span></span> <span data-ttu-id="2d7cb-109">パスを指定しない場合、ファイルはインストール時にローカル コンピューターにコピーされません。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-109">If you do not provide a path, the file will not be copied to the local computer on installation.</span></span>  
  
 <span data-ttu-id="2d7cb-110">また、.NET アセンブリの次のオプションを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-110">In addition, you might want to modify the following options for a .NET assembly:</span></span>  
  
-   <span data-ttu-id="2d7cb-111">**グローバル アセンブリ キャッシュに追加のリソース (gacutil) を追加します。**</span><span class="sxs-lookup"><span data-stu-id="2d7cb-111">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="2d7cb-112">このオプションをオンにすると、アセンブリをアプリケーションに追加するとき、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-112">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="2d7cb-113">また、後で、アセンブリを更新する場合 (右クリックし、をクリックして**更新**)、アセンブリが GAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-113">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="2d7cb-114">アセンブリが現在 GAC に存在する場合は、このオプションのチェック ボックスをオフにしても、アセンブリが GAC から削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-114">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="2d7cb-115">**MSI ファイル インポート (します gacutil) のグローバル アセンブリ キャッシュに追加します。**</span><span class="sxs-lookup"><span data-stu-id="2d7cb-115">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="2d7cb-116">このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-116">When you select this option, if the application is exported to an .msi file, and the .msi file is imported into a BizTalk group, the assembly is installed in the GAC on the local computer as part of the import process.</span></span>  
  
-   <span data-ttu-id="2d7cb-117">**MSI ファイル インストール (します gacutil) のグローバル アセンブリ キャッシュに追加します。**</span><span class="sxs-lookup"><span data-stu-id="2d7cb-117">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="2d7cb-118">このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、アプリケーションが .msi ファイルからコンピューターにインストールされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-118">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, the assembly is installed in the GAC on the local computer as part of the installation process.</span></span>  
  
-   <span data-ttu-id="2d7cb-119">**COM コンポーネント (regasm) に表示されるようにします。**</span><span class="sxs-lookup"><span data-stu-id="2d7cb-119">**Make visible to COM components (regasm).**</span></span> <span data-ttu-id="2d7cb-120">このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージ COM アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-120">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="2d7cb-121">このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-121">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
-   <span data-ttu-id="2d7cb-122">**登録サービスのコンポーネント (regsvcs)。**</span><span class="sxs-lookup"><span data-stu-id="2d7cb-122">**Register serviced components (regsvcs).**</span></span> <span data-ttu-id="2d7cb-123">このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージ COM+ アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-123">When you select this option, if the application is exported to an .msi file, and the application is installed on a computer from the .msi file, a managed COM+ assembly is added to the Windows registry on the local computer as part of the installation process.</span></span> <span data-ttu-id="2d7cb-124">このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-124">If you specify this option, you must also specify a location for the file in Destination.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2d7cb-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="2d7cb-125">Prerequisites</span></span>  
 <span data-ttu-id="2d7cb-126">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-126">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="2d7cb-127">また、アセンブリを直ちに GAC に追加するオプションを選択する場合は、アカウントはローカルの管理者グループのメンバーである必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-127">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="2d7cb-128">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-128">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a><span data-ttu-id="2d7cb-129">リソース アイテムの展開プロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="2d7cb-129">To modify the deployment properties of a resource artifact</span></span>  
  
1.  <span data-ttu-id="2d7cb-130">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-130">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2d7cb-131">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、展開オプションを変更するアイテムが含まれる BizTalk グループ、アイテムが含まれるアプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-131">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the artifact for which to modify deployment options, and then expand the application containing the artifact.</span></span>  
  
3.  <span data-ttu-id="2d7cb-132">クリックして、**リソース**フォルダーは、アイテムを右クリックし、をクリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-132">Click the **Resources** folder, right-click the artifact, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="2d7cb-133">**オプション** タブで、必要に応じて展開オプションを変更し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2d7cb-133">On the **Options** tab, modify the deployment options as necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7cb-134">参照</span><span class="sxs-lookup"><span data-stu-id="2d7cb-134">See Also</span></span>  
 [<span data-ttu-id="2d7cb-135">.NET アセンブリ、証明書、およびその他のリソースの管理</span><span class="sxs-lookup"><span data-stu-id="2d7cb-135">Managing .NET Assemblies, Certificates, and Other Resources</span></span>](../core/managing-net-assemblies-certificates-and-other-resources.md)