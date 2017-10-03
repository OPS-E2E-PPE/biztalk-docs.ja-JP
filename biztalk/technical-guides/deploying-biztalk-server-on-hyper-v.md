---
title: "BizTalk Server の HYPER-V の展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5a18798-3834-4f7d-8d6e-9406120a6e76
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3ddbfafe8a96f524642352b3e8188fd6396795f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-biztalk-server-on-hyper-v"></a><span data-ttu-id="e0d37-102">BizTalk Server の HYPER-V の展開</span><span class="sxs-lookup"><span data-stu-id="e0d37-102">Deploying BizTalk Server on Hyper-V</span></span>
<span data-ttu-id="e0d37-103">このセクションでは推奨事項とインストール、構成、および展開するためのベスト プラクティス、 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] HYPER-V 仮想環境でのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e0d37-103">This section provides recommendations and best practices for installing, configuring, and deploying a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] solution in a Hyper-V virtual environment.</span></span> <span data-ttu-id="e0d37-104">このセクションの内容を配置する利点を説明します、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ソリューションを HYPER-V 仮想環境、HYPER-V 仮想マシンを設定するための推奨事項と推奨事項のインストールと構成[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]HYPER-V で仮想マシン。</span><span class="sxs-lookup"><span data-stu-id="e0d37-104">This section describes advantages of deploying your [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] solution to a Hyper-V virtualized environment, recommendations for setting up the Hyper-V virtual machines and recommendations for installing and configuring [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] on the Hyper-V virtual machines.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0d37-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e0d37-105">In This Section</span></span>  
  
-   [<span data-ttu-id="e0d37-106">仮想化環境の Hyper V を BizTalk Server ソリューションを展開する潜在的なメリット</span><span class="sxs-lookup"><span data-stu-id="e0d37-106">Potential Benefits of Deploying a BizTalk Server Solution to a Hyper-V Virtualized Environment</span></span>](../technical-guides/benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-environment.md)  
  
-   [<span data-ttu-id="e0d37-107">インストールして、BizTalk Server で使用する HYPER-V 仮想マシンの構成</span><span class="sxs-lookup"><span data-stu-id="e0d37-107">Installing and Configuring a Hyper-V Virtual Machine for use with BizTalk Server</span></span>](../technical-guides/install-and-configure-a-hyper-v-virtual-machine-to-use-for-biztalk-server.md)  
  
-   [<span data-ttu-id="e0d37-108">インストールして、HYPER-V の BizTalk Server を構成するためのベスト プラクティスのチェックリスト:</span><span class="sxs-lookup"><span data-stu-id="e0d37-108">Checklist: Best Practices for Installing and Configuring BizTalk Server on Hyper-V</span></span>](../technical-guides/checklist-best-practices-to-install-and-configure-biztalk-server-on-hyper-v.md)