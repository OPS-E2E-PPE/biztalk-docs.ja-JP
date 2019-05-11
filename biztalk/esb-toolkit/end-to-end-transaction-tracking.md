---
title: エンド ツー エンドのトランザクションの追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebacd2e4-6b5c-4dc4-8361-b5b77042debc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7d19c4ce9bc30d60144ed69fc14f2323b4379d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306190"
---
# <a name="end-to-end-transaction-tracking"></a><span data-ttu-id="8bad7-102">エンド ツー エンドのトランザクション追跡</span><span class="sxs-lookup"><span data-stu-id="8bad7-102">End-to-End Transaction Tracking</span></span>
<span data-ttu-id="8bad7-103">実行時環境を通過するトラフィックのフローを監視する演算子とユーザーの能力をビジネス情報の表示が関連しています。</span><span class="sxs-lookup"><span data-stu-id="8bad7-103">Business visibility relates to the ability of operators and users to monitor the flow of traffic through the run-time environment.</span></span> <span data-ttu-id="8bad7-104">企業は、プロセスおよび各手順を確実に収益創出に貢献するのには、再生時にシステムを流れるトランザクションを追跡できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bad7-104">Enterprises must be able to track the processes and transactions flowing through their systems at each step to ensure that they play their part in contributing to revenue generation.</span></span> <span data-ttu-id="8bad7-105">AmberPoint SMS には、測定単位と Microsoft BizTalk Server でこれらのメッセージの追跡が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="8bad7-105">AmberPoint SMS simplifies the measurement and tracking of these messages in Microsoft BizTalk Server.</span></span> <span data-ttu-id="8bad7-106">システムでは、新しいパッケージ化し、個々 のサービス コンポーネントを展開する開発者が選択した方法に準拠するように求められるのではなく、エンド ツー エンドのビジネス プロセス フローと一致する管理単位を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="8bad7-106">The system allows users to define new units of management that align with end-to-end business process flows, instead of being required to conform to the way developers chose to package and deploy individual service components.</span></span> <span data-ttu-id="8bad7-107">図 1 には、管理単位を定義するための画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bad7-107">Figure 1 shows the screen for defining management units.</span></span>  
  
 <span data-ttu-id="8bad7-108">![BizTalk の定義トランザクション](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9 BizTalkDefiningTransaction")</span><span class="sxs-lookup"><span data-stu-id="8bad7-108">![BizTalk Defining Transaction](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")</span></span>  
  
 <span data-ttu-id="8bad7-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="8bad7-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="8bad7-110">**新しい管理単位として、トランザクションを定義します。**</span><span class="sxs-lookup"><span data-stu-id="8bad7-110">**Defining a transaction as a new unit of management**</span></span>  
  
 <span data-ttu-id="8bad7-111">トランザクションを定義した後は、ユーザーがインストルメント化でき、可視性を 1 つのサービス提供のと同じツールを使用して、各トランザクションに関連付けられているメッセージの追跡。</span><span class="sxs-lookup"><span data-stu-id="8bad7-111">After defining transactions, users can instrument and track messages associated with each transaction using the same tools that provide visibility into a single service.</span></span> <span data-ttu-id="8bad7-112">これらのツールでは、パフォーマンス メトリックを公開、に対するサービス レベル アグリーメント、パフォーマンスを監視、および図 2 に示すように、メッセージのログを生成できます。</span><span class="sxs-lookup"><span data-stu-id="8bad7-112">These tools can expose performance metrics, monitor performance against service level agreements, and generate message logs, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="8bad7-113">![BizTalk の監視](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9 BizTalkMonitoring")</span><span class="sxs-lookup"><span data-stu-id="8bad7-113">![BizTalk Monitoring](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")</span></span>  
  
 <span data-ttu-id="8bad7-114">**図 2**</span><span class="sxs-lookup"><span data-stu-id="8bad7-114">**Figure 2**</span></span>  
  
 <span data-ttu-id="8bad7-115">**パイプラインのエンド ツー エンドのパフォーマンスの監視**</span><span class="sxs-lookup"><span data-stu-id="8bad7-115">**Monitoring the end-to-end performance of a pipeline**</span></span>  
  
 <span data-ttu-id="8bad7-116">成功した実行時のガバナンスおよびシステムの監視の主要な要件は、例外、論理ビジネス トランザクション フローの処理が中断される可能性がありますアプリケーション エラーなどの重要なビジネス イベントの検出です。</span><span class="sxs-lookup"><span data-stu-id="8bad7-116">A major requirement for successful run-time governance and system monitoring is the detection of important business events, such as exceptions and application errors that may disrupt the logical processing of business transaction flows.</span></span> <span data-ttu-id="8bad7-117">AmberPoint SMS は、オペレーターとユーザーは、運用洞察とビジネス イベントを取得して、これらのイベントは、問題を生成したサービスに依存するすべてのコンポーネントに与える影響を監視できます。</span><span class="sxs-lookup"><span data-stu-id="8bad7-117">AmberPoint SMS allows operators and users to gain insight into operational and business events and to monitor the impact these events have on all components that depend on the service that generated the problem.</span></span> <span data-ttu-id="8bad7-118">さらに、オペレーターとユーザーことができますを迅速にトラブルシューティング システム全体の問題の根本原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="8bad7-118">In addition, operators and users can quickly troubleshoot the entire system to identify the root-cause of a problem.</span></span>