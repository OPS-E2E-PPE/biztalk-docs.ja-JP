---
title: "オーケストレーションをバインド解除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b8adc77e5e8579339931e49abb501f9981e5fc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="unbind-an-orchestration"></a><span data-ttu-id="6615d-102">オーケストレーションをバインド解除します。</span><span class="sxs-lookup"><span data-stu-id="6615d-102">Unbind an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="6615d-103">概要</span><span class="sxs-lookup"><span data-stu-id="6615d-103">Overview</span></span>
<span data-ttu-id="6615d-104">ここでは、BizTalk Server 管理コンソールを使用して、各種のバインド (受信ポート、送信ポート、ホスト) をオーケストレーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6615d-104">This topic describes how to use the BizTalk Server Administration console to remove receive port, send port, or host bindings from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6615d-105">アプリケーション開発者がオーケストレーションのバインドを削除するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6615d-105">The application developer can remove bindings for an orchestration  by using the procedure in this topic.</span></span> <span data-ttu-id="6615d-106">また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="6615d-106">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="6615d-107">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6615d-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="6615d-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="6615d-108">Prerequisites</span></span>  
 <span data-ttu-id="6615d-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6615d-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6615d-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="6615d-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="remove-bindings-from-an-orchestration"></a><span data-ttu-id="6615d-111">オーケストレーションからバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="6615d-111">Remove bindings from an orchestration</span></span>  
  
1.  <span data-ttu-id="6615d-112">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="6615d-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6615d-113">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、しを削除するオーケストレーションを含むアプリケーション展開バインド</span><span class="sxs-lookup"><span data-stu-id="6615d-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration from which you want to remove bindings</span></span>  
  
3.  <span data-ttu-id="6615d-114">をクリックして**オーケストレーション**、オーケストレーションを右クリックし、をクリックして**プロパティ**、順にクリック**バインド**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="6615d-114">Click **Orchestrations**, right-click the orchestration, click **Properties**, and then click **Bindings** in the left pane.</span></span>  
  
4.  <span data-ttu-id="6615d-115">ホストのバインドを削除する、**ホスト**一覧で、  **\<None\>**です。</span><span class="sxs-lookup"><span data-stu-id="6615d-115">To remove the host bindings, from the **Hosts** list, select **\<None\>**.</span></span>  
  
5.  <span data-ttu-id="6615d-116">削除する下にあるドロップダウン リストからの受信ポートのバインド、**受信ポート**をクリックして **\<None\>**です。</span><span class="sxs-lookup"><span data-stu-id="6615d-116">To remove receive port bindings, from the drop-down list under **Receive Ports**, click **\<None\>**.</span></span>  
  
6.  <span data-ttu-id="6615d-117">下にあるドロップダウン リストから送信ポートのバインドを削除する**送信ポート/送信ポート グループ**をクリックして **\<None\>**です。</span><span class="sxs-lookup"><span data-stu-id="6615d-117">To remove send port bindings, from the drop-down list under **Send Ports/Send Port Groups**, click **\<None\>**.</span></span>  
  
7.  <span data-ttu-id="6615d-118">バインド バインドを削除したらをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6615d-118">When finished removing bindings, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6615d-119">参照</span><span class="sxs-lookup"><span data-stu-id="6615d-119">See Also</span></span>  
 <span data-ttu-id="6615d-120">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="6615d-120">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="6615d-121">[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="6615d-121">[How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md) </span></span>  
 [<span data-ttu-id="6615d-122">展開して、BizTalk アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="6615d-122">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)