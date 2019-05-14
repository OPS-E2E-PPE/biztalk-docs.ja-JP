---
title: グループからサーバーを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- managing [groups], deleting servers
- servers, deleting
- deleting, groups
- servers
- managing [servers], deleting from groups
- groups, deleting
- servers, groups
- deleting, servers
ms.assetid: 85596e18-fa17-4f44-bc20-2e4cb578e109
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b8be9a991e70c3f1f4fb30673f2c1456a6fe3d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384339"
---
# <a name="how-to-remove-a-server-from-a-group"></a><span data-ttu-id="34968-102">サーバーをグループから削除する方法</span><span class="sxs-lookup"><span data-stu-id="34968-102">How to Remove a Server from a Group</span></span>
<span data-ttu-id="34968-103">サーバーは、1 つの BizTalk グループに関連付けられた場合のみできます。</span><span class="sxs-lookup"><span data-stu-id="34968-103">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="34968-104">サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34968-104">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34968-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="34968-105">Prerequisites</span></span>  
 <span data-ttu-id="34968-106">この手順を実行するには、Windows の Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34968-106">To perform this procedure, you must be logged on as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-remove-a-server-from-a-group"></a><span data-ttu-id="34968-107">グループからサーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="34968-107">To remove a server from a group</span></span>  
  
1. <span data-ttu-id="34968-108">BizTalk Server グループから削除するコンピューターで次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalkServerの構成。**.</span><span class="sxs-lookup"><span data-stu-id="34968-108">On the computer that you want to remove from a BizTalk Server group, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2. <span data-ttu-id="34968-109">メニュー バーでクリックして**機能の構成解除**します。</span><span class="sxs-lookup"><span data-stu-id="34968-109">On the menu bar, click **Unconfigure Features**.</span></span>  
  
3. <span data-ttu-id="34968-110">**機能の構成解除**ダイアログ ボックスで、**グループ**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="34968-110">In the **Unconfigure Features** dialog box, select **Group**, and then click **OK**.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="34968-111">グループを構成解除のコンピューターに既に構成されているすべての依存機能構成が解除されます。</span><span class="sxs-lookup"><span data-stu-id="34968-111">Unconfiguring a group will also unconfigure all dependent features that are already configured on that computer.</span></span>  
  
4. <span data-ttu-id="34968-112">**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34968-112">Click **Yes**.</span></span>  
  
5. <span data-ttu-id="34968-113">Microsoft BizTalk Server 構成ウィザードで次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="34968-113">In the Microsoft BizTalk Server Configuration Wizard, click **Next**.</span></span>  
  
    <span data-ttu-id="34968-114">グループとその依存する機能が構成されているではありません。</span><span class="sxs-lookup"><span data-stu-id="34968-114">The Group and its dependent features are unconfigured.</span></span>  
  
6. <span data-ttu-id="34968-115">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34968-115">Click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34968-116">参照</span><span class="sxs-lookup"><span data-stu-id="34968-116">See Also</span></span>  
 <span data-ttu-id="34968-117">[グループの管理](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="34968-117">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="34968-118">[BizTalk グループ](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="34968-118">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="34968-119">[サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="34968-119">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="34968-120">[1 つのグループからサーバーを移動する方法](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="34968-120">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 <span data-ttu-id="34968-121">[グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="34968-121">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 [<span data-ttu-id="34968-122">サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="34968-122">Managing Servers</span></span>](../core/managing-servers.md)