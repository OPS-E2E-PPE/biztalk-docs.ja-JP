---
title: BAM のセキュリティに関する推奨事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- managing [BAM], security
- BAM, security
ms.assetid: 73613123-c1ed-477a-9f5c-342b2573c975
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f26cd3051dd296cc2849cb9c8ba7f8aa1d7ac6a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232186"
---
# <a name="bam-security-recommendations"></a>BAM のセキュリティに関する推奨事項
BAM をセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。  
  
-   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] を使用している場合、BAM を展開するには、管理用コンピューターに次のソフトウェアがインストールされている必要があります。  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]クライアント ツール  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]Integration Services  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] Analysis Services  
  
    -   [!INCLUDE[SQLServer2005_SP3_long](../includes/sqlserver2005-sp3-long-md.md)] (BAM 警告を使用する場合)  
  
        > [!NOTE]
        >  [!INCLUDE[SQLServer2005_SP3_short](../includes/sqlserver2005-sp3-short-md.md)] は [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 用の [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] Notification Services を含みます。  
  
    > [!NOTE]
    >  分析 DTS パッケージを実行するユーザー コンテキストは、BAM プライマリ インポート データベースおよび BAM スター スキーマ データベースの db_owner [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ロールのメンバーであることが必要です。 さらに、Analysis Services を実行するサービス アカウントは、OLAP 管理者であると共に、BAM スター スキーマ データベースの db_owner である必要があります。 詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=22781](http://go.microsoft.com/fwlink/?LinkId=22781)です。  
  
-   複数のユーザーには、ライブ データとアーカイブ済みデータへのアクセスが必要があります: 営業担当者、ビジネス マネージャー、およびその他のユーザーです。 これらのユーザーには、BAM プライマリ インポート データベースおよび BAM 分析データベースが配置されているドメイン (企業ドメイン) のドメイン アカウントが必要です。ただし、BizTalk のリソースへのアクセス許可は不要です。  
  
-   ユーザーが BAM データのビューにアクセスするには、BAM 管理ユーティリティ (BM.exe) を使用してユーザーにビューへのアクセス許可を与えると共に、ユーザーに SQL ログインを与える必要があります。 BAM 管理ユーティリティの詳細については、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)です。  
  
-   BAM 分析データベースのキューブにアクセスできるロールにユーザーを追加するには、BAM データベースと同じドメイン内に管理用コンピューターを設定する必要があります。  
  
-   BAM の管理者は、BAM プライマリ インポート データベース、BAM スター スキーマ データベース、および BAM アーカイブ データベースの db_owner であることが必要です。 そのユーザーには、BAM 分析データベースの OLAP 管理者でもする必要があります。  
  
-   Microsoft Office Excel ブック (.xls ファイル) を展開している場合、管理用コンピューターに Excel をインストールする必要があります。 ブックを展開する前に、ブックを開き、マクロのセキュリティが [高] に設定されており、警告が表示されないことを確認してください。  
  
-   業務上、実際のデータに接続する BAM Excel ブックをユーザーに配布する必要がない場合、XML ファイルを使用してブックを展開することをお勧めします。 そのようにすることで、管理用コンピューターに Excel をインストールしたり、マクロのセキュリティ レベルを確認したりする必要がなくなります。  
  
    > [!IMPORTANT]
    >  ビューにユーザーの権限を削除するときにする必要がありますも覚えておいてください、ユーザーが設定したアラートのサブスクリプションを削除します。 サブスクライバーを警告からの削除の詳細については、次を参照してください。[アラートからサブスクライバーを削除する方法](../core/how-to-remove-subscribers-from-an-alert.md)です。  
  
## <a name="see-also"></a>参照  
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)   
 [BizTalk Server の展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md)