---
title: BAM 定義を削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], deleting
- deleting, definitions [BAM]
- managing [BAM definitions], deleting definitions
- Remove-All command
ms.assetid: a905f54b-7c55-49b8-809b-030ad65f3e46
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ad47285be2cb3188cc130e07d42204acbb5c7bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018206"
---
# <a name="how-to-remove-bam-definitions"></a><span data-ttu-id="fef10-102">BAM 定義を削除する方法</span><span class="sxs-lookup"><span data-stu-id="fef10-102">How to Remove BAM Definitions</span></span>
<span data-ttu-id="fef10-103">管理者を使用して、**すべて削除**すべてのビューおよび特定の BAM 定義ファイルを基になるアクティビティ テーブルを削除する、BAM 管理ユーティリティのコマンド。</span><span class="sxs-lookup"><span data-stu-id="fef10-103">Administrators use the **remove-all** command of the BAM Management utility to remove all views and underlying activity tables for a particular BAM definition file.</span></span>  
  
### <a name="to-remove-bam-definitions"></a><span data-ttu-id="fef10-104">BAM 定義を削除するには</span><span class="sxs-lookup"><span data-stu-id="fef10-104">To Remove BAM definitions</span></span>  
  
1. <span data-ttu-id="fef10-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="fef10-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="fef10-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="fef10-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="fef10-107">型**bm のすべての削除に DefinitionFile:\<def ファイル\>** します。</span><span class="sxs-lookup"><span data-stu-id="fef10-107">Type **bm remove-all DefinitionFile:\<def file\>**.</span></span>  
  
4. <span data-ttu-id="fef10-108">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fef10-108">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef10-109">参照</span><span class="sxs-lookup"><span data-stu-id="fef10-109">See Also</span></span>  
 <span data-ttu-id="fef10-110">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="fef10-110">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="fef10-111">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="fef10-111">BAM Management Utility</span></span>](../core/bam-management-utility.md)