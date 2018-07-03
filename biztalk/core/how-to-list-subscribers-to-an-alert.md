---
title: 警告にサブスクライバーを一覧表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, listing subscribers
- managing [BAM], listing alert subscribers
- subscriptions, listing subscribers
ms.assetid: 760cc88f-896d-43a3-a4af-b2a836190276
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae95582e2923c682a5d4138235029f21293fd847
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972651"
---
# <a name="how-to-list-subscribers-to-an-alert"></a><span data-ttu-id="6e8db-102">警告のサブスクライバーを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="6e8db-102">How to List Subscribers to an Alert</span></span>
<span data-ttu-id="6e8db-103">管理者を使用して、 **get サブスクリプション**コマンドを指定した警告のサブスクライバーをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6e8db-103">Administrators use the **get-subscriptions** command to list all of the subscribers to a specified alert.</span></span>  
  
### <a name="to-list-subscribers-to-an-alert"></a><span data-ttu-id="6e8db-104">警告のサブスクライバーを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="6e8db-104">To list subscribers to an alert</span></span>  
  
1. <span data-ttu-id="6e8db-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="6e8db-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="6e8db-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e8db-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="6e8db-107">型**bm get-サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>** します。</span><span class="sxs-lookup"><span data-stu-id="6e8db-107">Type **bm get-subscriptions -View:\<view name\> -Alert:\<alert name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6e8db-108">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e8db-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="6e8db-109">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6e8db-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8db-110">参照</span><span class="sxs-lookup"><span data-stu-id="6e8db-110">See Also</span></span>  
 <span data-ttu-id="6e8db-111">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="6e8db-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="6e8db-112">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="6e8db-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)