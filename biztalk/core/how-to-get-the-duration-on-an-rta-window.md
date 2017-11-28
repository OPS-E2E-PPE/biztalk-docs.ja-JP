---
title: "期間には、RTA ウィンドウを取得する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- managing [BAM], time intervals
- Get-RTAWindow command [BAM]
ms.assetid: 4e7ad0fd-e7ed-47f7-9435-ef01bbe17afa
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb930c3e9d252a23653f0464e1adaa1e18b4f45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-get-the-duration-on-an-rta-window"></a><span data-ttu-id="0517b-102">RTA 時間帯の期間を取得する方法</span><span class="sxs-lookup"><span data-stu-id="0517b-102">How to Get the Duration on an RTA Window</span></span>
<span data-ttu-id="0517b-103">管理者を使用して、 **rtawindow プロパティの get**コマンドを指定されたリアルタイム集計 (RTA) の実行時間を取得します。</span><span class="sxs-lookup"><span data-stu-id="0517b-103">Administrators use the **get-rtawindow** command to get the duration for the specified real-time aggregation (RTA).</span></span> <span data-ttu-id="0517b-104">このコマンドにより、期間の長さと、その期間の基準となる単位が返されます。</span><span class="sxs-lookup"><span data-stu-id="0517b-104">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
### <a name="to-get-the-duration-on-an-aggregation"></a><span data-ttu-id="0517b-105">集計の期間を取得するには</span><span class="sxs-lookup"><span data-stu-id="0517b-105">To get the duration on an aggregation</span></span>  
  
1.  <span data-ttu-id="0517b-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="0517b-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="0517b-107">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="0517b-107">Navigate to the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="0517b-108">型**bm get rtawindow-ビュー:\<ビュー名 >-アクティビティ:\<アクティビティ名 > -Rta:\<RTA 名 >**です。</span><span class="sxs-lookup"><span data-stu-id="0517b-108">Type **bm get-rtawindow -View:\<view name> -Activity:\<activity name> -Rta:\<RTA name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0517b-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0517b-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="0517b-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0517b-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0517b-111">参照</span><span class="sxs-lookup"><span data-stu-id="0517b-111">See Also</span></span>  
 <span data-ttu-id="0517b-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="0517b-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="0517b-113">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0517b-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="0517b-114">RTA 時間帯の期間を設定する方法</span><span class="sxs-lookup"><span data-stu-id="0517b-114">How to Set the Duration on an RTA Window</span></span>](../core/how-to-set-the-duration-on-an-rta-window.md)