---
title: "BizTalk ソリューションの高パフォーマンスのベスト プラクティスを instrumentation |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef6f243f894071aebb0089f063ed0242ee09d9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a><span data-ttu-id="bc56e-102">BizTalk ソリューションの高パフォーマンスのベスト プラクティスのインストルメンテーション</span><span class="sxs-lookup"><span data-stu-id="bc56e-102">Instrumentation Best Practices for High Performance BizTalk Solutions</span></span>
<span data-ttu-id="bc56e-103">このホワイト ペーパーのコピーをダウンロードするには[http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874)です。</span><span class="sxs-lookup"><span data-stu-id="bc56e-103">To download a copy of this paper, go to [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).</span></span>  
  
 <span data-ttu-id="bc56e-104">**公開:** 2010 年 11 月</span><span class="sxs-lookup"><span data-stu-id="bc56e-104">**Published:** November 2010</span></span>  
  
 <span data-ttu-id="bc56e-105">**作成者:** Valery Mizonov、米国 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bc56e-105">**Author:** Valery Mizonov, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="bc56e-106">**校閲者。**</span><span class="sxs-lookup"><span data-stu-id="bc56e-106">**Reviewed By:**</span></span>  
  
-   <span data-ttu-id="bc56e-107">Mark Simms、米国 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bc56e-107">Mark Simms, Microsoft Corporation</span></span>  
  
-   <span data-ttu-id="bc56e-108">Jayanthi Sampathkumar、米国 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bc56e-108">Jayanthi Sampathkumar, Microsoft Corporation</span></span>  
  
-   <span data-ttu-id="bc56e-109">Krish Srinivasan、米国 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bc56e-109">Krish Srinivasan, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="bc56e-110">**適用対象:** Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bc56e-110">**Applies To:** Microsoft BizTalk Server</span></span>  
  
 <span data-ttu-id="bc56e-111">**概要:** BizTalk ソリューションのインストルメント化の従来の方法とは限りませんパフォーマンスの観点から最も効果的です。</span><span class="sxs-lookup"><span data-stu-id="bc56e-111">**Summary:** The traditional ways of instrumenting BizTalk solutions may not always be the most effective from a performance standpoint.</span></span> <span data-ttu-id="bc56e-112">一般的に使用されるインストルメンテーションとトレーシング コンポーネントのデバッグの Win32 Api を活用することは可能性があります、潜在的なボトルネックを紹介し、なるストレス条件下で実行されるマルチ スレッドの BizTalk アプリケーションのパフォーマンスの低下を担当します。</span><span class="sxs-lookup"><span data-stu-id="bc56e-112">The commonly used instrumentation and tracing components leveraging the Win32 Debugging APIs may introduce a potential bottleneck and become responsible for performance degradations in multi-threaded BizTalk applications running under stress.</span></span>  
  
 <span data-ttu-id="bc56e-113">相手側からは、ソース コードのインストルメンテーションは、アプリケーションの動作に可視性のある程度の優れたは提供し、全体的なトラブルシューティングの作業の削減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bc56e-113">From the other side, source code instrumentation delivers a great degree of visibility into the application behavior and helps reduce the overall troubleshooting efforts.</span></span> <span data-ttu-id="bc56e-114">その結果、パフォーマンスの高い BizTalk ソリューションのインストルメント化するための根本的に新しいアプローチが重要になります重要な点を事実上オーバーヘッドなしと影響しない非割り込み型的で多機能かつ詳細な診断情報の収集を有効にするにはアプリケーションのパフォーマンスです。</span><span class="sxs-lookup"><span data-stu-id="bc56e-114">Consequently, a fundamentally new approach to instrumenting high performance BizTalk solutions has become crucially important to enable collecting the rich and detailed diagnostic information in a non-intrusive manner with virtually no overhead and no impact on the application performance.</span></span>  
  
 <span data-ttu-id="bc56e-115">[Windows Server AppFabric の Customer Advisory Team](http://blogs.msdn.com/appfabriccat) BizTalk 開発者が高パフォーマンスのインストルメンテーションとその解決策の強化に役立つ microsoft 検証済みのベスト プラクティスにコミュニティを提供する対象としています多くの Microsoft 製品によって内部的に採用します。</span><span class="sxs-lookup"><span data-stu-id="bc56e-115">The [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) at Microsoft aimed to provide the community with validated best practices to help BizTalk developers enrich their solutions with the high-performance instrumentation internally adopted by many Microsoft products.</span></span> <span data-ttu-id="bc56e-116">これらのベスト プラクティスは、BizTalk 開発者は簡単に接続して独自の実装にも適用する再利用可能なフレームワークの形式で反映されています。</span><span class="sxs-lookup"><span data-stu-id="bc56e-116">These best practices have been reflected in the form of a reusable framework which BizTalk developers can easily plug in and adopt in their own implementations.</span></span>  
  
 <span data-ttu-id="bc56e-117">完全なコピーをダウンロードする[高パフォーマンスの BizTalk ソリューションのベスト プラクティスをインストルメンテーション](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874)、Microsoft ダウンロード センターにします。</span><span class="sxs-lookup"><span data-stu-id="bc56e-117">You can download a complete copy of [Instrumentation Best Practices for High Performance BizTalk Solutions](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) on the Microsoft Download Center.</span></span>