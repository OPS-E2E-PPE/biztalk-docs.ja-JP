---
title: 送信ポートまたは送信ポート グループを開始する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 558a9b8444a38607f18757ff09196e44a3ae0b71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255602"
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="d3353-102">送信ポートまたは送信ポート グループを開始する方法</span><span class="sxs-lookup"><span data-stu-id="d3353-102">How to Start a Send Port or Send Port Group</span></span>
<span data-ttu-id="d3353-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3353-103">This topic describes how to use the BizTalk Server Administration console to start a send port or send port group.</span></span> <span data-ttu-id="d3353-104">メッセージを処理できるようにするには、送信ポートまたは送信ポート グループを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3353-104">You must start a send port or send port group before it can process messages.</span></span> <span data-ttu-id="d3353-105">参加解除した送信ポート グループまたは送信ポートを開始した場合、BizTalk は、送信ポートまたは送信ポート グループを参加させてから開始します。</span><span class="sxs-lookup"><span data-stu-id="d3353-105">If you start an unenlisted send port or send port group, BizTalk enlists the send port or send port group before starting it.</span></span> <span data-ttu-id="d3353-106">送信ポート グループを開始するには、グループ内の 1 つ以上の送信ポートが参加済みの状態になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3353-106">A send port group must contain at least one send port in an enlisted state before you can start the send port group.</span></span> <span data-ttu-id="d3353-107">送信ポート グループを開始または停止しても、そのグループに属する各送信ポートの状態は変わりません。</span><span class="sxs-lookup"><span data-stu-id="d3353-107">Starting and stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3353-108">既定では、BizTalk アプリケーションを開始すると、そこに含まれるすべてのアイテムが開始されます。</span><span class="sxs-lookup"><span data-stu-id="d3353-108">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="d3353-109">詳細については、次を参照してください。[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3353-109">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3353-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="d3353-110">Prerequisites</span></span>  
 <span data-ttu-id="d3353-111">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3353-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d3353-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3353-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-a-send-port-or-send-port-group"></a><span data-ttu-id="d3353-113">送信ポートまたは送信ポート グループを開始するには</span><span class="sxs-lookup"><span data-stu-id="d3353-113">To start a send port or send port group</span></span>  
  
1.  <span data-ttu-id="d3353-114">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="d3353-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d3353-115">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、送信ポートまたはする送信ポート グループを含むアプリケーションを展開起動します。</span><span class="sxs-lookup"><span data-stu-id="d3353-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to start.</span></span>  
  
3.  <span data-ttu-id="d3353-116">をクリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="d3353-116">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3353-117">参照</span><span class="sxs-lookup"><span data-stu-id="d3353-117">See Also</span></span>  
 [<span data-ttu-id="d3353-118">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="d3353-118">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)