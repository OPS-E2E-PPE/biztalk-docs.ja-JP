---
title: カスタム データベースをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ddab49315f7d4a194224eb0773a7ea1fa1a314
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998579"
---
# <a name="how-to-back-up-custom-databases"></a><span data-ttu-id="d3e20-102">カスタム データベースのバックアップ方法</span><span class="sxs-lookup"><span data-stu-id="d3e20-102">How to Back Up Custom Databases</span></span>
<span data-ttu-id="d3e20-103">カスタム データベースは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と一緒にインストールされないので、BizTalk Server のバックアップ ジョブによるバックアップ対象のデータベースの既定リストにも含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d3e20-103">Because your custom databases are not installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], they are not included in the default list of databases to be marked and backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="d3e20-104">BizTalk Server のバックアップ ジョブでカスタム データベースをバックアップする場合は、そのデータベースを BizTalk Server のバックアップ ジョブに手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e20-104">If you want the Backup BizTalk Server job to back up your custom databases, you must manually add the databases to the Backup BizTalk Server job.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3e20-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="d3e20-105">Prerequisites</span></span>  
  
1. <span data-ttu-id="d3e20-106">完全復旧モデルを使用するように SQL Server を構成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース バックアップ セットのデータの整合性を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e20-106">SQL Server must be configured to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  <span data-ttu-id="d3e20-107">詳細については、次を参照してください。[ログ配布](../core/log-shipping.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3e20-107">For more information see [Log Shipping](../core/log-shipping.md).</span></span>  
  
2. <span data-ttu-id="d3e20-108">カスタム データベースをバックアップするには、バックアップ対象の各データベースにアクセスできるユーザー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e20-108">To back up your custom databases, you must be logged on with a user account that has access to each of the databases you are backing up.</span></span>  
  
    <span data-ttu-id="d3e20-109">BizTalk Server には、BTS_BACKUP_USERS という名前の SQL Server ロールが含まれているため、データベースのバックアップに使用するユーザー アカウントは、SQL Server 内でシステム管理者のアクセス許可を必要としません。ただし、バックアップ プロセスを制御するプライマリ サーバーは例外です。</span><span class="sxs-lookup"><span data-stu-id="d3e20-109">BizTalk Server includes a SQL Server role named BTS_BACKUP_USERS so that the user account you use to back up your databases does not require System Administrator permissions within SQL Server, except for the primary server controlling the backup process.</span></span>  
  
    <span data-ttu-id="d3e20-110">使用しているユーザー アカウントでデータベースをバックアップするように設定する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3e20-110">When setting up the user account that you are using to back up your databases, note the following:</span></span>  
  
   -   <span data-ttu-id="d3e20-111">このユーザーの SQL Server ログオン アカウントを作成し、このユーザーを各サーバーの BizTalk BTS_BACKUP_USERS ロールに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e20-111">You must create a SQL Server logon account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS role on each server.</span></span>  
  
   -   <span data-ttu-id="d3e20-112">BizTalk Server バックアップ ジョブは、SQL Server エージェント サービスに使用されるユーザー アカウントとは異なるユーザー アカウントで実行されるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="d3e20-112">The BizTalk Server backup jobs can be configured to run under a user account that is different than the one used for the SQL Server Agent service.</span></span>  
  
   -   <span data-ttu-id="d3e20-113">SQL Server エージェント サービスは、ドメイン アカウントで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e20-113">You must configure the SQL Server Agent service to run under a domain account.</span></span> <span data-ttu-id="d3e20-114">すべてのデータベースが同じコンピューターに存在する場合は、ローカル アカウントを使用するように SQL Server エージェントを構成してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="d3e20-114">If all databases are on the same computer, you can configure SQL Server Agent to use a local account.</span></span>  
  
### <a name="to-back-up-custom-databases"></a><span data-ttu-id="d3e20-115">カスタム データベースをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="d3e20-115">To back up custom databases</span></span>  
  
1. <span data-ttu-id="d3e20-116">新しいデータベースに各種のオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="d3e20-116">Build the objects in the new database:</span></span>  
  
   - <span data-ttu-id="d3e20-117">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema ディレクトリを参照し、バックアップするすべてのカスタム データベースに対して Backup_Setup_All_Procs.sql と Backup_Setup_All_Tables.sql を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3e20-117">Browse to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema directory, and then run Backup_Setup_All_Procs.sql and Backup_Setup_All_Tables.sql against all your custom databases that you want to back up.</span></span> <span data-ttu-id="d3e20-118">これにより、必要なプロシージャ、テーブル、およびロールが作成され、ストアド プロシージャに対するアクセス許可が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d3e20-118">This creates the necessary procedures, table, and role and assigns permissions to the stored procedures.</span></span>  
  
2. <span data-ttu-id="d3e20-119">次の構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3e20-119">Perform the following configurations:</span></span>  
  
   -   <span data-ttu-id="d3e20-120">BizTalk 管理データベースがホストされている SQL Server を、新しいデータベースがホストされる SQL Server にリンクします。</span><span class="sxs-lookup"><span data-stu-id="d3e20-120">Link the SQL server that is hosting the BizTalk Management database to the SQL server hosting the new database.</span></span> <span data-ttu-id="d3e20-121">管理用 SQL Server で実行される SQL Server エージェント サービスには、すべての (つまり、バックアップ対象データベースが存在する) コンピューターにマップされたドメイン アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e20-121">The account used to run the SQL Server Agent service on the management SQL Server must be a domain account that is mapped to each computer holding a database to be backed up.</span></span> <span data-ttu-id="d3e20-122">すべてのデータベースが同じコンピューターに存在する場合、この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="d3e20-122">If the databases are on the same computer you can skip this step.</span></span> <span data-ttu-id="d3e20-123">この処理は自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="d3e20-123">This is done automatically.</span></span>  
  
   -   <span data-ttu-id="d3e20-124">新しいデータベースをホストする SQL Server に対し、管理用 SQL Server の SQL Server エージェント サービスを実行するアカウント用のログインを追加します。</span><span class="sxs-lookup"><span data-stu-id="d3e20-124">Add a login on the SQL server hosting the new database for the account running the SQL Server Agent service on the Mgmt SQL Server.</span></span> <span data-ttu-id="d3e20-125">すべてのデータベースが同じコンピューターに存在する場合、この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="d3e20-125">If the databases are on the same computer you can skip this step.</span></span>  
  
   -   <span data-ttu-id="d3e20-126">新しいデータベースに、直前の手順で作成したログインのユーザーを追加し、さらに、このユーザーを BTS_BACKUP_USERS ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="d3e20-126">Add a user in the new database for the login created in the previous step and add them to the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="d3e20-127">このロールは手順 1. のスクリプトによって作成されたもので、その際に、必要なプロシージャの実行権限も与えられています。</span><span class="sxs-lookup"><span data-stu-id="d3e20-127">This role is created and granted Execute permissions on the necessary procedures by the scripts in step 1.</span></span>  
  
3. <span data-ttu-id="d3e20-128">SQL Server Enterprise Manager または SQL Server Management Studio を使用して、BizTalk 管理 (BizTalkMgmtDb) データベースの変更、 **adm_OtherBackupDatabases**テーブルごとのカスタム データベースの行を含める。</span><span class="sxs-lookup"><span data-stu-id="d3e20-128">Using SQL Server Enterprise Manager or SQL Server Management Studio, in the BizTalk Management (BizTalkMgmtDb) database, modify the **adm_OtherBackupDatabases** table to include a row for each of your custom databases.</span></span>  
  
4. <span data-ttu-id="d3e20-129">次の表を参考にして、対応する列に新しいサーバー名とデータベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3e20-129">Type the new server and database names in the corresponding columns, as shown in the following table.</span></span>  
  
   |<span data-ttu-id="d3e20-130">[列]</span><span class="sxs-lookup"><span data-stu-id="d3e20-130">Column</span></span>|<span data-ttu-id="d3e20-131">値</span><span class="sxs-lookup"><span data-stu-id="d3e20-131">Value</span></span>|  
   |------------|-----------|  
   |<span data-ttu-id="d3e20-132">DefaultDatabaseName</span><span class="sxs-lookup"><span data-stu-id="d3e20-132">DefaultDatabaseName</span></span>|<span data-ttu-id="d3e20-133">カスタム データベースのフレンドリ名。</span><span class="sxs-lookup"><span data-stu-id="d3e20-133">The friendly name of your custom database.</span></span>|  
   |<span data-ttu-id="d3e20-134">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="d3e20-134">DatabaseName</span></span>|<span data-ttu-id="d3e20-135">カスタム データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="d3e20-135">The name of your custom database.</span></span>|  
   |<span data-ttu-id="d3e20-136">ServerName</span><span class="sxs-lookup"><span data-stu-id="d3e20-136">ServerName</span></span>|<span data-ttu-id="d3e20-137">SQL Server を実行するコンピューター名。</span><span class="sxs-lookup"><span data-stu-id="d3e20-137">The name of the computer running SQL Server.</span></span>|  
   |<span data-ttu-id="d3e20-138">BTSServerName</span><span class="sxs-lookup"><span data-stu-id="d3e20-138">BTSServerName</span></span>|<span data-ttu-id="d3e20-139">BizTalk Server の名前。</span><span class="sxs-lookup"><span data-stu-id="d3e20-139">The name of the BizTalk Server.</span></span> <span data-ttu-id="d3e20-140">実際にはこの値は使用されませんが、この列の値を空にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3e20-140">This value is not used, but it must contain a value nonetheless.</span></span>|  
  
   <span data-ttu-id="d3e20-141">これで、BizTalk Server のバックアップ ジョブを次に実行したときに、カスタム データベースがバックアップされるようになります。</span><span class="sxs-lookup"><span data-stu-id="d3e20-141">The next time you run the Backup BizTalk Server job, it will back up your custom databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e20-142">参照</span><span class="sxs-lookup"><span data-stu-id="d3e20-142">See Also</span></span>  
 <span data-ttu-id="d3e20-143">[バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="d3e20-143">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="d3e20-144">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="d3e20-144">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)