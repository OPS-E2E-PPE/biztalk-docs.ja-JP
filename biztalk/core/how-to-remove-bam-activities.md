---
title: "BAM アクティビティを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], deleting activities
- activities [BAM], deleting
- deleting, activities [BAM]
- Remove-Activity command [BAM]
ms.assetid: 6c4643dc-84df-487d-aad0-590d1a6a5107
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09e12e893df596a92377357b7e28b6e68f04b810
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-bam-activities"></a><span data-ttu-id="88961-102">BAM アクティビティを削除する方法</span><span class="sxs-lookup"><span data-stu-id="88961-102">How to Remove BAM Activities</span></span>
<span data-ttu-id="88961-103">管理者を使用して、**削除アクティビティ**BAM プライマリ インポート データベースから指定されたアクティビティを削除するコマンド。</span><span class="sxs-lookup"><span data-stu-id="88961-103">Administrators use the **remove-activity** command to remove the specified activity from the BAM Primary Import database.</span></span>  
  
### <a name="to-remove-a-bam-activity"></a><span data-ttu-id="88961-104">BAM アクティビティを削除するには</span><span class="sxs-lookup"><span data-stu-id="88961-104">To remove a BAM activity</span></span>  
  
1.  <span data-ttu-id="88961-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="88961-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="88961-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="88961-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
3.  <span data-ttu-id="88961-107">型**bm 削除アクティビティの名前:\<アクティビティ名 >**です。</span><span class="sxs-lookup"><span data-stu-id="88961-107">Type **bm remove-activity -Name:\<activity name>**.</span></span>  
  
4.  <span data-ttu-id="88961-108">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="88961-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88961-109">参照</span><span class="sxs-lookup"><span data-stu-id="88961-109">See Also</span></span>  
 <span data-ttu-id="88961-110">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="88961-110">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="88961-111">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="88961-111">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="88961-112">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="88961-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)