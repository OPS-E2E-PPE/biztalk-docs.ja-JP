---
title: 送信ポートと送信ポート グループの管理 |Microsoft ドキュメント
description: リンクを作成、構成、参加、参加解除、および開始し、停止の BizTalk Server での送信ポート
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
ms.openlocfilehash: 928160ed5b67602c8fc8d9d646459bf2425d7a01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262706"
---
# <a name="manage-send-ports-and-send-port-groups"></a><span data-ttu-id="d7d65-103">送信ポートと送信ポート グループを管理します。</span><span class="sxs-lookup"><span data-stu-id="d7d65-103">Manage Send Ports and Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="d7d65-104">概要</span><span class="sxs-lookup"><span data-stu-id="d7d65-104">Overview</span></span>
<span data-ttu-id="d7d65-105">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションの送信ポートおよび送信ポート グループを作成、構成、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d65-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to create, configure, and manage send ports and send port groups in a BizTalk application.</span></span> <span data-ttu-id="d7d65-106">送信ポートは、メッセージの送信先や、場合によっては応答の受信先となる場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d65-106">A send port specifies the location to which messages are sent and optionally responses are received.</span></span> <span data-ttu-id="d7d65-107">呼び出される送信ポート サービスの新しいインスタンスを作成すると、送信ポートにメッセージが送られるたび、*サービス インスタンス*です。</span><span class="sxs-lookup"><span data-stu-id="d7d65-107">Any time a message is sent to a send port, a new instance of the send port service is created, which is called a *service instance*.</span></span>  
  
 <span data-ttu-id="d7d65-108">送信ポート グループは、送信ポートの論理的な集まりです。</span><span class="sxs-lookup"><span data-stu-id="d7d65-108">A send port group is a logical grouping of send ports.</span></span> <span data-ttu-id="d7d65-109">1 つの送信ポート グループに送信されたメッセージは、関連するすべての送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d7d65-109">When a message is sent to a send port group, it is routed to all of the associated send ports.</span></span>  <span data-ttu-id="d7d65-110">送信ポートおよび送信ポート グループに関する背景情報については、次を参照してください。[送信ポートおよび送信ポート グループ](../core/send-ports-and-send-port-groups.md)です。</span><span class="sxs-lookup"><span data-stu-id="d7d65-110">For background information about send ports and send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7d65-111">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="d7d65-111">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="d7d65-112">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d7d65-112">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d7d65-113">BizTalk アプリケーションの開発中に、オーケストレーション デザイナーなど、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk デザイン ツールを使用して、送信ポートおよび送信ポート グループを作成および構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d7d65-113">While developing a BizTalk application, the developer can use BizTalk design tools in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], such as Orchestration Designer, to create and configure send ports and send port groups.</span></span> <span data-ttu-id="d7d65-114">詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="d7d65-114">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d7d65-115">次の手順</span><span class="sxs-lookup"><span data-stu-id="d7d65-115">Next steps</span></span>
  
-   [<span data-ttu-id="d7d65-116">作成して、送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="d7d65-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)  
  
-   [<span data-ttu-id="d7d65-117">作成して、送信ポート グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7d65-117">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)  
  
-   [<span data-ttu-id="d7d65-118">送信ポートまたは送信ポート グループを参加させる</span><span class="sxs-lookup"><span data-stu-id="d7d65-118">Enlist a Send Port or Send Port Group</span></span>](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="d7d65-119">送信ポートまたは送信ポート グループを参加解除します。</span><span class="sxs-lookup"><span data-stu-id="d7d65-119">Unenlist a Send Port or Send Port Group</span></span>](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="d7d65-120">送信ポートまたは送信ポート グループを開始します。</span><span class="sxs-lookup"><span data-stu-id="d7d65-120">Start a Send Port or Send Port Group</span></span>](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="d7d65-121">送信ポートまたは送信ポート グループを停止します。</span><span class="sxs-lookup"><span data-stu-id="d7d65-121">Stop a Send Port or Send Port Group</span></span>](../core/how-to-stop-a-send-port-or-send-port-group.md)