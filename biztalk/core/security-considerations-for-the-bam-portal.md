---
title: BAM ポータルのセキュリティに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22aa95167640482ccd2e00dfbfd98b0a323da1a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280316"
---
# <a name="security-considerations-for-the-bam-portal"></a><span data-ttu-id="d3553-102">BAM ポータルのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d3553-102">Security Considerations for the BAM Portal</span></span>
<span data-ttu-id="d3553-103">最小特権の原則を使用して、ユーザー アカウントは、BAM ポータルでの日常的なタスクを実行する制限の厳しいアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d3553-103">Using the principle of least privilege, user accounts should have restrictive permissions to perform routine tasks in the BAM portal.</span></span> <span data-ttu-id="d3553-104">ユーザーの適切なアクセス権を持つセキュリティのバランスを取るように BAM のユーザー アカウントを設定する際に注意してください、次の点を保持します。</span><span class="sxs-lookup"><span data-stu-id="d3553-104">Keep the following points in mind as you set up your user accounts for BAM to balance security with appropriate access for users.</span></span>  
  
## <a name="user-accounts"></a><span data-ttu-id="d3553-105">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="d3553-105">User accounts</span></span>  
 <span data-ttu-id="d3553-106">最小限のアクセス許可を持つユーザー アカウントを使用して、BAM ポータル分散 navigationfeature されません。</span><span class="sxs-lookup"><span data-stu-id="d3553-106">User accounts with minimum permissions are not able to use the BAM portal distributed navigationfeature.</span></span> <span data-ttu-id="d3553-107">この機能を使用できるようにするには、これらのアカウントは、ローカル コンピューターとリモート コンピューターでは、Web サービスへのアクセスを許可するための十分なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d3553-107">To be able to use this feature, these accounts must have sufficient permissions to allow access to the Web services on the remote computer as well as on the local computer.</span></span>  
  
 <span data-ttu-id="d3553-108">BAM Web サービスのユーザー アカウントは、すべての参照先データベースにアクセスする権限が必要し、参照先のデータベースの BAM_ManagementWS ロールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3553-108">User accounts for the BAM Web services must have permissions to access all referenced databases and must be a member of the BAM_ManagementWS role in the referenced databases.</span></span>  
  
 <span data-ttu-id="d3553-109">次のユーザーの種類のこれらの考慮事項の注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3553-109">For the following user types, you should be aware of these considerations:</span></span>  
  
-   <span data-ttu-id="d3553-110">ドメイン ユーザー、アクセス許可が必要リモート コンピューター上でそのプライマリ インポート データベースをホストにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d3553-110">Domain Users, must have access permissions on remote computers that host Primary Import databases that are being accessed.</span></span>  
  
-   <span data-ttu-id="d3553-111">ローカル ユーザーのロールが割り当てられたユーザーは、分散ナビゲーションを使用できません。</span><span class="sxs-lookup"><span data-stu-id="d3553-111">Users who are assigned Local User role, cannot use distributed navigation.</span></span>  
  
## <a name="administrator-accounts"></a><span data-ttu-id="d3553-112">管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="d3553-112">Administrator accounts</span></span>  
 <span data-ttu-id="d3553-113">管理者は、ドメイン ユーザーに権限を与える securityadmin または sysadmin グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3553-113">Administrators must be members of the securityadmin or sysadmin groups to grant permissions to domain users.</span></span>  
  
 <span data-ttu-id="d3553-114">BAM 管理ユーティリティを実行するには、BAM データベースの場合は、少なくともデータベース オペレーターがあります。</span><span class="sxs-lookup"><span data-stu-id="d3553-114">To run the BAM Management utility, you must be at least a database operator for the BAM databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3553-115">参照</span><span class="sxs-lookup"><span data-stu-id="d3553-115">See Also</span></span>  
 [<span data-ttu-id="d3553-116">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="d3553-116">BAM Portal</span></span>](../core/bam-portal.md)