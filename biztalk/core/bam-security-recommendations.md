---
title: "BAM のセキュリティに関する推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, BAM
- managing [BAM], security
- BAM, security
ms.assetid: 73613123-c1ed-477a-9f5c-342b2573c975
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f26cd3051dd296cc2849cb9c8ba7f8aa1d7ac6a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-security-recommendations"></a><span data-ttu-id="ef203-102">BAM のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="ef203-102">BAM Security Recommendations</span></span>
<span data-ttu-id="ef203-103">BAM をセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef203-103">We recommend that you follow these guidelines for securing and deploying BAM in your environment:</span></span>  
  
-   <span data-ttu-id="ef203-104">[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] を使用している場合、BAM を展開するには、管理用コンピューターに次のソフトウェアがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef203-104">If you are using [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], the administration computer must have the following software installed to deploy BAM:</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="ef203-105">クライアント ツール</span><span class="sxs-lookup"><span data-stu-id="ef203-105"> client tools</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="ef203-106">Integration Services</span><span class="sxs-lookup"><span data-stu-id="ef203-106"> Integration Services</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="ef203-107"> Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ef203-107"> Analysis Services</span></span>  
  
    -   [!INCLUDE[SQLServer2005_SP3_long](../includes/sqlserver2005-sp3-long-md.md)]<span data-ttu-id="ef203-108"> (BAM 警告を使用する場合)</span><span class="sxs-lookup"><span data-stu-id="ef203-108">, if you will be using BAM alerts</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[SQLServer2005_SP3_short](../includes/sqlserver2005-sp3-short-md.md)]<span data-ttu-id="ef203-109"> は [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 用の [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] Notification Services を含みます。</span><span class="sxs-lookup"><span data-stu-id="ef203-109"> contains [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services for [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef203-110">分析 DTS パッケージを実行するユーザー コンテキストは、BAM プライマリ インポート データベースおよび BAM スター スキーマ データベースの db_owner [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef203-110">The user context under which the analysis DTS package runs must be a member of the db_owner [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role of the BAM Primary Import and BAM Star Schema databases.</span></span> <span data-ttu-id="ef203-111">さらに、Analysis Services を実行するサービス アカウントは、OLAP 管理者であると共に、BAM スター スキーマ データベースの db_owner である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef203-111">In addition, the service account under which Analysis Services runs must be an OLAP administrator and must be a db_owner of the BAM Star Schema database.</span></span> <span data-ttu-id="ef203-112">詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=22781](http://go.microsoft.com/fwlink/?LinkId=22781)です。</span><span class="sxs-lookup"><span data-stu-id="ef203-112">For more information, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=22781](http://go.microsoft.com/fwlink/?LinkId=22781).</span></span>  
  
-   <span data-ttu-id="ef203-113">複数のユーザーには、ライブ データとアーカイブ済みデータへのアクセスが必要があります: 営業担当者、ビジネス マネージャー、およびその他のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ef203-113">Multiple users need access to the live and archived data: salespeople, business managers, and others.</span></span> <span data-ttu-id="ef203-114">これらのユーザーには、BAM プライマリ インポート データベースおよび BAM 分析データベースが配置されているドメイン (企業ドメイン) のドメイン アカウントが必要です。ただし、BizTalk のリソースへのアクセス許可は不要です。</span><span class="sxs-lookup"><span data-stu-id="ef203-114">These users must have domain accounts in the domain where the BAM Primary Import and BAM Analysis databases are (corporate domain), but their accounts do not need to have access to BizTalk resources.</span></span>  
  
-   <span data-ttu-id="ef203-115">ユーザーが BAM データのビューにアクセスするには、BAM 管理ユーティリティ (BM.exe) を使用してユーザーにビューへのアクセス許可を与えると共に、ユーザーに SQL ログインを与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef203-115">For users to access views of the BAM data, you must use the BAM management utility (BM.exe) to grant the users permissions to the views, and the users must have SQL logins.</span></span> <span data-ttu-id="ef203-116">BAM 管理ユーティリティの詳細については、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)です。</span><span class="sxs-lookup"><span data-stu-id="ef203-116">For more information about the BAM management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span>  
  
-   <span data-ttu-id="ef203-117">BAM 分析データベースのキューブにアクセスできるロールにユーザーを追加するには、BAM データベースと同じドメイン内に管理用コンピューターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef203-117">To add users to roles that have access to the cubes in the BAM Analysis database, you must have an administration computer in the same domain as the BAM databases.</span></span>  
  
-   <span data-ttu-id="ef203-118">BAM の管理者は、BAM プライマリ インポート データベース、BAM スター スキーマ データベース、および BAM アーカイブ データベースの db_owner であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef203-118">The person administering BAM must be db_owner for the BAM Primary Import, Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="ef203-119">そのユーザーには、BAM 分析データベースの OLAP 管理者でもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef203-119">That person must also be an OLAP administrator for the BAM Analysis database.</span></span>  
  
-   <span data-ttu-id="ef203-120">Microsoft Office Excel ブック (.xls ファイル) を展開している場合、管理用コンピューターに Excel をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef203-120">If you are deploying Microsoft Office Excel workbooks (.xls files), Excel must be installed on the administration computer.</span></span> <span data-ttu-id="ef203-121">ブックを展開する前に、ブックを開き、マクロのセキュリティが [高] に設定されており、警告が表示されないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ef203-121">Before you deploy a workbook, open it and ensure that the macro security is set to high, and that there are no warnings.</span></span>  
  
-   <span data-ttu-id="ef203-122">業務上、実際のデータに接続する BAM Excel ブックをユーザーに配布する必要がない場合、XML ファイルを使用してブックを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef203-122">If there is no business need to distribute to the users BAM Excel workbooks that connect to the real data, we recommend that you deploy the workbooks by using XML files.</span></span> <span data-ttu-id="ef203-123">そのようにすることで、管理用コンピューターに Excel をインストールしたり、マクロのセキュリティ レベルを確認したりする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ef203-123">This eliminates the need to install Excel on the administration computer, and the need to verify the macro security level.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ef203-124">ビューにユーザーの権限を削除するときにする必要がありますも覚えておいてください、ユーザーが設定したアラートのサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="ef203-124">When you remove a user's permissions on a view, you must also remember to eliminate any subscriptions to alerts that the user has set.</span></span> <span data-ttu-id="ef203-125">サブスクライバーを警告からの削除の詳細については、次を参照してください。[アラートからサブスクライバーを削除する方法](../core/how-to-remove-subscribers-from-an-alert.md)です。</span><span class="sxs-lookup"><span data-stu-id="ef203-125">For more information about removing subscribers from an alert, see [How to Remove Subscribers from an Alert](../core/how-to-remove-subscribers-from-an-alert.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef203-126">参照</span><span class="sxs-lookup"><span data-stu-id="ef203-126">See Also</span></span>  
 <span data-ttu-id="ef203-127">[セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="ef203-127">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 [<span data-ttu-id="ef203-128">BizTalk Server の展開のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="ef203-128">Security Recommendations for a BizTalk Server Deployment</span></span>](../core/security-recommendations-for-a-biztalk-server-deployment.md)