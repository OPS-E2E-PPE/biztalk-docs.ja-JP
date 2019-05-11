---
title: 動的ルーティングを使用して |Microsoft Docs
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
ms.openlocfilehash: e30d13458e9c020f66984f42d3a472364bc8b425
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396458"
---
# <a name="using-dynamic-routing"></a><span data-ttu-id="e5524-102">動的ルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5524-102">Using Dynamic Routing</span></span>
<span data-ttu-id="e5524-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]組み込みプロセスと、一般的な配布エージェントを使用してメッセージの動的なルーティングをサポートしている ESB ディスパッチャーまたは ESB ディスパッチャー逆アセンブル パイプライン コンポーネントを使用して、メッセージング層でのメッセージの動的ルーティングもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e5524-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports dynamic routing of messages using a built-in process and a generic delivery agent; it also supports dynamic routing of messages at the messaging layer using the ESB Dispatcher or ESB Dispatcher Disassemble pipeline components.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="e5524-104">概要</span><span class="sxs-lookup"><span data-stu-id="e5524-104">Overview</span></span>  
 <span data-ttu-id="e5524-105">動的解決メカニズムは[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが届いたとき、またはメッセージが配信される前にすぐにエンドポイントの探索を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5524-105">The dynamic resolution mechanism in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] enables discovery of endpoints when a message arrives or immediately before a message is delivered.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="e5524-106">しくみ</span><span class="sxs-lookup"><span data-stu-id="e5524-106">How It Works</span></span>  
 <span data-ttu-id="e5524-107">提供される一般的な配布エージェント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルであり、開発と動的ルーティングの手法の使用方法のガイド。</span><span class="sxs-lookup"><span data-stu-id="e5524-107">The generic delivery agent provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is both a sample and a guide to the development and usage of dynamic routing techniques.</span></span> <span data-ttu-id="e5524-108">エージェントの追加の配信を作成したり、(これは、オーケストレーションを実装していません) の送信ポートのみで構成される配信エージェントを実装したりすることができます簡単にします。</span><span class="sxs-lookup"><span data-stu-id="e5524-108">You can easily create additional delivery agents or implement delivery agents consisting of just a send port (which do not implement an orchestration).</span></span> <span data-ttu-id="e5524-109">既定では、ESB のディスパッチと ESB ディスパッチ逆アセンブラー パイプライン コンポーネントは、非常に動的ルーティング機能をより最適化されたを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5524-109">By default, the ESB Dispatch and ESB Dispatch Disassembler pipeline components offer a much more optimized dynamic routing capability.</span></span>  
  
 <span data-ttu-id="e5524-110">汎用的な配信エージェント自体がメッセージをサブスクライブするオーケストレーションを実装する場所、**名前**、現在の属性**ServiceInstance**旅行計画内の要素が**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="e5524-110">The generic delivery agent itself implements an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Routing**.</span></span> <span data-ttu-id="e5524-111">エージェントは、次の一連の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5524-111">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="e5524-112">型指定されていないメッセージ (System.Xml.XmlDocument) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e5524-112">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="e5524-113">N 個の競合回避モジュールのマネージャーを使用してエンドポイントを解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="e5524-113">It attempts to resolve n number of endpoints using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="e5524-114">アダプター マネージャーを使用して、メッセージ コンテキストと論理の動的ポートのエンドポイントのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e5524-114">It uses the adapter manager to set the endpoint properties of the message context and the logical dynamic port.</span></span>  
  
4.  <span data-ttu-id="e5524-115">さらにメッセージのルーティングに動的送信ポートでの BizTalk Server サブスクリプションをトリガーする、直接バインドされた送信ポートでメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="e5524-115">It publishes the message through the direct-bound send port, which triggers the BizTalk Server subscription on the dynamic send port for further message routing.</span></span>  
  
## <a name="how-to-configure-dynamic-routing"></a><span data-ttu-id="e5524-116">動的ルーティングを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e5524-116">How to Configure Dynamic Routing</span></span>  
 <span data-ttu-id="e5524-117">旅行プラン デザイナーを使用して動的ルーティングを構成する方法の詳細については、旅行プランを使用してスケジュールの作成のデザイナーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5524-117">For more information about how to configure dynamic routing using the Itinerary Designer, see Creating Itineraries Using Itinerary Designer.</span></span>  
  
## <a name="dynamic-routing-errors"></a><span data-ttu-id="e5524-118">動的ルーティング エラー</span><span class="sxs-lookup"><span data-stu-id="e5524-118">Dynamic Routing Errors</span></span>  
 <span data-ttu-id="e5524-119">動的ルーティング メカニズムを作成し、発行、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の場合にエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="e5524-119">The dynamic routing mechanism will create and publish an [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="e5524-120">配信エージェントは、ジャストイン タイム (JIT) の解決時にエンドポイントを決定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5524-120">The delivery agent cannot determine the endpoint during just-in-time (JIT) resolution.</span></span>  
  
-   <span data-ttu-id="e5524-121">配信エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e5524-121">A delivery failure occurs.</span></span>  
  
-   <span data-ttu-id="e5524-122">出力メッセージのサブスクライバーが存在しません。</span><span class="sxs-lookup"><span data-stu-id="e5524-122">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="e5524-123">すべてのシステム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="e5524-123">Any system exception occurs.</span></span>