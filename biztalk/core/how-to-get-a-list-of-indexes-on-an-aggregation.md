---
title: 集計のインデックスの一覧を取得する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- indexes [BAM], listing indexes
- aggregations [BAM], listing indexes
- Get-Index command [BAM]
ms.assetid: 46a4a2fc-10f8-499c-bf2a-d0a19bb84151
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c7803ba15bb06297b477e9bfcc5ad0535f0168b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385034"
---
# <a name="how-to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="b371e-102">集計のインデックスの一覧を取得する方法</span><span class="sxs-lookup"><span data-stu-id="b371e-102">How to Get a List of Indexes on an Aggregation</span></span>
<span data-ttu-id="b371e-103">管理者を使用して、 **get インデックス**コマンドを指定したアクティビティのすべてのインデックスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b371e-103">Administrators use the **get-index** command to get a list of all the indexes on the specified activity.</span></span>  
  
### <a name="to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="b371e-104">集計のインデックスの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="b371e-104">To get a list of indexes on an aggregation</span></span>  
  
1. <span data-ttu-id="b371e-105">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="b371e-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b371e-106">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="b371e-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="b371e-107">型**bm get-インデックスのアクティビティ:\<アクティビティ名\>** します。</span><span class="sxs-lookup"><span data-stu-id="b371e-107">Type **bm get-index -Activity:\<activity name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b371e-108">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b371e-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="b371e-109">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b371e-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b371e-110">参照</span><span class="sxs-lookup"><span data-stu-id="b371e-110">See Also</span></span>  
 <span data-ttu-id="b371e-111">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="b371e-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="b371e-112">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b371e-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="b371e-113">[インデックスを削除する方法](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="b371e-113">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="b371e-114">インデックスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b371e-114">How to Create an Index</span></span>](../core/how-to-create-an-index.md)