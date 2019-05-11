---
title: 別のアプリケーションへの参照を削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, references
ms.assetid: cc867706-7c56-4386-b7ec-9fd7cf6c83a4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d504489740976fda5bcff37c41f792ec95b3e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335061"
---
# <a name="how-to-remove-a-reference-to-another-application"></a><span data-ttu-id="9755a-102">他のアプリケーションへの参照を削除する方法</span><span class="sxs-lookup"><span data-stu-id="9755a-102">How to Remove a Reference to Another Application</span></span>
<span data-ttu-id="9755a-103">このトピックでは、BizTalk Server 管理コンソールを使用して、1 つのアプリケーションから別のアプリケーションへの参照を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9755a-103">This topic describes how to use the BizTalk Server Administration console to remove a reference from one application to another application.</span></span> <span data-ttu-id="9755a-104">同じ BizTalk グループの別のアプリケーション内に存在するアイテムを、現在のアプリケーションで使用する必要がなくなった場合は、参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="9755a-104">You remove a reference when you no longer need to use an artifact in the current application that exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="9755a-105">参照の追加の詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="9755a-105">For more information on adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
 <span data-ttu-id="9755a-106">参照先アプリケーションのアイテムが、現在のアプリケーションのアイテムによって引き続き使用されている場合、参照を削除する操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9755a-106">If artifacts in the current application still use artifacts in the referenced application, the operation to remove the reference will fail.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9755a-107">BizTalk Server のすべてのアプリケーションには自動的に BizTalk.System アプリケーションへの参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9755a-107">Every application in BizTalk Server automatically contains a reference to the BizTalk.System application.</span></span> <span data-ttu-id="9755a-108">これは、BizTalk.System に含まれるアイテムが、すべての BizTalk アプリケーションで使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="9755a-108">This is because the artifacts that BizTalk.System contains are used by every BizTalk application.</span></span> <span data-ttu-id="9755a-109">BizTalk.System アプリケーションへの参照は削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="9755a-109">You should never remove a reference to the BizTalk.System application.</span></span> <span data-ttu-id="9755a-110">削除すると、アプリケーションが正しく機能しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9755a-110">If you do, your application may not function correctly.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9755a-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="9755a-111">Prerequisites</span></span>  
 <span data-ttu-id="9755a-112">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9755a-112">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9755a-113">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="9755a-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-reference-to-another-application"></a><span data-ttu-id="9755a-114">他のアプリケーションへの参照を削除するには</span><span class="sxs-lookup"><span data-stu-id="9755a-114">To remove a reference to another application</span></span>  
  
1. <span data-ttu-id="9755a-115">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="9755a-115">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9755a-116">コンソール ツリーで、展開**BizTalk Server 管理**(別のアプリケーションを参照するもの) の参照を削除するアプリケーションを右クリックし、クリックして**プロパティ**.</span><span class="sxs-lookup"><span data-stu-id="9755a-116">In the console tree, expand  **BizTalk Server Administration**, right-click the application from which you want to remove a reference (the one that refers to another application), and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="9755a-117">[プロパティ] ページの左側のウィンドウで次のようにクリックします。**参照**します。</span><span class="sxs-lookup"><span data-stu-id="9755a-117">In the left pane of the properties page, click **References**.</span></span>  
  
4. <span data-ttu-id="9755a-118">右側のウィンドウで、[このアプリケーションから参照する必要がなくなったアプリケーションをクリックします。**削除**、] をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="9755a-118">In the right pane, click the application that you no longer want to reference from this application, click **Remove**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9755a-119">参照</span><span class="sxs-lookup"><span data-stu-id="9755a-119">See Also</span></span>  
 [<span data-ttu-id="9755a-120">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="9755a-120">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)