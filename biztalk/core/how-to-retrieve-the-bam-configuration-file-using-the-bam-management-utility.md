---
title: BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4277e6b088ed136021b898e26204a63dc782a895
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008515"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="e7ab6-102">BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法</span><span class="sxs-lookup"><span data-stu-id="e7ab6-102">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>
<span data-ttu-id="e7ab6-103">管理者および開発者は、BAM 管理ユーティリティを使用して、BAM インフラストラクチャの現在の構成を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e7ab6-103">Administrators and developers can use the BAM Management utility to retrieve the current configuration of the BAM infrastructure.</span></span> <span data-ttu-id="e7ab6-104">取得した構成を使用すると、BAM のインストールを新しいサーバーに移行したり、既存の BAM を更新したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7ab6-104">The retrieved configuration can be used to migrate a BAM installation to a new server or it can be modified and used to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e7ab6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="e7ab6-105">Prerequisites</span></span>  
 <span data-ttu-id="e7ab6-106">次に、このトピックの手順を実行するための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="e7ab6-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="e7ab6-107">構成済みの BAM データベース</span><span class="sxs-lookup"><span data-stu-id="e7ab6-107">Configured BAM databases</span></span>  
  
-   <span data-ttu-id="e7ab6-108">BAM プライマリ インポート データベースに対する読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e7ab6-108">Permissions to read the BAM Primary Import database</span></span>  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="e7ab6-109">BAM 管理ユーティリティを使用して BAM 構成ファイルを取得するには</span><span class="sxs-lookup"><span data-stu-id="e7ab6-109">To retrieve the BAM configuration file using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="e7ab6-110">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e7ab6-110">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e7ab6-111">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7ab6-111">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="e7ab6-112">コマンド ライン プロンプトで、次の入力: **bm config の取得のファイル名:\<出力ファイル\>** ここで、 \<*出力ファイル*\>は置き換えられます、BAM 構成ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="e7ab6-112">Type the following at the command line prompt: **bm get-config -FileName:\<output file\>**, where \<*output file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="e7ab6-113">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e7ab6-113">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ab6-114">参照</span><span class="sxs-lookup"><span data-stu-id="e7ab6-114">See Also</span></span>  
 [<span data-ttu-id="e7ab6-115">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="e7ab6-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)