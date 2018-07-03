---
title: オーケストレーションを参加解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, unenlisting
- enlisting, unenlisting
- managing [orchestrations], unenlisting
- unenlisting, orchestrations
ms.assetid: 038ed7bb-615c-4e4e-a5bb-79de2626de77
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7504551d6cc97f108d6cdee695f241ee983994a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993515"
---
# <a name="how-to-unenlist-an-orchestration"></a><span data-ttu-id="73bbe-102">オーケストレーションを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="73bbe-102">How to Unenlist an Orchestration</span></span>
<span data-ttu-id="73bbe-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを参加解除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-103">This topic describes how to unenlist an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="73bbe-104">オーケストレーションを参加解除は、ホストから削除します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-104">Unenlisting an orchestration removes it from the host.</span></span> <span data-ttu-id="73bbe-105">このオーケストレーションによってメッセージが処理されないように、サブスクリプションも削除されます。</span><span class="sxs-lookup"><span data-stu-id="73bbe-105">This removes the subscription so that the orchestration no longer processes messages.</span></span> <span data-ttu-id="73bbe-106">バインドを編集するには、事前にオーケストレーションを参加解除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bbe-106">You must unenlist an orchestration before you can edit its bindings.</span></span>  
  
 <span data-ttu-id="73bbe-107">オーケストレーションの参加を解除する前に」の説明に従って、実行中のインスタンスを終了する必要があります[中断、再開、およびオーケストレーション インスタンスを終了する方法](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-107">Before you can unenlist an orchestration, you must terminate any running instances, as described in [How to Suspend, Resume, and Terminate Orchestration Instances](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73bbe-108">アプリケーション開発者が開発プロセス中にオーケストレーションを参加解除するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-108">The application developer can unenlist an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="73bbe-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="73bbe-109">Prerequisites</span></span>  
 <span data-ttu-id="73bbe-110">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bbe-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="73bbe-111">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-an-orchestration"></a><span data-ttu-id="73bbe-112">オーケストレーションを参加解除するには</span><span class="sxs-lookup"><span data-stu-id="73bbe-112">To unenlist an orchestration</span></span>  
  
1. <span data-ttu-id="73bbe-113">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="73bbe-114">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、参加解除するオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to unenlist.</span></span>  
  
3. <span data-ttu-id="73bbe-115">クリックして**オーケストレーション**をクリックして参加を解除すると、オーケストレーションを右クリックして**参加解除**します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-115">Click **Orchestrations**, right-click the orchestration to unenlist, and then click **Unenlist**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="73bbe-116">一度に複数のオーケストレーションを参加解除し、shift キーを押しながら、参加を解除するには、各オーケストレーションを選択、オーケストレーションを右クリックし をクリックし、**参加解除**します。</span><span class="sxs-lookup"><span data-stu-id="73bbe-116">To unenlist multiple orchestrations at once, hold down the shift key and select each orchestration to unenlist, right-click an orchestration, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bbe-117">参照</span><span class="sxs-lookup"><span data-stu-id="73bbe-117">See Also</span></span>  
 <span data-ttu-id="73bbe-118">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="73bbe-118">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="73bbe-119">[オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="73bbe-119">[How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) </span></span>  
 [<span data-ttu-id="73bbe-120">BizTalk アプリケーション展開、管理</span><span class="sxs-lookup"><span data-stu-id="73bbe-120">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)