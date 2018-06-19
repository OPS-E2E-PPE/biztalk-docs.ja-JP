---
title: BAM 管理ユーティリティを使用して BAM データベースを設定する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 8cee3564b90b730334d2d891edd2e9abc221a367
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971312"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="aeb5f-102">BAM 管理ユーティリティを使用して BAM データベースを設定する方法</span><span class="sxs-lookup"><span data-stu-id="aeb5f-102">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>
<span data-ttu-id="aeb5f-103">管理者は、通常、BizTalk Server 構成ユーティリティを使用して、BAM データベースを設定します。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-103">Administrators typically use the BizTalk Server configuration utility to set up the BAM databases.</span></span> <span data-ttu-id="aeb5f-104">代わりに BAM 管理ユーティリティ (bm.exe) を使用して、データベースを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-104">You can use the BAM Management utility (bm.exe) as an alternate method to set up the databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aeb5f-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="aeb5f-105">Prerequisites</span></span>  
 <span data-ttu-id="aeb5f-106">このトピックの手順を実行するための前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="aeb5f-107">BAMPrimaryImport データベース、BAMStarSchema データベース、および BAMArchive データベースをホストする SQL Server に対する管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-107">You must have administrator permissions on the SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span>  
  
-   <span data-ttu-id="aeb5f-108">SQL Notification Services データベースを設定するには、管理者権限を持っており、ローカルの Administrators グループのメンバーであることが必要です。また、追加で構成された管理者グループ (BTS Admins グループなど) のメンバーであることも必要です。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-108">To set up the SQL Notification Services databases, you must have administrator permission and be a member of the local administrators group, as well as be a member of any additional administrator groups that have been configured, such as the BTS Admins group.</span></span>  
  
-   <span data-ttu-id="aeb5f-109">データベースの設定に使用する XML データを含む BAM 構成ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-109">You must have a BAM configuration file containing XML data from which to set up the databases.</span></span>  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="aeb5f-110">BAM 管理ユーティリティを使用して BAM データベースを設定するには</span><span class="sxs-lookup"><span data-stu-id="aeb5f-110">To set up the BAM databases using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="aeb5f-111">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-111">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="aeb5f-112">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-112">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="aeb5f-113">コマンド ライン プロンプトで、次を入力: **bm セットアップ データベース ConfigFile:\<構成ファイル\>** ここで、 \<*構成ファイル*\>は、BAM 構成ファイルの名前に置換します。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-113">Type the following at the command line prompt: **bm setup-databases -ConfigFile:\<configuration file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="aeb5f-114">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="aeb5f-114">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb5f-115">参照</span><span class="sxs-lookup"><span data-stu-id="aeb5f-115">See Also</span></span>  
 [<span data-ttu-id="aeb5f-116">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="aeb5f-116">BAM Management Utility</span></span>](../core/bam-management-utility.md)