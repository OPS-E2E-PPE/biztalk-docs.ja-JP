---
title: オーケストレーションのバインド解除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae12bd07729aa473cdc52eabec7ad409d8fa0a1a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333864"
---
# <a name="unbind-an-orchestration"></a><span data-ttu-id="d966b-102">オーケストレーションのバインド解除します。</span><span class="sxs-lookup"><span data-stu-id="d966b-102">Unbind an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="d966b-103">概要</span><span class="sxs-lookup"><span data-stu-id="d966b-103">Overview</span></span>
<span data-ttu-id="d966b-104">ここでは、BizTalk Server 管理コンソールを使用して、各種のバインド (受信ポート、送信ポート、ホスト) をオーケストレーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d966b-104">This topic describes how to use the BizTalk Server Administration console to remove receive port, send port, or host bindings from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d966b-105">アプリケーション開発者がオーケストレーションのバインドを削除するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d966b-105">The application developer can remove bindings for an orchestration  by using the procedure in this topic.</span></span> <span data-ttu-id="d966b-106">また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="d966b-106">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="d966b-107">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d966b-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="d966b-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="d966b-108">Prerequisites</span></span>  
 <span data-ttu-id="d966b-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d966b-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d966b-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="d966b-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="remove-bindings-from-an-orchestration"></a><span data-ttu-id="d966b-111">オーケストレーションからバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="d966b-111">Remove bindings from an orchestration</span></span>  
  
1. <span data-ttu-id="d966b-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="d966b-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d966b-113">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、削除するオーケストレーションを含むアプリケーションを展開バインド</span><span class="sxs-lookup"><span data-stu-id="d966b-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration from which you want to remove bindings</span></span>  
  
3. <span data-ttu-id="d966b-114">をクリックして**オーケストレーション**は、オーケストレーションを右クリックし、**プロパティ**、順にクリックします**バインド**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="d966b-114">Click **Orchestrations**, right-click the orchestration, click **Properties**, and then click **Bindings** in the left pane.</span></span>  
  
4. <span data-ttu-id="d966b-115">ホストのバインドを削除する、**ホスト**一覧で、  **\<None\>** します。</span><span class="sxs-lookup"><span data-stu-id="d966b-115">To remove the host bindings, from the **Hosts** list, select **\<None\>**.</span></span>  
  
5. <span data-ttu-id="d966b-116">削除する [ドロップダウン リストからの受信ポートのバインド、**受信ポート**、] をクリックして**\<なし\>**。</span><span class="sxs-lookup"><span data-stu-id="d966b-116">To remove receive port bindings, from the drop-down list under **Receive Ports**, click **\<None\>**.</span></span>  
  
6. <span data-ttu-id="d966b-117">下のドロップダウン リストから送信ポートのバインドを削除する**送信ポート/送信ポート グループ**、 をクリックして **\<None\>** します。</span><span class="sxs-lookup"><span data-stu-id="d966b-117">To remove send port bindings, from the drop-down list under **Send Ports/Send Port Groups**, click **\<None\>**.</span></span>  
  
7. <span data-ttu-id="d966b-118">バインド バインドを削除したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d966b-118">When finished removing bindings, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d966b-119">参照</span><span class="sxs-lookup"><span data-stu-id="d966b-119">See Also</span></span>  
 <span data-ttu-id="d966b-120">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="d966b-120">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="d966b-121">[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="d966b-121">[How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md) </span></span>  
 [<span data-ttu-id="d966b-122">BizTalk アプリケーション展開、管理</span><span class="sxs-lookup"><span data-stu-id="d966b-122">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)