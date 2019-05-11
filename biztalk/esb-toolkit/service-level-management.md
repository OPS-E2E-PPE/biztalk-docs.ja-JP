---
title: サービス レベルの管理 |Microsoft Docs
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
ms.openlocfilehash: c67b66bf5a353b22193037d7112de8233982834b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394006"
---
# <a name="service-level-management"></a><span data-ttu-id="6cf9a-102">サービス レベル管理</span><span class="sxs-lookup"><span data-stu-id="6cf9a-102">Service Level Management</span></span>
<span data-ttu-id="6cf9a-103">AmberPoint SMS サービス レベルのマネージャーは、特定のパフォーマンスと SOA ベースのエンタープライズ レベル システム内の可用性の問題を可視化を提供します。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-103">The AmberPoint SMS Service Level Manager provides visibility into specific performance and availability issues within enterprise-level SOA-based systems.</span></span> <span data-ttu-id="6cf9a-104">インストルメント化し、各 Microsoft BizTalk Server 受信場所と送信ポートのメトリックを追跡します。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-104">It instruments and tracks the metrics for each Microsoft BizTalk Server receive location and send port.</span></span> <span data-ttu-id="6cf9a-105">これは、これらのコンポーネントの継続的なパフォーマンス特性に加え、リアルタイムの正常性と状態表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-105">This provides real-time health and status indication, in addition to ongoing performance characterization of these components.</span></span> <span data-ttu-id="6cf9a-106">図 1 は、受信場所に関連付けられているメトリックの表示を示します。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-106">Figure 1 shows the display of the metrics associated with a receive location.</span></span>  
  
 <span data-ttu-id="6cf9a-107">![AmberPoint 受信場所](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9 AmberPointReceiveLocation")</span><span class="sxs-lookup"><span data-stu-id="6cf9a-107">![AmberPoint Receive Location](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9-AmberPointReceiveLocation")</span></span>  
  
 <span data-ttu-id="6cf9a-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="6cf9a-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="6cf9a-109">**受信場所に関連付けられているメトリック**</span><span class="sxs-lookup"><span data-stu-id="6cf9a-109">**The metrics associated with a receive location**</span></span>  
  
 <span data-ttu-id="6cf9a-110">AmberPoint の実行時の分析のしきい値を設定し、システムが準拠の警告イベント、コンプライアンス違反イベント、およびコンプライアンスに後続の戻り値を含む、重要なイベントのしきい値を超えたときにアラートを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-110">AmberPoint run-time analytics allow users to set thresholds and send alerts when a system crosses a critical event threshold, including compliance warnings events, compliance violations events, and a subsequent return to compliance.</span></span> <span data-ttu-id="6cf9a-111">図 2 は、ユーザーがサービス レベル アグリーメントを構成して、このサービス レベル アグリーメントに対して生成されたアラートの表示の表示を示しています。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-111">Figure 2 shows the display where users configure service level agreements and view alerts generated for this service level agreement.</span></span>  
  
 <span data-ttu-id="6cf9a-112">![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")</span><span class="sxs-lookup"><span data-stu-id="6cf9a-112">![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")</span></span>  
  
 <span data-ttu-id="6cf9a-113">**図 2**</span><span class="sxs-lookup"><span data-stu-id="6cf9a-113">**Figure 2**</span></span>  
  
 <span data-ttu-id="6cf9a-114">**サービス レベル アグリーメントを構成してアラートを表示する画面**</span><span class="sxs-lookup"><span data-stu-id="6cf9a-114">**The screens to configure a service level agreement and view alerts**</span></span>  
  
 <span data-ttu-id="6cf9a-115">サービス レベル マネージャー内でパフォーマンスのターゲットを確立することができます。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-115">You can establish performance targets within the Service Level Manager.</span></span> <span data-ttu-id="6cf9a-116">ソフトウェアでは、これらのターゲットに対するパフォーマンスを測定する、ユーザーのグループから個々 のメッセージ、特定のユーザーからのメッセージまたはメッセージを追跡します。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-116">The software then tracks individual messages, messages from a specific user, or messages from groups of users, to measure performance against these targets.</span></span>  
  
 <span data-ttu-id="6cf9a-117">AmberPoint SMS を動的に収集し、図 3 に示すように、メッセージのコンテキストと BizTalk Server を通過するデータを検査するように指示するログ記録ポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-117">You can also configure logging policies that instruct AmberPoint SMS to dynamically collect and inspect message context and data passing through BizTalk Server, as shown in Figure 3.</span></span> <span data-ttu-id="6cf9a-118">できますし、使用するこれらのログ「にその場で」のトラブルシューティングのため、テクニカル分析の問題、およびアーカイブの業界固有の規制を遵守します。</span><span class="sxs-lookup"><span data-stu-id="6cf9a-118">You can then use these logs for "on-the-fly" troubleshooting, for technical analysis of problems, and for archiving to comply with industry-specific regulations.</span></span>  
  
 <span data-ttu-id="6cf9a-119">![BizTalk サービスのメッセージ](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9 BizTalkServiceMessages")</span><span class="sxs-lookup"><span data-stu-id="6cf9a-119">![BizTalk Service Messages](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9-BizTalkServiceMessages")</span></span>  
  
 <span data-ttu-id="6cf9a-120">**図 3**</span><span class="sxs-lookup"><span data-stu-id="6cf9a-120">**Figure 3**</span></span>  
  
 <span data-ttu-id="6cf9a-121">**BizTalk Server サービスのメッセージをログ ファイル**</span><span class="sxs-lookup"><span data-stu-id="6cf9a-121">**The log file for BizTalk Server service messages**</span></span>