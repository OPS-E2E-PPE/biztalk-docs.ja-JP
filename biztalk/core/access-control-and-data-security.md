---
title: アクセス制御とデータ セキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e34babf08ccc18d0e20165b5f3a39914ad7324e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362259"
---
# <a name="access-control-and-data-security"></a><span data-ttu-id="e356d-102">アクセス制御とデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e356d-102">Access Control and Data Security</span></span>
<span data-ttu-id="e356d-103">BizTalk Server は、最小限のユーザーの権限を使用して、プロセスとデータベースへのアクセスを制限します。Microsoft Windows Server から機能を使用して、セキュリティで保護された重要なデータのシステムに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e356d-103">BizTalk Server limits access to its processes and databases by using minimum user rights; you can help secure important data in the system by using features from Microsoft Windows Server.</span></span> <span data-ttu-id="e356d-104">セキュリティ上の理由から、BizTalk Server 管理者と BizTalk ホストは必要ありません、ジョブを実行するために必要なユーザー権限。</span><span class="sxs-lookup"><span data-stu-id="e356d-104">For security reasons, BizTalk Server Administrators and BizTalk Hosts should not have more user rights than necessary to perform their jobs.</span></span>  
  
 <span data-ttu-id="e356d-105">両方ツールおよびデータベースを使用して直接データへのアクセスを制御するための SQL ロールを使用してデータにアクセスする BizTalk 制御管理します。</span><span class="sxs-lookup"><span data-stu-id="e356d-105">BizTalk controls Administrative access to data using SQL roles, thereby controlling access to data both via tools and directly via the database.</span></span> <span data-ttu-id="e356d-106">データへの BizTalk ホストでは、ホスト ユーザー グループとアカウントを使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="e356d-106">BizTalk Host access to data is controlled using Host User groups and accounts.</span></span>  
  
 <span data-ttu-id="e356d-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、2 つの管理ロール: BizTalk Server 管理者、および BizTalk Server Operator します。</span><span class="sxs-lookup"><span data-stu-id="e356d-107">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="e356d-108">インストールや、BizTalk Server 管理コンソールを使用して BizTalk Server データベースを作成するときにいつでも BizTalk Server により、これら両方の管理ロール用の SQL ロールがそのデータベースに自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="e356d-108">Anytime you create a BizTalk Server database through installation or the BizTalk Server Administration Console, BizTalk Server automatically creates SQL roles for both these administrative roles in that database.</span></span> <span data-ttu-id="e356d-109">BizTalk Server では、各ロール、およびロールに割り当てられているすべての SQL Server ログインで SQL Server オブジェクト (テーブル、ビュー、ストアド プロシージャなど) をそのデータベースでの管理タスクを実行する管理者の必要最小限のユーザー権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="e356d-109">BizTalk Server grants each role, and any SQL Server login assigned to the role, the minimum user rights needed by administrators on the SQL Server objects (tables, views, stored procedures, etc) to perform administrative tasks on that database.</span></span>  
  
 <span data-ttu-id="e356d-110">BizTalk Server の管理者は、構成データおよび追跡データへのアクセスを高い特権を持つロールです。</span><span class="sxs-lookup"><span data-stu-id="e356d-110">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="e356d-111">BizTalk Server Operator は、監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールです。</span><span class="sxs-lookup"><span data-stu-id="e356d-111">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="e356d-112">この後者のロールできますサービスの状態とメッセージ フローを表示しできます開始またはアプリケーションを停止および終了および再開サービス インスタンスしますが、メッセージのプロパティを構成またはビューとコンテンツを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e356d-112">This latter role can view service state and message flow and can start or stop applications and terminate and resume service instances, but cannot change configuration or view message properties and content.</span></span>  
  
 <span data-ttu-id="e356d-113">同様に、BizTalk Server は、各ホストの各データベースでユーザー グループ用の SQL ロールを作成し、このロールをホストするためのタスクを実行するユーザー グループに必要な最小ユーザー権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e356d-113">Similarly, BizTalk Server creates in each database a SQL role for the user group for each host, and grants this role the minimum user rights it needs for the user group to perform tasks for that host.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e356d-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e356d-114">In This Section</span></span>  
  
-   [<span data-ttu-id="e356d-115">BizTalk Server の Windows グループ アカウントとユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="e356d-115">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [<span data-ttu-id="e356d-116">グループ アカウントおよびサービス アカウントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="e356d-116">Access Control for Groups and Service Accounts</span></span>](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [<span data-ttu-id="e356d-117">管理ロールのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="e356d-117">Access Control for Administrative Roles</span></span>](../core/access-control-for-administrative-roles.md)  
  
-   [<span data-ttu-id="e356d-118">企業情報へのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="e356d-118">Access Control to Business Information</span></span>](../core/access-control-to-business-information.md)  
  
-   [<span data-ttu-id="e356d-119">セキュリティ保護のための最小ユーザー権限</span><span class="sxs-lookup"><span data-stu-id="e356d-119">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)