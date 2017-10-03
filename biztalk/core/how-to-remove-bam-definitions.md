---
title: "BAM 定義を削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definitions [BAM], deleting
- deleting, definitions [BAM]
- managing [BAM definitions], deleting definitions
- Remove-All command
ms.assetid: a905f54b-7c55-49b8-809b-030ad65f3e46
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bce5454528b3dc1cf0feb54a52eae2008e607811
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-bam-definitions"></a><span data-ttu-id="cee1c-102">BAM 定義を削除する方法</span><span class="sxs-lookup"><span data-stu-id="cee1c-102">How to Remove BAM Definitions</span></span>
<span data-ttu-id="cee1c-103">管理者を使用して、**削除すべて**コマンドを BAM 管理ユーティリティのすべてのビューと特定の BAM 定義ファイルを基になるアクティビティ テーブルを削除します。</span><span class="sxs-lookup"><span data-stu-id="cee1c-103">Administrators use the **remove-all** command of the BAM Management utility to remove all views and underlying activity tables for a particular BAM definition file.</span></span>  
  
### <a name="to-remove-bam-definitions"></a><span data-ttu-id="cee1c-104">BAM 定義を削除するには</span><span class="sxs-lookup"><span data-stu-id="cee1c-104">To Remove BAM definitions</span></span>  
  
1.  <span data-ttu-id="cee1c-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="cee1c-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="cee1c-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="cee1c-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="cee1c-107">型**bm 削除すべて DefinitionFile:\<def ファイル >**です。</span><span class="sxs-lookup"><span data-stu-id="cee1c-107">Type **bm remove-all DefinitionFile:\<def file>**.</span></span>  
  
4.  <span data-ttu-id="cee1c-108">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cee1c-108">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee1c-109">参照</span><span class="sxs-lookup"><span data-stu-id="cee1c-109">See Also</span></span>  
 <span data-ttu-id="cee1c-110">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="cee1c-110">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="cee1c-111">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="cee1c-111">BAM Management Utility</span></span>](../core/bam-management-utility.md)