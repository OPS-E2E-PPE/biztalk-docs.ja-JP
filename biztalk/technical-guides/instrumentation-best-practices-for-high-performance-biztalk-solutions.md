---
title: 高パフォーマンスの BizTalk ソリューションのインストルメンテーションのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60faad9e9e2905da963ee911dc9d7f13a39d2c67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997467"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a><span data-ttu-id="0576d-102">高パフォーマンスの BizTalk ソリューションのインストルメンテーションのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="0576d-102">Instrumentation Best Practices for High Performance BizTalk Solutions</span></span>
<span data-ttu-id="0576d-103">このホワイト ペーパーのコピーをダウンロードするには[ http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874)します。</span><span class="sxs-lookup"><span data-stu-id="0576d-103">To download a copy of this paper, go to [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).</span></span>  
  
 <span data-ttu-id="0576d-104">**公開日:** 2010 年 11 月</span><span class="sxs-lookup"><span data-stu-id="0576d-104">**Published:** November 2010</span></span>  
  
 <span data-ttu-id="0576d-105">**作成者:** Valery Mizonov、Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0576d-105">**Author:** Valery Mizonov, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="0576d-106">**校閲者。**</span><span class="sxs-lookup"><span data-stu-id="0576d-106">**Reviewed By:**</span></span>  
  
- <span data-ttu-id="0576d-107">Mark Simms、Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0576d-107">Mark Simms, Microsoft Corporation</span></span>  
  
- <span data-ttu-id="0576d-108">Jayanthi Sampathkumar、Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0576d-108">Jayanthi Sampathkumar, Microsoft Corporation</span></span>  
  
- <span data-ttu-id="0576d-109">Krish Srinivasan、Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0576d-109">Krish Srinivasan, Microsoft Corporation</span></span>  
  
  <span data-ttu-id="0576d-110">**適用対象:** Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0576d-110">**Applies To:** Microsoft BizTalk Server</span></span>  
  
  <span data-ttu-id="0576d-111">**概要:** BizTalk ソリューションのインストルメント化する従来の方法とは限りませんパフォーマンスの観点から最も効果的です。</span><span class="sxs-lookup"><span data-stu-id="0576d-111">**Summary:** The traditional ways of instrumenting BizTalk solutions may not always be the most effective from a performance standpoint.</span></span> <span data-ttu-id="0576d-112">一般的に使用されるインストルメンテーションとトレーシング コンポーネントのデバッグの Win32 Api を活用することは可能性があります、潜在的なボトルネックが生じるし、ストレス条件下で実行されているマルチ スレッドの BizTalk アプリケーションのパフォーマンス低下の責任になります。</span><span class="sxs-lookup"><span data-stu-id="0576d-112">The commonly used instrumentation and tracing components leveraging the Win32 Debugging APIs may introduce a potential bottleneck and become responsible for performance degradations in multi-threaded BizTalk applications running under stress.</span></span>  
  
  <span data-ttu-id="0576d-113">相手側からソース コードのインストルメンテーションは高いアプリケーションの動作を可視化を提供し、全体的なトラブルシューティング作業を軽減します。</span><span class="sxs-lookup"><span data-stu-id="0576d-113">From the other side, source code instrumentation delivers a great degree of visibility into the application behavior and helps reduce the overall troubleshooting efforts.</span></span> <span data-ttu-id="0576d-114">そのため、高パフォーマンスの BizTalk ソリューションのインストルメント化を根本的に新しいアプローチが重要な点が重要になりますほぼオーバーヘッドなしとまったく影響のない非侵入型の方法で多機能かつ詳細な診断情報の収集を有効にするにはアプリケーションのパフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="0576d-114">Consequently, a fundamentally new approach to instrumenting high performance BizTalk solutions has become crucially important to enable collecting the rich and detailed diagnostic information in a non-intrusive manner with virtually no overhead and no impact on the application performance.</span></span>  
  
  <span data-ttu-id="0576d-115">[Windows Server AppFabric の Customer Advisory Team](http://blogs.msdn.com/appfabriccat) BizTalk 開発者の高パフォーマンスのインストルメンテーションとその解決策の強化に役立つ、検証済みのベスト プラクティスをコミュニティに提供を目的としたマイクロソフト内部的に多くの Microsoft 製品で採用しています。</span><span class="sxs-lookup"><span data-stu-id="0576d-115">The [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) at Microsoft aimed to provide the community with validated best practices to help BizTalk developers enrich their solutions with the high-performance instrumentation internally adopted by many Microsoft products.</span></span> <span data-ttu-id="0576d-116">BizTalk 開発者は簡単にプラグインして、独自の実装で採用する再利用可能なフレームワークのフォームには、これらのベスト プラクティスが反映されています。</span><span class="sxs-lookup"><span data-stu-id="0576d-116">These best practices have been reflected in the form of a reusable framework which BizTalk developers can easily plug in and adopt in their own implementations.</span></span>  
  
  <span data-ttu-id="0576d-117">完全なコピーをダウンロードする[高パフォーマンスの BizTalk ソリューションのインストルメンテーションのベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874) Microsoft ダウンロード センター。</span><span class="sxs-lookup"><span data-stu-id="0576d-117">You can download a complete copy of [Instrumentation Best Practices for High Performance BizTalk Solutions](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) on the Microsoft Download Center.</span></span>