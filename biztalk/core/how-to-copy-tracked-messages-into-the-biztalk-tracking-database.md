---
title: 追跡メッセージを BizTalk 追跡データベースにコピーする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, copying between servers
- MessageBox database, Tracking database
- Tracking database, linking servers
- MessageBox database, copying messages
- linking, servers
- Tracking database, archiving
- archiving [Tracking database], linking servers
- Tracking database, MessageBox database
- Tracking database, copying messages
- archiving [Tracking database], MessageBox database
- MessageBox database, linking servers
- MessageBox database, archiving
ms.assetid: 369e972a-efbe-4ad5-a68f-aa3bbfb9ad54
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0db85ded3ae545ebc0a4648d6324515484765d01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340132"
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a><span data-ttu-id="7f9cc-102">追跡メッセージを BizTalk 追跡データベースにコピーする方法</span><span class="sxs-lookup"><span data-stu-id="7f9cc-102">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>
<span data-ttu-id="7f9cc-103">アーカイブおよび削除のプロセスは可能性のあるアクセスや、別の SQL server でデータベースを更新するため、関連する SQL Server インスタンス間のリンク サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-103">The archiving and purging process potentially accesses and/or updates databases in different SQL servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="7f9cc-104">リンク サーバーを使用して BizTalk 追跡 (BizTalkDTADb) データベースに、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース サーバーから追跡メッセージを直接コピーできます。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-104">You can directly copy tracked messages from the BizTalk MessageBox (BizTalkMsgBoxDb) database server to your BizTalk Tracking (BizTalkDTADb) database using a linked server.</span></span> <span data-ttu-id="7f9cc-105">間にリンク サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-105">You must set up linked servers between:</span></span>  
  
-   <span data-ttu-id="7f9cc-106">各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと BizTalk 追跡 (BizTalkDTADb) データベース。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-106">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
-   <span data-ttu-id="7f9cc-107">BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-107">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
-   <span data-ttu-id="7f9cc-108">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストするコンピューター上の SQL Server エージェント サービス アカウント、リンク サーバーで、BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader と db_datawriter 権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-108">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f9cc-109">SQL Server エージェントでは、コピー ジョブがエラーなく実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-109">In SQL Server Agent, verify that the copy job runs without errors.</span></span> <span data-ttu-id="7f9cc-110">それ以外の場合、エラーは、追跡データベースに移動してからデータを防止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-110">Otherwise, errors might prevent data from being moved to the tracking database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7f9cc-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="7f9cc-111">Prerequisites</span></span>  
 <span data-ttu-id="7f9cc-112">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-112">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a><span data-ttu-id="7f9cc-113">追跡メッセージを BizTalk 追跡データベース (SQL Server 2008) にコピーするには</span><span class="sxs-lookup"><span data-stu-id="7f9cc-113">To copy tracked messages into the BizTalk Tracking database (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="7f9cc-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-114">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="7f9cc-115">**サーバーへの接続**ダイアログ ボックスで、SQL server が BizTalk 追跡 (BizTalkDTADb) データベースが存在し、適切な認証の種類の名前を指定し、順にクリックします**Connect**に適切な SQL server に接続します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-115">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL server.</span></span>  
  
3.  <span data-ttu-id="7f9cc-116">**Microsoft SQL Server Management Studio**、ダブルクリックして**SQL Server エージェント**、順にクリックします**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-116">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="7f9cc-117">詳細ペインで右クリックして**TrackedMessages_Copy_BizTalkMsgBoxDb**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-117">In the details pane, right-click **TrackedMessages_Copy_BizTalkMsgBoxDb**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="7f9cc-118">**ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb**ダイアログ ボックスで、**ページの選択**、 をクリックして**手順**します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-118">In the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="7f9cc-119">**ジョブ ステップの一覧**、 をクリックして**パージ**、 をクリックし、**編集**。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-119">Under **Job step list**, click **Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="7f9cc-120">**コマンド**ボックス、追跡サーバーおよび必要に応じて、データベース名のパラメーターを編集し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-120">In the **Command** box, edit the tracking server and database names parameters as appropriate, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="7f9cc-121">**ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb**ダイアログ ボックスで、**ページの選択**、 をクリックして**全般**を選択、**有効**チェック ボックスをオンにして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-121">On the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **General**,select the **Enabled** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7f9cc-122">メッセージは、BizTalk 追跡 (BizTalkDTADb) データベースを BizTalk メッセージ ボックス (BizTalkMsgBoxDb) からコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-122">The messages will be copied from the BizTalk MessageBox (BizTalkMsgBoxDb) to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f9cc-123">新しいメッセージ ボックス データベースを追加する場合は、新しいメッセージ ボックス データベースのこの手順をもう一度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9cc-123">If you add a new MessageBox database, you will need to perform this procedure again for the new MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f9cc-124">参照</span><span class="sxs-lookup"><span data-stu-id="7f9cc-124">See Also</span></span>  
 [<span data-ttu-id="7f9cc-125">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="7f9cc-125">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)