---
title: 管理ポートの受信 |Microsoft Docs
description: クイック リンクを作成するなどの BizTalk Server での受信ポートを使用する受信場所を追加、マップを構成し、追跡を有効にします。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 561649b1-66f5-4895-b7a0-92d0a01bfbfb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc31bdab9f3c538a571e3fd6b082a431343683fb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531116"
---
# <a name="manage-receive-ports"></a><span data-ttu-id="0ec34-103">管理の受信ポート</span><span class="sxs-lookup"><span data-stu-id="0ec34-103">Manage Receive Ports</span></span>

## <a name="overview"></a><span data-ttu-id="0ec34-104">概要</span><span class="sxs-lookup"><span data-stu-id="0ec34-104">Overview</span></span>
<span data-ttu-id="0ec34-105">このセクションは、作成、構成、および管理する方法を説明します、BizTalk Server 管理コンソールを使用して BizTalk アプリケーションのポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="0ec34-105">This section describes how to create, configure, and manage receive ports for a BizTalk application by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="0ec34-106">受信ポートは、類似する受信場所の論理的な集まり。</span><span class="sxs-lookup"><span data-stu-id="0ec34-106">A receive port is logical grouping of similar receive locations.</span></span> <span data-ttu-id="0ec34-107">背景情報については、受信ポートを参照してください[受信ポート](../core/receive-ports.md)します。</span><span class="sxs-lookup"><span data-stu-id="0ec34-107">For background information on receive ports, see [Receive Ports](../core/receive-ports.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec34-108">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="0ec34-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="0ec34-109">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0ec34-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0ec34-110">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0ec34-110">Next steps</span></span>
  
-   [<span data-ttu-id="0ec34-111">受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="0ec34-111">Create a Receive Port</span></span>](../core/how-to-create-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-112">受信ポートのインスタンス情報を表示する</span><span class="sxs-lookup"><span data-stu-id="0ec34-112">View Instance Information for a Receive Port</span></span>](../core/how-to-view-instance-information-for-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-113">受信ポートの認証オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="0ec34-113">Configure Authentication Options for a Receive Port</span></span>](../core/how-to-configure-authentication-options-for-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-114">受信ポートが処理に失敗したメッセージのルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="0ec34-114">Enable Routing for Failed Messages for a Receive Port</span></span>](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-115">受信ポートに受信場所を追加する</span><span class="sxs-lookup"><span data-stu-id="0ec34-115">Add a Receive Location to a Receive Port</span></span>](../core/how-to-add-a-receive-location-to-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-116">受信ポートの受信マップを構成する</span><span class="sxs-lookup"><span data-stu-id="0ec34-116">Configure Inbound Maps for a Receive Port</span></span>](../core/how-to-configure-inbound-maps-for-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-117">受信ポートの送信マップを構成する</span><span class="sxs-lookup"><span data-stu-id="0ec34-117">Configure Outbound Maps for a Receive Port</span></span>](../core/how-to-configure-outbound-maps-for-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-118">受信ポートの追跡を構成する</span><span class="sxs-lookup"><span data-stu-id="0ec34-118">Configure Tracking for a Receive Port</span></span>](../core/how-to-configure-tracking-for-a-receive-port.md)  
  
-   [<span data-ttu-id="0ec34-119">受信ポートの削除</span><span class="sxs-lookup"><span data-stu-id="0ec34-119">Delete a Receive Port</span></span>](../core/how-to-delete-a-receive-port.md)