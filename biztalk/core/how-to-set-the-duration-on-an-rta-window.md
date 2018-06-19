---
title: RTA 時間帯の期間を設定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- Set-RTAWindow command [BAM]
- managing [BAM], time intervals
ms.assetid: 3042c3f5-be0f-48fb-9831-daa4868b90fe
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8b43fc846835ab8f24f664d4af54ab99b88576
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971360"
---
# <a name="how-to-set-the-duration-on-an-rta-window"></a><span data-ttu-id="9da66-102">特定の RTA 時間帯の期間を設定する方法</span><span class="sxs-lookup"><span data-stu-id="9da66-102">How to Set the Duration on an RTA Window</span></span>
<span data-ttu-id="9da66-103">管理者を使用して、**セット rtawindow**コマンドを指定されたリアルタイム集計 (RTA) の期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="9da66-103">Administrators use the **set-rtawindow** command to set the duration for the specified real-time aggregation (RTA).</span></span>  
  
### <a name="to-set-the-duration-on-an-aggregation"></a><span data-ttu-id="9da66-104">集計の期間を設定するには</span><span class="sxs-lookup"><span data-stu-id="9da66-104">To set the duration on an aggregation</span></span>  
  
1.  <span data-ttu-id="9da66-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="9da66-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9da66-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="9da66-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="9da66-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9da66-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="9da66-108">型**bm セット rtawindow-ビュー:\<ビュー名\>-アクティビティ:\<アクティビティ名\>-名前:\<RTA 名\>- TimeLength:\<整数\>- TimeUnit: 日 &#124;です。1 時間 &#124;です。分**です。</span><span class="sxs-lookup"><span data-stu-id="9da66-108">Type **bm set-rtawindow -View:\<view name\> -Activity:\<activity name\> -Name:\<RTA name\> -TimeLength:\<integer number\> -TimeUnit:Day&#124;Hour&#124;Minute**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9da66-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9da66-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="9da66-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9da66-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da66-111">参照</span><span class="sxs-lookup"><span data-stu-id="9da66-111">See Also</span></span>  
 <span data-ttu-id="9da66-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="9da66-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="9da66-113">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9da66-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="9da66-114">期間には、RTA ウィンドウを取得する方法</span><span class="sxs-lookup"><span data-stu-id="9da66-114">How to Get the Duration on an RTA Window</span></span>](../core/how-to-get-the-duration-on-an-rta-window.md)