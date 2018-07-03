---
title: アプリケーションの名前を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5620bc481f5350e752b71a1706e187016ed25977
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992443"
---
# <a name="how-to-change-the-name-of-an-application"></a><span data-ttu-id="f6ce3-102">アプリケーションの名前を変更する方法</span><span class="sxs-lookup"><span data-stu-id="f6ce3-102">How to Change the Name of an Application</span></span>
<span data-ttu-id="f6ce3-103">このトピックでは、BizTalk Server 管理コンソールを使用して、アプリケーションの名前を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-103">This topic describes how to use the BizTalk Server Administration console to change the name of an application.</span></span> <span data-ttu-id="f6ce3-104">アプリケーションには、グループ内に既に存在するアプリケーション名を付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-104">The application name that you use cannot already exist in the group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6ce3-105">名前を変更したアプリケーションへの参照を持つアプリケーションの .msi ファイルをエクスポートした場合、その参照はその .msi ファイルをインポートしたときには機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-105">If you have exported an .msi file for an application that has a reference to the renamed application, the reference will no longer function when you import the .msi file.</span></span> <span data-ttu-id="f6ce3-106">新しいアプリケーション名を使用して参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-106">You will need to update the reference with the new application name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6ce3-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="f6ce3-107">Prerequisites</span></span>  
 <span data-ttu-id="f6ce3-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f6ce3-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-name-of-an-application"></a><span data-ttu-id="f6ce3-110">アプリケーションの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="f6ce3-110">To change the name of an application</span></span>  
  
1. <span data-ttu-id="f6ce3-111">クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-111">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f6ce3-112">コンソール ツリーで、展開**BizTalk Server 管理**、アプリケーションを変更して、をクリックする名前を右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-112">In the console tree, expand  **BizTalk Server Administration**, right-click the application whose name you want to change, and click **Properties**.</span></span>  
  
3. <span data-ttu-id="f6ce3-113">**名前**ボックスで、アプリケーションの新しい名前を入力し、をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="f6ce3-113">In the **Name** box, type a new name for the application, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ce3-114">参照</span><span class="sxs-lookup"><span data-stu-id="f6ce3-114">See Also</span></span>  
 [<span data-ttu-id="f6ce3-115">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="f6ce3-115">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)