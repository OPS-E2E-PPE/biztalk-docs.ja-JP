---
title: "アクセス制御とデータのセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access control, BizTalk Server Operator role
- databases, SQL roles
- access control, about access control
- BizTalk Server Administrator role
- databases, access control
- access control
- access control, BizTalk Server Administrator role
- access control, SQL roles
- user accounts, access control
- BizTalk Server Operator role
ms.assetid: f04fd4a3-0f8c-4170-934a-9cc77edd7f34
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11cb00eabf6110de78e2d194e0a25bfac6a3b6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="access-control-and-data-security"></a><span data-ttu-id="ff1fc-102">アクセス制御とデータのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ff1fc-102">Access Control and Data Security</span></span>
<span data-ttu-id="ff1fc-103">BizTalk Server では、ユーザー権限を最小限にすることでプロセスとデータベースへのアクセスを制限しています。システム内の重要なデータは、Microsoft Windows Server の機能を使用して、セキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-103">BizTalk Server limits access to its processes and databases by using minimum user rights; you can help secure important data in the system by using features from Microsoft Windows Server.</span></span> <span data-ttu-id="ff1fc-104">セキュリティ上の理由から、BizTalk Server 管理者および BizTalk ホストに対して、業務の遂行に不要なユーザー権限を設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-104">For security reasons, BizTalk Server Administrators and BizTalk Hosts should not have more user rights than necessary to perform their jobs.</span></span>  
  
 <span data-ttu-id="ff1fc-105">BizTalk では、データへの管理アクセスは SQL ロールを使用して制御されます。この方法により、ツールを使用する場合も直接データベースを利用する場合もデータへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-105">BizTalk controls Administrative access to data using SQL roles, thereby controlling access to data both via tools and directly via the database.</span></span> <span data-ttu-id="ff1fc-106">BizTalk ホストからのデータへのアクセスは、ホスト ユーザー グループとアカウントを使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-106">BizTalk Host access to data is controlled using Host User groups and accounts.</span></span>  
  
 <span data-ttu-id="ff1fc-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、BizTalk Server 管理者と BizTalk Server Operator の 2 種類の管理者ロールがあります。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-107">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="ff1fc-108">インストールまたは BizTalk Server 管理コンソールを使用して BizTalk Server データベースを作成する BizTalk Server により、これら両方の管理ロール用の SQL ロールがそのデータベースに自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-108">Anytime you create a BizTalk Server database through installation or the BizTalk Server Administration Console, BizTalk Server automatically creates SQL roles for both these administrative roles in that database.</span></span> <span data-ttu-id="ff1fc-109">各ロール、およびロールに割り当てられる SQL Server ログインには、管理者がデータベースで管理タスクを実行するときに SQL Server オブジェクト (テーブル、ビュー、ストアド プロシージャなど) に対して持っている必要のある最小限のユーザー権限が許可されます。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-109">BizTalk Server grants each role, and any SQL Server login assigned to the role, the minimum user rights needed by administrators on the SQL Server objects (tables, views, stored procedures, etc) to perform administrative tasks on that database.</span></span>  
  
 <span data-ttu-id="ff1fc-110">BizTalk Server 管理者は権限レベルの高いロールで、構成データおよび追跡データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-110">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="ff1fc-111">BizTalk Server Operator は、監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールです。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-111">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="ff1fc-112">BizTalk Server Operator ロールはサービスの状態とメッセージ フローを表示したり、アプリケーションを開始および停止したり、サービス インスタンスを終了および再開することができますが、構成を変更したり、メッセージのプロパティと内容を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-112">This latter role can view service state and message flow and can start or stop applications and terminate and resume service instances, but cannot change configuration or view message properties and content.</span></span>  
  
 <span data-ttu-id="ff1fc-113">同様に、BizTalk Server では、各ホストのユーザー グループ用の SQL ロールが各データベースに作成されます。作成されたロールには、ユーザー グループがそのホストに対してタスクを実行するときに必要となる最小限のユーザー権限が許可されます。</span><span class="sxs-lookup"><span data-stu-id="ff1fc-113">Similarly, BizTalk Server creates in each database a SQL role for the user group for each host, and grants this role the minimum user rights it needs for the user group to perform tasks for that host.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff1fc-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ff1fc-114">In This Section</span></span>  
  
-   [<span data-ttu-id="ff1fc-115">BizTalk Server の Windows グループ アカウントとユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="ff1fc-115">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [<span data-ttu-id="ff1fc-116">グループおよびサービス アカウントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="ff1fc-116">Access Control for Groups and Service Accounts</span></span>](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [<span data-ttu-id="ff1fc-117">管理ロールのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="ff1fc-117">Access Control for Administrative Roles</span></span>](../core/access-control-for-administrative-roles.md)  
  
-   [<span data-ttu-id="ff1fc-118">ビジネス情報へのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="ff1fc-118">Access Control to Business Information</span></span>](../core/access-control-to-business-information.md)  
  
-   [<span data-ttu-id="ff1fc-119">セキュリティの最小ユーザー権限</span><span class="sxs-lookup"><span data-stu-id="ff1fc-119">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)