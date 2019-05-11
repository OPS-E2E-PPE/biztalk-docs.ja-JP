---
title: BAM 管理ユーティリティを使用して BAM データベースを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801338f4-b363-4f8e-b248-9c628065ded2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01b84fb3e538ee81351cbcfe380d893c5f0cc7b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334091"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="31bdc-102">BAM 管理ユーティリティを使用して BAM データベースを設定する方法</span><span class="sxs-lookup"><span data-stu-id="31bdc-102">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>
<span data-ttu-id="31bdc-103">通常、管理者は、BAM データベースを設定する、BizTalk Server 構成ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="31bdc-103">Administrators typically use the BizTalk Server configuration utility to set up the BAM databases.</span></span> <span data-ttu-id="31bdc-104">別の方法として、BAM 管理ユーティリティ (bm.exe) を使用するには、データベースを設定します。</span><span class="sxs-lookup"><span data-stu-id="31bdc-104">You can use the BAM Management utility (bm.exe) as an alternate method to set up the databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31bdc-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="31bdc-105">Prerequisites</span></span>  
 <span data-ttu-id="31bdc-106">次に、このトピックの手順を実行するための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="31bdc-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="31bdc-107">管理者のアクセス許可は、BAMPrimaryImport、bamstarschema データベース、および BAMArchive データベースをホストする SQL server が必要です。</span><span class="sxs-lookup"><span data-stu-id="31bdc-107">You must have administrator permissions on the SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span>  
  
-   <span data-ttu-id="31bdc-108">SQL Notification Services データベースを設定するにする必要があります管理者権限を持っていると、ローカルの administrators グループのメンバーであるだけでなく、BTS Admins グループなど、構成されているすべての追加の管理者グループのメンバーであります。</span><span class="sxs-lookup"><span data-stu-id="31bdc-108">To set up the SQL Notification Services databases, you must have administrator permission and be a member of the local administrators group, as well as be a member of any additional administrator groups that have been configured, such as the BTS Admins group.</span></span>  
  
-   <span data-ttu-id="31bdc-109">元のデータベースを設定する XML データを含む BAM 構成ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="31bdc-109">You must have a BAM configuration file containing XML data from which to set up the databases.</span></span>  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="31bdc-110">BAM 管理ユーティリティを使用して BAM データベースを設定するには</span><span class="sxs-lookup"><span data-stu-id="31bdc-110">To set up the BAM databases using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="31bdc-111">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="31bdc-111">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="31bdc-112">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="31bdc-112">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="31bdc-113">コマンド ライン プロンプトで、次の入力: **bm セットアップ データベース ConfigFile:\<構成ファイル\>** ここで、 \<*構成ファイル*\>、BAM 構成ファイルの名前は置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="31bdc-113">Type the following at the command line prompt: **bm setup-databases -ConfigFile:\<configuration file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="31bdc-114">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="31bdc-114">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31bdc-115">参照</span><span class="sxs-lookup"><span data-stu-id="31bdc-115">See Also</span></span>  
 [<span data-ttu-id="31bdc-116">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="31bdc-116">BAM Management Utility</span></span>](../core/bam-management-utility.md)