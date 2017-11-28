---
title: "BizTalk グループを復元する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12a1deff8fea6d769f138aa34bf6dab269a167f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-the-biztalk-group"></a><span data-ttu-id="6ab9d-102">BizTalk グループを復元します。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-102">Restoring the BizTalk Group</span></span>
<span data-ttu-id="6ab9d-103">BizTalk グループのセットによって表されます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース、SSIS パッケージ、および SQL エージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-103">The BizTalk group is represented by the set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases, SSIS packages, and SQL Agent Jobs.</span></span> <span data-ttu-id="6ab9d-104">このセクションでは、BizTalk グループを復元するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-104">This section describes the process for restoring the BizTalk group.</span></span>  
  
 <span data-ttu-id="6ab9d-105">送信先システム (災害復旧サイト) への切り替えが必要なことは、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-105">In the event that a switchover to the destination system (disaster recovery site) is required, the following steps must be completed:</span></span>  
  
1.  <span data-ttu-id="6ab9d-106">復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と Analysis Services データベースです。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-106">Restore [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and Analysis Services databases.</span></span>  
  
2.  <span data-ttu-id="6ab9d-107">復元[!INCLUDE[prague](../includes/prague-md.md)]ランタイム サーバーおよびアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-107">Restore [!INCLUDE[prague](../includes/prague-md.md)] runtime servers and applications.</span></span>  
  
 <span data-ttu-id="6ab9d-108">障害復旧サイトでこれらの手順の完了時に、BizTalk グループが確立されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をランタイムにサーバーを構成して、アプリケーションは、BizTalk グループに展開できます。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-108">Upon completion of these steps, the BizTalk group has been established at the disaster recovery site, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime servers can be configured, and the applications can be deployed into the BizTalk group.</span></span> <span data-ttu-id="6ab9d-109">このセクションのトピックでは、このプロセスの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ab9d-109">The topics in this section cover the details of this process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ab9d-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ab9d-110">In This Section</span></span>  
  
-   [<span data-ttu-id="6ab9d-111">ソース システムで処理するアプリケーションを停止しています</span><span class="sxs-lookup"><span data-stu-id="6ab9d-111">Stopping Application Processing on the Source System</span></span>](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [<span data-ttu-id="6ab9d-112">バックアップの BizTalk Server のジョブ内のデータベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="6ab9d-112">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="6ab9d-113">バックアップの BizTalk Server のジョブに含まれていないデータベースの復元</span><span class="sxs-lookup"><span data-stu-id="6ab9d-113">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)