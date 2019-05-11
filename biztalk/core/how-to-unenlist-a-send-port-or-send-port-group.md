---
title: 送信ポートまたは送信ポート グループを参加解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dbd8a3a7c3450fcf36d66467cd95a38e39583dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333777"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="74dbd-102">送信ポートまたは送信ポート グループを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="74dbd-102">How to Unenlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="74dbd-103">このトピックでは、送信ポートを参加解除、または送信ポート グループを BizTalk Server 管理コンソールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="74dbd-103">This topic describes how to use the BizTalk Server Administration console to unenlist a send port or send port group.</span></span> <span data-ttu-id="74dbd-104">送信ポートまたは送信ポート グループを参加解除、その送信ポートに関連付けられているすべてのサブスクリプションを排除または送信ポート グループ。</span><span class="sxs-lookup"><span data-stu-id="74dbd-104">Unenlisting a send port or send port group eliminates all subscriptions associated with that send port or send port group.</span></span> <span data-ttu-id="74dbd-105">実行中と停止の両方の送信ポートの参加を解除したり、送信ポート グループができます。</span><span class="sxs-lookup"><span data-stu-id="74dbd-105">You can unenlist both running and stopped send ports or send port groups.</span></span> <span data-ttu-id="74dbd-106">送信ポートまたは送信ポート グループを自動的に参加解除するには、そのは停止します。</span><span class="sxs-lookup"><span data-stu-id="74dbd-106">Unenlisting a send port or send port group automatically stops it.</span></span>  
  
 <span data-ttu-id="74dbd-107">送信ポートを参加解除、または送信ポート グループ、そのバインドを編集したいなどのポートまたは送信ポート グループを BizTalk Server 環境からの送信を削除するかどうかまたはします。</span><span class="sxs-lookup"><span data-stu-id="74dbd-107">For example, you may want to unenlist a send port or send port group to edit its bindings, or if you want to remove the send port or send port group from the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="74dbd-108">参加しているまたは実行中である送信ポート グループ内の最後の参加させた送信ポートを参加解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="74dbd-108">You cannot unenlist the last enlisted send port within a send port group that is enlisted or running.</span></span> <span data-ttu-id="74dbd-109">送信ポート グループを参加解除しても、それに含まれる送信ポートの状態は変わりません。</span><span class="sxs-lookup"><span data-stu-id="74dbd-109">Unenlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="74dbd-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="74dbd-110">Prerequisites</span></span>  
 <span data-ttu-id="74dbd-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74dbd-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="74dbd-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="74dbd-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a><span data-ttu-id="74dbd-113">送信ポートを参加解除または送信ポート グループ</span><span class="sxs-lookup"><span data-stu-id="74dbd-113">To unenlist a send port or send port group</span></span>  
  
1. <span data-ttu-id="74dbd-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="74dbd-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="74dbd-115">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、送信ポートまたは送信ポート グループにするを含むアプリケーションを展開し、参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="74dbd-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to unenlist.</span></span>  
  
3. <span data-ttu-id="74dbd-116">クリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**参加解除**します。</span><span class="sxs-lookup"><span data-stu-id="74dbd-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74dbd-117">参照</span><span class="sxs-lookup"><span data-stu-id="74dbd-117">See Also</span></span>  
 [<span data-ttu-id="74dbd-118">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="74dbd-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)