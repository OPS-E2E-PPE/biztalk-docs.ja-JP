---
title: Admin-explorerom (BizTalk Server Samples フォルダー) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, administering
- administering, examples
ms.assetid: f6553138-9ab3-4368-84bf-9813e909e372
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bd9f560c81781a54a79af21464341d68509ed6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360042"
---
# <a name="admin-explorerom-biztalk-server-samples-folder"></a><span data-ttu-id="f04ff-102">Admin-explorerom (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="f04ff-102">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="f04ff-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK) の admin \explorerom フォルダーにサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f04ff-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes samples in the Admin\ExplorerOM folder in its software development kit (SDK).</span></span> <span data-ttu-id="f04ff-104">ここでは、各 BizTalk エクスプ ローラー オブジェクト モデル管理サンプルを構築して、サンプルと予想される結果を実行する手順が示されている機能の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-104">This section provides detailed information about the functionality demonstrated by each BizTalk Explorer object model administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f04ff-105">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04ff-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="f04ff-106">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04ff-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f04ff-107">Microsoft.BizTalk.ExplorerOM.dll は、32 ビットと 64 ビットの両方のプロセスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f04ff-107">Microsoft.BizTalk.ExplorerOM.dll supports both 32 bit and 64 bit processes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f04ff-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f04ff-108">In This Section</span></span>  
  
-   <span data-ttu-id="f04ff-109">[ApplicationManager (BizTalk Server サンプル)](../core/applicationmanager-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-109">[ApplicationManager (BizTalk Server Sample)](../core/applicationmanager-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-110">開始または BizTalk アプリケーションを停止する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-110">Demonstrates how to start or stop a BizTalk application.</span></span>  
  
-   <span data-ttu-id="f04ff-111">[BrowsingArtifacts (BizTalk Server サンプル)](../core/browsingartifacts-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-111">[BrowsingArtifacts (BizTalk Server Sample)](../core/browsingartifacts-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-112">BizTalk アイテムと属性を列挙する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-112">Demonstrates how to enumerate BizTalk artifacts and attributes.</span></span>  
  
-   <span data-ttu-id="f04ff-113">[CBR (BizTalk Server サンプル)](../core/cbr-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-113">[CBR (BizTalk Server Sample)](../core/cbr-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-114">追加して、BizTalk メッセージのコンテンツ ベース ルーティング用の新しい送信ポートの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-114">Demonstrates adding and configuring new send ports for content based routing of BizTalk messages.</span></span>  
  
-   <span data-ttu-id="f04ff-115">[DeleteParty (BizTalk Server サンプル)](../core/deleteparty-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-115">[DeleteParty (BizTalk Server Sample)](../core/deleteparty-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-116">指定したパーティを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-116">Demonstrates how to delete a specified party.</span></span>  
  
-   <span data-ttu-id="f04ff-117">[OrchestrationBinding (BizTalk Server サンプル)](../core/orchestrationbinding-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-117">[OrchestrationBinding (BizTalk Server Sample)](../core/orchestrationbinding-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-118">構成して、オーケストレーションの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-118">Demonstrates configuring and managing orchestrations.</span></span>  
  
-   <span data-ttu-id="f04ff-119">[PartnerManagement (BizTalk Server サンプル)](../core/partnermanagement-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-119">[PartnerManagement (BizTalk Server Sample)](../core/partnermanagement-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-120">作成とパーティの削除について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-120">Demonstrates creating and deleting parties.</span></span> <span data-ttu-id="f04ff-121">ロールにパーティを参加および参加解除についても示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-121">Also demonstrates enlisting and un-enlisting parties with roles.</span></span>  
  
-   <span data-ttu-id="f04ff-122">[ReceiveLocations (BizTalk Server サンプル)](../core/receivelocations-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-122">[ReceiveLocations (BizTalk Server Sample)](../core/receivelocations-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-123">作成および管理する方法を示します 受信ポートの受信場所。</span><span class="sxs-lookup"><span data-stu-id="f04ff-123">Demonstrates how to create and manage receive locations for receive ports.</span></span>  
  
-   <span data-ttu-id="f04ff-124">[ReceivePorts (BizTalk Server サンプル)](../core/receiveports-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-124">[ReceivePorts (BizTalk Server Sample)](../core/receiveports-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-125">受信ポートの作成、列挙、および削除について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-125">Demonstrates creating, enumerating and deleting receive ports.</span></span>  
  
-   <span data-ttu-id="f04ff-126">[SendPortGroups (BizTalk Server サンプル)](../core/sendportgroups-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-126">[SendPortGroups (BizTalk Server Sample)](../core/sendportgroups-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-127">列挙および送信ポート グループを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-127">Demonstrates how to enumerate and manage send port groups.</span></span>  
  
-   <span data-ttu-id="f04ff-128">[SendPorts (BizTalk Server サンプル)](../core/sendports-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-128">[SendPorts (BizTalk Server Sample)](../core/sendports-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-129">列挙および送信ポートを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-129">Demonstrates how to enumerate and manage send ports.</span></span>  
  
-   <span data-ttu-id="f04ff-130">[UnenlistParties (BizTalk Server サンプル)](../core/unenlistparties-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-130">[UnenlistParties (BizTalk Server Sample)](../core/unenlistparties-biztalk-server-sample.md).</span></span> <span data-ttu-id="f04ff-131">すべての展開された BizTalk アセンブリに関連付けられているパーティの参加を解除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04ff-131">Demonstrates how to unenlist all of the parties associated with a deployed BizTalk assembly.</span></span>