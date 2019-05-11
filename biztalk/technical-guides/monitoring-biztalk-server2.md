---
title: BizTalk Server2 の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11c7181e-6281-44f2-ac63-69b705df5545
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e76afff1ff1c37de808ffe17f8b6fb5190abbed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240413"
---
# <a name="monitoring-biztalk-server"></a><span data-ttu-id="f4c34-102">BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="f4c34-102">Monitoring BizTalk Server</span></span>
<span data-ttu-id="f4c34-103">このセクションでは、BizTalk アプリケーションとインフラストラクチャを監視するための必須タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f4c34-103">This section describes essential tasks for monitoring BizTalk applications and infrastructure.</span></span> <span data-ttu-id="f4c34-104">監視[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を定期的に、BizTalk アプリケーションがアクセスできるようにするために役立ちますを検索する問題の解決でします。</span><span class="sxs-lookup"><span data-stu-id="f4c34-104">Monitoring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a regular basis and resolving any issues that you find helps to keep your BizTalk applications accessible.</span></span> <span data-ttu-id="f4c34-105">監視する目的は、時間を最小限に抑えるには問題が検出されないし、そのため、未解決のことです。</span><span class="sxs-lookup"><span data-stu-id="f4c34-105">The goal of monitoring is to minimize the amount of time that an issue goes undetected and therefore, unresolved.</span></span> <span data-ttu-id="f4c34-106">さらに、監視を使用して問題を引き起こす可能性がある状況を検出できます。</span><span class="sxs-lookup"><span data-stu-id="f4c34-106">Additionally, you can use monitoring to help detect situations that might cause an issue.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4c34-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f4c34-107">In This Section</span></span>  
  
-   [<span data-ttu-id="f4c34-108">BizTalk Server 環境の監視</span><span class="sxs-lookup"><span data-stu-id="f4c34-108">Monitoring the BizTalk Server Environment</span></span>](../technical-guides/monitoring-the-biztalk-server-environment.md)  
  
-   [<span data-ttu-id="f4c34-109">監視に関するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="f4c34-109">Best Practices for Monitoring</span></span>](../technical-guides/best-practices-for-monitoring.md)  
  
-   [<span data-ttu-id="f4c34-110">定期的な監視タスク</span><span class="sxs-lookup"><span data-stu-id="f4c34-110">Routine Monitoring Tasks</span></span>](../technical-guides/routine-monitoring-tasks.md)  
  
-   [<span data-ttu-id="f4c34-111">ログ (PAL) ツールのパフォーマンス分析の使用</span><span class="sxs-lookup"><span data-stu-id="f4c34-111">Using the Performance Analysis of Logs (PAL) Tool</span></span>](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)  
  
-   [<span data-ttu-id="f4c34-112">System Center Operations Manager 2007 による BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="f4c34-112">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)