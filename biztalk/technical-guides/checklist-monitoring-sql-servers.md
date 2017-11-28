---
title: "チェックリスト: SQL サーバーの監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5dea6db0-5347-497c-b07d-6a339e409f0a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cd47efb3bf9417c3733212b8f45946a2f13fa19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-monitoring-sql-servers"></a><span data-ttu-id="7c512-102">チェックリスト: SQL サーバーの監視</span><span class="sxs-lookup"><span data-stu-id="7c512-102">Checklist: Monitoring SQL Servers</span></span>
<span data-ttu-id="7c512-103">監視するために従う必要の手順を説明[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実稼働で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="7c512-103">This topic describes the steps that should be followed to monitor [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] in a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
|<span data-ttu-id="7c512-104">タスク</span><span class="sxs-lookup"><span data-stu-id="7c512-104">Task</span></span>|<span data-ttu-id="7c512-105">リファレンス</span><span class="sxs-lookup"><span data-stu-id="7c512-105">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="7c512-106">Microsoft インストール[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Operations Manager 2007 用の管理パック</span><span class="sxs-lookup"><span data-stu-id="7c512-106">Install the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for Operations Manager 2007</span></span>|<span data-ttu-id="7c512-107">[SQL Server 管理パックの監視](http://go.microsoft.com/fwlink/?linkid=109858)(http://go.microsoft.com/fwlink/?linkid=109858)</span><span class="sxs-lookup"><span data-stu-id="7c512-107">[SQL Server Monitoring Management Pack](http://go.microsoft.com/fwlink/?linkid=109858) (http://go.microsoft.com/fwlink/?linkid=109858)</span></span>|  
|<span data-ttu-id="7c512-108">指定、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを対象として、SQL Server 管理パックでは重要です。</span><span class="sxs-lookup"><span data-stu-id="7c512-108">Designate the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases as critical in the SQL Server Management Pack.</span></span>|[<span data-ttu-id="7c512-109">カスタマイズした監視の BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="7c512-109">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)|  
|<span data-ttu-id="7c512-110">SQL server コンピューターを監視することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c512-110">Ensure that the SQL server machines are monitored.</span></span>|[<span data-ttu-id="7c512-111">SQL Server エージェント ジョブおよびデータベースの監視</span><span class="sxs-lookup"><span data-stu-id="7c512-111">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)|  
|<span data-ttu-id="7c512-112">BizTalk SQL エージェント ジョブを監視することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c512-112">Ensure that the BizTalk SQL Agent jobs are monitored.</span></span>|[<span data-ttu-id="7c512-113">SQL Server エージェント ジョブおよびデータベースの監視</span><span class="sxs-lookup"><span data-stu-id="7c512-113">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)|