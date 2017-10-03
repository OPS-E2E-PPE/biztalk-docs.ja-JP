---
title: "オーケストレーションを停止する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], stopping
- orchestrations, stopping
ms.assetid: a8009c23-ca83-4d2f-97dd-df660adbc279
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57e51842171c31f2da509e92d9364948aeceb1d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-stop-an-orchestration"></a><span data-ttu-id="64b0c-102">オーケストレーションを停止する方法</span><span class="sxs-lookup"><span data-stu-id="64b0c-102">How to Stop an Orchestration</span></span>
<span data-ttu-id="64b0c-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを停止する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64b0c-103">This topic describes how to use the BizTalk Server Administration console to stop an orchestration.</span></span> <span data-ttu-id="64b0c-104">オーケストレーションを停止すると、到着したアクティベーション メッセージがすべて非アクティブ化されて中断されます。</span><span class="sxs-lookup"><span data-stu-id="64b0c-104">Stopping an orchestration deactivates and suspends all of the arriving activation messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64b0c-105">アプリケーション開発者が開発プロセス中にオーケストレーションを停止するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64b0c-105">The application developer stop an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="64b0c-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="64b0c-106">Prerequisites</span></span>  
 <span data-ttu-id="64b0c-107">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b0c-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="64b0c-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="64b0c-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-an-orchestration"></a><span data-ttu-id="64b0c-109">オーケストレーションを停止するには</span><span class="sxs-lookup"><span data-stu-id="64b0c-109">To stop an orchestration</span></span>  
  
1.  <span data-ttu-id="64b0c-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="64b0c-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="64b0c-111">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、オーケストレーションを停止するを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="64b0c-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to stop.</span></span>  
  
3.  <span data-ttu-id="64b0c-112">をクリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="64b0c-112">Click **Orchestrations**, right-click the orchestration, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b0c-113">参照</span><span class="sxs-lookup"><span data-stu-id="64b0c-113">See Also</span></span>  
 <span data-ttu-id="64b0c-114">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="64b0c-114">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="64b0c-115">[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="64b0c-115">[How to Start an Orchestration](../core/how-to-start-an-orchestration.md) </span></span>  
 [<span data-ttu-id="64b0c-116">BizTalk アプリケーション開始および停止する方法</span><span class="sxs-lookup"><span data-stu-id="64b0c-116">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)