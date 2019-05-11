---
title: リリース フェーズの推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a186306a951b249c7bcadb243549c8761f6408fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397968"
---
# <a name="release-phase-recommendations"></a><span data-ttu-id="4ad9f-102">リリース フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="4ad9f-102">Release Phase Recommendations</span></span>
<span data-ttu-id="4ad9f-103">リリース フェーズでは、実稼働のハードウェア上に現在検証済みのシステムを伝達する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-103">The release phase involves propagating the now validated system onto the production hardware.</span></span>  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a><span data-ttu-id="4ad9f-104">テスト ベッド最適化の実稼働システムに反映されるまでください。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-104">Propagate Test Bed Optimizations to Production Systems</span></span>  
 <span data-ttu-id="4ad9f-105">システムの成果物と実稼働のハードウェア上に構成を反映し、最大を開始すること、プロセスは、比較的簡単なプロセスになります。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-105">Propagating the system artifacts and configuration onto the production hardware and starting it up to process is a relatively straightforward process.</span></span> <span data-ttu-id="4ad9f-106">ただし、実際が簡単に見落とされることができますが、このフェーズ中にパフォーマンスに関する考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-106">However, in practice, there are things to consider regarding performance during this phase that can be easily missed:</span></span>  
  
-   <span data-ttu-id="4ad9f-107">**プラットフォームの最適化が伝達されていることを確認**します。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-107">**Verify that platform optimizations are propagated**.</span></span> <span data-ttu-id="4ad9f-108">実装との検証中には、任意の数のプラットフォーム レベルのパフォーマンスの最適化を実装するために一般的です。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-108">During implementation and verification, it is common to implement any number of platform level performance optimizations.</span></span>  
  
     <span data-ttu-id="4ad9f-109">たとえば、HTTP などの分離アダプターのインターネット インフォメーション サーバー (IIS) を使用する場合は、数など、アダプターを実行する IIS のプロセスの数を増やすために使用できる一般的なパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-109">For example, when using an isolated adapter such as HTTP on Internet Information Server (IIS), there are a number of common performance optimizations that can be used such as increasing the number of processes in IIS in which the adapters will run.</span></span> <span data-ttu-id="4ad9f-110">リリースの追跡し、同様、運用環境に反映する必要があります前に見つかったパフォーマンス最適化などにします。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-110">Any such performance optimizations found before release must be tracked and propagated to the production environment as well.</span></span>  
  
-   <span data-ttu-id="4ad9f-111">**設定してデータのバックアップを自動化、ログ配布、データ保有期間の構成、および削除タスク**します。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-111">**Set up and automate data backup, log shipping, data retention configurations, and purging tasks**.</span></span> <span data-ttu-id="4ad9f-112">実稼働に対する保証の一環として、データベースのバックアップおよび消去されます (例、BizTalk 追跡データベース、および BAM データベース) の位置の頻度は持続可能性に対するキーがまだ存在しない実稼働環境にこれらの設定を移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ad9f-112">As part of certification for production, the frequency at which databases are backed up and purged (for example, the BizTalk Tracking database and BAM database) is key to sustainability so those settings must be migrated to production they don’t already exist there.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad9f-113">参照</span><span class="sxs-lookup"><span data-stu-id="4ad9f-113">See Also</span></span>  
 <span data-ttu-id="4ad9f-114">[プロジェクトの計画フェーズの推奨事項](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="4ad9f-114">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="4ad9f-115">[要件フェーズの推奨事項](../core/requirements-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="4ad9f-115">[Requirements Phase Recommendations](../core/requirements-phase-recommendations.md) </span></span>  
 <span data-ttu-id="4ad9f-116">[デザイン フェーズの推奨事項](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="4ad9f-116">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="4ad9f-117">[実装フェーズの推奨事項](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="4ad9f-117">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="4ad9f-118">検証フェーズの推奨事項</span><span class="sxs-lookup"><span data-stu-id="4ad9f-118">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)