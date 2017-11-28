---
title: "オーケストレーションを参加解除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, unenlisting
- enlisting, unenlisting
- managing [orchestrations], unenlisting
- unenlisting, orchestrations
ms.assetid: 038ed7bb-615c-4e4e-a5bb-79de2626de77
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c55f0f7daee927e90e514cb7b566b058cee8044a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-unenlist-an-orchestration"></a><span data-ttu-id="21c1a-102">オーケストレーションを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="21c1a-102">How to Unenlist an Orchestration</span></span>
<span data-ttu-id="21c1a-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを参加解除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21c1a-103">This topic describes how to unenlist an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="21c1a-104">オーケストレーションを参加解除は、ホストから削除します。</span><span class="sxs-lookup"><span data-stu-id="21c1a-104">Unenlisting an orchestration removes it from the host.</span></span> <span data-ttu-id="21c1a-105">このオーケストレーションによってメッセージが処理されないように、サブスクリプションも削除されます。</span><span class="sxs-lookup"><span data-stu-id="21c1a-105">This removes the subscription so that the orchestration no longer processes messages.</span></span> <span data-ttu-id="21c1a-106">バインドを編集するには、事前にオーケストレーションを参加解除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="21c1a-106">You must unenlist an orchestration before you can edit its bindings.</span></span>  
  
 <span data-ttu-id="21c1a-107">オーケストレーションの参加を解除する前に」の説明に従って、実行中のインスタンスを終了する必要が[中断、再開、およびオーケストレーション インスタンスを終了する方法](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="21c1a-107">Before you can unenlist an orchestration, you must terminate any running instances, as described in [How to Suspend, Resume, and Terminate Orchestration Instances](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21c1a-108">アプリケーション開発者が開発プロセス中にオーケストレーションを参加解除するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="21c1a-108">The application developer can unenlist an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="21c1a-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="21c1a-109">Prerequisites</span></span>  
 <span data-ttu-id="21c1a-110">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="21c1a-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="21c1a-111">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="21c1a-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-unenlist-an-orchestration"></a><span data-ttu-id="21c1a-112">オーケストレーションを参加解除するには</span><span class="sxs-lookup"><span data-stu-id="21c1a-112">To unenlist an orchestration</span></span>  
  
1.  <span data-ttu-id="21c1a-113">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="21c1a-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="21c1a-114">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、参加解除するオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="21c1a-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to unenlist.</span></span>  
  
3.  <span data-ttu-id="21c1a-115">をクリックして**オーケストレーション**、参加解除、およびをクリックするオーケストレーションを右クリックして**参加解除**です。</span><span class="sxs-lookup"><span data-stu-id="21c1a-115">Click **Orchestrations**, right-click the orchestration to unenlist, and then click **Unenlist**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="21c1a-116">一度に複数のオーケストレーションの参加を解除し、shift キーを押しながら各オーケストレーションを参加解除するを選択、オーケストレーションを右クリックし、をクリックして**参加解除**です。</span><span class="sxs-lookup"><span data-stu-id="21c1a-116">To unenlist multiple orchestrations at once, hold down the shift key and select each orchestration to unenlist, right-click an orchestration, and then click **Unenlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c1a-117">参照</span><span class="sxs-lookup"><span data-stu-id="21c1a-117">See Also</span></span>  
 <span data-ttu-id="21c1a-118">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="21c1a-118">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="21c1a-119">[オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="21c1a-119">[How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) </span></span>  
 [<span data-ttu-id="21c1a-120">展開して、BizTalk アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="21c1a-120">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)