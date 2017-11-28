---
title: "ログ配布のユーザー アカウントとロール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b19a7d7c87289e07c7ac7a26bacd0c96f9090c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="log-shipping-user-accounts-and-roles"></a><span data-ttu-id="a038f-102">ログ配布のユーザー アカウントとロール</span><span class="sxs-lookup"><span data-stu-id="a038f-102">Log Shipping User Accounts and Roles</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="a038f-103">ログ配布は、バックアップおよびログを復元するプロセスを自動化する SQL Server エージェント ジョブによって左右されます。</span><span class="sxs-lookup"><span data-stu-id="a038f-103"> log shipping is driven by a SQL Server Agent job to automate the process of restoring backups and logs.</span></span> <span data-ttu-id="a038f-104">不適切なアクセス許可によって実行される復元操作が発生することができます[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布が失敗します。</span><span class="sxs-lookup"><span data-stu-id="a038f-104">Incorrect permissions can cause restore operations performed by [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping to fail.</span></span> <span data-ttu-id="a038f-105">データベースを復元するように構成するユーザー アカウントは、BizTalk 管理データベースをホストしている実稼働データベース インスタンスへのアクセスに必要です。</span><span class="sxs-lookup"><span data-stu-id="a038f-105">The user account configured to restore databases must have access to the production database instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="a038f-106">ほとんどの場合これは意味をサービス アカウント、SQL Server エージェント ジョブを推進するため、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]災害復旧でログ配布ジョブ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは、ログインや、をホストしている実稼働データベースインスタンスに対するアクセス許可が必要です[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。管理データベース。</span><span class="sxs-lookup"><span data-stu-id="a038f-106">In most cases this means that the service account for the SQL Server Agent job driving the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping job on the disaster recovery [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance requires a login and permissions on the production database instance that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span> <span data-ttu-id="a038f-107">これにより、ジョブの所有者として、SQL Server エージェント サービス アカウントが構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a038f-107">This assumes that the SQL Server Agent service account is configured as the job owner.</span></span>  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="a038f-108">データベースを復元するように構成するユーザー アカウントに SQL Server システム管理者権限が必要がないように、BTS_BACKUP_USERS をという名前の SQL Server ロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a038f-108"> includes a SQL Server role named BTS_BACKUP_USERS so that the user account configured to restore databases does not require SQL Server System Administrators permission.</span></span>  
  
 <span data-ttu-id="a038f-109">一部としてデータベースの復元操作を実行するユーザー アカウントを構成するときに[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布、次を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a038f-109">When configuring the user account that will perform database restore operations as part of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping, please verify the following:</span></span>  
  
-   <span data-ttu-id="a038f-110">構成されているマップされたユーザーのドメイン アカウントで実行する SQL Server エージェント サービスを構成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (で**セキュリティ**、**ログイン**) ごとに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスですホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で復元されたデータベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配布ジョブを記録します。</span><span class="sxs-lookup"><span data-stu-id="a038f-110">Configure the SQL Server Agent service to run under a domain account with a mapped user configured in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio (in **Security**, **Logins**) on each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance that hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases restored by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping jobs.</span></span>  
  
-   <span data-ttu-id="a038f-111">構成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインこのユーザーのアカウントし、各サーバー上で BizTalk BTS_BACKUP_USERS SQL ロールにこのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a038f-111">Configure a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS SQL role on each server.</span></span>  
  
-   <span data-ttu-id="a038f-112">このユーザーを割り当てる、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム管理者ロールを実行するコンピューターの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベース。</span><span class="sxs-lookup"><span data-stu-id="a038f-112">Assign this user to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] System Administrators role on the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span>  
  
-   <span data-ttu-id="a038f-113">バックアップを実行するアカウントと復元操作の読み取りが必要と UNC への書き込みアクセスは、バックアップ ファイルが作成される場所を共有します。</span><span class="sxs-lookup"><span data-stu-id="a038f-113">The account that performs backup and restore operations must have Read and Write access to the UNC share where backup files are created.</span></span>