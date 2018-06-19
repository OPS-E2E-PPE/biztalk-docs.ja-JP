---
title: リンク サーバーを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, linking for backups
- backing up, linking servers
ms.assetid: 7d4aba3d-77c0-4cdf-8547-71e821ce34a1
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ae08df9b522e1a772d7c8a9ad7d02c36dcb999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249810"
---
# <a name="how-to-create-a-linked-server"></a><span data-ttu-id="2f7b4-102">リンク サーバーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="2f7b4-102">How to Create a Linked Server</span></span>
<span data-ttu-id="2f7b4-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が分散型トポロジにインストールされている場合は、BizTalk グループに属するデータベースが複数の [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に存在します。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed in a distributed topology, the databases that belong to a BizTalk Group exist on multiple [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="2f7b4-104">BizTalk 管理サーバーから BizTalk 環境全体をバックアップする前に、各リモート サーバーへのリンク サーバー接続を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-104">You must configure a linked server connection to each of the remote servers before you can back up the entire BizTalk environment from the BizTalk Management server.</span></span> <span data-ttu-id="2f7b4-105">リンク サーバーは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 分散クエリで使用される OLE DB データ ソースです。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-105">A linked server is an OLE DB data source that is used in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="2f7b4-106">バックアップおよび復元プロセスの一部として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブは、リンク サーバーを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-106">As a part of the backup and restore process, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job automatically creates linked servers.</span></span> <span data-ttu-id="2f7b4-107">必要に応じて、次の手順を使用してリンク サーバーを手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-107">If necessary, however, you can manually create linked servers using this procedure.</span></span>  
  
 <span data-ttu-id="2f7b4-108">使用してリンク サーバーを作成することも、 *sp_addlinkedserver*ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-108">Linked servers can also be created using the *sp_addlinkedserver* stored procedure.</span></span> <span data-ttu-id="2f7b4-109">この方法では、セキュリティに関する事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-109">There are security considerations associated with this operation.</span></span> <span data-ttu-id="2f7b4-110">sp_addlinkedserver を使用してリンク サーバーを作成した場合、すべてのローカル ログインが新しいリンク サーバーに既定でマップされます。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-110">When a linked server is created using sp_addlinkedserver, all local logins will be mapped to the new linked server by default.</span></span> <span data-ttu-id="2f7b4-111">リンク サーバーへのアクセスを制御する、 *sp_droplinkedsvrlogin*を続けて、グローバル ログイン マッピングを削除するプロシージャを使用する必要があります*sp_addlinkedsvrlogin*に目的のログイン アカウントにマップするには新しいリンク サーバー。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-111">To control access to the linked server, the *sp_droplinkedsvrlogin* procedure should be used to drop the global login mapping, followed by *sp_addlinkedsvrlogin* to map the desired login account(s) to the new linked server.</span></span> <span data-ttu-id="2f7b4-112">Sp_addlinkedsvrlogin を使用する場合は、設定することをお勧めしますが、@useselfパラメーター TRUE を = です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-112">When using sp_addlinkedsvrlogin, it is recommended that you set the @useself parameter = TRUE.</span></span> <span data-ttu-id="2f7b4-113">これにより、ユーザー名およびパスワードを SQL スクリプトに埋め込む必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-113">This avoids the need to embed a user name and password into your SQL script.</span></span>  

> [!TIP]
> <span data-ttu-id="2f7b4-114">次の手順は、時間の経過と共に変更可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-114">These steps may change over time.</span></span> <span data-ttu-id="2f7b4-115">参照することをお勧め、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-115">We recommend referring to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] documentation at [Create Linked Servers](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="2f7b4-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="2f7b4-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="2f7b4-117">メンバーであるアカウントでサインイン、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin**固定サーバー ロール</span><span class="sxs-lookup"><span data-stu-id="2f7b4-117">Sign in with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin** fixed server role</span></span>  
  
-   <span data-ttu-id="2f7b4-118">ローカルの作成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインします。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-118">Create a local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login.</span></span> <span data-ttu-id="2f7b4-119">次の手順では、ログインにこのアカウントをマップで、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクされます。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-119">In the following steps, this account is mapped to a login on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] you will link to.</span></span> 
  
## <a name="create-a-linked-server"></a><span data-ttu-id="2f7b4-120">リンク サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-120">Create a linked server</span></span>
  
1.  <span data-ttu-id="2f7b4-121">開いている**SQL Server Management Studio**、ローカルの名前を入力[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、し、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-121">Open **SQL Server Management Studio**, enter the name of your local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and then select **Connect**.</span></span>  
  
2.  <span data-ttu-id="2f7b4-122">展開**Server オブジェクト**を右クリックして**リンク サーバー**、し、**新規リンク サーバー**です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-122">Expand **Server Objects**, right-click **Linked Servers**, and then select **New Linked Server**.</span></span>  

    <span data-ttu-id="2f7b4-123">表示する**Server オブジェクト**、ローカル オンプレミスへの接続[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-123">To see **Server Objects**, connect to a local on-premises [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="2f7b4-124">その後、 **Server オブジェクト**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-124">Then, **Server Objects** should be displayed.</span></span>
  
3.  <span data-ttu-id="2f7b4-125">**Linked server**テキスト ボックスに、完全なネットワーク名を入力、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクします。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-125">In the **Linked server** text box, enter the full network name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] you want to link to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f7b4-126">この手順では、リンク先のサーバーをリモート サーバーと呼んでいます。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-126">This procedure often refers to the server you are linking to as the remote server.</span></span> <span data-ttu-id="2f7b4-127">これは、(リモートの) リンク サーバーとローカル サーバーの関係をわかりやすく示すためです。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-127">This is for convenience only, to indicate the relationship of the linked (“remote”) server to the local server.</span></span>  
  
4.  <span data-ttu-id="2f7b4-128">**サーバーの種類** **SQL Server**です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-128">Under **Server type**, select **SQL Server**.</span></span>  
  
5.  <span data-ttu-id="2f7b4-129">左ペインで、 **[セキュリティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-129">In the left pane, select **Security**.</span></span> 

    <span data-ttu-id="2f7b4-130">このステップでは、リモート サーバーのログインを作成したローカル アカウントをマップします。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-130">In this step, you map the local account you created to the remote server login.</span></span> <span data-ttu-id="2f7b4-131">オプション:</span><span class="sxs-lookup"><span data-stu-id="2f7b4-131">Your options:</span></span> 
    
    | | | 
    |---|---|
    | <span data-ttu-id="2f7b4-132">**作成するログインの現在のセキュリティ コンテキストを使用します。**</span><span class="sxs-lookup"><span data-stu-id="2f7b4-132">**Be made using the login’s current security context**</span></span> | <span data-ttu-id="2f7b4-133">ドメイン環境でのユーザーは、通常、ドメイン ログインを持つ接続します。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-133">In domain environments, users typically connect with their domain logins.</span></span> <span data-ttu-id="2f7b4-134">このオプションは、サインインしているドメイン アカウントのセキュリティ コンテキストが作成したローカル アカウントにマップされるため、最適なことがあります。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-134">This option may be best since the security context of the signed-in domain account is mapped to the local account you created.</span></span>|
    | <span data-ttu-id="2f7b4-135">**[このセキュリティ コンテキストを使用する]**</span><span class="sxs-lookup"><span data-stu-id="2f7b4-135">**Be made using this security context**</span></span> | <span data-ttu-id="2f7b4-136">ユーザーは、SQL Server ログインを使用してローカルの SQL Server に接続する場合は、このオプションが最適なにあります。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-136">When users connect to the local SQL Server using a SQL Server login, then this option may be best.</span></span> <span data-ttu-id="2f7b4-137">ログインとパスワードの入力、アカウント、リンク サーバーでします。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-137">Then enter the login and password for the account on the linked server.</span></span> |


6. <span data-ttu-id="2f7b4-138">選択**追加**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-138">Select **Add**, and enter the following:</span></span> 

    1. <span data-ttu-id="2f7b4-139">**ローカル ログイン**、作成したローカル アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-139">Under **Local Login**, select the local account you created.</span></span> 
    2. <span data-ttu-id="2f7b4-140">確認**Impersonate**ローカル ログインがリモート サーバー上にも存在する場合。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-140">Check **Impersonate** if the local login also exists on the remote server.</span></span> 
    3. <span data-ttu-id="2f7b4-141">代わりに、ローカル ログインがリモートにマッピングするかどうか[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインを入力するには、**リモート ユーザー**名および**リモート パスワード**リモート サーバーのログインをします。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-141">Alternatively, if the local login will be mapped to a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login you, enter the **Remote User** name and **Remote Password** for the remote server login.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f7b4-142">権限借用を使用するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の構成とログイン アカウントが委任の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-142">To use impersonation, your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] configuration and login accounts must meet the requirements for delegation.</span></span> <span data-ttu-id="2f7b4-143">参照してください[委任に対してリンク サーバーを構成する](https://msdn.microsoft.com/library/ms189580.aspx)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-143">See [Configuring Linked Servers for Delegation](https://msdn.microsoft.com/library/ms189580.aspx) for more details.</span></span>  

7. <span data-ttu-id="2f7b4-144">左側のペインで選択**サーバー オプション**です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-144">In the left pane, choose **Server Options**.</span></span> <span data-ttu-id="2f7b4-145">設定、 **RPC**と**RPC Out**パラメーターを**True**、し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-145">Set the **RPC** and **RPC Out** parameters to **True**, and then select **OK**.</span></span> 
 
> [!TIP]
> <span data-ttu-id="2f7b4-146">詳細および推奨事項、リンク サーバーを作成するときに includig を使用して、 `sp_addlinkedserver` procedcure、格納されているを参照してください[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。</span><span class="sxs-lookup"><span data-stu-id="2f7b4-146">For more details and recommendations when creating linked servers, includig using the `sp_addlinkedserver` stored procedcure, see [Create Linked Servers](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="2f7b4-147">参照</span><span class="sxs-lookup"><span data-stu-id="2f7b4-147">See Also</span></span>  
 [<span data-ttu-id="2f7b4-148">バックアップと復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="2f7b4-148">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)