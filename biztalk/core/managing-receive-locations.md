---
title: 管理の受信場所 |Microsoft Docs
description: 作成する、プロパティを変更するを有効にする (&) 無効にすると、証明書を追加、削除など、BizTalk Server で受信場所を使用
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b3ff581-e7e9-4a6e-a9ea-70c55a3b9318
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9522772af3b37ae637f11cee02d99fcffd85d79f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380212"
---
# <a name="manage-receive-locations"></a><span data-ttu-id="fa8d3-103">管理の受信場所</span><span class="sxs-lookup"><span data-stu-id="fa8d3-103">Manage Receive Locations</span></span>

## <a name="overview"></a><span data-ttu-id="fa8d3-104">概要</span><span class="sxs-lookup"><span data-stu-id="fa8d3-104">Overview</span></span>
<span data-ttu-id="fa8d3-105">このセクションでは説明を作成、構成、および BizTalk Server 管理コンソールを使用して受信 BizTalk アプリケーションの場所の管理します。</span><span class="sxs-lookup"><span data-stu-id="fa8d3-105">This section provides instructions on creating, configuring, and managing receive locations for a BizTalk application by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="fa8d3-106">受信場所は、受信メッセージを受信し、そのアドレスで受信したメッセージを処理するメッセージング パイプラインするアドレスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fa8d3-106">A receive location consists of an address at which inbound messages arrive and the messaging pipeline that processes the message received at that address.</span></span> <span data-ttu-id="fa8d3-107">背景情報は、次を参照してください。[受信場所](../core/receive-locations.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa8d3-107">For background information, see [Receive Locations](../core/receive-locations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa8d3-108">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa8d3-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="fa8d3-109">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="fa8d3-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="fa8d3-110">次のステップ</span><span class="sxs-lookup"><span data-stu-id="fa8d3-110">Next steps</span></span> 
  
-   [<span data-ttu-id="fa8d3-111">受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="fa8d3-111">Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-112">受信場所のプロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="fa8d3-112">Edit the Properties of a Receive Location</span></span>](../core/how-to-edit-the-properties-of-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-113">受信場所のインスタンスごとにパイプライン プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="fa8d3-113">Configure Per-instance Pipeline Properties for a Receive Location</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-114">受信場所の有効化</span><span class="sxs-lookup"><span data-stu-id="fa8d3-114">Enable a Receive Location</span></span>](../core/how-to-enable-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-115">受信場所の無効化</span><span class="sxs-lookup"><span data-stu-id="fa8d3-115">Disable a Receive Location</span></span>](../core/how-to-disable-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-116">受信場所のスケジュールを構成する</span><span class="sxs-lookup"><span data-stu-id="fa8d3-116">Configure Scheduling for a Receive Location</span></span>](../core/how-to-configure-scheduling-for-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-117">受信場所に証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fa8d3-117">Assign a Certificate to a Receive Location</span></span>](../core/how-to-assign-a-certificate-to-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-118">受信場所から証明書を削除する</span><span class="sxs-lookup"><span data-stu-id="fa8d3-118">Remove a Certificate from a Receive Location</span></span>](../core/how-to-remove-a-certificate-from-a-receive-location.md)  
  
-   [<span data-ttu-id="fa8d3-119">受信場所の削除</span><span class="sxs-lookup"><span data-stu-id="fa8d3-119">Delete a Receive Location</span></span>](../core/how-to-delete-a-receive-location.md)