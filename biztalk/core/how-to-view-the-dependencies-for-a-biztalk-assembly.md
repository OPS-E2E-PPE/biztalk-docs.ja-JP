---
title: BizTalk アセンブリの依存関係を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- viewing, dependencies
- assemblies, dependencies
- managing [assemblies], dependencies
- assemblies, viewing
- viewing, assemblies
- managing [assemblies], viewing
ms.assetid: 872abc99-8248-4397-9fcb-24a0ba6f4757
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b02a773ff51c35de2505336137dfa6c4c11c0825
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001219"
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a><span data-ttu-id="f4c7b-102">BizTalk アセンブリの依存関係を表示する方法</span><span class="sxs-lookup"><span data-stu-id="f4c7b-102">How to View the Dependencies for a BizTalk Assembly</span></span>
<span data-ttu-id="f4c7b-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アセンブリに依存関係を持つアイテムの一覧を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-103">This topic describes how to use the BizTalk Server Administration console to view the list of artifacts that have dependencies on a BizTalk assembly.</span></span> <span data-ttu-id="f4c7b-104">依存関係とアプリケーションの配置への影響についての背景については、[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-104">For background information about dependencies and how they affect application deployment, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4c7b-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="f4c7b-105">Prerequisites</span></span>  
 <span data-ttu-id="f4c7b-106">このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Operators group.</span></span> <span data-ttu-id="f4c7b-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a><span data-ttu-id="f4c7b-108">BizTalk アセンブリの依存関係を表示するには</span><span class="sxs-lookup"><span data-stu-id="f4c7b-108">To view the dependencies of a BizTalk assembly</span></span>  
  
1. <span data-ttu-id="f4c7b-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f4c7b-110">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、依存関係を表示する BizTalk アセンブリが含まれる BizTalk グループ、BizTalk アセンブリが含まれるアプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the BizTalk assembly for which you want to view dependencies, and then expand the application containing the BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="f4c7b-111">をクリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、順にクリックします**変更**します。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-111">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="f4c7b-112">をクリックして、**依存関係**タブ。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-112">Click the **Dependencies** tab.</span></span>  
  
    <span data-ttu-id="f4c7b-113">この BizTalk アセンブリに依存関係を持つアイテムの名前と状態が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4c7b-113">The name and status of the artifacts that have dependencies on this BizTalk assembly are displayed in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c7b-114">参照</span><span class="sxs-lookup"><span data-stu-id="f4c7b-114">See Also</span></span>  
 [<span data-ttu-id="f4c7b-115">BizTalk アセンブリの管理</span><span class="sxs-lookup"><span data-stu-id="f4c7b-115">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)