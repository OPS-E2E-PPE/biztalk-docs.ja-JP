---
title: 削除する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], deleting
- receive locations, deleting
- deleting, receive locations
ms.assetid: aa859355-af4c-48d9-b224-78fd3ef618fc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3acc788e1c0bfeb9e722aee0b55d66e6f09d096
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991443"
---
# <a name="how-to-delete-a-receive-location"></a><span data-ttu-id="674b3-102">受信場所を削除する方法</span><span class="sxs-lookup"><span data-stu-id="674b3-102">How to Delete a Receive Location</span></span>
<span data-ttu-id="674b3-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="674b3-103">This topic describes how to use the BizTalk Server Administration console to delete a receive location.</span></span> <span data-ttu-id="674b3-104">削除した受信場所は、BizTalk 管理データベースから削除され、BizTalk Server 管理コンソールに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="674b3-104">When you delete a receive location, it is removed from the BizTalk Management database and is no longer displayed in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="674b3-105">受信場所を削除する際には、次の重要事項を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="674b3-105">When deleting a receive location, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="674b3-106">受信場所を削除する前にする必要があります最初に無効にすること、」の説明に従って[受信場所を無効にする方法](../core/how-to-disable-a-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="674b3-106">Before you can delete a receive location, it must first be disabled, as described in [How to Disable a Receive Location](../core/how-to-disable-a-receive-location.md).</span></span>  
  
-   <span data-ttu-id="674b3-107">受信ポートのプライマリ受信場所を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="674b3-107">You cannot delete the primary receive location for a receive port.</span></span> <span data-ttu-id="674b3-108">プライマリ受信場所を削除しようとすると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="674b3-108">If you attempt this, you will receive an error message.</span></span> <span data-ttu-id="674b3-109">受信場所を削除するには、受信ポートを削除してそれに含まれるすべての受信場所を削除するか、または別の受信場所をプライマリに設定してから元の受信場所を削除します。</span><span class="sxs-lookup"><span data-stu-id="674b3-109">To delete the receive location, you can either delete the receive port, which also deletes all of the receive locations that it contains, or you can make a different receive location primary and then delete the original receive location.</span></span> <span data-ttu-id="674b3-110">プライマリ受信場所の受信場所を作成する手順については、[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="674b3-110">For instructions on making a receive location the primary receive location, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
-   <span data-ttu-id="674b3-111">受信場所を削除した後、削除した受信場所に対応する分離ホストのワーカー プロセスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="674b3-111">After you delete a receive location, restart the Isolated Host Worker Processes corresponding to the deleted receive location.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="674b3-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="674b3-112">Prerequisites</span></span>  
 <span data-ttu-id="674b3-113">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="674b3-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="674b3-114">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="674b3-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-location"></a><span data-ttu-id="674b3-115">受信場所を削除するには</span><span class="sxs-lookup"><span data-stu-id="674b3-115">To delete a receive location</span></span>  
  
1. <span data-ttu-id="674b3-116">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="674b3-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="674b3-117">コンソール ツリーで、BizTalk グループを展開し、受信場所を削除する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="674b3-117">In the console tree, expand the BizTalk group and the BizTalk application for which you want to delete a receive location.</span></span>  
  
3. <span data-ttu-id="674b3-118">をクリックして**受信場所**、削除、およびをクリックし、受信場所を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="674b3-118">Click **Receive Locations**, right-click the receive location to delete, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="674b3-119">参照</span><span class="sxs-lookup"><span data-stu-id="674b3-119">See Also</span></span>  
 [<span data-ttu-id="674b3-120">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="674b3-120">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)