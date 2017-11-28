---
title: "送信ポートを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55b4e08fa03380c3361a44b7989301b606732d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-send-port"></a><span data-ttu-id="0a36e-102">送信ポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="0a36e-102">How to Delete a Send Port</span></span>
<span data-ttu-id="0a36e-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートを BizTalk アプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a36e-103">This topic describes how to use the BizTalk Server Administration console to delete a send port from a BizTalk application.</span></span> <span data-ttu-id="0a36e-104">送信ポートを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも送信ポート グループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0a36e-104">When you do this, the send port is also deleted from the BizTalk Management database for the group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a36e-105">送信ポートを削除すると、そのポートに関連付けられている実行中のサービス インスタンスからは、送信ポートに関する情報 (送信ポート名など) を一切取得できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0a36e-105">When you delete a send port, any running service instances associated with that port can no longer obtain configuration information about the send port, such as its name.</span></span> <span data-ttu-id="0a36e-106">送信ポートに関する情報はキャッシュされますが、サービス インスタンスがメッセージを再送しなければならなくなった場合に、再送処理を最後まで実行できず、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="0a36e-106">Although this information is cached, if the service instance must resend a message, it will not be able to complete, and the message will be suspended.</span></span> <span data-ttu-id="0a36e-107">送信ポートを削除する前に実行がないことを確認する必要があります」の説明に従ってのインスタンスをサービス[送信ポートのインスタンス情報を表示する方法](../core/how-to-view-instance-information-for-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-107">Before deleting a send port, you should verify that there are no running service instances, as described in [How to View Instance Information for a Send Port](../core/how-to-view-instance-information-for-a-send-port.md).</span></span>  
  
 <span data-ttu-id="0a36e-108">送信ポートを削除できるのは、次の条件を満たしている場合だけです。</span><span class="sxs-lookup"><span data-stu-id="0a36e-108">You can delete a send port only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="0a36e-109">送信ポートにオーケストレーションがバインドされていない: </span><span class="sxs-lookup"><span data-stu-id="0a36e-109">An orchestration is not bound to the send port.</span></span> <span data-ttu-id="0a36e-110">次の手順で、バインドを解除するには大文字と小文字の場合は、[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-110">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="0a36e-111">送信ポートが停止および参加解除されている: </span><span class="sxs-lookup"><span data-stu-id="0a36e-111">The send port is both stopped and unenlisted.</span></span> <span data-ttu-id="0a36e-112">停止し、送信ポートを参加解除の手順については、次を参照してください。[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)と[送信ポートまたは送信ポート グループを停止する方法](../core/how-to-stop-a-send-port-or-send-port-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-112">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="0a36e-113">送信ポートがパーティで参照されていない: </span><span class="sxs-lookup"><span data-stu-id="0a36e-113">The send port is not referenced by a party.</span></span> <span data-ttu-id="0a36e-114">パーティから送信ポートへの参照を削除する方法の詳細については、次を参照してください。[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-114">For instructions on removing a reference to a send port from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
-   <span data-ttu-id="0a36e-115">送信ポートが送信ポート グループに属していない: </span><span class="sxs-lookup"><span data-stu-id="0a36e-115">The send port is not included in a send port group.</span></span> <span data-ttu-id="0a36e-116">送信ポート グループから送信ポートを削除する方法の詳細については、次を参照してください。[送信ポート グループから送信ポートを削除する方法](../core/how-to-remove-a-send-port-from-a-send-port-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-116">For instructions on removing a send port from a send port group, see [How to Remove a Send Port from a Send Port Group](../core/how-to-remove-a-send-port-from-a-send-port-group.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a36e-117">アプリケーション開発者が開発プロセス中に送信ポートを削除するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a36e-117">The application developer can delete a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a36e-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="0a36e-118">Prerequisites</span></span>  
 <span data-ttu-id="0a36e-119">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a36e-119">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0a36e-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port"></a><span data-ttu-id="0a36e-121">送信ポートを削除するには</span><span class="sxs-lookup"><span data-stu-id="0a36e-121">To delete a send port</span></span>  
  
1.  <span data-ttu-id="0a36e-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0a36e-123">コンソール ツリーで、[[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理]、[BizTalk グループ]、[アプリケーション] の順に展開し、削除する送信ポートを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="0a36e-123">In the console tree, expand [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration, expand the BizTalk group, expand Applications, and then expand the application containing the send port that you want to delete</span></span>  
  
3.  <span data-ttu-id="0a36e-124">をクリックして**送信ポート**送信ポートを右クリックし、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="0a36e-124">Click **Send Ports**, right-click the send port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a36e-125">参照</span><span class="sxs-lookup"><span data-stu-id="0a36e-125">See Also</span></span>  
 [<span data-ttu-id="0a36e-126">作成して、送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="0a36e-126">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)