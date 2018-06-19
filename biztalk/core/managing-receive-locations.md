---
title: 管理の受信場所 |Microsoft ドキュメント
description: 作成する、プロパティを変更する、有効にする (&) を無効にする、証明書の追加と削除など、BizTalk Server で受信場所を使用
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
ms.openlocfilehash: 8ddaf0756eb2f0b78ddb851d13ff1acab12c6a83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262506"
---
# <a name="manage-receive-locations"></a><span data-ttu-id="86c83-103">管理の受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-103">Manage Receive Locations</span></span>

## <a name="overview"></a><span data-ttu-id="86c83-104">概要</span><span class="sxs-lookup"><span data-stu-id="86c83-104">Overview</span></span>
<span data-ttu-id="86c83-105">このセクションでは、BizTalk Server 管理コンソールを使用して BizTalk アプリケーションの受信場所を作成、構成、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="86c83-105">This section provides instructions on creating, configuring, and managing receive locations for a BizTalk application by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="86c83-106">受信場所は、受信メッセージを受信し、そのアドレスでメッセージを処理するメッセージング パイプラインが受信するアドレスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="86c83-106">A receive location consists of an address at which inbound messages arrive and the messaging pipeline that processes the message received at that address.</span></span> <span data-ttu-id="86c83-107">背景情報について、次を参照してください。[受信場所](../core/receive-locations.md)です。</span><span class="sxs-lookup"><span data-stu-id="86c83-107">For background information, see [Receive Locations](../core/receive-locations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86c83-108">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="86c83-108">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="86c83-109">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="86c83-109">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="86c83-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="86c83-110">Next steps</span></span> 
  
-   [<span data-ttu-id="86c83-111">作成、受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-111">Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-112">プロパティを編集する受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-112">Edit the Properties of a Receive Location</span></span>](../core/how-to-edit-the-properties-of-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-113">インスタンスごとのパイプライン プロパティを構成する受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-113">Configure Per-instance Pipeline Properties for a Receive Location</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-114">有効にする、受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-114">Enable a Receive Location</span></span>](../core/how-to-enable-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-115">無効にする、受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-115">Disable a Receive Location</span></span>](../core/how-to-disable-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-116">スケジュールを構成する受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-116">Configure Scheduling for a Receive Location</span></span>](../core/how-to-configure-scheduling-for-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-117">証明書を割り当てる、受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-117">Assign a Certificate to a Receive Location</span></span>](../core/how-to-assign-a-certificate-to-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-118">証明書を削除する受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-118">Remove a Certificate from a Receive Location</span></span>](../core/how-to-remove-a-certificate-from-a-receive-location.md)  
  
-   [<span data-ttu-id="86c83-119">削除、受信場所</span><span class="sxs-lookup"><span data-stu-id="86c83-119">Delete a Receive Location</span></span>](../core/how-to-delete-a-receive-location.md)