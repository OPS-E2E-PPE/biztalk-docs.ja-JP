---
title: インデックスを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Create-Index command [BAM]
- indexes [BAM], creating
- indexes [BAM], aggregations
- creating, indexes [BAM]
- aggregations [BAM], indexes
ms.assetid: 456d94e6-2e84-4d12-ad38-49f9eeb103f3
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 764456fa0f58c1bc5fe526b0ceede2e85ff6f85b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339528"
---
# <a name="how-to-create-an-index"></a><span data-ttu-id="23b9e-102">インデックスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="23b9e-102">How to Create an Index</span></span>
<span data-ttu-id="23b9e-103">管理者を使用して、**インデックスの作成**コマンドを特定のチェックポイントで指定したアクティビティにインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="23b9e-103">Administrators use the **create-index** command to create an index on the specified activity at the specified checkpoints.</span></span>  
  
### <a name="to-create-an-index-on-an-activity"></a><span data-ttu-id="23b9e-104">アクティビティにインデックスを作成するには</span><span class="sxs-lookup"><span data-stu-id="23b9e-104">To create an index on an activity</span></span>  
  
1. <span data-ttu-id="23b9e-105">コマンド プロンプトから次のディレクトリを参照してください。[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="23b9e-105">From a command prompt, browse to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
2. <span data-ttu-id="23b9e-106">型**bm インデックスの作成-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>-チェックポイント:\<チェックポイント 1\>** します。</span><span class="sxs-lookup"><span data-stu-id="23b9e-106">Type **bm create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="23b9e-107">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23b9e-107">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
3. <span data-ttu-id="23b9e-108">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="23b9e-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b9e-109">参照</span><span class="sxs-lookup"><span data-stu-id="23b9e-109">See Also</span></span>  
 <span data-ttu-id="23b9e-110">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="23b9e-110">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="23b9e-111">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="23b9e-111">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="23b9e-112">[インデックスを削除する方法](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="23b9e-112">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="23b9e-113">集計のインデックスの一覧を取得する方法</span><span class="sxs-lookup"><span data-stu-id="23b9e-113">How to Get a List of Indexes on an Aggregation</span></span>](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)