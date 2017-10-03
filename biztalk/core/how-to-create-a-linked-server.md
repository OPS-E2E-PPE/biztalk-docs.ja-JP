---
title: "リンク サーバーを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, linking for backups
- backing up, linking servers
ms.assetid: 7d4aba3d-77c0-4cdf-8547-71e821ce34a1
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ae08df9b522e1a772d7c8a9ad7d02c36dcb999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-linked-server"></a>リンク サーバーを作成する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が分散型トポロジにインストールされている場合は、BizTalk グループに属するデータベースが複数の [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に存在します。 BizTalk 管理サーバーから BizTalk 環境全体をバックアップする前に、各リモート サーバーへのリンク サーバー接続を構成する必要があります。 リンク サーバーは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 分散クエリで使用される OLE DB データ ソースです。  
  
 バックアップおよび復元プロセスの一部として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブは、リンク サーバーを自動的に作成します。 必要に応じて、次の手順を使用してリンク サーバーを手動で作成できます。  
  
 使用してリンク サーバーを作成することも、 *sp_addlinkedserver*ストアド プロシージャです。 この方法では、セキュリティに関する事項を考慮する必要があります。 sp_addlinkedserver を使用してリンク サーバーを作成した場合、すべてのローカル ログインが新しいリンク サーバーに既定でマップされます。 リンク サーバーへのアクセスを制御する、 *sp_droplinkedsvrlogin*を続けて、グローバル ログイン マッピングを削除するプロシージャを使用する必要があります*sp_addlinkedsvrlogin*に目的のログイン アカウントにマップするには新しいリンク サーバー。 Sp_addlinkedsvrlogin を使用する場合は、設定することをお勧めしますが、@useselfパラメーター TRUE を = です。 これにより、ユーザー名およびパスワードを SQL スクリプトに埋め込む必要がなくなります。  

> [!TIP]
> 次の手順は、時間の経過と共に変更可能性があります。 参照することをお勧め、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。
  
## <a name="prerequisites"></a>前提条件  
  
-   メンバーであるアカウントでサインイン、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin**固定サーバー ロール  
  
-   ローカルの作成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインします。 次の手順では、ログインにこのアカウントをマップで、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクされます。 
  
## <a name="create-a-linked-server"></a>リンク サーバーを作成します。
  
1.  開いている**SQL Server Management Studio**、ローカルの名前を入力[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、し、**接続**です。  
  
2.  展開**Server オブジェクト**を右クリックして**リンク サーバー**、し、**新規リンク サーバー**です。  

    表示する**Server オブジェクト**、ローカル オンプレミスへの接続[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 その後、 **Server オブジェクト**が表示されます。
  
3.  **Linked server**テキスト ボックスに、完全なネットワーク名を入力、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクします。  
  
    > [!NOTE]
    >  この手順では、リンク先のサーバーをリモート サーバーと呼んでいます。 これは、(リモートの) リンク サーバーとローカル サーバーの関係をわかりやすく示すためです。  
  
4.  **サーバーの種類** **SQL Server**です。  
  
5.  左ペインで、 **[セキュリティ]**を選択します。 

    このステップでは、リモート サーバーのログインを作成したローカル アカウントをマップします。 オプション: 
    
    | | | 
    |---|---|
    | **作成するログインの現在のセキュリティ コンテキストを使用します。** | ドメイン環境でのユーザーは、通常、ドメイン ログインを持つ接続します。 このオプションは、サインインしているドメイン アカウントのセキュリティ コンテキストが作成したローカル アカウントにマップされるため、最適なことがあります。|
    | **[このセキュリティ コンテキストを使用する]** | ユーザーは、SQL Server ログインを使用してローカルの SQL Server に接続する場合は、このオプションが最適なにあります。 ログインとパスワードの入力、アカウント、リンク サーバーでします。 |


6. 選択**追加**」と入力します。 

    1. **ローカル ログイン**、作成したローカル アカウントを選択します。 
    2. 確認**Impersonate**ローカル ログインがリモート サーバー上にも存在する場合。 
    3. 代わりに、ローカル ログインがリモートにマッピングするかどうか[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインを入力するには、**リモート ユーザー**名および**リモート パスワード**リモート サーバーのログインをします。  
  
    > [!NOTE]
    >  権限借用を使用するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の構成とログイン アカウントが委任の要件を満たす必要があります。 参照してください[委任に対してリンク サーバーを構成する](https://msdn.microsoft.com/library/ms189580.aspx)詳細についてはします。  

7. 左側のペインで選択**サーバー オプション**です。 設定、 **RPC**と**RPC Out**パラメーターを**True**、し、 **OK**です。 
 
> [!TIP]
> 詳細および推奨事項、リンク サーバーを作成するときに includig を使用して、 `sp_addlinkedserver` procedcure、格納されているを参照してください[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。

  
## <a name="see-also"></a>参照  
 [バックアップと復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)