---
title: リンクを作成および構成する送信ポート |Microsoft ドキュメント
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
ms.openlocfilehash: 31361c9a6dff1d35c21bede4a82d513c6a073218
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238250"
---
# <a name="creating-and-configuring-send-ports"></a><span data-ttu-id="1f7f5-102">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="1f7f5-102">Creating and Configuring Send Ports</span></span>

## <a name="overview"></a><span data-ttu-id="1f7f5-103">概要</span><span class="sxs-lookup"><span data-stu-id="1f7f5-103">Overview</span></span>
<span data-ttu-id="1f7f5-104">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションの送信ポートを作成および構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to create and configure send ports for a BizTalk application.</span></span> <span data-ttu-id="1f7f5-105">送信ポートは、メッセージの送信先または受信メッセージの送信元となる場所であり、名前によって一意に識別できます。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-105">A send port is a location to which messages are sent or from which messages are received and is uniquely identified by its name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f7f5-106">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-106">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="1f7f5-107">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1f7f5-108">次の手順</span><span class="sxs-lookup"><span data-stu-id="1f7f5-108">Next steps</span></span>
  
-   [<span data-ttu-id="1f7f5-109">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-109">Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)  
  
-   [<span data-ttu-id="1f7f5-110">送信ポートのインスタンス情報の表示</span><span class="sxs-lookup"><span data-stu-id="1f7f5-110">View Instance Information for a Send Port</span></span>](../core/how-to-view-instance-information-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-111">送信ポートのインスタンスごとにパイプライン プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-111">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-112">送信ポート、送信ポート グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-112">Add a Send Port to a Send Port Group</span></span>](../core/how-to-add-a-send-port-to-a-send-port-group.md)  
  
-   [<span data-ttu-id="1f7f5-113">送信ポート、送信ポート グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-113">Remove a Send Port from a Send Port Group</span></span>](../core/how-to-remove-a-send-port-from-a-send-port-group.md)  
  
-   [<span data-ttu-id="1f7f5-114">トランスポートの詳細、送信ポートのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-114">Configure Transport Advanced Options for a Send Port</span></span>](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-115">送信ポートに対してバックアップ トランスポートのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-115">Configure Backup Transport Options for a Send Port</span></span>](../core/how-to-configure-backup-transport-options-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-116">送信ポートの受信マップを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-116">Configure Inbound Maps for a Send Port</span></span>](../core/how-to-configure-inbound-maps-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-117">送信ポートの送信マップを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-117">Configure Outbound Maps for a Send Port</span></span>](../core/how-to-configure-outbound-maps-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-118">送信ポートのフィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-118">Configure Filters for a Send Port</span></span>](../core/how-to-configure-filters-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-119">送信ポートに証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="1f7f5-119">Assign a Certificate to a Send Port</span></span>](../core/how-to-assign-a-certificate-to-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-120">送信ポートから証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-120">Remove a Certificate from a Send Port</span></span>](../core/how-to-remove-a-certificate-from-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-121">送信ポートの追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-121">Configure Tracking for a Send Port</span></span>](../core/how-to-configure-tracking-for-a-send-port.md)  
  
-   [<span data-ttu-id="1f7f5-122">送信ポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f7f5-122">Delete a Send Port</span></span>](../core/how-to-delete-a-send-port.md)