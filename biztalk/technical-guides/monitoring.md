---
title: 監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c7d6e8870d435163c83c053f981d42bad1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249630"
---
# <a name="monitoring"></a><span data-ttu-id="dae74-102">監視</span><span class="sxs-lookup"><span data-stu-id="dae74-102">Monitoring</span></span>
<span data-ttu-id="dae74-103">既定では、すべての BizTalk Server の監視とタスクを使用して、既定のアクション アカウント実行プロファイルで BizTalk Server 監視アカウントのターゲットの特定の実行アカウントが定義されていないがある場合。</span><span class="sxs-lookup"><span data-stu-id="dae74-103">By default, all BizTalk Server monitoring and tasks use the default action account when there is no specific Run As Account defined for the target in the Run As Profile of the BizTalk Server Monitoring Account.</span></span> <span data-ttu-id="dae74-104">実行アカウントを BizTalk Server の監視のために必要なアクセス許可の最小セットで構成するには、次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="dae74-104">To configure a Run As Account with the minimum set of permissions that are required for BizTalk Server monitoring purposes, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="dae74-105">アカウントは、監視対象のコンピューターのビルトイン Administrators グループとパフォーマンス モニター ユーザー グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae74-105">The account must be a member of the monitored computer’s built-in Administrators group and Performance Monitors Users group.</span></span>  
  
-   <span data-ttu-id="dae74-106">アカウントは、SQL インスタンスまたはデータベースとジョブ監視されている BizTalk グループをホストしているインスタンス内で SysAdmin ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae74-106">The account must be a member of the SysAdmin role within the SQL instance or instances hosting the databases and jobs for the BizTalk group that is being monitored.</span></span>  
  
-   <span data-ttu-id="dae74-107">BizTalk Server を監視するため、アカウントは BizTalk Operators グループの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae74-107">For BizTalk Server monitoring purposes, the account must be a part of BizTalk Operators group.</span></span>  
  
-   <span data-ttu-id="dae74-108">SCOM コンソールからタスクを実行するため、アカウントは、BizTalk Application Users グループの一部をある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae74-108">For running tasks through SCOM console, the account must be a part of BizTalk Application Users group.</span></span>  
  
-   <span data-ttu-id="dae74-109">管理タスクを実行するには、アカウントは、BizTalk 管理者グループの一部をある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae74-109">For performing administrative tasks, the account must be a part of BizTalk Administrator group.</span></span>