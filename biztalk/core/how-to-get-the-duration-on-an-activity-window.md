---
title: "アクティビティ ウィンドウの期間を取得する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], time intervals
- managing [BAM], time intervals
- Get-ActivityWindow command [BAM]
ms.assetid: d70f6767-f6f7-4ecf-ad9d-4a9d8c76edea
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c5bb2c60133d19887e157f8e06633527e0fa11
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-get-the-duration-on-an-activity-window"></a><span data-ttu-id="9705f-102">アクティビティ時間帯の期間を取得する方法</span><span class="sxs-lookup"><span data-stu-id="9705f-102">How to Get the Duration on an Activity Window</span></span>
<span data-ttu-id="9705f-103">管理者を使用して、 **get activitywindow**コマンドを指定されたアクティビティの期間を取得します。</span><span class="sxs-lookup"><span data-stu-id="9705f-103">Administrators use the **get-activitywindow** command to get the duration for the specified activity.</span></span> <span data-ttu-id="9705f-104">このコマンドにより、期間の長さと、その期間の基準となる単位が返されます。</span><span class="sxs-lookup"><span data-stu-id="9705f-104">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
### <a name="to-get-the-duration-on-an-activity"></a><span data-ttu-id="9705f-105">アクティビティの期間を取得するには</span><span class="sxs-lookup"><span data-stu-id="9705f-105">To get the duration on an activity</span></span>  
  
1.  <span data-ttu-id="9705f-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="9705f-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9705f-107">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="9705f-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="9705f-108">入力 bm get activitywindow-アクティビティ:\<アクティビティ名\>です。</span><span class="sxs-lookup"><span data-stu-id="9705f-108">Type  bm get-activitywindow -Activity:\<activity name\>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9705f-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9705f-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="9705f-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9705f-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9705f-111">参照</span><span class="sxs-lookup"><span data-stu-id="9705f-111">See Also</span></span>  
 <span data-ttu-id="9705f-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="9705f-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="9705f-113">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9705f-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="9705f-114">アクティビティ ウィンドウの期間を設定する方法</span><span class="sxs-lookup"><span data-stu-id="9705f-114">How to Set the Duration on an Activity Window</span></span>](../core/how-to-set-the-duration-on-an-activity-window.md)