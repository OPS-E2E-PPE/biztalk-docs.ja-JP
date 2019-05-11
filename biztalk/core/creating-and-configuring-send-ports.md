---
title: 送信ポートのクイック リンクを作成および構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b26ed07-b7ed-48a5-9bd9-dfba9c1d3c02
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0fc4fa887c8e9855d9067e5166afb4f2afa4d7a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353861"
---
# <a name="creating-and-configuring-send-ports"></a><span data-ttu-id="a2a7e-102">作成と送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="a2a7e-102">Creating and Configuring Send Ports</span></span>

## <a name="overview"></a><span data-ttu-id="a2a7e-103">概要</span><span class="sxs-lookup"><span data-stu-id="a2a7e-103">Overview</span></span>
<span data-ttu-id="a2a7e-104">このセクションで使用方法については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを作成して BizTalk アプリケーションの送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="a2a7e-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to create and configure send ports for a BizTalk application.</span></span> <span data-ttu-id="a2a7e-105">送信ポートは、場所をメッセージは送信またはメッセージから受信され、名前によって一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="a2a7e-105">A send port is a location to which messages are sent or from which messages are received and is uniquely identified by its name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2a7e-106">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2a7e-106">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="a2a7e-107">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a2a7e-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a2a7e-108">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a2a7e-108">Next steps</span></span>
  
-   [<span data-ttu-id="a2a7e-109">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="a2a7e-109">Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)  
  
-   [<span data-ttu-id="a2a7e-110">送信ポートのインスタンス情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-110">View Instance Information for a Send Port</span></span>](../core/how-to-view-instance-information-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-111">送信ポートのインスタンスごとにパイプライン プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-111">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-112">送信ポート グループへの送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="a2a7e-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="a2a7e-113">送信ポート グループから送信ポートを削除する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="a2a7e-114">送信ポートに対してトランスポートの詳細オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-114">Configure Transport Advanced Options for a Send Port</span></span>](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-115">送信ポートに対してバックアップ トランスポートのオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-115">Configure Backup Transport Options for a Send Port</span></span>](../core/how-to-configure-backup-transport-options-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-116">送信ポートの受信マップを構成する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-116">Configure Inbound Maps for a Send Port</span></span>](../core/how-to-configure-inbound-maps-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-117">送信ポートの送信マップを構成する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-117">Configure Outbound Maps for a Send Port</span></span>](../core/how-to-configure-outbound-maps-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-118">送信ポートのフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-118">Configure Filters for a Send Port</span></span>](../core/how-to-configure-filters-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-119">送信ポートに証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a2a7e-119">Assign a Certificate to a Send Port</span></span>](../core/how-to-assign-a-certificate-to-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-120">送信ポートから証明書を削除する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-120">Remove a Certificate from a Send Port</span></span>](../core/how-to-remove-a-certificate-from-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-121">送信ポートの追跡を構成する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-121">Configure Tracking for a Send Port</span></span>](../core/how-to-configure-tracking-for-a-send-port.md)  
  
-   [<span data-ttu-id="a2a7e-122">送信ポートを削除する</span><span class="sxs-lookup"><span data-stu-id="a2a7e-122">Delete a Send Port</span></span>](../core/how-to-delete-a-send-port.md)