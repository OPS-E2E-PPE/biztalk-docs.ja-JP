---
title: "BizTalk Server2 を維持する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b9c10d1-101b-4b9d-8eab-767b853f17d8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d1b171f0506d7855d5faf23f2ebea393d21f60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="maintaining-biztalk-server2"></a><span data-ttu-id="1d125-102">BizTalk Server2 を維持します。</span><span class="sxs-lookup"><span data-stu-id="1d125-102">Maintaining BizTalk Server2</span></span>
<span data-ttu-id="1d125-103">メンテナンス操作は、サービスの監視と管理 (SMC) のシステムの管理機能は Microsoft Operations Framework (MOF) で定義されている部分です。</span><span class="sxs-lookup"><span data-stu-id="1d125-103">Maintenance activities are part of the Service Monitoring and Control (SMC) system management function as defined by the Microsoft Operations Framework (MOF).</span></span> <span data-ttu-id="1d125-104">SMC の主な目的がの正常性を確認するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。</span><span class="sxs-lookup"><span data-stu-id="1d125-104">The primary goal of SMC is to observe the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="1d125-105">SMC チェックでは、潜在的なサービスの問題を回避し、発生時にサービス インシデントの影響を最小限に抑える修復アクションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="1d125-105">SMC checks may initiate remedial actions to avoid potential service incidents and to minimize the impact of service incidents when they do occur.</span></span>  
  
 <span data-ttu-id="1d125-106">このガイドのこのセクションの目的で、SMC アクティビティが 4 つに分かれています。 3 つのカテゴリ: 信頼性、管理、セキュリティ、およびパフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="1d125-106">For the purposes of this section of the guide, SMC activities are divided into four three broad categories: reliability, administration, security, and performance.</span></span> <span data-ttu-id="1d125-107">毎日、毎週、および毎月の保守のチェックリストでは、それぞれのチェックを実行する頻度に従って SMC チェックを整理します。</span><span class="sxs-lookup"><span data-stu-id="1d125-107">The daily, weekly, and monthly maintenance checklists organize SMC checks according to how frequently each check should be performed.</span></span> <span data-ttu-id="1d125-108">SMC チェックでは、是正措置が必要であることを示す場合のチェックリストが表示の問題を解決するのには追加の情報源にされます。</span><span class="sxs-lookup"><span data-stu-id="1d125-108">If SMC checks indicate that remedial action is necessary, the checklists will direct you to sources of additional information to resolve the problem.</span></span>  
  
 <span data-ttu-id="1d125-109">セクションで、信頼性の解決に関連する管理、セキュリティ、およびパフォーマンスの問題が特定および解決中に発生した多くの一般的な問題に関する情報を含む[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作します。</span><span class="sxs-lookup"><span data-stu-id="1d125-109">The sections pertaining to resolving reliability, administration, security, and performance issues contain information about identifying and resolving many common problems encountered during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operations.</span></span>  
  
 <span data-ttu-id="1d125-110">Microsoft Operations Framework の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047)です。</span><span class="sxs-lookup"><span data-stu-id="1d125-110">For more information about the Microsoft Operations Framework, see [http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047).</span></span> <span data-ttu-id="1d125-111">サービスの監視と制御関数の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341)です。</span><span class="sxs-lookup"><span data-stu-id="1d125-111">For more information about the Service Monitoring and Control function, see [http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d125-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1d125-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1d125-113">信頼性を維持します。</span><span class="sxs-lookup"><span data-stu-id="1d125-113">Maintaining Reliability</span></span>](../technical-guides/maintaining-reliability.md)  
  
-   [<span data-ttu-id="1d125-114">管理用のメンテナンス</span><span class="sxs-lookup"><span data-stu-id="1d125-114">Administrative Maintenance</span></span>](../technical-guides/administrative-maintenance.md)  
  
-   [<span data-ttu-id="1d125-115">パフォーマンスを維持します。</span><span class="sxs-lookup"><span data-stu-id="1d125-115">Maintaining Performance</span></span>](../technical-guides/maintaining-performance.md)  
  
-   [<span data-ttu-id="1d125-116">BizTalk Server データベースの保守</span><span class="sxs-lookup"><span data-stu-id="1d125-116">Maintaining BizTalk Server Databases</span></span>](../technical-guides/maintaining-biztalk-server-databases.md)  
  
## <a name="related-sections"></a><span data-ttu-id="1d125-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d125-117">Related Sections</span></span>  
 [<span data-ttu-id="1d125-118">チェックリスト: メンテナンスを毎日チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d125-118">Checklist: Performing Daily Maintenance Checks</span></span>](../technical-guides/checklist-performing-daily-maintenance-checks.md)  
  
 [<span data-ttu-id="1d125-119">チェックリスト: 毎週の保守チェックの実行</span><span class="sxs-lookup"><span data-stu-id="1d125-119">Checklist: Performing Weekly Maintenance Checks</span></span>](../technical-guides/checklist-performing-weekly-maintenance-checks.md)  
  
 [<span data-ttu-id="1d125-120">チェックリスト: 毎月の保守チェックの実行</span><span class="sxs-lookup"><span data-stu-id="1d125-120">Checklist: Performing Monthly Maintenance Checks</span></span>](../technical-guides/checklist-performing-monthly-maintenance-checks.md)