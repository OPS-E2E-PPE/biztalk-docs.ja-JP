---
title: BizTalk グループの復元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9bea20bacdd6b681d39e2bf3995d7626b9b1f63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021642"
---
# <a name="restoring-the-biztalk-group"></a><span data-ttu-id="03c1d-102">BizTalk グループの復元</span><span class="sxs-lookup"><span data-stu-id="03c1d-102">Restoring the BizTalk Group</span></span>
<span data-ttu-id="03c1d-103">BizTalk グループのセットによって表されます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース、SSIS パッケージ、および SQL エージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="03c1d-103">The BizTalk group is represented by the set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases, SSIS packages, and SQL Agent Jobs.</span></span> <span data-ttu-id="03c1d-104">このセクションでは、BizTalk グループを復元するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="03c1d-104">This section describes the process for restoring the BizTalk group.</span></span>  
  
 <span data-ttu-id="03c1d-105">送信先システム (ディザスター リカバリー サイト) への切り替えが必要なことは、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03c1d-105">In the event that a switchover to the destination system (disaster recovery site) is required, the following steps must be completed:</span></span>  
  
1. <span data-ttu-id="03c1d-106">復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と Analysis Services データベース。</span><span class="sxs-lookup"><span data-stu-id="03c1d-106">Restore [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and Analysis Services databases.</span></span>  
  
2. <span data-ttu-id="03c1d-107">BizTalk Server ランタイム サーバーやアプリケーションを復元します。</span><span class="sxs-lookup"><span data-stu-id="03c1d-107">Restore BizTalk Server runtime servers and applications.</span></span>  
  
   <span data-ttu-id="03c1d-108">障害復旧サイトで、次の手順を完了すると、BizTalk グループが確立された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーを構成することができ、アプリケーションは、BizTalk グループにデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="03c1d-108">Upon completion of these steps, the BizTalk group has been established at the disaster recovery site, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime servers can be configured, and the applications can be deployed into the BizTalk group.</span></span> <span data-ttu-id="03c1d-109">このセクションのトピックでは、このプロセスの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="03c1d-109">The topics in this section cover the details of this process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03c1d-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="03c1d-110">In This Section</span></span>  
  
-   [<span data-ttu-id="03c1d-111">ソース システムでのアプリケーション処理の停止</span><span class="sxs-lookup"><span data-stu-id="03c1d-111">Stopping Application Processing on the Source System</span></span>](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [<span data-ttu-id="03c1d-112">バックアップ BizTalk Server ジョブでデータベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="03c1d-112">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="03c1d-113">バックアップ BizTalk Server ジョブに含まれていないデータベースの復元</span><span class="sxs-lookup"><span data-stu-id="03c1d-113">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)