---
title: BAM プライマリ インポート データベースへの参照を無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b89e9df78d91a6e4737b964223f81983e74dd29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998195"
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a><span data-ttu-id="13ef1-102">BAM プライマリ インポート データベースへの参照を無効にする方法 </span><span class="sxs-lookup"><span data-stu-id="13ef1-102">How to Disable a BAM Primary Import Database Reference</span></span>
<span data-ttu-id="13ef1-103">管理者を使用して、**無効にする参照**指定された BAM プライマリ インポート データベースへの参照を無効にするコマンド。</span><span class="sxs-lookup"><span data-stu-id="13ef1-103">Administrators use the **disable-reference** command to disable a reference to a specified BAM Primary Import database.</span></span>  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a><span data-ttu-id="13ef1-104">BAM プライマリ インポート データベースへの参照を無効にするには</span><span class="sxs-lookup"><span data-stu-id="13ef1-104">To disable a reference to a BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="13ef1-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="13ef1-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="13ef1-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="13ef1-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="13ef1-107">コマンド ライン プロンプトで、次の入力: **bm 無効にする参照 TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>[-サーバー:\<server\> ][-データベース:\<データベース\>]** ここで、 **\<**<em>ターゲット サーバー</em> **\>** によって指定されるターゲットの BAM プライマリ インポート データベースを SQL server の名前は置き換え\<*ターゲット データベース*\>が存在します。</span><span class="sxs-lookup"><span data-stu-id="13ef1-107">Type the following at the command line prompt: **bm disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**, where **\<**<em>target server</em>**\>** is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<*target database*\> resides.</span></span> <span data-ttu-id="13ef1-108">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="13ef1-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ef1-109">参照</span><span class="sxs-lookup"><span data-stu-id="13ef1-109">See Also</span></span>  
 [<span data-ttu-id="13ef1-110">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="13ef1-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)