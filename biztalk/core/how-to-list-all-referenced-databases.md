---
title: "すべての一覧を表示する方法には、データベースが参照されている |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69c6411378311892f85821a3e86d65a85f909d0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-all-referenced-databases"></a><span data-ttu-id="d73b0-102">すべての参照先データベースを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="d73b0-102">How to List All Referenced Databases</span></span>
<span data-ttu-id="d73b0-103">管理者を使用して、 **get 参照**のすべてのローカルの BAM プライマリ インポート データベースへの参照が指定されている他の BizTalk server で BAM プライマリ インポート データベースの一覧を表示するコマンド。</span><span class="sxs-lookup"><span data-stu-id="d73b0-103">Administrators use the **get-references** command to list all of the BAM Primary Import databases on other BizTalk servers that have been given references to the local BAM Primary Import database.</span></span>  
  
### <a name="to-list-all-referenced-databases"></a><span data-ttu-id="d73b0-104">すべての参照先データベースを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="d73b0-104">To list all referenced databases</span></span>  
  
1.  <span data-ttu-id="d73b0-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="d73b0-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d73b0-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="d73b0-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="d73b0-107">コマンド ライン プロンプトで、次を入力: **bm.exe get 参照**です。</span><span class="sxs-lookup"><span data-stu-id="d73b0-107">Type the following at the command line prompt: **bm.exe get-references**.</span></span> <span data-ttu-id="d73b0-108">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d73b0-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d73b0-109">参照</span><span class="sxs-lookup"><span data-stu-id="d73b0-109">See Also</span></span>  
 [<span data-ttu-id="d73b0-110">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d73b0-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)