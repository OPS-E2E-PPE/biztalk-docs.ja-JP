---
title: 参加またはロールに対してパーティを参加解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [role links], enlisting
- enlisting, role links
- role links, unenlisting
- role links, enlisting
- managing [role links], unenlisting
ms.assetid: 06fc2a64-3add-400c-9f9d-fab22fdf5366
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 095a1c2a180c0592641cd791875f23d633d908c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337834"
---
# <a name="how-to-enlist-or-unenlist-a-party-for-a-role"></a><span data-ttu-id="bc586-102">ロールに対してパーティを参加させる、または参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="bc586-102">How to Enlist or Unenlist a Party for a Role</span></span>
<span data-ttu-id="bc586-103">このトピックでは、BizTalk Server 管理コンソールを使用して、ロールに対してパーティを参加させる、または参加解除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc586-103">This topic describes how to use the BizTalk Server Administration console to enlist or unenlist a party for a role.</span></span> <span data-ttu-id="bc586-104">ロールにパーティを参加させるとパーティがロールに割り当てられ、パーティを参加解除するとパーティがロールから削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc586-104">Enlisting a party for a role assigns the party to the role and unenlisting the party removes the party from the role.</span></span>  
  
 <span data-ttu-id="bc586-105">ロールに対してパーティを参加させる、または参加解除する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc586-105">When enlisting or unenlisting a party for a role, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="bc586-106">参加させるパーティをあらかじめ作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc586-106">You must create a party before you can enlist it.</span></span> <span data-ttu-id="bc586-107">手順については、次を参照してください。[パーティを作成する方法](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)します。</span><span class="sxs-lookup"><span data-stu-id="bc586-107">For instructions, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span>  
  
-   <span data-ttu-id="bc586-108">ロールに対してパーティを参加させる、または参加解除する場合、アプリケーションを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bc586-108">You can enlist or unenlist a party for a role without needing to restart the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc586-109">アプリケーション開発者が開発プロセス中にパーティを参加させる、または参加解除するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc586-109">The application developer can enlist or unenlist a party during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc586-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="bc586-110">Prerequisites</span></span>  
 <span data-ttu-id="bc586-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc586-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="bc586-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc586-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-or-unenlist-a-party-for-a-role"></a><span data-ttu-id="bc586-113">ロールに対してパーティを参加させる、または参加解除するには</span><span class="sxs-lookup"><span data-stu-id="bc586-113">To enlist or unenlist a party for a role</span></span>  
  
1. <span data-ttu-id="bc586-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="bc586-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="bc586-115">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、参加するロール リンクを含むアプリケーションを展開し、またはパーティの参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="bc586-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the role link for which you want to enlist or unenlist a party.</span></span>  
  
3. <span data-ttu-id="bc586-116">クリックして**ロール リンク**、参加や、パーティを参加解除 をクリックするロール リンクを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="bc586-116">Click **Role Links**, right-click the role link for which you want to enlist or unenlist a party, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="bc586-117">パーティを参加させるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc586-117">To enlist a party, do the following:</span></span>  
  
   -   <span data-ttu-id="bc586-118">クリックして**参加**に参加させるパーティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc586-118">Click **Enlist** and click the party to enlist.</span></span>  
  
   -   <span data-ttu-id="bc586-119">をクリックして**バインド**で、**送信ポート**ドロップダウン リストで、クリック、送信をこのパーティに使用するポートの順にクリックします**OK** 2 回です。</span><span class="sxs-lookup"><span data-stu-id="bc586-119">Click **Bind**, in the **Send Port** drop-down list, click the send port to use for this party, and then click **OK** twice.</span></span>  
  
5. <span data-ttu-id="bc586-120">パーティの参加を解除するパーティをクリックし**参加解除**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="bc586-120">To unenlist a party, click the party, click **Unenlist**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc586-121">参照</span><span class="sxs-lookup"><span data-stu-id="bc586-121">See Also</span></span>  
 [<span data-ttu-id="bc586-122">ロール リンクの管理</span><span class="sxs-lookup"><span data-stu-id="bc586-122">Managing Role Links</span></span>](../core/managing-role-links.md)