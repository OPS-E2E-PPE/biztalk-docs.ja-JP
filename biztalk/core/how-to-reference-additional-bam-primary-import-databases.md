---
title: 追加の BAM プライマリ インポート データベースを参照する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea80b32c-f2cb-4aca-89f4-d5b72e1ba021
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54982491ca8ce2c7ca7acd9e176a7341b2642c78
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992315"
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a><span data-ttu-id="b7d9e-102">追加の BAM プライマリ インポート データベースを参照する方法</span><span class="sxs-lookup"><span data-stu-id="b7d9e-102">How to Reference Additional BAM Primary Import Databases</span></span>
<span data-ttu-id="b7d9e-103">管理者を使用して、**参照を有効にする**コマンドを追加の BAM プライマリ インポート データベースを参照します。</span><span class="sxs-lookup"><span data-stu-id="b7d9e-103">Administrators use the **enable-reference** command to reference additional BAM Primary Import databases.</span></span> <span data-ttu-id="b7d9e-104">分散 BAM アクティビティの表示を容易にするには、複数の BAM プライマリ インポート データベースを参照します。</span><span class="sxs-lookup"><span data-stu-id="b7d9e-104">You reference multiple BAM Primary Import databases to facilitate viewing distributed BAM activities.</span></span>  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a><span data-ttu-id="b7d9e-105">追加の BAM プライマリ インポート データベースへの参照を有効にするには</span><span class="sxs-lookup"><span data-stu-id="b7d9e-105">To enable a reference to an additional BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="b7d9e-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="b7d9e-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b7d9e-107">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="b7d9e-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="b7d9e-108">コマンド ライン プロンプトで、次の入力: **bm 参照を有効にする TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>** ここで、 \<*ターゲット サーバー* \>によって指定されるターゲットの BAM プライマリ インポート データベースを SQL server の名前は置き換え\<ターゲット データベース\>が存在します。</span><span class="sxs-lookup"><span data-stu-id="b7d9e-108">Type the following at the command line prompt: **bm enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>**, where \<*target server*\> is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<target database\> resides.</span></span> <span data-ttu-id="b7d9e-109">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b7d9e-109">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d9e-110">参照</span><span class="sxs-lookup"><span data-stu-id="b7d9e-110">See Also</span></span>  
 [<span data-ttu-id="b7d9e-111">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="b7d9e-111">BAM Management Utility</span></span>](../core/bam-management-utility.md)