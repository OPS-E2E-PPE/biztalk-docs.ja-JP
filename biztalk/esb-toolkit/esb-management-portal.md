---
title: "管理ポータルの ESB |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b702d03a-2e0a-4c46-a785-c0aeae35a5f0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90f7563ddee7a77291d50fd32054a9aca4f143b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="esb-management-portal"></a><span data-ttu-id="a2d49-102">ESB 管理ポータル</span><span class="sxs-lookup"><span data-stu-id="a2d49-102">ESB Management Portal</span></span>
<span data-ttu-id="a2d49-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括的な Web ベースの例外とエラー メッセージ管理フレームワーク システムおよび business の両方の例外の一貫した処理を推進するが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2d49-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes a comprehensive Web-based exception and fault message management framework that promotes consistent handling of both system and business exceptions.</span></span> <span data-ttu-id="a2d49-104">含まれる、ポータルは、ポータル アプリケーションがメトリックと ESB アクティビティから表示を提供する方法のサンプルとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a2d49-104">The included portal serves as a sample of how a portal application can provide metrics and visibility into ESB activities.</span></span>  
  
 <span data-ttu-id="a2d49-105">ESB 管理ポータルでは、監査および追跡のメカニズムにより例外仲介機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a2d49-105">The ESB Management Portal provides exception mediation capabilities through an auditing and tracking mechanism.</span></span> <span data-ttu-id="a2d49-106">(コンテキスト プロパティを含む)、例外が発生した時に"インフライト"であったメッセージもキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a2d49-106">It also captures messages (including the context properties) that were "in flight" at the time that the exception occurred.</span></span> <span data-ttu-id="a2d49-107">これにより、高度な例外の回復、および「修復し、再実行してください」のパターン。</span><span class="sxs-lookup"><span data-stu-id="a2d49-107">This enables powerful exception recovery and "repair and resubmit" patterns.</span></span>  
  
 <span data-ttu-id="a2d49-108">ポータルを ESB アプリケーションを簡単に管理するには、管理者とユーザーを許可するのには、カスタム条件に基づいて警告を生成およびサブスクライバーに通知を送信できるアラートと通知メカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="a2d49-108">To allow administrators and users to easily manage ESB applications, the portal also provides an alert and notification mechanism that can generate alerts based on custom conditions and send notifications to subscribers.</span></span>  
  
 <span data-ttu-id="a2d49-109">アプリケーションのパフォーマンスを監視し、フォールトの傾向を分析、ポータルできます生成しのグラフとレポート、時間の指定した期間にわたって構成可能な範囲を表示および指定した BizTalk アプリケーションからのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2d49-109">To monitor application performance and analyze fault trends, the portal can generate and display a range of charts and reports, configurable over specified periods of time, and include data from specified BizTalk applications.</span></span>  
  
 <span data-ttu-id="a2d49-110">さらに、ポータルは自動的にまたは管理者が制御承認プロセスのいずれかは、UDDI を BizTalk のエンドポイントを公開するためのグラフィカル ユーザー インターフェイスを提供する Microsoft UDDI 3.0 サーバーと統合できます。</span><span class="sxs-lookup"><span data-stu-id="a2d49-110">Additionally, the portal integrates with a Microsoft UDDI 3.0 server to provide a graphical user interface for publishing BizTalk endpoints to UDDI, either automatically or through an administrator-controlled approval process.</span></span>  
  
 <span data-ttu-id="a2d49-111">ESB の管理ポータルの詳細については、次を参照してください。[例外管理フレームワークのコンポーネント](../esb-toolkit/the-components-of-the-exception-management-framework.md)です。</span><span class="sxs-lookup"><span data-stu-id="a2d49-111">For more information about the ESB Management Portal, see [The Components of the Exception Management Framework](../esb-toolkit/the-components-of-the-exception-management-framework.md).</span></span>