---
title: アプリケーションの参照を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, viewing
- applications, referencing
ms.assetid: 5f1026e1-c73e-495d-8160-9ba68f38b9d8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a23583edde1e1edbf4f0613904ebf24271a225f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979275"
---
# <a name="how-to-view-the-references-of-an-application"></a><span data-ttu-id="96f63-102">アプリケーションの参照を表示する方法</span><span class="sxs-lookup"><span data-stu-id="96f63-102">How to View the References of an Application</span></span>
<span data-ttu-id="96f63-103">このトピックでは、BizTalk Server 管理コンソールを使用して、現在のアプリケーションが参照しているアプリケーションの一覧を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96f63-103">This topic describes how to use the BizTalk Server Administration console to view the list of applications to which the current application has references.</span></span> <span data-ttu-id="96f63-104">参照を追加する方法の詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="96f63-104">For more information about adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span> <span data-ttu-id="96f63-105">このアプリケーションを参照しているアプリケーションの一覧も表示できます。</span><span class="sxs-lookup"><span data-stu-id="96f63-105">You can also view the list of applications that have references to this application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96f63-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="96f63-106">Prerequisites</span></span>  
 <span data-ttu-id="96f63-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96f63-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="96f63-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="96f63-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-references-for-an-application"></a><span data-ttu-id="96f63-109">アプリケーションの参照を表示するには</span><span class="sxs-lookup"><span data-stu-id="96f63-109">To view the references for an application</span></span>  
  
1. <span data-ttu-id="96f63-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="96f63-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="96f63-111">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、アプリケーションを表示する をクリックするが参照を右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="96f63-111">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click the application whose references you want to view, and click **Properties**.</span></span>  
  
3. <span data-ttu-id="96f63-112">[プロパティ] ページの左側のウィンドウで次のようにクリックします。**参照**します。</span><span class="sxs-lookup"><span data-stu-id="96f63-112">In the left pane of the properties page, click **References**.</span></span>  
  
    <span data-ttu-id="96f63-113">このアプリケーションが参照しているアプリケーションの一覧が、右ペインの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="96f63-113">The applications to which this application refers are listed in the upper section of the right pane.</span></span> <span data-ttu-id="96f63-114">このアプリケーションを参照しているアプリケーションの一覧は、右ペインの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="96f63-114">The applications that refer to this application are listed in the lower section of the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f63-115">参照</span><span class="sxs-lookup"><span data-stu-id="96f63-115">See Also</span></span>  
 [<span data-ttu-id="96f63-116">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="96f63-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)