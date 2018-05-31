---
title: 動的ルーティングを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa3a35f-cafa-4524-8b96-f8a333b7ff87
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b668f53ba87a461441b0dbb498ae0677fa5956
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295698"
---
# <a name="using-dynamic-routing"></a><span data-ttu-id="d7a9d-102">動的ルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-102">Using Dynamic Routing</span></span>
<span data-ttu-id="d7a9d-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]組み込みプロセスと、一般的な配布エージェントを使用してメッセージの動的なルーティングをサポートしている ESB ディスパッチャーまたは ESB ディスパッチャーの逆アセンブル パイプライン コンポーネントを使用して、メッセージング レイヤーでのメッセージの動的ルーティングもサポートします。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports dynamic routing of messages using a built-in process and a generic delivery agent; it also supports dynamic routing of messages at the messaging layer using the ESB Dispatcher or ESB Dispatcher Disassemble pipeline components.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d7a9d-104">概要</span><span class="sxs-lookup"><span data-stu-id="d7a9d-104">Overview</span></span>  
 <span data-ttu-id="d7a9d-105">動的解決のメカニズムで[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが到着したときに、またはメッセージが配信される前にすぐにエンドポイントの探索を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-105">The dynamic resolution mechanism in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] enables discovery of endpoints when a message arrives or immediately before a message is delivered.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="d7a9d-106">しくみ</span><span class="sxs-lookup"><span data-stu-id="d7a9d-106">How It Works</span></span>  
 <span data-ttu-id="d7a9d-107">提供される一般的な配布エージェント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルであり、開発と動的ルーティング手法の利用をガイドします。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-107">The generic delivery agent provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is both a sample and a guide to the development and usage of dynamic routing techniques.</span></span> <span data-ttu-id="d7a9d-108">簡単に追加の配信エージェントを作成したり、送信ポートのみで構成される配信エージェント (これは、オーケストレーションを実装していません) を実装できます。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-108">You can easily create additional delivery agents or implement delivery agents consisting of just a send port (which do not implement an orchestration).</span></span> <span data-ttu-id="d7a9d-109">既定では、ESB ディスパッチと ESB ディスパッチ逆アセンブラー パイプライン コンポーネントは、非常に最適化動的ルーティング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-109">By default, the ESB Dispatch and ESB Dispatch Disassembler pipeline components offer a much more optimized dynamic routing capability.</span></span>  
  
 <span data-ttu-id="d7a9d-110">一般的な配布エージェント自体がメッセージをサブスクライブするオーケストレーションを実装する場所、**名前**、現在の属性**ServiceInstance**旅行計画内の要素は**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-110">The generic delivery agent itself implements an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Routing**.</span></span> <span data-ttu-id="d7a9d-111">エージェントでは、次の操作手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-111">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="d7a9d-112">型指定されていないメッセージ (system.xml.xmldocument など) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-112">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="d7a9d-113">N 個の競合回避モジュールのマネージャーを使用してエンドポイントを解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-113">It attempts to resolve n number of endpoints using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="d7a9d-114">アダプター マネージャーを使用してメッセージのコンテキストと論理の動的なポートのエンドポイント プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-114">It uses the adapter manager to set the endpoint properties of the message context and the logical dynamic port.</span></span>  
  
4.  <span data-ttu-id="d7a9d-115">さらにメッセージのルーティング用の動的送信ポートの BizTalk Server サブスクリプションをトリガーする、直接バインドの送信ポートでメッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-115">It publishes the message through the direct-bound send port, which triggers the BizTalk Server subscription on the dynamic send port for further message routing.</span></span>  
  
## <a name="how-to-configure-dynamic-routing"></a><span data-ttu-id="d7a9d-116">動的ルーティングを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d7a9d-116">How to Configure Dynamic Routing</span></span>  
 <span data-ttu-id="d7a9d-117">行程デザイナーを使用して動的ルーティングを構成する方法の詳細については、「行程のデザイナーを使用して日程を作成するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-117">For more information about how to configure dynamic routing using the Itinerary Designer, see Creating Itineraries Using Itinerary Designer.</span></span>  
  
## <a name="dynamic-routing-errors"></a><span data-ttu-id="d7a9d-118">動的ルーティング エラー</span><span class="sxs-lookup"><span data-stu-id="d7a9d-118">Dynamic Routing Errors</span></span>  
 <span data-ttu-id="d7a9d-119">動的ルーティング メカニズムを作成し、発行、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の場合、エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-119">The dynamic routing mechanism will create and publish an [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="d7a9d-120">配信エージェントは、・ イン タイム (JIT) の解決時にエンドポイントを決定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-120">The delivery agent cannot determine the endpoint during just-in-time (JIT) resolution.</span></span>  
  
-   <span data-ttu-id="d7a9d-121">配信エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-121">A delivery failure occurs.</span></span>  
  
-   <span data-ttu-id="d7a9d-122">出力メッセージのサブスクライバーが存在しません。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-122">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="d7a9d-123">すべてのシステム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="d7a9d-123">Any system exception occurs.</span></span>