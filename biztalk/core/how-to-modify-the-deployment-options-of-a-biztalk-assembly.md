---
title: BizTalk アセンブリの展開オプションを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16ba9dc20893a2899f7fbed78aefb3d1a0bcfdb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973587"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="d3d22-102">BizTalk アセンブリの展開オプションを変更する方法</span><span class="sxs-lookup"><span data-stu-id="d3d22-102">How to Modify the Deployment Options of a BizTalk Assembly</span></span>
<span data-ttu-id="d3d22-103">このトピックでは、BizTalk Server 管理コンソールを使用して BizTalk アセンブリの展開オプションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3d22-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of a BizTalk assembly.</span></span>  
  
 <span data-ttu-id="d3d22-104">次の展開オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d3d22-104">You can specify the following deployment options:</span></span>  
  
-   <span data-ttu-id="d3d22-105">**グローバル アセンブリ キャッシュへの追加に (gacutil) のリソースを追加します。**</span><span class="sxs-lookup"><span data-stu-id="d3d22-105">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="d3d22-106">このオプションをオンにすると、アセンブリをアプリケーションに追加するとき、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d3d22-106">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="d3d22-107">さらに、後で、アセンブリを更新する場合 (右クリックし、をクリックして**更新**)、アセンブリが GAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="d3d22-107">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="d3d22-108">アセンブリが現在 GAC に存在する場合は、このオプションのチェック ボックスをオフにしても、アセンブリが GAC から削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d3d22-108">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="d3d22-109">**MSI ファイルのインポート (gacutil) のグローバル アセンブリ キャッシュに追加します。**</span><span class="sxs-lookup"><span data-stu-id="d3d22-109">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="d3d22-110">アプリケーションの .msi ファイルがインポートされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d3d22-110">Install the assembly to the GAC on the local computer when the application .msi file is imported.</span></span>  
  
-   <span data-ttu-id="d3d22-111">**MSI ファイル インストール (gacutil)、グローバル アセンブリ キャッシュに追加します。**</span><span class="sxs-lookup"><span data-stu-id="d3d22-111">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="d3d22-112">アプリケーションが .msi ファイルからインストールされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d3d22-112">Install the assembly to the GAC on the local computer when the application is installed from the .msi file.</span></span>  
  
-   <span data-ttu-id="d3d22-113">**アップグレード先の場所:** パスをアプリケーションがインストールされているとき、アセンブリ ファイルにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="d3d22-113">**Destination location:** Path to which the assembly file will be copied when the application is installed.</span></span> <span data-ttu-id="d3d22-114">パスを指定しないと、インストール時にローカル ファイル システムにアセンブリ ファイルがコピーされません。</span><span class="sxs-lookup"><span data-stu-id="d3d22-114">If a path is not provided, the assembly file is not copied to the local file system on installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3d22-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="d3d22-115">Prerequisites</span></span>  
 <span data-ttu-id="d3d22-116">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d22-116">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d3d22-117">また、アセンブリを直ちに GAC に追加するオプションを選択する場合は、アカウントはローカルの管理者グループのメンバーである必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d3d22-117">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="d3d22-118">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3d22-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="d3d22-119">BizTalk アセンブリの展開オプションを変更するには</span><span class="sxs-lookup"><span data-stu-id="d3d22-119">To modify the deployment options of a BizTalk assembly</span></span>  
  
1. <span data-ttu-id="d3d22-120">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="d3d22-120">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d3d22-121">コンソール ツリーで BizTalk Server 管理コンソールを展開し、展開オプションを変更する対象の BizTalk アセンブリが含まれる BizTalk グループを展開し、BizTalk アセンブリを格納しているアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="d3d22-121">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the BizTalk assembly for which to modify deployment options, and then expand the application containing the BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="d3d22-122">をクリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、順にクリックします**変更**します。</span><span class="sxs-lookup"><span data-stu-id="d3d22-122">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="d3d22-123">**オプション**、必要な展開オプションのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d22-123">In **Options**, select the check boxes of the deployment options that you want.</span></span>  
  
5. <span data-ttu-id="d3d22-124">必要に応じて、**先**アセンブリが、アプリケーションがインストールされているときにコピーされ、をクリックし、パスを編集する**OK**。</span><span class="sxs-lookup"><span data-stu-id="d3d22-124">If necessary, in **Destination location** edit the path where the assembly will be copied when the application is installed, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d22-125">参照</span><span class="sxs-lookup"><span data-stu-id="d3d22-125">See Also</span></span>  
 [<span data-ttu-id="d3d22-126">BizTalk アセンブリの管理</span><span class="sxs-lookup"><span data-stu-id="d3d22-126">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)