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
# <a name="how-to-create-a-linked-server"></a>リンク サーバーを作成する方法
ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がインストールされている複数の分散トポロジでは、BizTalk グループに属しているデータベースが存在して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 BizTalk 環境全体をバックアップするには、BizTalk 管理サーバーから前に、各リモート サーバーへのリンク サーバー接続を構成する必要があります。 リンク サーバーは、OLE DB データ ソースで使用されている[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分散クエリ。  
  
 バックアップと復元のプロセス、バックアップの一部として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは、リンク サーバーを自動的に作成します。 必要に応じて、ただし、手動で作成できますこの手順を使用してリンク サーバー。  
  
 使用してリンク サーバーを作成することも、 *sp_addlinkedserver*ストアド プロシージャ。 この操作に関連付けられているセキュリティの考慮事項があります。 Sp_addlinkedserver を使用してリンク サーバーが作成されると、すべてのローカル ログインは既定で新しいリンク サーバーにマップされます。 リンク サーバーへのアクセスを制御する、 *sp_droplinkedsvrlogin*プロシージャを使用すると後に、グローバル ログイン マッピングを削除する必要があります*sp_addlinkedsvrlogin*に目的のログイン アカウントにマップするには新しいリンク サーバー。 Sp_addlinkedsvrlogin を使用する場合は、設定することをお勧めしますが、@useselfパラメーター TRUE を = です。 これにより、SQL スクリプトにユーザー名とパスワードを埋め込む必要があります。  

> [!TIP]
> 次の手順は、時間の経過と共に変更可能性があります。 参照することをお勧めします。、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。
  
## <a name="prerequisites"></a>前提条件  
  
- メンバーであるアカウントでサインイン、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin**固定サーバー ロール  
  
- ローカル作成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインします。 次の手順では、ログインにこのアカウントをマップで、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクされます。 
  
## <a name="create-a-linked-server"></a>リンク サーバーを作成します。
  
1. 開いている**SQL Server Management Studio**、ローカルの名前を入力[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、し、**接続**。  
  
2. 展開**サーバー オブジェクト**、右クリック**リンク サーバー**、し、**新しいリンク サーバー**します。  

   表示する**サーバー オブジェクト**をローカルでのオンプレミスに接続する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 次に、**サーバー オブジェクト**が表示されます。
  
3. **Linked server**テキスト ボックスに、完全なネットワーク名を入力、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]にリンクします。  
  
   > [!NOTE]
   >  この手順は、多くの場合、リモート サーバーとしてにリンクしているサーバーを指します。 これは、便宜上のみ、ローカル サーバーへのリンク (「リモート」) サーバーのリレーションシップを示します。  
  
4. **サーバーの種類**、 **SQL Server**します。  
  
5. 左ペインで、 **[セキュリティ]** を選択します。 

   この手順では、リモート サーバー ログインに、作成したローカル アカウントをマップします。 オプションがあります。 
    
   | | | 
   |---|---|
   | **ログインの現在のセキュリティ コンテキストを使用します。** | ドメイン環境でユーザーは、通常、ドメイン ログインで接続します。 このオプションは、サインイン済みのドメイン アカウントのセキュリティ コンテキストが作成したローカル アカウントにマップされるため、最適な可能性があります。|
   | **[このセキュリティ コンテキストを使用する]** | ユーザーは、SQL Server ログインを使用してローカルの SQL Server に接続するときに、このオプションが最適なに可能性があります。 ログインとパスワードの入力、アカウント、リンク サーバーでします。 |


6. 選択**追加**、」と入力します。 

   1. **ローカル ログイン**、作成したローカル アカウントを選択します。 
   2. 確認**Impersonate**ローカル ログインがリモート サーバー上にも存在する場合。 
   3. または、ローカル ログインは、リモートにマップするかどうか[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインを入力するには、**リモート ユーザー**名と**リモート パスワード**のリモート サーバー ログインします。  
  
      > [!NOTE]
      >  権限借用を使用する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]構成とログイン アカウントが委任の要件を満たす必要があります。 参照してください[委任のためのリンク サーバーを構成](https://msdn.microsoft.com/library/ms189580.aspx)の詳細。  

7. 左側のウィンドウで次のように選択します。**サーバー オプション**します。 設定、 **RPC**と**RPC Out**パラメーターを**True**、し、 **OK**。 
 
> [!TIP]
> 詳細と、リンク サーバーを作成するときの推奨事項は includig を使用して、 `sp_addlinkedserver` procedcure、格納されているを参照してください[リンク サーバーの作成](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)です。

  
## <a name="see-also"></a>参照  
 [バックアップおよび復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)