---
title: インデックスを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- indexes [BAM], deleting
- Get-Index command [BAM]
- aggregations [BAM], indexes
ms.assetid: 5f9c7989-3357-451f-8565-1d4b01c1d16a
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db57ce24952c1a1987a61aabcbe24e706a2b63e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385341"
---
# <a name="how-to-delete-an-index"></a><span data-ttu-id="e783a-102">インデックスを削除する方法</span><span class="sxs-lookup"><span data-stu-id="e783a-102">How to Delete an Index</span></span>
<span data-ttu-id="e783a-103">管理者を使用して、**インデックスを削除**特定のチェックポイントで指定したアクティビティのインデックスを削除するコマンド。</span><span class="sxs-lookup"><span data-stu-id="e783a-103">Administrators use the **delete-index** command to delete an index on the specified activity at the specified checkpoints.</span></span>  
  
### <a name="to-delete-an-index-on-an-activity"></a><span data-ttu-id="e783a-104">アクティビティのインデックスを削除するには</span><span class="sxs-lookup"><span data-stu-id="e783a-104">To delete an index on an activity</span></span>  
  
1. <span data-ttu-id="e783a-105">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e783a-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e783a-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="e783a-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="e783a-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e783a-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="e783a-108">型**bm インデックスを削除-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>** します。</span><span class="sxs-lookup"><span data-stu-id="e783a-108">Type **bm delete-index -IndexName:\<index name\> -Activity:\<activity name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e783a-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e783a-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="e783a-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e783a-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e783a-111">参照</span><span class="sxs-lookup"><span data-stu-id="e783a-111">See Also</span></span>  
 <span data-ttu-id="e783a-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="e783a-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="e783a-113">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e783a-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="e783a-114">[インデックスを削除する方法](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="e783a-114">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="e783a-115">集計のインデックスの一覧を取得する方法</span><span class="sxs-lookup"><span data-stu-id="e783a-115">How to Get a List of Indexes on an Aggregation</span></span>](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)