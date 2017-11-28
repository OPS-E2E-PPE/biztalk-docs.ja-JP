---
title: "BizTalk アセンブリの依存関係を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- viewing, dependencies
- assemblies, dependencies
- managing [assemblies], dependencies
- assemblies, viewing
- viewing, assemblies
- managing [assemblies], viewing
ms.assetid: 872abc99-8248-4397-9fcb-24a0ba6f4757
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99fbc09a5adb59691a4914a8ddc341c8034c8bb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a><span data-ttu-id="a4f49-102">BizTalk アセンブリの依存関係を表示する方法</span><span class="sxs-lookup"><span data-stu-id="a4f49-102">How to View the Dependencies for a BizTalk Assembly</span></span>
<span data-ttu-id="a4f49-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アセンブリに依存関係を持つアイテムの一覧を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4f49-103">This topic describes how to use the BizTalk Server Administration console to view the list of artifacts that have dependencies on a BizTalk assembly.</span></span> <span data-ttu-id="a4f49-104">依存関係とアプリケーションの展開への影響に関する背景情報については、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="a4f49-104">For background information about dependencies and how they affect application deployment, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4f49-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="a4f49-105">Prerequisites</span></span>  
 <span data-ttu-id="a4f49-106">このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4f49-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Operators group.</span></span> <span data-ttu-id="a4f49-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="a4f49-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a><span data-ttu-id="a4f49-108">BizTalk アセンブリの依存関係を表示するには</span><span class="sxs-lookup"><span data-stu-id="a4f49-108">To view the dependencies of a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="a4f49-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="a4f49-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a4f49-110">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、依存関係を表示する BizTalk アセンブリが含まれる BizTalk グループ、BizTalk アセンブリが含まれるアプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="a4f49-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the BizTalk assembly for which you want to view dependencies, and then expand the application containing the BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="a4f49-111">クリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、をクリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="a4f49-111">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="a4f49-112">クリックして、**の依存関係**タブです。</span><span class="sxs-lookup"><span data-stu-id="a4f49-112">Click the **Dependencies** tab.</span></span>  
  
     <span data-ttu-id="a4f49-113">この BizTalk アセンブリに依存関係を持つアイテムの名前と状態が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4f49-113">The name and status of the artifacts that have dependencies on this BizTalk assembly are displayed in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f49-114">参照</span><span class="sxs-lookup"><span data-stu-id="a4f49-114">See Also</span></span>  
 [<span data-ttu-id="a4f49-115">BizTalk アセンブリの管理</span><span class="sxs-lookup"><span data-stu-id="a4f49-115">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)