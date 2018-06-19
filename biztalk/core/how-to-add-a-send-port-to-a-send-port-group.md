---
title: 送信ポート、送信ポート グループを追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send port groups], adding send ports
- managing [send ports], adding to send port groups
- send port groups, send ports
- send ports, send port groups
- adding, send ports
ms.assetid: a61b3b32-c05e-40b9-abf1-09b7065fb6a2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e10a16b31f5cc112e814faf119dc424c99ba67
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969576"
---
# <a name="how-to-add-a-send-port-to-a-send-port-group"></a><span data-ttu-id="3756d-102">送信ポートを送信ポート グループに追加する方法</span><span class="sxs-lookup"><span data-stu-id="3756d-102">How to Add a Send Port to a Send Port Group</span></span>
<span data-ttu-id="3756d-103">このトピックでは、BizTalk Server 管理コンソールを使用して、1 つまたは複数の送信ポートを送信ポート グループに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3756d-103">This topic describes how to use the BizTalk Server Administration console to add one or more send ports to a send port group.</span></span> <span data-ttu-id="3756d-104">静的な一方向の送信ポートは、送信ポート グループにのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="3756d-104">You can only add one-way static send ports to a send port group.</span></span>  
  
 <span data-ttu-id="3756d-105">別のアプリケーションに存在する送信ポートを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="3756d-105">You can add a send port that exists in a different application.</span></span> <span data-ttu-id="3756d-106">別のアプリケーションの送信ポートを追加する場合は、送信ポート グループのあるアプリケーションから目的の送信ポートがあるアプリケーションへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3756d-106">If you do this, you must add a reference from the application containing the send port group to the application containing the send port.</span></span> <span data-ttu-id="3756d-107">手順については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3756d-107">For instructions, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3756d-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="3756d-108">Prerequisites</span></span>  
 <span data-ttu-id="3756d-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3756d-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3756d-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3756d-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-send-port-to-a-send-port-group"></a><span data-ttu-id="3756d-111">送信ポート グループへ送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="3756d-111">To add a send port to a send port group</span></span>  
  
1.  <span data-ttu-id="3756d-112">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="3756d-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3756d-113">コンソール ツリーで、BizTalk グループを展開し、送信ポート グループに送信ポートを追加する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="3756d-113">In the console tree, expand the BizTalk group and the BizTalk application in which you want to add a send port to a send port group.</span></span>  
  
3.  <span data-ttu-id="3756d-114">をクリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="3756d-114">Click **Send Port Groups**, right-click the send port group, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3756d-115">**送信ポート**、下にあるドロップダウン リストをクリックして**名前**、送信ポート グループに追加する送信ポート をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3756d-115">In **Send ports**, click the drop-down list under **Name**, and click the send port to add to the send port group.</span></span> <span data-ttu-id="3756d-116">グループに追加する送信ポートごとにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3756d-116">Repeat for each send port you want to add to the group.</span></span> <span data-ttu-id="3756d-117">新しい送信ポートを作成し、追加して、クリックして**\<新しいポートを送信しています.\>** し、指示に従って、[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。</span><span class="sxs-lookup"><span data-stu-id="3756d-117">To create a new send port and add it, click **\<New send port…\>** and then follow the instructions in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
5.  <span data-ttu-id="3756d-118">送信ポートの送信ポート グループに追加したらをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="3756d-118">When finished adding send ports to the send port group, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3756d-119">参照</span><span class="sxs-lookup"><span data-stu-id="3756d-119">See Also</span></span>  
 <span data-ttu-id="3756d-120">[作成して、送信ポート グループを構成します。](../core/creating-and-configuring-send-port-groups.md) </span><span class="sxs-lookup"><span data-stu-id="3756d-120">[Creating and Configuring Send Port Groups](../core/creating-and-configuring-send-port-groups.md) </span></span>  
 [<span data-ttu-id="3756d-121">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="3756d-121">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)