---
title: "SQL Server エージェント ジョブおよびデータベースの監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c9991e7ebd61c72bbeb6a090b0497244da63e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a><span data-ttu-id="4f6d7-102">SQL Server エージェント ジョブとデータベースの監視</span><span class="sxs-lookup"><span data-stu-id="4f6d7-102">Monitoring SQL Server Agent Jobs and Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4f6d7-103">複数含まれています[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]動作状況と状態、サーバーを保つために重要な機能を実行するエージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-103"> includes multiple [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="4f6d7-104">これらのジョブの状態を監視し、エラーが発生せずに動作していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span> <span data-ttu-id="4f6d7-105">Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックには、SQL データベースなどの項目を監視するためのルールが含まれています。 および[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-105">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack contains rules for monitoring items such as SQL databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="4f6d7-106">構成する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]すべての包括的な監視用管理パック[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースおよび[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-106">You should configure the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for comprehensive monitoring of all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="4f6d7-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックには、2 つの最も重要な BizTalk のヘルスを監視するための 2 つの無効化されたルールが含まれています。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack includes two disabled rules for monitoring the health of two of the most important BizTalk [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs:</span></span>  
  
-   <span data-ttu-id="4f6d7-108">重大なエラー: BizTalk SQL Server エージェント ジョブに失敗しました - BizTalk Server のバックアップ</span><span class="sxs-lookup"><span data-stu-id="4f6d7-108">Critical Error: A BizTalk SQL Server Agent job failed - Backup BizTalk Server</span></span>  
  
-   <span data-ttu-id="4f6d7-109">重大なエラー: BizTalk SQL Server エージェント ジョブが失敗しました: メッセージのコピーを追跡</span><span class="sxs-lookup"><span data-stu-id="4f6d7-109">Critical Error: A BizTalk SQL Server Agent job failed – Tracked Message Copy</span></span>  
  
 <span data-ttu-id="4f6d7-110">すべての BizTalk Server を監視する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]内からのエージェント ジョブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、これらの規則を有効にし、追加の規則を使用して、次のプロセスを監視する他のジョブを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-110">To monitor all BizTalk Server [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack, you must enable these rules and create additional rules for other jobs that you want to monitor using the following process.</span></span>  
  
-   <span data-ttu-id="4f6d7-111">Operations Manager 管理者コンソールでの 2 つの前述の規則のいずれかのコピーを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コア ルール グループ化、およびルールを適切に名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-111">In the Operations Manager Administrator console, create a copy of either of the two preceding rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Core Rule group, and rename the rule appropriately.</span></span>  
  
-   <span data-ttu-id="4f6d7-112">ルールの [条件] セクションで適切にパラメーター 1 に対するワイルドカード比較を変更します。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-112">In the criteria section for the rule, change the wildcard comparison for Parameter 1 appropriately.</span></span>  
  
-   <span data-ttu-id="4f6d7-113">場合によっては、ジョブ名はデータベース名、ユーザーが作成、たとえば、メッセージ ボックス データベースの名前に依存します。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-113">In some cases, job names are dependent on database names that the user creates, for example, the name of the MessageBox database.</span></span>  
  
-   <span data-ttu-id="4f6d7-114">ルールのターゲットとなるジョブの方向にいずれかに関連付けられている 1 つのメッセージ ボックス データベースまたはすべてのメッセージ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="4f6d7-114">Your rule can be targeted either towards a job associated with a single MessageBox or all MessageBoxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f6d7-115">参照</span><span class="sxs-lookup"><span data-stu-id="4f6d7-115">See Also</span></span>  
 [<span data-ttu-id="4f6d7-116">SQL Server エージェントを開始する方法</span><span class="sxs-lookup"><span data-stu-id="4f6d7-116">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)