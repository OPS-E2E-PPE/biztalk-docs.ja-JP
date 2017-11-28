---
title: "送信ポートまたは送信ポート グループを参加解除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac2599ae3d06a75506de244a4f996a9e77cef6ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="ecbfc-102">送信ポートまたは送信ポート グループを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="ecbfc-102">How to Unenlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="ecbfc-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを参加解除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-103">This topic describes how to use the BizTalk Server Administration console to unenlist a send port or send port group.</span></span> <span data-ttu-id="ecbfc-104">送信ポートまたは送信ポート グループを参加解除すると、そこに関連付けられていたすべてのサブスクリプションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-104">Unenlisting a send port or send port group eliminates all subscriptions associated with that send port or send port group.</span></span> <span data-ttu-id="ecbfc-105">送信ポートまたは送信ポート グループは、実行中であるか停止されているかに関係なく参加解除できます。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-105">You can unenlist both running and stopped send ports or send port groups.</span></span> <span data-ttu-id="ecbfc-106">参加解除された送信ポートまたは送信ポート グループは自動的に停止されます。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-106">Unenlisting a send port or send port group automatically stops it.</span></span>  
  
 <span data-ttu-id="ecbfc-107">送信ポートまたは送信ポート グループの参加解除が必要になる状況としては、バインドを編集したい場合や、送信ポートまたは送信ポート グループを BizTalk Server 環境から削除したい場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-107">For example, you may want to unenlist a send port or send port group to edit its bindings, or if you want to remove the send port or send port group from the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="ecbfc-108">実行中または参加済みの送信ポート グループに対して最後に参加させた送信ポートを参加解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-108">You cannot unenlist the last enlisted send port within a send port group that is enlisted or running.</span></span> <span data-ttu-id="ecbfc-109">送信ポート グループを参加解除しても、そのグループに属する各送信ポートの状態は変わりません。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-109">Unenlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ecbfc-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="ecbfc-110">Prerequisites</span></span>  
 <span data-ttu-id="ecbfc-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ecbfc-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="ecbfc-113">送信ポートまたは送信ポート グループを参加解除するには</span><span class="sxs-lookup"><span data-stu-id="ecbfc-113">To unenlist a send port or send port group</span></span>  
  
1.  <span data-ttu-id="ecbfc-114">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ecbfc-115">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、送信ポートまたはする送信ポート グループを含むアプリケーションを展開参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to unenlist.</span></span>  
  
3.  <span data-ttu-id="ecbfc-116">をクリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**参加解除**です。</span><span class="sxs-lookup"><span data-stu-id="ecbfc-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbfc-117">参照</span><span class="sxs-lookup"><span data-stu-id="ecbfc-117">See Also</span></span>  
 [<span data-ttu-id="ecbfc-118">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="ecbfc-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)