---
title: "監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c45bb70e3f92f4c85def07add4390a0451cb87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring"></a><span data-ttu-id="fb460-102">監視</span><span class="sxs-lookup"><span data-stu-id="fb460-102">Monitoring</span></span>
<span data-ttu-id="fb460-103">既定では、すべての BizTalk Server の監視およびタスクを使用して既定のアクション アカウントが、実行プロファイルで、BizTalk Server 監視アカウントのターゲットの特定の実行アカウントが定義されていない場合。</span><span class="sxs-lookup"><span data-stu-id="fb460-103">By default, all BizTalk Server monitoring and tasks use the default action account when there is no specific Run As Account defined for the target in the Run As Profile of the BizTalk Server Monitoring Account.</span></span> <span data-ttu-id="fb460-104">実行アカウントを BizTalk Server を監視するために必要なアクセス許可の最小セットを構成するのには、次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb460-104">To configure a Run As Account with the minimum set of permissions that are required for BizTalk Server monitoring purposes, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="fb460-105">アカウントは、監視対象のコンピューターの組み込みの Administrators グループとパフォーマンス モニターのユーザー グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb460-105">The account must be a member of the monitored computer’s built-in Administrators group and Performance Monitors Users group.</span></span>  
  
-   <span data-ttu-id="fb460-106">アカウントは、SQL インスタンスまたはデータベースとジョブが監視されている BizTalk グループをホストしているインスタンス内の SysAdmin ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb460-106">The account must be a member of the SysAdmin role within the SQL instance or instances hosting the databases and jobs for the BizTalk group that is being monitored.</span></span>  
  
-   <span data-ttu-id="fb460-107">BizTalk Server が監視するため、アカウントは、BizTalk Operators グループの一部をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb460-107">For BizTalk Server monitoring purposes, the account must be a part of BizTalk Operators group.</span></span>  
  
-   <span data-ttu-id="fb460-108">を、SCOM コンソールのタスクを実行するため、アカウントは、BizTalk Application Users グループの一部をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb460-108">For running tasks through SCOM console, the account must be a part of BizTalk Application Users group.</span></span>  
  
-   <span data-ttu-id="fb460-109">管理タスクを実行するため、アカウントは、BizTalk 管理者グループの一部にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb460-109">For performing administrative tasks, the account must be a part of BizTalk Administrator group.</span></span>