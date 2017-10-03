---
title: "チェックリスト: 監視の運用の準備 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef77ccc2-1d39-4e78-8fea-5c17d05c8174
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 913ed00da2bda4126ba298bbb9bce2980efa4366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-monitoring-operational-readiness"></a><span data-ttu-id="ee670-102">チェックリスト: 監視の運用の準備</span><span class="sxs-lookup"><span data-stu-id="ee670-102">Checklist: Monitoring Operational Readiness</span></span>
<span data-ttu-id="ee670-103">このトピックは、実稼働環境を監視する際に従う必要のある手順を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="ee670-103">This topic lists the steps that you should follow when monitoring a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
|<span data-ttu-id="ee670-104">手順</span><span class="sxs-lookup"><span data-stu-id="ee670-104">Steps</span></span>|<span data-ttu-id="ee670-105">リファレンス</span><span class="sxs-lookup"><span data-stu-id="ee670-105">Reference</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="ee670-106">選択して、BizTalk アプリケーションとインフラストラクチャの監視の戦略を実装します。</span><span class="sxs-lookup"><span data-stu-id="ee670-106">Select and implement a monitoring strategy for your BizTalk applications and infrastructure.</span></span>|[<span data-ttu-id="ee670-107">BizTalk Server 環境を監視します。</span><span class="sxs-lookup"><span data-stu-id="ee670-107">Monitoring the BizTalk Server Environment</span></span>](../technical-guides/monitoring-the-biztalk-server-environment.md)|  
|<span data-ttu-id="ee670-108">ディスク領域使用率を監視します。</span><span class="sxs-lookup"><span data-stu-id="ee670-108">Monitor disk space usage.</span></span>|[<span data-ttu-id="ee670-109">ディスク領域使用率の監視</span><span class="sxs-lookup"><span data-stu-id="ee670-109">Monitoring Disk Space Usage</span></span>](../technical-guides/monitoring-disk-space-usage.md)|  
|<span data-ttu-id="ee670-110">モニターの SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ee670-110">Monitor SQL Server:</span></span><br /><br /> <span data-ttu-id="ee670-111">検証ハウジングの SQL Server を実行しているコンピューターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースの監視されています。</span><span class="sxs-lookup"><span data-stu-id="ee670-111">-   Verify that computers running SQL Server housing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are being monitored.</span></span><br /><span data-ttu-id="ee670-112">-ことを確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが監視されています。</span><span class="sxs-lookup"><span data-stu-id="ee670-112">-   Verify that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] jobs are being monitored.</span></span>|<span data-ttu-id="ee670-113">-   [SQL サーバーの監視](../technical-guides/monitoring-sql-servers.md)</span><span class="sxs-lookup"><span data-stu-id="ee670-113">-   [Monitoring SQL Servers](../technical-guides/monitoring-sql-servers.md)</span></span><br /><span data-ttu-id="ee670-114">-   [BizTalk Server データベースの監視](../technical-guides/monitoring-biztalk-server-databases.md)</span><span class="sxs-lookup"><span data-stu-id="ee670-114">-   [Monitoring BizTalk Server Databases](../technical-guides/monitoring-biztalk-server-databases.md)</span></span>|  
|<span data-ttu-id="ee670-115">BizTalk アプリケーションを監視します。</span><span class="sxs-lookup"><span data-stu-id="ee670-115">Monitor BizTalk applications:</span></span><br /><br /> <span data-ttu-id="ee670-116">-既存の規則またはカスタムの BizTalk アプリケーションを監視するカスタム管理パックにルールのコピーを変更します。</span><span class="sxs-lookup"><span data-stu-id="ee670-116">-   Modify existing rules and/or copy rules to a custom management pack to monitor a custom BizTalk application.</span></span><br /><span data-ttu-id="ee670-117">定義された各ルールのアクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee670-117">-   Create actions for each defined rule.</span></span><br /><span data-ttu-id="ee670-118">-手動のタスクを自動化する反復的なプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee670-118">-   Create iterative processes to automate manual tasks.</span></span><br /><span data-ttu-id="ee670-119">-手動のタスクを自動化するのにしきい値規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="ee670-119">-   Use threshold rules to automate manual tasks.</span></span>|<span data-ttu-id="ee670-120">-   [アプリケーションとホスト インスタンスの監視](../technical-guides/monitoring-applications-and-host-instances.md)</span><span class="sxs-lookup"><span data-stu-id="ee670-120">-   [Monitoring Applications and Host Instances](../technical-guides/monitoring-applications-and-host-instances.md)</span></span><br /><span data-ttu-id="ee670-121">-   [BizTalk Server2 の監視](../technical-guides/monitoring-biztalk-server2.md)</span><span class="sxs-lookup"><span data-stu-id="ee670-121">-   [Monitoring BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="ee670-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ee670-122">In This Section</span></span>  
  
-   [<span data-ttu-id="ee670-123">ディスク領域使用率の監視</span><span class="sxs-lookup"><span data-stu-id="ee670-123">Monitoring Disk Space Usage</span></span>](../technical-guides/monitoring-disk-space-usage.md)