---
title: "BAM ポータルのセキュリティに関する考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0f5220eba5b66daf41dffc7ab74f93df8bb509
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-the-bam-portal"></a><span data-ttu-id="02f97-102">BAM ポータルのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="02f97-102">Security Considerations for the BAM Portal</span></span>
<span data-ttu-id="02f97-103">最小特権の原則に従って、ユーザー アカウントには、BAM ポータルでは定型的なタスクのみを実行できる、制限付きのアクセス許可を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f97-103">Using the principle of least privilege, user accounts should have restrictive permissions to perform routine tasks in the BAM portal.</span></span> <span data-ttu-id="02f97-104">セキュリティと適切なユーザー アクセスとのバランスが取れるように BAM のユーザー アカウントを設定する際は、次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="02f97-104">Keep the following points in mind as you set up your user accounts for BAM to balance security with appropriate access for users.</span></span>  
  
## <a name="user-accounts"></a><span data-ttu-id="02f97-105">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="02f97-105">User accounts</span></span>  
 <span data-ttu-id="02f97-106">最低限の権限を持つユーザー アカウントは、BAM ポータル分散 navigationfeature を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="02f97-106">User accounts with minimum permissions are not able to use the BAM portal distributed navigationfeature.</span></span> <span data-ttu-id="02f97-107">この機能を使用できるようにするには、ローカル コンピューターだけでなくリモート コンピューターの Web サービスにもアクセスできるように十分なアクセス許可を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f97-107">To be able to use this feature, these accounts must have sufficient permissions to allow access to the Web services on the remote computer as well as on the local computer.</span></span>  
  
 <span data-ttu-id="02f97-108">BAM Web サービスのユーザー アカウントは、すべての参照データベースにアクセスするのに十分なアクセス許可を持っていて、参照データベースの BAM_ManagementWS ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="02f97-108">User accounts for the BAM Web services must have permissions to access all referenced databases and must be a member of the BAM_ManagementWS role in the referenced databases.</span></span>  
  
 <span data-ttu-id="02f97-109">特定のユーザーの種類に関する考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02f97-109">For the following user types, you should be aware of these considerations:</span></span>  
  
-   <span data-ttu-id="02f97-110">ドメイン ユーザーは、アクセス対象のプライマリ インポート データベースをホストしているリモート コンピューターに対するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f97-110">Domain Users, must have access permissions on remote computers that host Primary Import databases that are being accessed.</span></span>  
  
-   <span data-ttu-id="02f97-111">ローカル ユーザー ロールを割り当てられているユーザーは、分散ナビゲーションを使用できません。</span><span class="sxs-lookup"><span data-stu-id="02f97-111">Users who are assigned Local User role, cannot use distributed navigation.</span></span>  
  
## <a name="administrator-accounts"></a><span data-ttu-id="02f97-112">管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="02f97-112">Administrator accounts</span></span>  
 <span data-ttu-id="02f97-113">ドメイン ユーザーにアクセス許可を与えるには、管理者が securityadmin または sysadmin グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f97-113">Administrators must be members of the securityadmin or sysadmin groups to grant permissions to domain users.</span></span>  
  
 <span data-ttu-id="02f97-114">BAM 管理ユーティリティを実行するには、少なくとも BAM データベースのデータベース オペレーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f97-114">To run the BAM Management utility, you must be at least a database operator for the BAM databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02f97-115">参照</span><span class="sxs-lookup"><span data-stu-id="02f97-115">See Also</span></span>  
 [<span data-ttu-id="02f97-116">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="02f97-116">BAM Portal</span></span>](../core/bam-portal.md)