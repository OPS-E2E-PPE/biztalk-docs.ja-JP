---
title: "リリース フェーズの推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a38a8a06fac8dc35fed4d965ea9b7952c5fdfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="release-phase-recommendations"></a><span data-ttu-id="bda82-102">リリース フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="bda82-102">Release Phase Recommendations</span></span>
<span data-ttu-id="bda82-103">リリース フェーズでは、現在検証済みのシステムを実稼働のハードウェアに反映させます。</span><span class="sxs-lookup"><span data-stu-id="bda82-103">The release phase involves propagating the now validated system onto the production hardware.</span></span>  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a><span data-ttu-id="bda82-104">テスト ベッド最適化の実稼働システムへの反映</span><span class="sxs-lookup"><span data-stu-id="bda82-104">Propagate Test Bed Optimizations to Production Systems</span></span>  
 <span data-ttu-id="bda82-105">実稼働のハードウェアに対してシステムのアイテムおよび構成を反映させ、このハードウェアを起動して処理できるようにすることは、比較的簡単なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="bda82-105">Propagating the system artifacts and configuration onto the production hardware and starting it up to process is a relatively straightforward process.</span></span> <span data-ttu-id="bda82-106">ただし、このフェーズでは、パフォーマンスに関して見落とされがちな次の事項を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bda82-106">However, in practice, there are things to consider regarding performance during this phase that can be easily missed:</span></span>  
  
-   <span data-ttu-id="bda82-107">**プラットフォームの最適化が反映されることを確認してください。**です。</span><span class="sxs-lookup"><span data-stu-id="bda82-107">**Verify that platform optimizations are propagated**.</span></span> <span data-ttu-id="bda82-108">実装と検証の間に、通常、プラットフォーム レベルのパフォーマンスの最適化を必要に応じて実装します。</span><span class="sxs-lookup"><span data-stu-id="bda82-108">During implementation and verification, it is common to implement any number of platform level performance optimizations.</span></span>  
  
     <span data-ttu-id="bda82-109">たとえば、インターネット インフォメーション サーバー (IIS) で HTTP などの分離アダプターを使用する場合、アダプターが実行される IIS 内のプロセス数を増やすなど、一般的なパフォーマンスの最適化をいくつか利用できます。</span><span class="sxs-lookup"><span data-stu-id="bda82-109">For example, when using an isolated adapter such as HTTP on Internet Information Server (IIS), there are a number of common performance optimizations that can be used such as increasing the number of processes in IIS in which the adapters will run.</span></span> <span data-ttu-id="bda82-110">このようなリリース前に見つかったパフォーマンスの最適化は、追跡して実稼働環境にも反映させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bda82-110">Any such performance optimizations found before release must be tracked and propagated to the production environment as well.</span></span>  
  
-   <span data-ttu-id="bda82-111">**設定し、データのバックアップを自動化し、ログ配布、データ保有期間の構成、および削除の各タスク**です。</span><span class="sxs-lookup"><span data-stu-id="bda82-111">**Set up and automate data backup, log shipping, data retention configurations, and purging tasks**.</span></span> <span data-ttu-id="bda82-112">実稼働に対する保証の一環として、データベース (BizTalk 追跡データベースや BAM データベースなど) のバックアップおよび削除の頻度は、これらの設定をデータベースがまだ存在しない実稼働に移行する必要があることから持続性において重要です。</span><span class="sxs-lookup"><span data-stu-id="bda82-112">As part of certification for production, the frequency at which databases are backed up and purged (for example, the BizTalk Tracking database and BAM database) is key to sustainability so those settings must be migrated to production they don’t already exist there.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda82-113">参照</span><span class="sxs-lookup"><span data-stu-id="bda82-113">See Also</span></span>  
 <span data-ttu-id="bda82-114">[プロジェクト計画のフェーズの推奨事項](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="bda82-114">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="bda82-115">[要件フェーズの推奨事項](../core/requirements-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="bda82-115">[Requirements Phase Recommendations](../core/requirements-phase-recommendations.md) </span></span>  
 <span data-ttu-id="bda82-116">[設計フェーズの推奨事項](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="bda82-116">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="bda82-117">[実装フェーズの推奨事項](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="bda82-117">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="bda82-118">検証フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="bda82-118">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)