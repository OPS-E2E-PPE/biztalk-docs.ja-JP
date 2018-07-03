---
title: ログ配布のユーザー アカウントとロール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3d82e9cd3f1ea942513319d0d68d528762ef35a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024488"
---
# <a name="log-shipping-user-accounts-and-roles"></a><span data-ttu-id="ecbf4-102">ログ配布のユーザー アカウントとロール</span><span class="sxs-lookup"><span data-stu-id="ecbf4-102">Log Shipping User Accounts and Roles</span></span>
<span data-ttu-id="ecbf4-103">BizTalk Server のバックアップおよびログを復元するプロセスを自動化するログ配布は SQL Server エージェント ジョブによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-103">BizTalk Server log shipping is driven by a SQL Server Agent job to automate the process of restoring backups and logs.</span></span> <span data-ttu-id="ecbf4-104">不適切なアクセス許可には、復元操作が失敗する BizTalk Server ログ配布によって実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-104">Incorrect permissions can cause restore operations performed by BizTalk Server log shipping to fail.</span></span> <span data-ttu-id="ecbf4-105">データベースを復元するように構成するユーザー アカウントは、BizTalk 管理データベースをホストする実稼働データベースのインスタンスへのアクセスに必要です。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-105">The user account configured to restore databases must have access to the production database instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="ecbf4-106">ほとんどの場合つまりサービス アカウントのディザスター リカバリーを BizTalk Server のログ配布ジョブを促進する SQL Server エージェント ジョブ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは、ログインと、をホストする実稼働データベースのインスタンスでアクセス許可が必要です[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。管理データベース。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-106">In most cases this means that the service account for the SQL Server Agent job driving the BizTalk Server log shipping job on the disaster recovery [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance requires a login and permissions on the production database instance that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span> <span data-ttu-id="ecbf4-107">これにより、ジョブの所有者として、SQL Server エージェント サービス アカウントが構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-107">This assumes that the SQL Server Agent service account is configured as the job owner.</span></span>  

 <span data-ttu-id="ecbf4-108">BizTalk Server には BTS_BACKUP_USERS という名前のデータベースを復元するように構成するユーザー アカウントに SQL Server システム管理者のアクセス許可が必要としないように SQL Server ロールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-108">BizTalk Server includes a SQL Server role named BTS_BACKUP_USERS so that the user account configured to restore databases does not require SQL Server System Administrators permission.</span></span>  

 <span data-ttu-id="ecbf4-109">BizTalk Server ログ配布の一部としてデータベースの復元操作を実行するユーザー アカウントを構成する場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-109">When configuring the user account that will perform database restore operations as part of BizTalk Server log shipping, please verify the following:</span></span>  

- <span data-ttu-id="ecbf4-110">マップされたユーザーで構成されているドメイン アカウントで実行する SQL Server エージェント サービスを構成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (で**セキュリティ**、**ログイン**) 各[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスに移動ホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で復元されたデータベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配布ジョブ ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-110">Configure the SQL Server Agent service to run under a domain account with a mapped user configured in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio (in **Security**, **Logins**) on each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance that hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases restored by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping jobs.</span></span>  

- <span data-ttu-id="ecbf4-111">構成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインこのユーザー アカウントし、このユーザーを各サーバーでの BizTalk BTS_BACKUP_USERS SQL ロールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-111">Configure a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] login account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS SQL role on each server.</span></span>  

- <span data-ttu-id="ecbf4-112">このユーザーを割り当てる、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム管理者の役割が実行されているコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベース。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-112">Assign this user to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] System Administrators role on the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span>  

- <span data-ttu-id="ecbf4-113">バックアップを実行するアカウントと復元操作の読み取りが必要と UNC への書き込みアクセスは、バックアップ ファイルが作成される場所を共有します。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-113">The account that performs backup and restore operations must have Read and Write access to the UNC share where backup files are created.</span></span>
