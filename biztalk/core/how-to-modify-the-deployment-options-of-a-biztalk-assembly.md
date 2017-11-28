---
title: "BizTalk アセンブリの展開オプションを変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416fc38c8768e7391659d133877b2ae59e704463
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="0f779-102">BizTalk アセンブリの展開オプションを変更する方法</span><span class="sxs-lookup"><span data-stu-id="0f779-102">How to Modify the Deployment Options of a BizTalk Assembly</span></span>
<span data-ttu-id="0f779-103">このトピックでは、BizTalk Server 管理コンソールを使用して BizTalk アセンブリの展開オプションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f779-103">This topic describes how to use the BizTalk Server Administration console to modify the deployment options of a BizTalk assembly.</span></span>  
  
 <span data-ttu-id="0f779-104">次の展開オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0f779-104">You can specify the following deployment options:</span></span>  
  
-   <span data-ttu-id="0f779-105">**グローバル アセンブリ キャッシュに追加のリソース (gacutil) を追加します。**</span><span class="sxs-lookup"><span data-stu-id="0f779-105">**Add to the global assembly cache on add resource (gacutil).**</span></span> <span data-ttu-id="0f779-106">このオプションをオンにすると、アセンブリをアプリケーションに追加するとき、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="0f779-106">When you select this option, the assembly is added to the global assembly cache (GAC) on the local computer when the assembly is added to the application.</span></span> <span data-ttu-id="0f779-107">また、後で、アセンブリを更新する場合 (右クリックし、をクリックして**更新**)、アセンブリが GAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="0f779-107">In addition, if you later refresh the assembly (right-click it and click **Refresh**), the assembly is added to the GAC.</span></span> <span data-ttu-id="0f779-108">アセンブリが現在 GAC に存在する場合は、このオプションのチェック ボックスをオフにしても、アセンブリが GAC から削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="0f779-108">Clearing the check box for this option does not remove the assembly from the GAC, if it currently exists there.</span></span>  
  
-   <span data-ttu-id="0f779-109">**MSI ファイル インポート (します gacutil) のグローバル アセンブリ キャッシュに追加します。**</span><span class="sxs-lookup"><span data-stu-id="0f779-109">**Add to the global assembly cache on MSI file import (gacutil).**</span></span> <span data-ttu-id="0f779-110">アプリケーションの .msi ファイルがインポートされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f779-110">Install the assembly to the GAC on the local computer when the application .msi file is imported.</span></span>  
  
-   <span data-ttu-id="0f779-111">**MSI ファイル インストール (します gacutil) のグローバル アセンブリ キャッシュに追加します。**</span><span class="sxs-lookup"><span data-stu-id="0f779-111">**Add to the global assembly cache on MSI file install (gacutil).**</span></span> <span data-ttu-id="0f779-112">アプリケーションが .msi ファイルからインストールされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f779-112">Install the assembly to the GAC on the local computer when the application is installed from the .msi file.</span></span>  
  
-   <span data-ttu-id="0f779-113">**移行先の場所:**コピー先となるアセンブリ ファイルは、アプリケーションがインストールされているときにパスします。</span><span class="sxs-lookup"><span data-stu-id="0f779-113">**Destination location:** Path to which the assembly file will be copied when the application is installed.</span></span> <span data-ttu-id="0f779-114">パスを指定しないと、インストール時にローカル ファイル システムにアセンブリ ファイルがコピーされません。</span><span class="sxs-lookup"><span data-stu-id="0f779-114">If a path is not provided, the assembly file is not copied to the local file system on installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f779-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="0f779-115">Prerequisites</span></span>  
 <span data-ttu-id="0f779-116">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f779-116">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0f779-117">また、アセンブリを直ちに GAC に追加するオプションを選択する場合は、アカウントはローカルの管理者グループのメンバーである必要もあります。</span><span class="sxs-lookup"><span data-stu-id="0f779-117">In addition, if you select an option that immediately adds the assembly to the GAC, your account must also be a member of the local Administrator's group.</span></span> <span data-ttu-id="0f779-118">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="0f779-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a><span data-ttu-id="0f779-119">BizTalk アセンブリの展開オプションを変更するには</span><span class="sxs-lookup"><span data-stu-id="0f779-119">To modify the deployment options of a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="0f779-120">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="0f779-120">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0f779-121">コンソール ツリーで、[[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理]、展開オプションを変更する BizTalk アセンブリが含まれる BizTalk グループ、BizTalk アセンブリが含まれるアプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="0f779-121">In the console tree, expand [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration, expand the BizTalk group containing the BizTalk assembly for which to modify deployment options, and then expand the application containing the BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="0f779-122">クリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、をクリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="0f779-122">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="0f779-123">**オプション**、必要な展開オプションのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0f779-123">In **Options**, select the check boxes of the deployment options that you want.</span></span>  
  
5.  <span data-ttu-id="0f779-124">必要に応じて、**先の場所**アセンブリが、アプリケーションがインストールされているときにコピーされ、をクリックし、パスを編集**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0f779-124">If necessary, in **Destination location** edit the path where the assembly will be copied when the application is installed, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f779-125">参照</span><span class="sxs-lookup"><span data-stu-id="0f779-125">See Also</span></span>  
 [<span data-ttu-id="0f779-126">BizTalk アセンブリの管理</span><span class="sxs-lookup"><span data-stu-id="0f779-126">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)