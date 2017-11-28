---
title: "BAM プライマリ インポート データベース参照を無効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6efa79822f6a5406db29c69b5ba0892a63bcc5f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a><span data-ttu-id="d5bde-102">BAM プライマリ インポート データベースへの参照を無効にする方法 </span><span class="sxs-lookup"><span data-stu-id="d5bde-102">How to Disable a BAM Primary Import Database Reference</span></span>
<span data-ttu-id="d5bde-103">管理者を使用して、**無効参照**指定された BAM プライマリ インポート データベースへの参照を無効にするコマンド。</span><span class="sxs-lookup"><span data-stu-id="d5bde-103">Administrators use the **disable-reference** command to disable a reference to a specified BAM Primary Import database.</span></span>  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a><span data-ttu-id="d5bde-104">BAM プライマリ インポート データベースへの参照を無効にするには</span><span class="sxs-lookup"><span data-stu-id="d5bde-104">To disable a reference to a BAM Primary Import database</span></span>  
  
1.  <span data-ttu-id="d5bde-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="d5bde-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d5bde-106">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="d5bde-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="d5bde-107">コマンド ライン プロンプトで、次を入力: **bm 無効参照 TargetServer:\<対象サーバー > - TargetDatabase:\<対象データベース > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**ここで、  **\<** *ターゲット サーバー*  **>** 先の SQL サーバーの名前に置き換え指定されたターゲットの BAM プライマリ インポート データベース\<*ターゲット データベース*> が存在します。</span><span class="sxs-lookup"><span data-stu-id="d5bde-107">Type the following at the command line prompt: **bm disable-reference -TargetServer:\<target server> -TargetDatabase:\<target database>[ -Server:\<server> ][ -Database:\<database> ]**, where **\<***target server***>** is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<*target database*> resides.</span></span> <span data-ttu-id="d5bde-108">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d5bde-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5bde-109">参照</span><span class="sxs-lookup"><span data-stu-id="d5bde-109">See Also</span></span>  
 [<span data-ttu-id="d5bde-110">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d5bde-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)