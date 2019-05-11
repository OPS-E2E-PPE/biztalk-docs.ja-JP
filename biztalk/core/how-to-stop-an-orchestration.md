---
title: オーケストレーションを停止する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], stopping
- orchestrations, stopping
ms.assetid: a8009c23-ca83-4d2f-97dd-df660adbc279
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6da194b0ae99a8dbc986eab34bbe3b7ecae1a443
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333895"
---
# <a name="how-to-stop-an-orchestration"></a><span data-ttu-id="44124-102">オーケストレーションを停止する方法</span><span class="sxs-lookup"><span data-stu-id="44124-102">How to Stop an Orchestration</span></span>
<span data-ttu-id="44124-103">このトピックでは、BizTalk Server 管理コンソールを使用してオーケストレーションを停止する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="44124-103">This topic describes how to use the BizTalk Server Administration console to stop an orchestration.</span></span> <span data-ttu-id="44124-104">オーケストレーションを停止すると、非アクティブ化し、到着したアクティベーション メッセージのすべてを中断します。</span><span class="sxs-lookup"><span data-stu-id="44124-104">Stopping an orchestration deactivates and suspends all of the arriving activation messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44124-105">アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中にオーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="44124-105">The application developer stop an orchestration during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44124-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="44124-106">Prerequisites</span></span>  
 <span data-ttu-id="44124-107">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44124-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="44124-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="44124-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-an-orchestration"></a><span data-ttu-id="44124-109">オーケストレーションを停止するには</span><span class="sxs-lookup"><span data-stu-id="44124-109">To stop an orchestration</span></span>  
  
1. <span data-ttu-id="44124-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="44124-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="44124-111">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、停止するオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="44124-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to stop.</span></span>  
  
3. <span data-ttu-id="44124-112">クリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**停止**します。</span><span class="sxs-lookup"><span data-stu-id="44124-112">Click **Orchestrations**, right-click the orchestration, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44124-113">参照</span><span class="sxs-lookup"><span data-stu-id="44124-113">See Also</span></span>  
 <span data-ttu-id="44124-114">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="44124-114">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="44124-115">[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="44124-115">[How to Start an Orchestration](../core/how-to-start-an-orchestration.md) </span></span>  
 [<span data-ttu-id="44124-116">BizTalk アプリケーション開始および停止する方法</span><span class="sxs-lookup"><span data-stu-id="44124-116">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)