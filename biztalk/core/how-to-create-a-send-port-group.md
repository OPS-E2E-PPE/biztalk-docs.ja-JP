---
title: 送信ポート グループを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send port groups
- send port groups, creating
- managing [send port groups], creating
ms.assetid: de3e72aa-83f4-4760-9f39-a488f904f1d3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d27914dd5d7ae59b0823c2e6009ab307c41b9b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970368"
---
# <a name="how-to-create-a-send-port-group"></a><span data-ttu-id="d44b7-102">送信ポート グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d44b7-102">How to Create a Send Port Group</span></span>
<span data-ttu-id="d44b7-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アプリケーションで送信ポート グループを作成して、送信ポートを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d44b7-103">This topic describes how to use the BizTalk Server Administration console to create a send port group in a BizTalk application and then add send ports to it.</span></span> <span data-ttu-id="d44b7-104">送信ポート グループには、静的な一方向の送信ポートのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="d44b7-104">You can add static one-way send ports only to a send port group.</span></span> <span data-ttu-id="d44b7-105">メッセージをルーティングするには、送信ポート グループに少なくとも 1 つの送信ポートが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d44b7-105">A send port group must contain at least one send port to route messages.</span></span>  
  
 <span data-ttu-id="d44b7-106">別のアプリケーションに存在する送信ポートを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="d44b7-106">You can add a send port that exists in a different application.</span></span> <span data-ttu-id="d44b7-107">別のアプリケーションの送信ポートを追加する場合は、送信ポート グループのあるアプリケーションから目的の送信ポートがあるアプリケーションへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d44b7-107">If you do this, you must add a reference from the application containing the send port group to the application containing the send port.</span></span> <span data-ttu-id="d44b7-108">手順については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="d44b7-108">For instructions, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d44b7-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="d44b7-109">Prerequisites</span></span>  
 <span data-ttu-id="d44b7-110">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d44b7-110">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d44b7-111">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="d44b7-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-create-a-send-port-group"></a><span data-ttu-id="d44b7-112">送信ポート グループを作成するには</span><span class="sxs-lookup"><span data-stu-id="d44b7-112">To create a send port group</span></span>  
  
1.  <span data-ttu-id="d44b7-113">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="d44b7-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d44b7-114">コンソール ツリーで、BizTalk グループを展開し、送信ポート グループを作成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="d44b7-114">In the console tree, expand the BizTalk group and the BizTalk application in which you want to create a send port group.</span></span>  
  
3.  <span data-ttu-id="d44b7-115">右クリック**送信ポート グループ**、 をポイント**新規**、クリックして**送信ポート グループ**です。</span><span class="sxs-lookup"><span data-stu-id="d44b7-115">Right-click **Send Port Groups**, point to **New**, and then click **Send Port Group**.</span></span>  
  
4.  <span data-ttu-id="d44b7-116">**名前**ボックスで、送信ポート グループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d44b7-116">In the **Name** box, type a name for the send port group.</span></span>  
  
5.  <span data-ttu-id="d44b7-117">**送信ポート**、下にあるドロップダウン リストをクリックして**名前**、送信ポート グループに追加する送信ポート をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d44b7-117">In **Send ports**, click the drop-down list under **Name**, and click the send port to add to the send port group.</span></span> <span data-ttu-id="d44b7-118">グループに追加する送信ポートごとにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d44b7-118">Repeat for each send port you want to add to the group.</span></span> <span data-ttu-id="d44b7-119">新しい送信ポートを作成し、追加して、クリックして**\<新しいポートを送信しています.\>** し、指示に従って、[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。</span><span class="sxs-lookup"><span data-stu-id="d44b7-119">To create a new send port and add it, click **\<New send port…\>** and then follow the instructions in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
6.  <span data-ttu-id="d44b7-120">送信ポートの送信ポート グループに追加したらをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d44b7-120">When finished adding send ports to the send port group, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44b7-121">参照</span><span class="sxs-lookup"><span data-stu-id="d44b7-121">See Also</span></span>  
 [<span data-ttu-id="d44b7-122">送信ポート グループの作成および構成</span><span class="sxs-lookup"><span data-stu-id="d44b7-122">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)