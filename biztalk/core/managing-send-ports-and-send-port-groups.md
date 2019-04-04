---
title: 送信ポートと送信ポート グループの管理 |Microsoft Docs
description: リンクを作成するには、構成、参加、参加解除、および開始し、停止の BizTalk Server での送信ポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db45f9f9-b32a-4b9c-a3bf-8c271d0f0cf9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3fe64a46ec4dd80d278e36f91406db0c431972
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015755"
---
# <a name="manage-send-ports-and-send-port-groups"></a><span data-ttu-id="8579d-103">送信ポートと送信ポート グループを管理します。</span><span class="sxs-lookup"><span data-stu-id="8579d-103">Manage Send Ports and Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="8579d-104">概要</span><span class="sxs-lookup"><span data-stu-id="8579d-104">Overview</span></span>
<span data-ttu-id="8579d-105">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションの送信ポートおよび送信ポート グループを作成、構成、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8579d-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to create, configure, and manage send ports and send port groups in a BizTalk application.</span></span> <span data-ttu-id="8579d-106">送信ポートは、メッセージの送信先や、場合によっては応答の受信先となる場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8579d-106">A send port specifies the location to which messages are sent and optionally responses are received.</span></span> <span data-ttu-id="8579d-107">送信ポートのサービスの新しいインスタンスを作成すると、送信ポートにメッセージが送信されると呼ばれる時間を*サービス インスタンス*します。</span><span class="sxs-lookup"><span data-stu-id="8579d-107">Any time a message is sent to a send port, a new instance of the send port service is created, which is called a *service instance*.</span></span>  
  
 <span data-ttu-id="8579d-108">送信ポート グループは、送信ポートの論理的な集まりです。</span><span class="sxs-lookup"><span data-stu-id="8579d-108">A send port group is a logical grouping of send ports.</span></span> <span data-ttu-id="8579d-109">1 つの送信ポート グループに送信されたメッセージは、関連するすべての送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8579d-109">When a message is sent to a send port group, it is routed to all of the associated send ports.</span></span>  <span data-ttu-id="8579d-110">送信ポートおよび送信ポート グループの背景については、[送信ポートと送信ポート グループ](../core/send-ports-and-send-port-groups.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8579d-110">For background information about send ports and send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8579d-111">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="8579d-111">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="8579d-112">WMI の使用方法の詳細については、、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8579d-112">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="8579d-113">BizTalk アプリケーションの開発中に、オーケストレーション デザイナーなど、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk デザイン ツールを使用して、送信ポートおよび送信ポート グループを作成および構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8579d-113">While developing a BizTalk application, the developer can use BizTalk design tools in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], such as Orchestration Designer, to create and configure send ports and send port groups.</span></span> <span data-ttu-id="8579d-114">詳細については、[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8579d-114">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8579d-115">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8579d-115">Next steps</span></span>
  
-   [<span data-ttu-id="8579d-116">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="8579d-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)  
  
-   [<span data-ttu-id="8579d-117">送信ポート グループの作成および構成</span><span class="sxs-lookup"><span data-stu-id="8579d-117">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)  
  
-   [<span data-ttu-id="8579d-118">送信ポートまたは送信ポート グループの登録</span><span class="sxs-lookup"><span data-stu-id="8579d-118">Enlist a Send Port or Send Port Group</span></span>](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="8579d-119">送信ポートまたは送信ポート グループの登録解除</span><span class="sxs-lookup"><span data-stu-id="8579d-119">Unenlist a Send Port or Send Port Group</span></span>](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="8579d-120">送信ポートまたは送信ポート グループを開始する</span><span class="sxs-lookup"><span data-stu-id="8579d-120">Start a Send Port or Send Port Group</span></span>](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="8579d-121">送信ポートまたは送信ポート グループを停止する</span><span class="sxs-lookup"><span data-stu-id="8579d-121">Stop a Send Port or Send Port Group</span></span>](../core/how-to-stop-a-send-port-or-send-port-group.md)