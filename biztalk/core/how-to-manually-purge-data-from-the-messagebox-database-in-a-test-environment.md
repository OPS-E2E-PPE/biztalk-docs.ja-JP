---
title: テスト環境でメッセージ ボックス データベースからデータを手動で削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 398991a9-344a-487a-a817-dfc97d48ebe6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5282ad864e5c2d4f47b541b59d608087f090f935
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979735"
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a><span data-ttu-id="161cc-102">テスト環境でメッセージ ボックス データベースから手動でデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="161cc-102">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>
<span data-ttu-id="161cc-103">開発環境またはテスト環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行する場合、メッセージ ボックス データベースに格納されているデータは、通常、ビジネスで重要な "実際の" データではないので、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="161cc-103">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a development or test environment, data that is stored in the MessageBox database is not usually business critical "live" data and therefore may be deleted.</span></span> <span data-ttu-id="161cc-104">このようなシナリオでは、メッセージ ボックス データベースからデータを削除するための簡単な方法が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="161cc-104">In these scenarios, you may need a "quick and dirty" method for purging data from the MessageBox database.</span></span> <span data-ttu-id="161cc-105">bts_CleanupMsgbox ストアド プロシージャを使用して、メッセージ ボックス データベースから手動でデータを削除するには、このトピックの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="161cc-105">Follow the procedures in this topic to manually purge data from the MessageBox database using the bts_CleanupMsgbox stored procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="161cc-106">以下の手順は、テスト環境でのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="161cc-106">You should only perform these steps in a test environment.</span></span> <span data-ttu-id="161cc-107">運用環境で BizTalk メッセージ ボックス データベースのデータを手動で削除することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="161cc-107">Manually purging the BizTalk MessageBox database in a production environment is not supported.</span></span>  
  
### <a name="to-stop-biztalk-services"></a><span data-ttu-id="161cc-108">BizTalk サービスを停止するには</span><span class="sxs-lookup"><span data-stu-id="161cc-108">To stop BizTalk services</span></span>  
  
1.  <span data-ttu-id="161cc-109">サービス コンソールから BizTalk サービスのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="161cc-109">Stop any instances of the BizTalk service from the Services console.</span></span>  
  
2.  <span data-ttu-id="161cc-110">分離ホストでアダプターを実行している場合 (HTTP、SOAP、WCF など) は、コマンド プロンプトから IISRESET を実行して IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="161cc-110">If you are running any adapters in isolated hosts (for example HTTP, SOAP, or WCF), restart IIS by running the IISRESET from a command prompt.</span></span>  
  
3.  <span data-ttu-id="161cc-111">実行中のカスタム分離アダプターをすべてシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="161cc-111">Shut down any custom Isolated Adapters that are running.</span></span>  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a><span data-ttu-id="161cc-112">SQL Server 2008 を使用して bts_CleanupMsgbox ストアド プロシージャを作成および実行するには</span><span class="sxs-lookup"><span data-stu-id="161cc-112">To create and execute the bts_CleanupMsgbox stored procedure using SQL Server 2008</span></span>  
  
1. <span data-ttu-id="161cc-113">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="161cc-113">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="161cc-114">**SQL サーバーへの接続**ダイアログ ボックスで、SQL server と、適切な認証方式を選択し、順にクリックします**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="161cc-114">In the **Connect to SQL Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="161cc-115">**利用可能なデータベース**ドロップダウン リストで、BizTalk メッセージ ボックス データベースを選択 (**BizTalkMsgBoxDB**既定)。</span><span class="sxs-lookup"><span data-stu-id="161cc-115">In the **Available databases** drop-down list, select the BizTalk Messagebox database (**BizTalkMsgBoxDB** by default).</span></span>  
  
4. <span data-ttu-id="161cc-116">をクリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="161cc-116">Click the **New Query** icon on the toolbar.</span></span>  
  
5. <span data-ttu-id="161cc-117">開く、 **msgbox_cleanup_logic.sql** SQL Server Management Studio からのファイル。</span><span class="sxs-lookup"><span data-stu-id="161cc-117">Open the **msgbox_cleanup_logic.sql** file from SQL Server Management Studio.</span></span> <span data-ttu-id="161cc-118">msgbox_cleanup_logic.sql ファイルは、BizTalk Server コンピューターの [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="161cc-118">The msgbox_cleanup_logic.sql file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ directory of the BizTalk Server computer.</span></span>  
  
6. <span data-ttu-id="161cc-119">をクリックして、**クエリの実行**bts_CleanupMsgbox を作成するスクリプトを実行するツールバーのアイコンをストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="161cc-119">Click the **Execute Query** icon on the toolbar to run the script to create the bts_CleanupMsgbox stored procedure.</span></span> <span data-ttu-id="161cc-120">これで、bts_CleanupMsgbox ストアド プロシージャが、ストアド プロシージャの一覧に dbo.bts_CleanupMsgbox として表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="161cc-120">The bts_CleanupMsgbox stored procedure can then be viewed in the list of stored procedures as dbo.bts_CleanupMsgbox.</span></span>  
  
7. <span data-ttu-id="161cc-121">をクリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="161cc-121">Click the **New Query** icon on the toolbar.</span></span>  
  
8. <span data-ttu-id="161cc-122">次のコマンドを新しいクエリ ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="161cc-122">Paste the following command into the new query window:</span></span>  
  
   ```  
   exec bts_CleanupMsgbox  
   ```  
  
9. <span data-ttu-id="161cc-123">をクリックして、**クエリの実行**bts_CleanupMsgbox を実行するには、ツールバーのアイコンには、プロシージャが格納されています。</span><span class="sxs-lookup"><span data-stu-id="161cc-123">Click the **Execute Query** icon on the toolbar to run the bts_CleanupMsgbox stored procedure.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="161cc-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行している運用サーバーでは、bts_CleanupMsgbox ストアド プロシージャを実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="161cc-124">Do not run the bts_CleanupMsgbox stored procedure on a production server that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="161cc-125">bts_CleanupMsgbox ストアド プロシージャは、テスト環境でのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="161cc-125">You should only run the bts_CleanupMsgbox stored procedure in a test environment.</span></span> <span data-ttu-id="161cc-126">運用環境での bts_CleanupMsgbox ストアド プロシージャの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="161cc-126">Running the bts_CleanupMsgbox stored procedure in a production environment is not supported.</span></span>  
  
10. <span data-ttu-id="161cc-127">必要に応じて、BizTalk サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="161cc-127">Restart BizTalk services as needed.</span></span>  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a><span data-ttu-id="161cc-128">bts_CleanupMsgbox ストアド プロシージャを実行する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="161cc-128">Considerations when running the bts_CleanupMsgbox stored procedure</span></span>  
 <span data-ttu-id="161cc-129">bts_CleanupMsgbox ストアド プロシージャを実行する際の考慮事項は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="161cc-129">The following considerations apply when running the bts_CleanupMsgbox stored procedure:</span></span>  
  
1.  <span data-ttu-id="161cc-130">BizTalk データベース スキーマを更新する修正プログラムをテスト システムにインストールする場合、修正プログラムによって、bts_CleanupMsgbox ストアド プロシージャに、このストアド プロシージャの空のバージョンが上書きされることがあります。</span><span class="sxs-lookup"><span data-stu-id="161cc-130">If you install a hot fix onto your test system that updates the BizTalk database schemas, the hot fix may overwrite the bts_CleanupMsgbox stored procedure with an empty version of this stored procedure.</span></span> <span data-ttu-id="161cc-131">この場合、このトピックで説明した手順に従って、bts_CleanupMsgbox ストアド プロシージャを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="161cc-131">In this case, you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
2.  <span data-ttu-id="161cc-132">新しいメッセージ ボックス データベースを作成した場合、bts_CleanupMsgbox ストアド プロシージャは空であり、このトピックで説明した手順に従って、bts_CleanupMsgbox ストアド プロシージャを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="161cc-132">If you create a new MessageBox database, the bts_CleanupMsgbox stored procedure will be empty and you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
3.  <span data-ttu-id="161cc-133">Bts_CleanupMsgbox ストアド プロシージャの使用は**はサポートされていません**実稼働システムにします。</span><span class="sxs-lookup"><span data-stu-id="161cc-133">Use of the bts_CleanupMsgbox stored procedure is **not supported** on a production system.</span></span> <span data-ttu-id="161cc-134">このストアド プロシージャは、メッセージ ボックス データベース内のすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="161cc-134">This stored procedure will delete all of the data in your MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161cc-135">参照</span><span class="sxs-lookup"><span data-stu-id="161cc-135">See Also</span></span>  
 [<span data-ttu-id="161cc-136">BizTalk 追跡データベースからデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="161cc-136">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)