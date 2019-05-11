---
title: BizTalk Server2 のメンテナンス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b9c10d1-101b-4b9d-8eab-767b853f17d8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b09c8f6ffd1a7467a992c51a737d1f77a75ba93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396273"
---
# <a name="maintaining-biztalk-server2"></a><span data-ttu-id="739bc-102">BizTalk Server2 のメンテナンス</span><span class="sxs-lookup"><span data-stu-id="739bc-102">Maintaining BizTalk Server2</span></span>
<span data-ttu-id="739bc-103">メンテナンス操作は、サービスの監視と管理 (SMC) のシステムの管理関数は、Microsoft Operations Framework (MOF) によって定義されているの一部です。</span><span class="sxs-lookup"><span data-stu-id="739bc-103">Maintenance activities are part of the Service Monitoring and Control (SMC) system management function as defined by the Microsoft Operations Framework (MOF).</span></span> <span data-ttu-id="739bc-104">SMC の主な目的は、の正常性を確認するのには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="739bc-104">The primary goal of SMC is to observe the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="739bc-105">SMC チェックでは、潜在的なサービスの問題を回避するために、発生時に、サービスのインシデントの影響を最小限に抑えるための修復アクションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="739bc-105">SMC checks may initiate remedial actions to avoid potential service incidents and to minimize the impact of service incidents when they do occur.</span></span>  
  
 <span data-ttu-id="739bc-106">ガイドのこのセクションの目的において、SMC アクティビティが 4 つに分かれています。 3 つのカテゴリ: 信頼性、管理、セキュリティ、およびパフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="739bc-106">For the purposes of this section of the guide, SMC activities are divided into four three broad categories: reliability, administration, security, and performance.</span></span> <span data-ttu-id="739bc-107">毎日、毎週、および毎月のメンテナンスのチェックリストでは、各チェックの実行頻度に従って SMC チェックを整理します。</span><span class="sxs-lookup"><span data-stu-id="739bc-107">The daily, weekly, and monthly maintenance checklists organize SMC checks according to how frequently each check should be performed.</span></span> <span data-ttu-id="739bc-108">SMC チェックは、修復アクションが必要であることを示す場合、チェックリストの問題を解決するのには追加の情報源が直接されます。</span><span class="sxs-lookup"><span data-stu-id="739bc-108">If SMC checks indicate that remedial action is necessary, the checklists will direct you to sources of additional information to resolve the problem.</span></span>  
  
 <span data-ttu-id="739bc-109">信頼性の解決に関連するセクションで、管理、セキュリティ、およびパフォーマンスの問題には特定と解決中に発生した多くの一般的な問題に関する情報が含まれて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作。</span><span class="sxs-lookup"><span data-stu-id="739bc-109">The sections pertaining to resolving reliability, administration, security, and performance issues contain information about identifying and resolving many common problems encountered during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operations.</span></span>  
  
 <span data-ttu-id="739bc-110">Microsoft Operations Framework の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047)します。</span><span class="sxs-lookup"><span data-stu-id="739bc-110">For more information about the Microsoft Operations Framework, see [http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047).</span></span> <span data-ttu-id="739bc-111">サービスの監視と制御関数の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341)します。</span><span class="sxs-lookup"><span data-stu-id="739bc-111">For more information about the Service Monitoring and Control function, see [http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="739bc-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="739bc-112">In This Section</span></span>  
  
-   [<span data-ttu-id="739bc-113">信頼性の維持</span><span class="sxs-lookup"><span data-stu-id="739bc-113">Maintaining Reliability</span></span>](../technical-guides/maintaining-reliability.md)  
  
-   [<span data-ttu-id="739bc-114">管理メンテナンス</span><span class="sxs-lookup"><span data-stu-id="739bc-114">Administrative Maintenance</span></span>](../technical-guides/administrative-maintenance.md)  
  
-   [<span data-ttu-id="739bc-115">パフォーマンスの維持</span><span class="sxs-lookup"><span data-stu-id="739bc-115">Maintaining Performance</span></span>](../technical-guides/maintaining-performance.md)  
  
-   [<span data-ttu-id="739bc-116">BizTalk Server データベースのメンテナンス</span><span class="sxs-lookup"><span data-stu-id="739bc-116">Maintaining BizTalk Server Databases</span></span>](../technical-guides/maintaining-biztalk-server-databases.md)  
  
## <a name="related-sections"></a><span data-ttu-id="739bc-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="739bc-117">Related Sections</span></span>  
 [<span data-ttu-id="739bc-118">チェックリスト:毎日のメンテナンス チェックの実行</span><span class="sxs-lookup"><span data-stu-id="739bc-118">Checklist: Performing Daily Maintenance Checks</span></span>](../technical-guides/checklist-performing-daily-maintenance-checks.md)  
  
 [<span data-ttu-id="739bc-119">チェックリスト:毎週のメンテナンス チェックの実行</span><span class="sxs-lookup"><span data-stu-id="739bc-119">Checklist: Performing Weekly Maintenance Checks</span></span>](../technical-guides/checklist-performing-weekly-maintenance-checks.md)  
  
 [<span data-ttu-id="739bc-120">チェックリスト:毎月のメンテナンス チェックの実行</span><span class="sxs-lookup"><span data-stu-id="739bc-120">Checklist: Performing Monthly Maintenance Checks</span></span>](../technical-guides/checklist-performing-monthly-maintenance-checks.md)