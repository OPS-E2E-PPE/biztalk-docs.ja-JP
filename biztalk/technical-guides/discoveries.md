---
title: 検出 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5350c4b3-ecc5-487e-a75a-16af090ffa06
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48eb4faf03dddb50122011a20349578ef6ab64c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305695"
---
# <a name="discoveries"></a><span data-ttu-id="0c67b-102">検出</span><span class="sxs-lookup"><span data-stu-id="0c67b-102">Discoveries</span></span>
<span data-ttu-id="0c67b-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]一元的な管理と BizTalk Server に関連する成果物のエクスペリエンスの監視管理パックを提供します。</span><span class="sxs-lookup"><span data-stu-id="0c67b-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack provides a centralized management and monitoring experience for BizTalk Server related artifacts.</span></span>  
  
## <a name="discovery-of-artifacts"></a><span data-ttu-id="0c67b-104">成果物の検出</span><span class="sxs-lookup"><span data-stu-id="0c67b-104">Discovery of artifacts</span></span>  
 <span data-ttu-id="0c67b-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、監視エージェントが 1 つのランタイム コンピューターから成果物を検出します。</span><span class="sxs-lookup"><span data-stu-id="0c67b-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack, the monitoring agents discover the artifacts from a single runtime machine.</span></span> <span data-ttu-id="0c67b-106">既定では、管理パックは、BizTalk グループに参加している最初のコンピューター上のアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="0c67b-106">By default, the management pack discovers the artifacts on the first machine that is joined to the BizTalk group.</span></span> <span data-ttu-id="0c67b-107">ただし、任意のコンピューター上のアイテムを検出する場合は、自動検出の設定を変更する上書き機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c67b-107">However if you want plan to discover the artifacts on the machine of your choice then you must use the override feature to change the settings for automatic discovery.</span></span> <span data-ttu-id="0c67b-108">自動検出の設定を変更する上書きを使用して、次を参照してください。[オプションの構成](../technical-guides/optional-configurations.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c67b-108">To use an override to change the setting for automatic discovery, see [Optional Configurations](../technical-guides/optional-configurations.md).</span></span>  
  
 <span data-ttu-id="0c67b-109">アクションと SCOM のオペレーション コンソールから実行されるタスク、成果物が探索され、ランタイムのすべてのマシンの監視に固有です。</span><span class="sxs-lookup"><span data-stu-id="0c67b-109">The actions and tasks that are carried from the SCOM Operations Console are unique to the artifacts that are discovered and monitored on all runtime machines.</span></span> <span data-ttu-id="0c67b-110">BizTalk Server 管理パックは、すべてのタスクを表示するには、次のようにクリックします。**タスク**  /2012 R2 の Operations Manager 2007 オペレーション コンソールの [監視] ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="0c67b-110">To see all the tasks the BizTalk Server Management Pack provides, click **Tasks** in the Monitoring pane of the Operations Manager 2007 R2/2012 Operations Console.</span></span>