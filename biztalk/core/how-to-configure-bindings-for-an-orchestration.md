---
title: "オーケストレーションのバインドの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9724a3a0-c217-4f98-b6d9-21f788ce50ba
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb695f9636327107887397372d5fc2dda74e4eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a><span data-ttu-id="cfb42-102">オーケストレーションのバインドを構成する方法</span><span class="sxs-lookup"><span data-stu-id="cfb42-102">How to Configure Bindings for an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="cfb42-103">概要</span><span class="sxs-lookup"><span data-stu-id="cfb42-103">Overview</span></span>
<span data-ttu-id="cfb42-104">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションのバインドを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfb42-104">This topic describes how to use the BizTalk Server Administration console to configure bindings for an orchestration.</span></span> <span data-ttu-id="cfb42-105">この作業には、オーケストレーションをホストにバインドしたり、オーケストレーションに定義されている論理ポートを、ステージング環境や実稼働環境の物理ポートにバインドしたりする作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfb42-105">This involves binding the logical ports defined for the orchestration to physical ports in the staging or production environment as well as binding the orchestration to a host.</span></span> <span data-ttu-id="cfb42-106">オーケストレーションのバインドが済んでいる場合は、この手順を使ってバインドを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="cfb42-106">If the orchestration has already been bound, you can change the bindings by using this procedure.</span></span>  
  
 <span data-ttu-id="cfb42-107">バインドの構成後、オーケストレーションを参加させることによって、メッセージの処理を開始できます。</span><span class="sxs-lookup"><span data-stu-id="cfb42-107">After configuring bindings, you can enlist the orchestration and then start it so that it begins processing messages.</span></span> <span data-ttu-id="cfb42-108">これらのタスクの実行方法の詳細については、次を参照してください。[にオーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)と[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="cfb42-108">For instructions on performing these tasks, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Start an Orchestration](../core/how-to-start-an-orchestration.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfb42-109">アプリケーション開発者が開発プロセス中にオーケストレーションのバインドを構成してその機能をテストするには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfb42-109">The application developer can configure bindings for an orchestration to test its functionality during the development process either by using the procedure in this topic.</span></span> <span data-ttu-id="cfb42-110">また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="cfb42-110">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="cfb42-111">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="cfb42-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="cfb42-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="cfb42-112">Prerequisites</span></span>  
 <span data-ttu-id="cfb42-113">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfb42-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="cfb42-114">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="cfb42-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="configure-bindings-for-an-orchestration"></a><span data-ttu-id="cfb42-115">オーケストレーションのバインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="cfb42-115">Configure bindings for an orchestration</span></span>  
  
1.  <span data-ttu-id="cfb42-116">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="cfb42-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="cfb42-117">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、しをオーケストレーションを含むアプリケーション展開バインディングを構成します。</span><span class="sxs-lookup"><span data-stu-id="cfb42-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to configure bindings</span></span>  
  
3.  <span data-ttu-id="cfb42-118">をクリックして**オーケストレーション**をクリックして、バインドを構成するオーケストレーションを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="cfb42-118">Click **Orchestrations**, right-click the orchestration for which you want to configure bindings, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="cfb42-119">クリックして、**バインド** タブとの間、**ホスト**一覧で、オーケストレーションを参加させるホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfb42-119">Click the **Bindings** tab, and from the **Host** list, select the host on which to enlist an orchestration.</span></span>  
  
5.  <span data-ttu-id="cfb42-120">ドロップダウン リストからの一覧で、**受信ポート**各受信論理ポートの横の列が、論理ポートをバインドする受信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfb42-120">From the drop-down lists in the **Receive Ports** column, next to each inbound logical port, select the receive port to which you want to bind the logical port.</span></span>  
  
6.  <span data-ttu-id="cfb42-121">ドロップダウン リストから、**送信ポート/送信ポート グループ**各受信論理ポートの横の列をクリックして、論理ポートをバインドする送信ポートの選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cfb42-121">From the drop-down list in the **Send Ports/Send Port Groups** column, next to each inbound logical port, select the send port to which you want to bind the logical port, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb42-122">参照</span><span class="sxs-lookup"><span data-stu-id="cfb42-122">See Also</span></span>  
 <span data-ttu-id="cfb42-123">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="cfb42-123">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="cfb42-124">[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="cfb42-124">[How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md) </span></span>  
 [<span data-ttu-id="cfb42-125">展開して、BizTalk アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="cfb42-125">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)