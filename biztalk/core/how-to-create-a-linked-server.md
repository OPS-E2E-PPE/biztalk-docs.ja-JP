---
title: リンク サーバーを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: 3ddb25ae58ee7adddd936f4904a131d4064a608f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385570"
---
# <a name="how-to-create-a-linked-server"></a><span data-ttu-id="b7ad5-102">リンク サーバーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b7ad5-102">How to Create a Linked Server</span></span>
<span data-ttu-id="b7ad5-103">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がインストールされている複数の分散トポロジでは、BizTalk グループに属しているデータベースが存在して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed in a distributed topology, the databases that belong to a BizTalk Group exist on multiple [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="b7ad5-104">BizTalk 環境全体をバックアップするには、BizTalk 管理サーバーから前に、各リモート サーバーへのリンク サーバー接続を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-104">You must configure a linked server connection to each of the remote servers before you can back up the entire BizTalk environment from the BizTalk Management server.</span></span> <span data-ttu-id="b7ad5-105">リンク サーバーは、OLE DB データ ソースで使用されている[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分散クエリ。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-105">A linked server is an OLE DB data source that is used in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="b7ad5-106">バックアップと復元のプロセス、バックアップの一部として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは、リンク サーバーを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-106">As a part of the backup and restore process, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job automatically creates linked servers.</span></span> <span data-ttu-id="b7ad5-107">必要に応じて、ただし、手動で作成できますこの手順を使用してリンク サーバー。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-107">If necessary, however, you can manually create linked servers using this procedure.</span></span>  
  
 <span data-ttu-id="b7ad5-108">使用してリンク サーバーを作成することも、 *sp_addlinkedserver*ストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-108">Linked servers can also be created using the *sp_addlinkedserver* stored procedure.</span></span> <span data-ttu-id="b7ad5-109">この操作に関連付けられているセキュリティの考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-109">There are security considerations associated with this operation.</span></span> <span data-ttu-id="b7ad5-110">Sp_addlinkedserver を使用してリンク サーバーが作成されると、すべてのローカル ログインは既定で新しいリンク サーバーにマップされます。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-110">When a linked server is created using sp_addlinkedserver, all local logins will be mapped to the new linked server by default.</span></span> <span data-ttu-id="b7ad5-111">リンク サーバーへのアクセスを制御する、 *sp_droplinkedsvrlogin*プロシージャを使用すると後に、グローバル ログイン マッピングを削除する必要があります*sp_addlinkedsvrlogin*に目的のログイン アカウントにマップするには新しいリンク サーバー。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-111">To control access to the linked server, the *sp_droplinkedsvrlogin* procedure should be used to drop the global login mapping, followed by *sp_addlinkedsvrlogin* to map the desired login account(s) to the new linked server.</span></span> <span data-ttu-id="b7ad5-112">Sp_addlinkedsvrlogin を使用する場合は、設定することをお勧めしますが、@useselfパラメーター TRUE を = です。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-112">When using sp_addlinkedsvrlogin, it is recommended that you set the @useself parameter = TRUE.</span></span> <span data-ttu-id="b7ad5-113">これにより、SQL スクリプトにユーザー名とパスワードを埋め込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-113">This avoids the need to embed a user name and password into your SQL script.</span></span>  

> [!TIP]
> <span data-ttu-id="b7ad5-114">次の手順は、時間の経過と共に変更可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-114">These steps may change over time.</span></span> <span data-ttu-id="b7ad5-115">参照することをお勧めします。、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-115">We recommend referring to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] documentation at [Create Linked Servers](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="b7ad5-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="b7ad5-116">Prerequisites</span></span>  
  
- <span data-ttu-id="b7ad5-117">メンバーであるアカウントでサインイン、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin**固定サーバー ロール</span><span class="sxs-lookup"><span data-stu-id="b7ad5-117">Sign in with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin** fixed server role</span></span>  
  
- <span data-ttu-id="b7ad5-118">ローカル作成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインします。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-118">Create a local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login.</span></span> <span data-ttu-id="b7ad5-119">次の手順では、ログインにこのアカウントをマップで、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクされます。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-119">In the following steps, this account is mapped to a login on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] you will link to.</span></span> 
  
## <a name="create-a-linked-server"></a><span data-ttu-id="b7ad5-120">リンク サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-120">Create a linked server</span></span>
  
1. <span data-ttu-id="b7ad5-121">開いている**SQL Server Management Studio**、ローカルの名前を入力[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、し、**接続**。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-121">Open **SQL Server Management Studio**, enter the name of your local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and then select **Connect**.</span></span>  
  
2. <span data-ttu-id="b7ad5-122">展開**サーバー オブジェクト**、右クリック**リンク サーバー**、し、**新しいリンク サーバー**します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-122">Expand **Server Objects**, right-click **Linked Servers**, and then select **New Linked Server**.</span></span>  

   <span data-ttu-id="b7ad5-123">表示する**サーバー オブジェクト**をローカルでのオンプレミスに接続する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-123">To see **Server Objects**, connect to a local on-premises [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="b7ad5-124">次に、**サーバー オブジェクト**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-124">Then, **Server Objects** should be displayed.</span></span>
  
3. <span data-ttu-id="b7ad5-125">**Linked server**テキスト ボックスに、完全なネットワーク名を入力、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクします。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-125">In the **Linked server** text box, enter the full network name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] you want to link to.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b7ad5-126">この手順は、多くの場合、リモート サーバーとしてにリンクしているサーバーを指します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-126">This procedure often refers to the server you are linking to as the remote server.</span></span> <span data-ttu-id="b7ad5-127">これは、便宜上のみ、ローカル サーバーへのリンク (「リモート」) サーバーのリレーションシップを示します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-127">This is for convenience only, to indicate the relationship of the linked (“remote”) server to the local server.</span></span>  
  
4. <span data-ttu-id="b7ad5-128">**サーバーの種類**、 **SQL Server**します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-128">Under **Server type**, select **SQL Server**.</span></span>  
  
5. <span data-ttu-id="b7ad5-129">左ペインで、 **[セキュリティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-129">In the left pane, select **Security**.</span></span> 

   <span data-ttu-id="b7ad5-130">この手順では、リモート サーバー ログインに、作成したローカル アカウントをマップします。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-130">In this step, you map the local account you created to the remote server login.</span></span> <span data-ttu-id="b7ad5-131">オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-131">Your options:</span></span> 
    
   | | | 
   |---|---|
   | <span data-ttu-id="b7ad5-132">**ログインの現在のセキュリティ コンテキストを使用します。**</span><span class="sxs-lookup"><span data-stu-id="b7ad5-132">**Be made using the login’s current security context**</span></span> | <span data-ttu-id="b7ad5-133">ドメイン環境でユーザーは、通常、ドメイン ログインで接続します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-133">In domain environments, users typically connect with their domain logins.</span></span> <span data-ttu-id="b7ad5-134">このオプションは、サインイン済みのドメイン アカウントのセキュリティ コンテキストが作成したローカル アカウントにマップされるため、最適な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-134">This option may be best since the security context of the signed-in domain account is mapped to the local account you created.</span></span>|
   | <span data-ttu-id="b7ad5-135">**[このセキュリティ コンテキストを使用する]**</span><span class="sxs-lookup"><span data-stu-id="b7ad5-135">**Be made using this security context**</span></span> | <span data-ttu-id="b7ad5-136">ユーザーは、SQL Server ログインを使用してローカルの SQL Server に接続するときに、このオプションが最適なに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-136">When users connect to the local SQL Server using a SQL Server login, then this option may be best.</span></span> <span data-ttu-id="b7ad5-137">ログインとパスワードの入力、アカウント、リンク サーバーでします。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-137">Then enter the login and password for the account on the linked server.</span></span> |


6. <span data-ttu-id="b7ad5-138">選択**追加**、」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-138">Select **Add**, and enter the following:</span></span> 

   1. <span data-ttu-id="b7ad5-139">**ローカル ログイン**、作成したローカル アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-139">Under **Local Login**, select the local account you created.</span></span> 
   2. <span data-ttu-id="b7ad5-140">確認**Impersonate**ローカル ログインがリモート サーバー上にも存在する場合。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-140">Check **Impersonate** if the local login also exists on the remote server.</span></span> 
   3. <span data-ttu-id="b7ad5-141">または、ローカル ログインは、リモートにマップするかどうか[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインを入力するには、**リモート ユーザー**名と**リモート パスワード**のリモート サーバー ログインします。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-141">Alternatively, if the local login will be mapped to a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login you, enter the **Remote User** name and **Remote Password** for the remote server login.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="b7ad5-142">権限借用を使用する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]構成とログイン アカウントが委任の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-142">To use impersonation, your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] configuration and login accounts must meet the requirements for delegation.</span></span> <span data-ttu-id="b7ad5-143">参照してください[委任のためのリンク サーバーを構成](https://msdn.microsoft.com/library/ms189580.aspx)の詳細。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-143">See [Configuring Linked Servers for Delegation](https://msdn.microsoft.com/library/ms189580.aspx) for more details.</span></span>  

7. <span data-ttu-id="b7ad5-144">左側のウィンドウで次のように選択します。**サーバー オプション**します。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-144">In the left pane, choose **Server Options**.</span></span> <span data-ttu-id="b7ad5-145">設定、 **RPC**と**RPC Out**パラメーターを**True**、し、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-145">Set the **RPC** and **RPC Out** parameters to **True**, and then select **OK**.</span></span> 
 
> [!TIP]
> <span data-ttu-id="b7ad5-146">詳細と、リンク サーバーを作成するときの推奨事項は includig を使用して、 `sp_addlinkedserver` procedcure、格納されているを参照してください[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。</span><span class="sxs-lookup"><span data-stu-id="b7ad5-146">For more details and recommendations when creating linked servers, includig using the `sp_addlinkedserver` stored procedcure, see [Create Linked Servers](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="b7ad5-147">参照</span><span class="sxs-lookup"><span data-stu-id="b7ad5-147">See Also</span></span>  
 [<span data-ttu-id="b7ad5-148">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="b7ad5-148">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)