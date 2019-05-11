---
title: サブスクライバーを警告から削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- managing [BAM], deleting alert subscibers
- alerts, subscribers
ms.assetid: d5571863-26e3-4c1b-991f-538cd1fef347
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cc00662ce082721ee8c6d385a5c83cd105d0b83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335000"
---
# <a name="how-to-remove-subscribers-from-an-alert"></a><span data-ttu-id="bf630-102">サブスクライバーを警告から削除する方法</span><span class="sxs-lookup"><span data-stu-id="bf630-102">How to Remove Subscribers from an Alert</span></span>
<span data-ttu-id="bf630-103">管理者を使用して、**削除サブスクリプション**アラートから、サブスクライバーとして、指定されたユーザーを削除するコマンド。</span><span class="sxs-lookup"><span data-stu-id="bf630-103">Administrators use the **remove-subscription** command to remove the specified user as a subscriber from an alert.</span></span>  
  
### <a name="to-remove-subscribers-from-an-alert"></a><span data-ttu-id="bf630-104">サブスクライバーを警告から削除するには</span><span class="sxs-lookup"><span data-stu-id="bf630-104">To remove subscribers from an alert</span></span>  
  
1. <span data-ttu-id="bf630-105">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="bf630-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="bf630-106">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="bf630-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="bf630-107">型**bm 削除-サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>-accountname:\<アカウント名\>** します。</span><span class="sxs-lookup"><span data-stu-id="bf630-107">Type **bm remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf630-108">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf630-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="bf630-109">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bf630-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf630-110">参照</span><span class="sxs-lookup"><span data-stu-id="bf630-110">See Also</span></span>  
 <span data-ttu-id="bf630-111">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="bf630-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="bf630-112">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="bf630-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="bf630-113">警告にサブスクライバーを追加する方法</span><span class="sxs-lookup"><span data-stu-id="bf630-113">How to Add Subscribers to an Alert</span></span>](../core/how-to-add-subscribers-to-an-alert.md)