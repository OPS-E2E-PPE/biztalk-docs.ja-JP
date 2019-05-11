---
title: チェックリスト:SQL Server の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dea6db0-5347-497c-b07d-6a339e409f0a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12ee05a8f18c06516ecb6542b003a74537995894
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270639"
---
# <a name="checklist-monitoring-sql-servers"></a><span data-ttu-id="8bb8c-102">チェックリスト:SQL Server の監視</span><span class="sxs-lookup"><span data-stu-id="8bb8c-102">Checklist: Monitoring SQL Servers</span></span>
<span data-ttu-id="8bb8c-103">このトピックでは、監視するために従う必要がある手順を説明します。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 、運用環境で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="8bb8c-103">This topic describes the steps that should be followed to monitor [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] in a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  


|                                                                       <span data-ttu-id="8bb8c-104">タスク</span><span class="sxs-lookup"><span data-stu-id="8bb8c-104">Task</span></span>                                                                        |                                                                        <span data-ttu-id="8bb8c-105">リファレンス</span><span class="sxs-lookup"><span data-stu-id="8bb8c-105">Reference</span></span>                                                                        |
|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|   <span data-ttu-id="8bb8c-106">インストール、Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用 Operations Manager 2007 管理パック</span><span class="sxs-lookup"><span data-stu-id="8bb8c-106">Install the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for Operations Manager 2007</span></span>    |        <span data-ttu-id="8bb8c-107">[SQL Server 管理パックの監視](http://go.microsoft.com/fwlink/?linkid=109858)(<http://go.microsoft.com/fwlink/?linkid=109858>)</span><span class="sxs-lookup"><span data-stu-id="8bb8c-107">[SQL Server Monitoring Management Pack](http://go.microsoft.com/fwlink/?linkid=109858) (<http://go.microsoft.com/fwlink/?linkid=109858>)</span></span>         |
| <span data-ttu-id="8bb8c-108">指定、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースとして SQL Server の管理パックでは重要です。</span><span class="sxs-lookup"><span data-stu-id="8bb8c-108">Designate the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases as critical in the SQL Server Management Pack.</span></span> | [<span data-ttu-id="8bb8c-109">カスタマイズした監視用に BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="8bb8c-109">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md) |
|                                                <span data-ttu-id="8bb8c-110">SQL server マシンを監視することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bb8c-110">Ensure that the SQL server machines are monitored.</span></span>                                                 |                 [<span data-ttu-id="8bb8c-111">SQL Server エージェント ジョブとデータベースの監視</span><span class="sxs-lookup"><span data-stu-id="8bb8c-111">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)                 |
|                                               <span data-ttu-id="8bb8c-112">BizTalk SQL エージェント ジョブを監視することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bb8c-112">Ensure that the BizTalk SQL Agent jobs are monitored.</span></span>                                               |                 [<span data-ttu-id="8bb8c-113">SQL Server エージェント ジョブとデータベースの監視</span><span class="sxs-lookup"><span data-stu-id="8bb8c-113">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)                 |

