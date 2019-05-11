---
title: 送信ポートまたは送信ポート グループを開始する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting, send port groups
- starting, send ports
- managing [send port groups], starting
- managing [send ports], starting
- send port groups, starting
- send ports, starting
ms.assetid: f17c0b7c-cad7-4c5e-a08c-3ebf838faa54
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1749862ee78c549d3aa3fd79a62eedd1ecba144
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334030"
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="4a546-102">送信ポートまたは送信ポート グループを開始する方法</span><span class="sxs-lookup"><span data-stu-id="4a546-102">How to Start a Send Port or Send Port Group</span></span>
<span data-ttu-id="4a546-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a546-103">This topic describes how to use the BizTalk Server Administration console to start a send port or send port group.</span></span> <span data-ttu-id="4a546-104">メッセージを処理できるようにするには、送信ポートまたは送信ポート グループを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a546-104">You must start a send port or send port group before it can process messages.</span></span> <span data-ttu-id="4a546-105">参加解除した送信ポート グループまたは送信ポートを開始した場合、BizTalk は、送信ポートまたは送信ポート グループを参加させてから開始します。</span><span class="sxs-lookup"><span data-stu-id="4a546-105">If you start an unenlisted send port or send port group, BizTalk enlists the send port or send port group before starting it.</span></span> <span data-ttu-id="4a546-106">送信ポート グループを開始するには、グループ内の 1 つ以上の送信ポートが参加済みの状態になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a546-106">A send port group must contain at least one send port in an enlisted state before you can start the send port group.</span></span> <span data-ttu-id="4a546-107">送信ポート グループを開始または停止しても、そのグループに属する各送信ポートの状態は変わりません。</span><span class="sxs-lookup"><span data-stu-id="4a546-107">Starting and stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a546-108">既定では、BizTalk アプリケーションを開始すると、そこに含まれるすべてのアイテムが開始されます。</span><span class="sxs-lookup"><span data-stu-id="4a546-108">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="4a546-109">詳細については、次を参照してください。 [BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a546-109">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a546-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="4a546-110">Prerequisites</span></span>  
 <span data-ttu-id="4a546-111">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a546-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4a546-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a546-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="4a546-113">送信ポートまたは送信ポート グループを開始するには</span><span class="sxs-lookup"><span data-stu-id="4a546-113">To start a send port or send port group</span></span>  
  
1. <span data-ttu-id="4a546-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4a546-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4a546-115">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、送信ポートまたは送信ポート グループにするを含むアプリケーションを展開し、起動します。</span><span class="sxs-lookup"><span data-stu-id="4a546-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to start.</span></span>  
  
3. <span data-ttu-id="4a546-116">をクリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="4a546-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a546-117">参照</span><span class="sxs-lookup"><span data-stu-id="4a546-117">See Also</span></span>  
 [<span data-ttu-id="4a546-118">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="4a546-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)