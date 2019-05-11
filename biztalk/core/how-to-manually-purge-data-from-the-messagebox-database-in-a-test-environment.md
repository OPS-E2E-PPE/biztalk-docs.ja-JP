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
ms.openlocfilehash: c1ea4d8356aa5812958e2ba9690dfbf8cc414dd5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336673"
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a><span data-ttu-id="94e85-102">テスト環境でメッセージ ボックス データベースから手動でデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="94e85-102">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>
<span data-ttu-id="94e85-103">実行時に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発またはテスト環境では、メッセージ ボックス データベースに格納されているデータは通常ビジネス クリティカルな「ライブ」データであり削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94e85-103">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a development or test environment, data that is stored in the MessageBox database is not usually business critical "live" data and therefore may be deleted.</span></span> <span data-ttu-id="94e85-104">これらのシナリオでは、メッセージ ボックス データベースからデータを消去するため「クイックとダーティ」メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="94e85-104">In these scenarios, you may need a "quick and dirty" method for purging data from the MessageBox database.</span></span> <span data-ttu-id="94e85-105">Bts_CleanupMsgbox ストアド プロシージャを使用してメッセージ ボックス データベースからデータを手動で削除するには、このトピックの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="94e85-105">Follow the procedures in this topic to manually purge data from the MessageBox database using the bts_CleanupMsgbox stored procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94e85-106">これらの手順は、テスト環境でのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e85-106">You should only perform these steps in a test environment.</span></span> <span data-ttu-id="94e85-107">運用環境で BizTalk メッセージ ボックス データベースを手動で削除することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94e85-107">Manually purging the BizTalk MessageBox database in a production environment is not supported.</span></span>  
  
### <a name="to-stop-biztalk-services"></a><span data-ttu-id="94e85-108">BizTalk サービスを停止するには</span><span class="sxs-lookup"><span data-stu-id="94e85-108">To stop BizTalk services</span></span>  
  
1.  <span data-ttu-id="94e85-109">サービス コンソールから BizTalk サービスのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="94e85-109">Stop any instances of the BizTalk service from the Services console.</span></span>  
  
2.  <span data-ttu-id="94e85-110">分離ホスト (たとえば、HTTP、SOAP、または WCF など) で、アダプターを実行する場合は、コマンド プロンプトから IISRESET を実行して IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="94e85-110">If you are running any adapters in isolated hosts (for example HTTP, SOAP, or WCF), restart IIS by running the IISRESET from a command prompt.</span></span>  
  
3.  <span data-ttu-id="94e85-111">実行している任意のカスタム分離アダプターをシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="94e85-111">Shut down any custom Isolated Adapters that are running.</span></span>  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a><span data-ttu-id="94e85-112">作成し、実行、bts_CleanupMsgbox ストアド プロシージャの SQL Server 2008 の使用</span><span class="sxs-lookup"><span data-stu-id="94e85-112">To create and execute the bts_CleanupMsgbox stored procedure using SQL Server 2008</span></span>  
  
1. <span data-ttu-id="94e85-113">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="94e85-113">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="94e85-114">**SQL サーバーへの接続**ダイアログ ボックスで、SQL server と、適切な認証方式を選択し、順にクリックします**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="94e85-114">In the **Connect to SQL Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="94e85-115">**利用可能なデータベース**ドロップダウン リストで、BizTalk メッセージ ボックス データベースを選択 (**BizTalkMsgBoxDB**既定)。</span><span class="sxs-lookup"><span data-stu-id="94e85-115">In the **Available databases** drop-down list, select the BizTalk Messagebox database (**BizTalkMsgBoxDB** by default).</span></span>  
  
4. <span data-ttu-id="94e85-116">をクリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="94e85-116">Click the **New Query** icon on the toolbar.</span></span>  
  
5. <span data-ttu-id="94e85-117">開く、 **msgbox_cleanup_logic.sql** SQL Server Management Studio からのファイル。</span><span class="sxs-lookup"><span data-stu-id="94e85-117">Open the **msgbox_cleanup_logic.sql** file from SQL Server Management Studio.</span></span> <span data-ttu-id="94e85-118">Msgbox_cleanup_logic.sql ファイルにある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BizTalk Server コンピューターの schema \ ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="94e85-118">The msgbox_cleanup_logic.sql file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ directory of the BizTalk Server computer.</span></span>  
  
6. <span data-ttu-id="94e85-119">をクリックして、**クエリの実行**bts_CleanupMsgbox を作成するスクリプトを実行するツールバーのアイコンをストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="94e85-119">Click the **Execute Query** icon on the toolbar to run the script to create the bts_CleanupMsgbox stored procedure.</span></span> <span data-ttu-id="94e85-120">Bts_CleanupMsgbox ストアド プロシージャは、dbo.bts_CleanupMsgbox としてストアド プロシージャの一覧で表示できます。</span><span class="sxs-lookup"><span data-stu-id="94e85-120">The bts_CleanupMsgbox stored procedure can then be viewed in the list of stored procedures as dbo.bts_CleanupMsgbox.</span></span>  
  
7. <span data-ttu-id="94e85-121">をクリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="94e85-121">Click the **New Query** icon on the toolbar.</span></span>  
  
8. <span data-ttu-id="94e85-122">新しいクエリ ウィンドウには、次のコマンドを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="94e85-122">Paste the following command into the new query window:</span></span>  
  
   ```  
   exec bts_CleanupMsgbox  
   ```  
  
9. <span data-ttu-id="94e85-123">をクリックして、**クエリの実行**bts_CleanupMsgbox を実行するには、ツールバーのアイコンには、プロシージャが格納されています。</span><span class="sxs-lookup"><span data-stu-id="94e85-123">Click the **Execute Query** icon on the toolbar to run the bts_CleanupMsgbox stored procedure.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="94e85-124">実行している実稼働サーバーでの bts_CleanupMsgbox ストアド プロシージャを実行しない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="94e85-124">Do not run the bts_CleanupMsgbox stored procedure on a production server that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="94e85-125">テスト環境でのみ、bts_CleanupMsgbox ストアド プロシージャを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e85-125">You should only run the bts_CleanupMsgbox stored procedure in a test environment.</span></span> <span data-ttu-id="94e85-126">実行、bts_CleanupMsgbox ストアド プロシージャ、運用環境ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="94e85-126">Running the bts_CleanupMsgbox stored procedure in a production environment is not supported.</span></span>  
  
10. <span data-ttu-id="94e85-127">必要に応じて、BizTalk サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="94e85-127">Restart BizTalk services as needed.</span></span>  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a><span data-ttu-id="94e85-128">ストアド プロシージャを bts_CleanupMsgbox の実行時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="94e85-128">Considerations when running the bts_CleanupMsgbox stored procedure</span></span>  
 <span data-ttu-id="94e85-129">次の考慮事項は、実行、bts_CleanupMsgbox ストアド プロシージャに適用されます。</span><span class="sxs-lookup"><span data-stu-id="94e85-129">The following considerations apply when running the bts_CleanupMsgbox stored procedure:</span></span>  
  
1.  <span data-ttu-id="94e85-130">BizTalk データベース スキーマを更新するテスト システムに修正プログラムをインストールする場合、修正プログラムでは、このストアド プロシージャの空のバージョンで、bts_CleanupMsgbox ストアド プロシージャが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="94e85-130">If you install a hot fix onto your test system that updates the BizTalk database schemas, the hot fix may overwrite the bts_CleanupMsgbox stored procedure with an empty version of this stored procedure.</span></span> <span data-ttu-id="94e85-131">この場合、bts_CleanupMsgbox ストアド プロシージャを再作成には、このトピックで説明した手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e85-131">In this case, you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
2.  <span data-ttu-id="94e85-132">新しいメッセージ ボックス データベースを作成する場合、bts_CleanupMsgbox ストアド プロシージャは空にして、bts_CleanupMsgbox ストアド プロシージャを再作成するには、このトピックで説明する手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e85-132">If you create a new MessageBox database, the bts_CleanupMsgbox stored procedure will be empty and you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
3.  <span data-ttu-id="94e85-133">Bts_CleanupMsgbox ストアド プロシージャの使用は**はサポートされていません**実稼働システムにします。</span><span class="sxs-lookup"><span data-stu-id="94e85-133">Use of the bts_CleanupMsgbox stored procedure is **not supported** on a production system.</span></span> <span data-ttu-id="94e85-134">このストアド プロシージャは、メッセージ ボックス データベースにデータをすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="94e85-134">This stored procedure will delete all of the data in your MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e85-135">参照</span><span class="sxs-lookup"><span data-stu-id="94e85-135">See Also</span></span>  
 [<span data-ttu-id="94e85-136">BizTalk 追跡データベースからデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="94e85-136">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)