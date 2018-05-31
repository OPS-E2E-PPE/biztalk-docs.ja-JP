---
title: サービス レベル管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add50343-5470-4db3-a029-c827523e2f2c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b7ba1672660af2a68a5d193729a0a9009173d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294730"
---
# <a name="service-level-management"></a><span data-ttu-id="77c64-102">サービス レベル管理</span><span class="sxs-lookup"><span data-stu-id="77c64-102">Service Level Management</span></span>
<span data-ttu-id="77c64-103">AmberPoint SMS サービス レベル マネージャーは、特定のパフォーマンスやエンタープライズ レベルの SOA ベースのシステム内の可用性に関する問題の可視性を提供します。</span><span class="sxs-lookup"><span data-stu-id="77c64-103">The AmberPoint SMS Service Level Manager provides visibility into specific performance and availability issues within enterprise-level SOA-based systems.</span></span> <span data-ttu-id="77c64-104">インストルメント化し、各 Microsoft BizTalk Server 受信場所と送信ポートのメトリックを追跡します。</span><span class="sxs-lookup"><span data-stu-id="77c64-104">It instruments and tracks the metrics for each Microsoft BizTalk Server receive location and send port.</span></span> <span data-ttu-id="77c64-105">これは、これらのコンポーネントの継続的なパフォーマンス特性に加え、リアルタイムの正常性と状態表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c64-105">This provides real-time health and status indication, in addition to ongoing performance characterization of these components.</span></span> <span data-ttu-id="77c64-106">図 1 は、受信場所に関連付けられているメトリックの表示を示しています。</span><span class="sxs-lookup"><span data-stu-id="77c64-106">Figure 1 shows the display of the metrics associated with a receive location.</span></span>  
  
 <span data-ttu-id="77c64-107">![AmberPoint 受信場所](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9 AmberPointReceiveLocation")</span><span class="sxs-lookup"><span data-stu-id="77c64-107">![AmberPoint Receive Location](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9-AmberPointReceiveLocation")</span></span>  
  
 <span data-ttu-id="77c64-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="77c64-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="77c64-109">**受信場所に関連付けられているメトリック**</span><span class="sxs-lookup"><span data-stu-id="77c64-109">**The metrics associated with a receive location**</span></span>  
  
 <span data-ttu-id="77c64-110">AmberPoint の実行時の分析のしきい値を設定し、システムが準拠の警告イベント、コンプライアンス違反イベント、およびコンプライアンスに後続の戻り値を含む、重要なイベントのしきい値を超えたときにアラートを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="77c64-110">AmberPoint run-time analytics allow users to set thresholds and send alerts when a system crosses a critical event threshold, including compliance warnings events, compliance violations events, and a subsequent return to compliance.</span></span> <span data-ttu-id="77c64-111">図 2 は、ユーザーがサービス レベル アグリーメントを構成して、このサービス レベル アグリーメントに生成されたアラートの表示の表示を示しています。</span><span class="sxs-lookup"><span data-stu-id="77c64-111">Figure 2 shows the display where users configure service level agreements and view alerts generated for this service level agreement.</span></span>  
  
 <span data-ttu-id="77c64-112">![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9 AmberPointSLA")</span><span class="sxs-lookup"><span data-stu-id="77c64-112">![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")</span></span>  
  
 <span data-ttu-id="77c64-113">**図 2**</span><span class="sxs-lookup"><span data-stu-id="77c64-113">**Figure 2**</span></span>  
  
 <span data-ttu-id="77c64-114">**サービス レベル アグリーメントを構成して、通知を表示する画面**</span><span class="sxs-lookup"><span data-stu-id="77c64-114">**The screens to configure a service level agreement and view alerts**</span></span>  
  
 <span data-ttu-id="77c64-115">サービス レベル マネージャー内でパフォーマンスのターゲットを確立することができます。</span><span class="sxs-lookup"><span data-stu-id="77c64-115">You can establish performance targets within the Service Level Manager.</span></span> <span data-ttu-id="77c64-116">ソフトウェアでは、これらのターゲットに対するパフォーマンスを測定する、ユーザーのグループからの個々 のメッセージ、特定のユーザーからのメッセージまたはメッセージを追跡します。</span><span class="sxs-lookup"><span data-stu-id="77c64-116">The software then tracks individual messages, messages from a specific user, or messages from groups of users, to measure performance against these targets.</span></span>  
  
 <span data-ttu-id="77c64-117">AmberPoint SMS を動的に収集し、図 3 に示すように、メッセージのコンテキストと BizTalk Server を通過するデータを検査するように指示するログ記録のポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="77c64-117">You can also configure logging policies that instruct AmberPoint SMS to dynamically collect and inspect message context and data passing through BizTalk Server, as shown in Figure 3.</span></span> <span data-ttu-id="77c64-118">できますし、使用するこれらのログ「での実行時」のトラブルシューティングのため、技術的な問題、分析するため、およびアーカイブするため業界特有の規制に準拠します。</span><span class="sxs-lookup"><span data-stu-id="77c64-118">You can then use these logs for "on-the-fly" troubleshooting, for technical analysis of problems, and for archiving to comply with industry-specific regulations.</span></span>  
  
 <span data-ttu-id="77c64-119">![BizTalk サービスのメッセージ](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9 BizTalkServiceMessages")</span><span class="sxs-lookup"><span data-stu-id="77c64-119">![BizTalk Service Messages](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9-BizTalkServiceMessages")</span></span>  
  
 <span data-ttu-id="77c64-120">**図 3**</span><span class="sxs-lookup"><span data-stu-id="77c64-120">**Figure 3**</span></span>  
  
 <span data-ttu-id="77c64-121">**BizTalk Server サービスのメッセージをログ ファイル**</span><span class="sxs-lookup"><span data-stu-id="77c64-121">**The log file for BizTalk Server service messages**</span></span>