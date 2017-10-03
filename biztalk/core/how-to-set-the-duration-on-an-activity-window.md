---
title: "アクティビティ ウィンドウの期間を設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Set-ActivityWindow command [BAM]
- activities [BAM], time intervals
- managing [BAM], time intervals
ms.assetid: e39c315e-f215-4f81-9774-cf7aedf6ba33
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50b4aaa0187c10038dde907fa8b5fa8c595d2847
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-duration-on-an-activity-window"></a><span data-ttu-id="fec7c-102">アクティビティ時間帯の期間を設定する方法</span><span class="sxs-lookup"><span data-stu-id="fec7c-102">How to Set the Duration on an Activity Window</span></span>
<span data-ttu-id="fec7c-103">管理者を使用して、**セット activitywindow**コマンドを指定したアクティビティの期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="fec7c-103">Administrators use the **set-activitywindow** command to set the duration for the specified activity.</span></span>  
  
### <a name="to-set-the-duration-on-an-activity"></a><span data-ttu-id="fec7c-104">アクティビティの期間を設定するには</span><span class="sxs-lookup"><span data-stu-id="fec7c-104">To set the duration on an activity</span></span>  
  
1.  <span data-ttu-id="fec7c-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="fec7c-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="fec7c-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="fec7c-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="fec7c-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fec7c-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="fec7c-108">型**bm セット activitywindow-アクティビティ:\<アクティビティ名 > - TimeLength:\<整数の番号 > - TimeUnit: 月 &#124; 日付 & #124 です。1 時間 & #124 です。分**です。</span><span class="sxs-lookup"><span data-stu-id="fec7c-108">Type **bm set-activitywindow -Activity:\<activity name> -TimeLength:\<integer number> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fec7c-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fec7c-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="fec7c-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fec7c-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec7c-111">参照</span><span class="sxs-lookup"><span data-stu-id="fec7c-111">See Also</span></span>  
 <span data-ttu-id="fec7c-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="fec7c-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="fec7c-113">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fec7c-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="fec7c-114">アクティビティ ウィンドウの期間を取得する方法</span><span class="sxs-lookup"><span data-stu-id="fec7c-114">How to Get the Duration on an Activity Window</span></span>](../core/how-to-get-the-duration-on-an-activity-window.md)