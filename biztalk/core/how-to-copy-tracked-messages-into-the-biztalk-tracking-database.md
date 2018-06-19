---
title: BizTalk 追跡データベースに追跡されるメッセージをコピーする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 23aaa8e3bea3405d51a18da1778d420550ad4584
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22248130"
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a><span data-ttu-id="737f1-102">追跡メッセージを BizTalk 追跡データベースにコピーする方法</span><span class="sxs-lookup"><span data-stu-id="737f1-102">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>
<span data-ttu-id="737f1-103">アーカイブおよび削除プロセスでは、さまざまな SQL Server データベースに対するアクセスや更新が行われる可能性があるため、関連する SQL Server インスタンス間にリンク サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="737f1-103">The archiving and purging process potentially accesses and/or updates databases in different SQL servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="737f1-104">リンク サーバーを使用すると、追跡メッセージを BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース サーバーから BizTalk 追跡 (BizTalkDTADb) データベースに直接コピーできます。</span><span class="sxs-lookup"><span data-stu-id="737f1-104">You can directly copy tracked messages from the BizTalk MessageBox (BizTalkMsgBoxDb) database server to your BizTalk Tracking (BizTalkDTADb) database using a linked server.</span></span> <span data-ttu-id="737f1-105">次のそれぞれのインスタンス間にリンク サーバーを設定してください。</span><span class="sxs-lookup"><span data-stu-id="737f1-105">You must set up linked servers between:</span></span>  
  
-   <span data-ttu-id="737f1-106">各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと BizTalk 追跡 (BizTalkDTADb) データベース</span><span class="sxs-lookup"><span data-stu-id="737f1-106">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
-   <span data-ttu-id="737f1-107">BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。</span><span class="sxs-lookup"><span data-stu-id="737f1-107">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
-   <span data-ttu-id="737f1-108">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストしているコンピューター上の SQL Server エージェントのサービス アカウントは、リンク サーバー上の BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader 権限および db_datawriter 権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="737f1-108">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="737f1-109">SQL Server エージェントで、コピー ジョブの実行時にエラーが発生しないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="737f1-109">In SQL Server Agent, verify that the copy job runs without errors.</span></span> <span data-ttu-id="737f1-110">エラーが発生すると、データが追跡データベースに移動されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="737f1-110">Otherwise, errors might prevent data from being moved to the tracking database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="737f1-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="737f1-111">Prerequisites</span></span>  
 <span data-ttu-id="737f1-112">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="737f1-112">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a><span data-ttu-id="737f1-113">追跡メッセージを BizTalk 追跡データベース (SQL Server 2008) にコピーするには</span><span class="sxs-lookup"><span data-stu-id="737f1-113">To copy tracked messages into the BizTalk Tracking database (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="737f1-114">クリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして **Microsoft SQL Server 2008 R2**, 、順にクリック **SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="737f1-114">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="737f1-115">**サーバーへの接続**  ダイアログ ボックスが BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL server と、適切な認証の種類の名前を指定し、クリックして **接続** 対象の SQL server に接続します。</span><span class="sxs-lookup"><span data-stu-id="737f1-115">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL server.</span></span>  
  
3.  <span data-ttu-id="737f1-116">**Microsoft SQL Server Management Studio**, をダブルクリックして **SQL Server エージェント**, 、クリックして **ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="737f1-116">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="737f1-117">詳細ペインで右クリック **TrackedMessages_Copy_BizTalkMsgBoxDb**, 、クリックして **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="737f1-117">In the details pane, right-click **TrackedMessages_Copy_BizTalkMsgBoxDb**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="737f1-118">**ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb** ダイアログ ボックスで、 **ページの選択**, をクリックして **手順**します。</span><span class="sxs-lookup"><span data-stu-id="737f1-118">In the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="737f1-119">**ジョブ ステップの一覧**, 、 をクリックして **パージ**, 、 をクリックし、 **編集**します。</span><span class="sxs-lookup"><span data-stu-id="737f1-119">Under **Job step list**, click **Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="737f1-120">**コマンド** ボックス、追跡サーバーと、必要に応じてデータベース名のパラメーターを編集し、クリックして **OK**します。</span><span class="sxs-lookup"><span data-stu-id="737f1-120">In the **Command** box, edit the tracking server and database names parameters as appropriate, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="737f1-121">**ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb** ダイアログ ボックスで、 **ページの選択**, 、 をクリックして **全般**,を選択、 **有効** チェック ボックスをオンにし **ok**します。</span><span class="sxs-lookup"><span data-stu-id="737f1-121">On the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **General**,select the **Enabled** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="737f1-122">メッセージが BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースから BizTalk 追跡 (BizTalkDTADb) データベースにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="737f1-122">The messages will be copied from the BizTalk MessageBox (BizTalkMsgBoxDb) to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="737f1-123">新しいメッセージ ボックス データベースを追加する場合は、新しいメッセージ ボックス データベースに対して上記の手順を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="737f1-123">If you add a new MessageBox database, you will need to perform this procedure again for the new MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="737f1-124">参照</span><span class="sxs-lookup"><span data-stu-id="737f1-124">See Also</span></span>  
 [<span data-ttu-id="737f1-125">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="737f1-125">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)