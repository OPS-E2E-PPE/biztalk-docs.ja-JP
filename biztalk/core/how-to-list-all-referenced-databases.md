---
title: 参照されるデータベースのすべての一覧を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40677d08d41bfd913427aa18e8f63aef1b6ebaee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384838"
---
# <a name="how-to-list-all-referenced-databases"></a><span data-ttu-id="ffbe6-102">参照されるデータベースのすべての一覧を表示する方法</span><span class="sxs-lookup"><span data-stu-id="ffbe6-102">How to List All Referenced Databases</span></span>
<span data-ttu-id="ffbe6-103">管理者を使用して、 **get 参照**すべてのローカルの BAM プライマリ インポート データベースへの参照が指定されている他の BizTalk server で BAM プライマリ インポート データベースの一覧を表示するコマンド。</span><span class="sxs-lookup"><span data-stu-id="ffbe6-103">Administrators use the **get-references** command to list all of the BAM Primary Import databases on other BizTalk servers that have been given references to the local BAM Primary Import database.</span></span>  
  
### <a name="to-list-all-referenced-databases"></a><span data-ttu-id="ffbe6-104">すべての参照先のデータベースを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="ffbe6-104">To list all referenced databases</span></span>  
  
1. <span data-ttu-id="ffbe6-105">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="ffbe6-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="ffbe6-106">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="ffbe6-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="ffbe6-107">コマンド ライン プロンプトで、次の入力: **bm.exe の get 参照**します。</span><span class="sxs-lookup"><span data-stu-id="ffbe6-107">Type the following at the command line prompt: **bm.exe get-references**.</span></span> <span data-ttu-id="ffbe6-108">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ffbe6-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbe6-109">参照</span><span class="sxs-lookup"><span data-stu-id="ffbe6-109">See Also</span></span>  
 [<span data-ttu-id="ffbe6-110">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="ffbe6-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)