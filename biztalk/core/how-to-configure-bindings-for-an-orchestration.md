---
title: オーケストレーションのバインドの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9724a3a0-c217-4f98-b6d9-21f788ce50ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de8d8626dbe0ad110e46d399c32f2dc9ba8a321
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386309"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a><span data-ttu-id="2dbe9-102">オーケストレーションのバインドを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2dbe9-102">How to Configure Bindings for an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="2dbe9-103">概要</span><span class="sxs-lookup"><span data-stu-id="2dbe9-103">Overview</span></span>
<span data-ttu-id="2dbe9-104">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションのバインドを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-104">This topic describes how to use the BizTalk Server Administration console to configure bindings for an orchestration.</span></span> <span data-ttu-id="2dbe9-105">この作業には、オーケストレーションをホストにバインドしたり、オーケストレーションに定義されている論理ポートを、ステージング環境や実稼働環境の物理ポートにバインドしたりする作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-105">This involves binding the logical ports defined for the orchestration to physical ports in the staging or production environment as well as binding the orchestration to a host.</span></span> <span data-ttu-id="2dbe9-106">オーケストレーションのバインドが済んでいる場合は、この手順を使ってバインドを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-106">If the orchestration has already been bound, you can change the bindings by using this procedure.</span></span>  
  
 <span data-ttu-id="2dbe9-107">バインドの構成後、オーケストレーションを参加させることによって、メッセージの処理を開始できます。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-107">After configuring bindings, you can enlist the orchestration and then start it so that it begins processing messages.</span></span> <span data-ttu-id="2dbe9-108">これらのタスクを実行する方法の詳細については、次を参照してください。[オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)と[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-108">For instructions on performing these tasks, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2dbe9-109">アプリケーション開発者が開発プロセス中にオーケストレーションのバインドを構成してその機能をテストするには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-109">The application developer can configure bindings for an orchestration to test its functionality during the development process either by using the procedure in this topic.</span></span> <span data-ttu-id="2dbe9-110">また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-110">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="2dbe9-111">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="2dbe9-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="2dbe9-112">Prerequisites</span></span>  
 <span data-ttu-id="2dbe9-113">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="2dbe9-114">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="configure-bindings-for-an-orchestration"></a><span data-ttu-id="2dbe9-115">オーケストレーションのバインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-115">Configure bindings for an orchestration</span></span>  
  
1. <span data-ttu-id="2dbe9-116">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2dbe9-117">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、順に展開する対象のオーケストレーションを含むアプリケーションバインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure bindings</span></span>  
  
3. <span data-ttu-id="2dbe9-118">クリックして**オーケストレーション**をクリックして、バインドを構成するオーケストレーションを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-118">Click **Orchestrations**, right-click the orchestration for which you want to configure bindings, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="2dbe9-119">をクリックして、**バインド** タブとの間、**ホスト**一覧でオーケストレーションを参加させるホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-119">Click the **Bindings** tab, and from the **Host** list, select the host on which to enlist an orchestration.</span></span>  
  
5. <span data-ttu-id="2dbe9-120">ドロップダウン リストからの一覧で、**受信ポート**列、各受信論理ポートの横にある論理ポートをバインドする受信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-120">From the drop-down lists in the **Receive Ports** column, next to each inbound logical port, select the receive port to which you want to bind the logical port.</span></span>  
  
6. <span data-ttu-id="2dbe9-121">ドロップダウン リストから、**送信ポート/送信ポート グループ**各受信論理ポートの横の列をクリックして、論理ポートをバインドする送信ポートを選択する**OK**します。</span><span class="sxs-lookup"><span data-stu-id="2dbe9-121">From the drop-down list in the **Send Ports/Send Port Groups** column, next to each inbound logical port, select the send port to which you want to bind the logical port, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbe9-122">参照</span><span class="sxs-lookup"><span data-stu-id="2dbe9-122">See Also</span></span>  
 <span data-ttu-id="2dbe9-123">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="2dbe9-123">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="2dbe9-124">[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="2dbe9-124">[How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md) </span></span>  
 [<span data-ttu-id="2dbe9-125">BizTalk アプリケーション展開、管理</span><span class="sxs-lookup"><span data-stu-id="2dbe9-125">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)