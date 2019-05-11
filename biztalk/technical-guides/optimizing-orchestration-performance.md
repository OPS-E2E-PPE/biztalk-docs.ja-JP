---
title: オーケストレーション パフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 688aae3d543d93941bb356c0d6d207eb1d4be851
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291411"
---
# <a name="optimizing-orchestration-performance"></a><span data-ttu-id="9bd71-102">オーケストレーション パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="9bd71-102">Optimizing Orchestration Performance</span></span>
<span data-ttu-id="9bd71-103">このトピックでは、オーケストレーションを BizTalk Server ソリューションで使用するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-103">This topic describes best practices for using orchestrations in BizTalk Server solutions.</span></span> <span data-ttu-id="9bd71-104">これには、推奨事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-104">This includes recommendations for:</span></span>  
  
-   <span data-ttu-id="9bd71-105">オーケストレーションを使用して BizTalk Server ソリューションの遅延時間の短縮</span><span class="sxs-lookup"><span data-stu-id="9bd71-105">Reducing latency of BizTalk Server solutions that use orchestrations</span></span>  
  
    -   <span data-ttu-id="9bd71-106">メッセージングのみのパターンのオーケストレーションを排除</span><span class="sxs-lookup"><span data-stu-id="9bd71-106">Eliminating orchestrations for messaging only patterns</span></span>  
  
    -   <span data-ttu-id="9bd71-107">オーケストレーションから送信インラインを利用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-107">Utilizing inline sends from orchestrations</span></span>  
  
    -   <span data-ttu-id="9bd71-108">オーケストレーションの永続化ポイントを最小限に抑える</span><span class="sxs-lookup"><span data-stu-id="9bd71-108">Minimizing orchestration persistence points</span></span>  
  
-   <span data-ttu-id="9bd71-109">オーケストレーションを入れ子</span><span class="sxs-lookup"><span data-stu-id="9bd71-109">Nesting orchestrations</span></span>  
  
-   <span data-ttu-id="9bd71-110">オーケストレーションのデザイン パターン</span><span class="sxs-lookup"><span data-stu-id="9bd71-110">Orchestration design patterns</span></span>  
  
-   <span data-ttu-id="9bd71-111">オーケストレーションの例外処理ブロック</span><span class="sxs-lookup"><span data-stu-id="9bd71-111">Orchestration exception handling blocks</span></span>  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a><span data-ttu-id="9bd71-112">低待機時間シナリオのオーケストレーションを最適化するための推奨事項</span><span class="sxs-lookup"><span data-stu-id="9bd71-112">Recommendations for optimizing orchestrations for low latency scenarios</span></span>  
 <span data-ttu-id="9bd71-113">オーケストレーションを使用して BizTalk Server ソリューションの待機時間を短縮する、次の手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-113">The following techniques can be used to reduce latency of BizTalk Server solutions that use orchestrations.</span></span>  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a><span data-ttu-id="9bd71-114">メッセージングのみのパターンのオーケストレーションを排除します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-114">Eliminate orchestrations for messaging only patterns</span></span>  
 <span data-ttu-id="9bd71-115">可能な場合は、全体的なスループットが向上し、ビジネス プロセスの待機時間を短縮するためのオーケストレーションの使用を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-115">When possible minimize the use of orchestrations to increase overall throughput and reduce the latency of business processes.</span></span> <span data-ttu-id="9bd71-116">長時間実行する必要が実行されていないトランザクションと、要求ごとに複数のシステムを起動する必要はありませんが、検討してくださいオーケストレーションを排除し、ビジネス ロジックをへのラウンドト リップの合計量を削減するには、受信と送信ポートに移動しますBizTalkMsgBoxDb とデータベースへのアクセスのための待機時間が減少します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-116">If there is no need to run long running transactions and there is no need to invoke several systems for each request, then consider eliminating orchestrations and moving business logic to Receive and Send Ports to reduce the total amount of roundtrips to the BizTalkMsgBoxDb and decrease the latency due to database access.</span></span> <span data-ttu-id="9bd71-117">この場合は、カスタム パイプラインを実装し、オーケストレーションから呼び出された以前ヘルパー クラスを再利用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-117">In this case, implement custom pipelines and reuse helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="9bd71-118">散布図や収集や、コンボイのデザイン パターンを実装するには、厳密に必要な場合にのみ、オーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-118">Use orchestrations only when strictly needed to implement design patterns as Scatter and Gather or Convoys.</span></span> <span data-ttu-id="9bd71-119">オーケストレーションのデザイン パターンの詳細については、トピックを参照してください。[オーケストレーションのデザイン パターンを実装する](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) 、BizTalk Server のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-119">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation.</span></span>  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a><span data-ttu-id="9bd71-120">低待機時間シナリオに対応するために使用してインラインはオーケストレーションから送信します</span><span class="sxs-lookup"><span data-stu-id="9bd71-120">Use inline sends from orchestrations to accommodate low latency scenarios</span></span>  
 <span data-ttu-id="9bd71-121">可能であれば、オーケストレーションの使用を最小限に抑えるし、全体的なスループットを向上させる、ビジネス プロセスの待機時間を短縮してメッセージングのみのパターンを優先します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-121">Whenever possible, minimize the use of orchestrations and favor messaging-only patterns to increase the overall throughput and reduce the latency of the business processes.</span></span> <span data-ttu-id="9bd71-122">実行時間の長いトランザクションの必要性がなく、ビジネス ロジックをいくつかのシステムを呼び出す必要はない場合、は、受信し、送信ポートにビジネス ロジックを移動して、オーケストレーションの使用を排除することを検討しています。</span><span class="sxs-lookup"><span data-stu-id="9bd71-122">If there is no need for long-running transactions and there is no need for business logic to invoke several systems, then consider moving business logic to receive and send Ports and eliminating the use of orchestrations.</span></span> <span data-ttu-id="9bd71-123">カスタム パイプラインでこのアプローチを実装することができ、オーケストレーションから呼び出された以前ヘルパー クラスを再利用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-123">This approach can be implemented with custom pipelines and which reuse the helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="9bd71-124">低待機時間シナリオでパフォーマンスの向上を実現するために、次の方法のいずれかを採用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-124">In order to achieve better performance in low latency scenarios, adopt one of the following approaches:</span></span>  
  
-   <span data-ttu-id="9bd71-125">不要なオーケストレーションを排除し、BizTalk メッセージ ボックス データベースへのラウンド トリップの合計量を削減するメッセージングのみのパターンを採用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-125">Eliminate unnecessary orchestrations and adopt messaging-only patterns to reduce the total amount of roundtrips to the BizTalk MessageBox database.</span></span> <span data-ttu-id="9bd71-126">このアプローチはインライン送信のバイパス、BizTalk メッセージング エンジンと関連付けられているため、低待機時間に対応のオーバーヘッド。</span><span class="sxs-lookup"><span data-stu-id="9bd71-126">This approach accommodates low latency because inline sends bypass the BizTalk messaging engine and the associated overhead.</span></span> <span data-ttu-id="9bd71-127">BizTalk Server 2006 以降のバージョンと、オーケストレーション インライン送信機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-127">Orchestration inline send functionality is provided with BizTalk Server 2006 and later.</span></span>  
  
-   <span data-ttu-id="9bd71-128">内側のオーケストレーションは、物理ポートにバインドされた論理ポートを排除し、代わりに使用して行を送信します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-128">Inside orchestrations, eliminate logical ports bound to physical ports and use in-line sends in their place.</span></span> <span data-ttu-id="9bd71-129">たとえば、インライン送信は、ダウン ストリーム Web サービスまたは SQL Server データベースへのアクセスに ADO.NET コンポーネントを呼び出す、WCF プロキシ クラスのインスタンスを作成する管理される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-129">For example, an inline send could be used to create an instance of a  WCF proxy class to invoke a downstream Web service or an ADO.NET component to access a SQL Server database.</span></span> <span data-ttu-id="9bd71-130">オーケストレーションが内部的には、WCF の使用して、業務のコンポーネントをインスタンス化するときに実行する、インライン送信では、次の図では、ダウン ストリーム Web サービスの直接呼び出しオブジェクトをプロキシします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-130">In the following diagram, an inline send is performed when the orchestration instantiates a business component, which internally makes use of a WCF  proxy object to directly invoke a downstream Web service:</span></span>  
  
     <span data-ttu-id="9bd71-131">![BizTalk オーケストレーション インライン送信の説明図](../technical-guides/media/inlinesend.gif "InlineSend")</span><span class="sxs-lookup"><span data-stu-id="9bd71-131">![Depiction of BizTalk Orchestration Inline Send](../technical-guides/media/inlinesend.gif "InlineSend")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bd71-132">オーケストレーション インライン送信を使用すると、待機時間が大幅に少なくは、この方法に制限があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-132">Although using inline sends from orchestrations will significantly reduce latency, there are limitations to this approach.</span></span> <span data-ttu-id="9bd71-133">インラインの送信は、BizTalk メッセージング エンジンをバイパスするため、次に、メッセージング エンジンによって提供される機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9bd71-133">Because inline sends bypass the BizTalk messaging engine, the following functionality provided with the messaging engine is not available:</span></span>  
> 
> - <span data-ttu-id="9bd71-134">トランザクション パイプライン</span><span class="sxs-lookup"><span data-stu-id="9bd71-134">Transactional pipelines</span></span>  
>   -   <span data-ttu-id="9bd71-135">回復可能パイプライン。</span><span class="sxs-lookup"><span data-stu-id="9bd71-135">Recoverable pipelines</span></span>  
>   -   <span data-ttu-id="9bd71-136">BAM インターセプター API を呼び出すパイプライン</span><span class="sxs-lookup"><span data-stu-id="9bd71-136">Pipelines that call the BAM interceptor API</span></span>  
>   -   <span data-ttu-id="9bd71-137">BizTalk Server アダプターのサポート</span><span class="sxs-lookup"><span data-stu-id="9bd71-137">BizTalk Server adapter support</span></span>  
>   -   <span data-ttu-id="9bd71-138">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="9bd71-138">Batching</span></span>  
>   -   <span data-ttu-id="9bd71-139">[再試行の回数]</span><span class="sxs-lookup"><span data-stu-id="9bd71-139">Retries</span></span>  
>   -   <span data-ttu-id="9bd71-140">関連付けセットの初期化</span><span class="sxs-lookup"><span data-stu-id="9bd71-140">Correlation set initialization</span></span>  
>   -   <span data-ttu-id="9bd71-141">宣言型の構成</span><span class="sxs-lookup"><span data-stu-id="9bd71-141">Declarative configuration</span></span>  
>   -   <span data-ttu-id="9bd71-142">セカンダリ トランスポート</span><span class="sxs-lookup"><span data-stu-id="9bd71-142">Secondary transports</span></span>  
>   -   <span data-ttu-id="9bd71-143">Tracking</span><span class="sxs-lookup"><span data-stu-id="9bd71-143">Tracking</span></span>  
>   -   <span data-ttu-id="9bd71-144">BAM の宣言型の使用</span><span class="sxs-lookup"><span data-stu-id="9bd71-144">Declarative use of BAM</span></span>  
  
 <span data-ttu-id="9bd71-145">オーケストレーション内から実行することはできませんのパイプラインの種類の詳細については、トピックの「制限事項」セクションを参照してください[パイプラインの実行に式を使用する方法](http://go.microsoft.com/fwlink/?LinkId=158008)(http://go.microsoft.com/fwlink/?LinkId=158008) BizTalk server。2010 のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="9bd71-145">For more information about the types of pipelines that cannot be executed from within an orchestration, see the “Restrictions” section of the topic [How to Use Expressions to Execute Pipelines](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.microsoft.com/fwlink/?LinkId=158008) in the BizTalk Server 2010 documentation.</span></span>  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a><span data-ttu-id="9bd71-146">可能であれば、永続化ポイントの数を減らすことで、オーケストレーションの待機時間を最適化します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-146">Optimize orchestration latency by reducing the number of persistence points, if possible</span></span>  
 <span data-ttu-id="9bd71-147">のみ、オーケストレーションの範囲としてマークする必要がある"実行時間の長いトランザクション"補正またはスコープのタイムアウトを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="9bd71-147">An orchestration scope only needs to be marked as “long-running transactional” if you want to use compensation or scope timeouts.</span></span> <span data-ttu-id="9bd71-148">実行時間の長いトランザクションのスコープは補正またはスコープのタイムアウトを使用する必要がないときに、避ける必要がありますので、スコープの最後に、余分な永続化ポイントをによりします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-148">A long-running transactional scope causes an extra persistence point at the end of the scope, so they should be avoided when you don’t need to use compensation or scope timeouts.</span></span> <span data-ttu-id="9bd71-149">アトミックのスコープは、スコープの最後の永続化ポイントもアトミックのスコープで永続化ポイントが発生しないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-149">An atomic scope causes a persistence point at the end of the scope, but also guarantees that no persistence points will occur inside the atomic scope.</span></span> <span data-ttu-id="9bd71-150">(複数の実行を送信するときなど)、バッチの永続化ポイントする方が得策ない永続化、スコープ内でのこの副作用を使用こともありますできます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-150">This side-effect of no persistence inside the scope can sometimes be used to your advantage to batch persistence points (when doing multiple sends, for example).</span></span> <span data-ttu-id="9bd71-151">一般に、ただし、できるだけアトミックのスコープ可能な場合。</span><span class="sxs-lookup"><span data-stu-id="9bd71-151">In general, though, we recommend avoiding atomic scopes if possible.</span></span> <span data-ttu-id="9bd71-152">オーケストレーション エンジンは、永続的ストレージに全体の状態を保存さまざまなポイントで実行中のオーケストレーション インスタンス、インスタンスは後でメモリ内で復元および完了するために実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-152">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be restored in memory and carried out to completion.</span></span>   
<span data-ttu-id="9bd71-153">**オーケストレーションの永続化ポイントの数は、オーケストレーションを通過するメッセージの待機時間に影響を与える主な要因の 1 つ**します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-153">**The number of persistence points in an orchestration is one of the key factors influencing the latency of messages flowing through orchestrations**.</span></span> <span data-ttu-id="9bd71-154">エンジンは、永続化ポイントをヒットするたびに実行中のオーケストレーションの内部状態をシリアル化され、メッセージ ボックス データベースに保存し、この操作が待機時間のコストが発生します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-154">Each time the engine hits a persistence point, the internal state of a running orchestration is serialized and saved to the MessageBox and this operation incurs a latency cost.</span></span> <span data-ttu-id="9bd71-155">内部の状態のシリアル化には、すべてのメッセージおよびインスタンス化され、オーケストレーションで公開されていない変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9bd71-155">The serialization of the internal state includes all messages and variables instantiated and not yet released in the orchestration.</span></span> <span data-ttu-id="9bd71-156">大きいほど、メッセージおよび変数とそれらの数が大きいほど、長くかかりますオーケストレーションの内部状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-156">The larger the messages and variables and the greater the number of these, the longer it will take to persist the internal state of an orchestration.</span></span> <span data-ttu-id="9bd71-157">永続化ポイントの数が多すぎるは、パフォーマンスが著しく低下につながります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-157">An excessive number of persistence points can lead to significant performance degradation.</span></span> <span data-ttu-id="9bd71-158">このためはトランザクション スコープの数を減らすことで、オーケストレーションからの不要な永続化ポイントを排除することをお勧めし、送信図形。</span><span class="sxs-lookup"><span data-stu-id="9bd71-158">For this reason, we recommend eliminating unnecessary persistence points from orchestrations by reducing the number of transactional scopes and Send shapes.</span></span> <span data-ttu-id="9bd71-159">これにより、全体的なスケーラビリティを向上させると、オーケストレーションの遅延時間の短縮により、オーケストレーションの退避と復元、MessageBox に競合が少なくできます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-159">This approach allows decreasing the contention on the MessageBox due to orchestration dehydration and rehydration, increasing the overall scalability, and reducing orchestration latency.</span></span>   
<span data-ttu-id="9bd71-160">別の推奨事項では、常にオーケストレーションの内部状態をできるだけ小さくしてください。</span><span class="sxs-lookup"><span data-stu-id="9bd71-160">Another recommendation is to always keep the internal state of an orchestration as small as possible.</span></span> <span data-ttu-id="9bd71-161">この手法では、シリアル化、永続化および永続化ポイントが発生した場合、オーケストレーションの内部状態の復元は、XLANG エンジンで費やされた時間を大幅に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-161">This technique can significantly reduce the time spent by the XLANG Engine serializing, persisting and restoring the internal state of an orchestration in case of persistence point.</span></span> <span data-ttu-id="9bd71-162">これを実現する方法の 1 つは、できるだけ変数と、遅延メッセージを作成し、できるだけ早くリリースとして可能ですたとえば、オーケストレーション内で非トランザクションのスコープを紹介し、変数とそれらを最上位レベルで宣言する代わりにこれらの内部スコープ内のメッセージを宣言します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-162">One way to achieve this is to create variables and messages as late as possible and release them as early as possible; for example introduce non transactional scopes inside your orchestrations and declare variables and messages within these inner scopes instead of declaring them at the top-most level.</span></span> <span data-ttu-id="9bd71-163">オーケストレーションの永続化ポイントを最小限に抑えることの詳細については、BizTalk Server 2010 のドキュメントでは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd71-163">For more information about minimizing orchestration persistence points, see the following topics in the BizTalk Server  2010 documentation:</span></span>  
  
-   <span data-ttu-id="9bd71-164">[永続性とオーケストレーション エンジン](http://go.microsoft.com/fwlink/?LinkID=155292)(http://go.microsoft.com/fwlink/?LinkID=155292)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-164">[Persistence and the Orchestration Engine](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
-   <span data-ttu-id="9bd71-165">[オーケストレーションの退避と復元](http://go.microsoft.com/fwlink/?LinkID=155284)(http://go.microsoft.com/fwlink/?LinkID=155292)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-165">[Orchestration Dehydration and Rehydration](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a><span data-ttu-id="9bd71-166">使用するためのガイドラインは、オーケストレーションからメッセージのタグをアクセスまたは属性のプロパティを昇格</span><span class="sxs-lookup"><span data-stu-id="9bd71-166">Guidelines for using promoted properties to access message tags or attributes from an orchestration</span></span>  
 <span data-ttu-id="9bd71-167">プロパティを昇格する場合は、メッセージのルーティング、フィルター、およびメッセージの関連付けに使用されるプロパティのみを昇格します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-167">If you do need to promote properties, promote only those properties that are used for message routing, filters, and message correlation.</span></span> <span data-ttu-id="9bd71-168">各プロパティの昇格では、逆アセンブラー コンポーネント (XML、フラットなカスタム) をドキュメントの種類を認識し、ドキュメントの種類を定義する XSD に含まれる相対注釈からの XPath 式を使用して、メッセージからデータを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-168">The promotion of each property requires the disassembler component (XML, Flat, custom) to recognize the document type and to retrieve data from the message using the XPath expression from the relative annotation contained in the XSD that defines the document type.</span></span> <span data-ttu-id="9bd71-169">さらに、各プロパティの昇格では、メッセージ エージェントは、メッセージ ボックス データベースにメッセージを公開する場合、bts_InsertProperty ストアド プロシージャの別個の呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-169">In addition, each property promotion causes a separate call of the bts_InsertProperty stored procedure when the Message Agent publishes the message to the MessageBox database.</span></span> <span data-ttu-id="9bd71-170">オーケストレーションは、特定の要素または属性に含まれる XML ドキュメントにアクセスする必要がある場合、は、次の手法の 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-170">If an orchestration needs to access a particular element or attribute contained by an XML document, use one of the following techniques:</span></span>  
  
- <span data-ttu-id="9bd71-171">書き込みや昇格させたプロパティの数を削減し、厳密には必要ないものを排除します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-171">Reduce the number of written and promoted properties and eliminate those that are not strictly necessary.</span></span>  
  
- <span data-ttu-id="9bd71-172">不要な識別フィールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-172">Eliminate unnecessary distinguished fields.</span></span> <span data-ttu-id="9bd71-173">識別フィールドには、コンテキスト プロパティが書き込まれ、その名前がデータを取得するために使用される XPath 式と同じように簡単に重要な領域を占めることができます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-173">The distinguished fields are written context properties and they can easily occupy significant space as their name is equal to the XPath expression that is used to retrieve data.</span></span> <span data-ttu-id="9bd71-174">識別プロパティは、ドキュメント型を定義する XSD の注釈として定義されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-174">The distinguished property is defined as annotations in the XSD that defines the document type.</span></span> <span data-ttu-id="9bd71-175">逆アセンブラー コンポーネントでは、昇格させたプロパティを採用して同じアプローチを使用し、受信ドキュメント内で検索する識別フィールドを定義する XPath 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-175">The disassembler component uses the same approach adopted for promoted properties and uses the XPath expression that defines a distinguished field to find it within in the incoming document.</span></span> <span data-ttu-id="9bd71-176">次に、逆アセンブラー コンポーネントは、コンテキストのプロパティを書き込みます場所。</span><span class="sxs-lookup"><span data-stu-id="9bd71-176">Then, the disassembler component writes a property in the context where:</span></span>  
  
  - <span data-ttu-id="9bd71-177">**[名前]**:注釈で定義された XPath 式。</span><span class="sxs-lookup"><span data-stu-id="9bd71-177">**Name**: XPath Expression defined in the annotation.</span></span>  
  
  - <span data-ttu-id="9bd71-178">**値**:受信ドキュメント内で XPath 式で識別される要素の値。</span><span class="sxs-lookup"><span data-stu-id="9bd71-178">**Value**: Value of the element identified by the XPath expression within an incoming document.</span></span>  
  
    <span data-ttu-id="9bd71-179">XPath 式は、対象の要素がドキュメント スキーマで非常に深い場合に特に非常に長いです。</span><span class="sxs-lookup"><span data-stu-id="9bd71-179">The XPath Expressions can be very long, especially when the element in question is very deep in the document schema.</span></span> <span data-ttu-id="9bd71-180">これをより識別フィールドより大きなコンテキストのサイズ。</span><span class="sxs-lookup"><span data-stu-id="9bd71-180">So, the more distinguished fields, the larger the context size.</span></span> <span data-ttu-id="9bd71-181">これにより、全体的なパフォーマンスがさらに悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-181">This in turn adversely affects the overall performance.</span></span>  
  
- <span data-ttu-id="9bd71-182">オーケストレーション ランタイムによって提供される XPath 組み込み関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-182">Use the XPath built-in function provided by the orchestration runtime.</span></span>  
  
- <span data-ttu-id="9bd71-183">メッセージが非常に小さい場合 (数キロバイト) と XML 形式の .NET クラスのインスタンスにメッセージを逆シリアル化してパブリック フィールドとプロパティを操作します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-183">If messages are quite small (a few kilobytes) and XML-formatted, you can de-serialize the message into a .NET class instance and work with public fields and properties.</span></span> <span data-ttu-id="9bd71-184">メッセージには、複雑な詰める (カスタム コード、ビジネス ルール エンジン ポリシーなど) が必要がある場合ははるかに高速 XPath 式を使用して、.NET クラスのインスタンスによって公開されるプロパティを使用してデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-184">If the message needs a complex elaboration (custom code, Business Rule Engine policies, etc.) accessing data using the properties exposed by an instance of a .NET class is much faster using XPath expressions.</span></span> <span data-ttu-id="9bd71-185">オーケストレーションによって呼び出されるビジネス ロジックが完了したら、エンティティ オブジェクトは BizTalk メッセージにシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-185">When the business logic invoked by the orchestration has completed, the entity object can be serialized back into a BizTalk message.</span></span> <span data-ttu-id="9bd71-186">次のツールのいずれかを使用して XML スキーマから .NET クラスを作成できます。XSD ツール (.NET Framework 2.0) または SVCUTIL (.NET Framework 3.0)。</span><span class="sxs-lookup"><span data-stu-id="9bd71-186">You can create .NET classes from an XML schema using one of the following tools: XSD tool (.NET Framework 2.0) or SVCUTIL (.NET Framework 3.0).</span></span>  
  
- <span data-ttu-id="9bd71-187">オーケストレーションからヘルパー コンポーネントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-187">Enable a helper component from an orchestration.</span></span> <span data-ttu-id="9bd71-188">この手法では、識別フィールドを使用する利点があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-188">This technique has an advantage over using distinguished fields.</span></span> <span data-ttu-id="9bd71-189">XPath のため、XPath 式を変更するときは変更する必要はありません (構成ファイル、SSO 構成ストア、カスタム Db、およびなど) を構成から式が格納および再デプロイすると、スキーマが昇格させたプロパティや d を行う必要があります、オーケストレーションが実際には、読み取ることができます。istinguished フィールドです。</span><span class="sxs-lookup"><span data-stu-id="9bd71-189">In fact, an orchestration may read the XPath expression from a config store (config file, SSO Config Store, custom Db, and so on) so, when you have to change the XPath expression, you do not have to change and redeploy a schema, as you should do for promoted properties and distinguished fields.</span></span> <span data-ttu-id="9bd71-190">次のコード サンプルでは、ヘルパー コンポーネントの例を示します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-190">The following code sample provides an example of a helper component.</span></span> <span data-ttu-id="9bd71-191">コンポーネントは、BizTalk ランタイムによって提供される XPathReader クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-191">The component uses the XPathReader class that is provided by the BizTalk runtime.</span></span> <span data-ttu-id="9bd71-192">これにより、XPath 式が見つかるまで、ドキュメント ストリームを読み取るコード。</span><span class="sxs-lookup"><span data-stu-id="9bd71-192">This allows the code to read through the document stream until the XPath expression is found.</span></span>  
  
```  
#region Copyright  
//===  
//Microsoft Windows Server AppFabric Customer Advisory Team (CAT)   
//  
// This sample is supplemental to the technical guidance published on the community  
// blog.  
//   
// Author: Paolo Salvatori.  
//===  
// Copyright © 2010 Microsoft Corporation. All rights reserved.  
//   
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER   
// EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF   
// MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. YOU BEAR THE RISK OF USING IT.  
//===  
#endregion  
#region Using Directives  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Xml;  
using System.Linq;  
using System.Text;  
using System.Globalization;  
using Microsoft.XLANGs.BaseTypes;   
using Microsoft.BizTalk.Streaming;  
using Microsoft.BizTalk.XPath;  
#endregion  
namespace Microsoft.AppFabric.CAT.Samples.DuplexMEP.Helpers  
{  
public class XPathHelper  
{  
#region Private Constants   
private const string MessageCannotBeNull = "[XPathReader] The message cannot be null.";  
#endregion  
#region Public Static Methods  
public static string GetValue(XLANGMessage message, int partIndex, string xpath)  
{  
try  
{  
if (message == null)  
{  
throw new ApplicationException(MessageCannotBeNull);  
}  
using (Stream stream = message[partIndex].RetrieveAs(typeof(Stream)) as Stream)  
{  
XmlTextReader xmlTextReader = new XmlTextReader(stream);  
XPathCollection xPathCollection = new XPathCollection();  
XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
xPathCollection.Add(xpath);  
while (xPathReader.Read())  
{  
if (xPathReader.HasAttributes)  
{  
for (int i = 0; i < xPathReader.AttributeCount; i++)  
{  
xPathReader.MoveToAttribute(i);  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.GetAttribute(i);  
}  
}  
}  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.ReadString();  
}  
}  
}  
}  
finally  
{  
message.Dispose();  
}  
return string.Empty;  
}  
#endregion  
}  
}  
```  
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a><span data-ttu-id="9bd71-193">パフォーマンスを向上させるためにオーケストレーションの複雑さを最小限に抑える</span><span class="sxs-lookup"><span data-stu-id="9bd71-193">Minimize orchestration complexity to improve performance</span></span>  
 <span data-ttu-id="9bd71-194">オーケストレーションの複雑さは、パフォーマンスに大きな影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-194">The complexity of orchestrations has a significant impact on performance.</span></span> <span data-ttu-id="9bd71-195">オーケストレーションの複雑さの増大に合わせて、全体的なパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-195">As orchestration complexity increases, overall performance decreases.</span></span> <span data-ttu-id="9bd71-196">オーケストレーションは、ほぼ無限さまざまなシナリオで使用でき、各シナリオは、複雑さの異なるオーケストレーションを伴う場合があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-196">Orchestrations can be used in an almost infinite variety of scenarios, and each scenario might involve orchestrations of varying complexity.</span></span> <span data-ttu-id="9bd71-197">モジュール式の手法を優先して可能な場合は、複雑なオーケストレーションを回避します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-197">Avoid complex orchestrations when possible in favor of a modular approach.</span></span> <span data-ttu-id="9bd71-198">つまり、ビジネス ロジックを複数に分割再利用可能なオーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-198">In other words, split your business logic into multiple, reusable orchestrations.</span></span>  
  
 <span data-ttu-id="9bd71-199">複雑なオーケストレーションを実装する必要がある場合は、メッセージや変数をルート レベルではなく、可能な限り、内側のスコープに定義します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-199">If you do need to implement a complex orchestration, define messages and variables into inner scopes whenever possible rather than at the root level.</span></span> <span data-ttu-id="9bd71-200">この手法は、変数およびメッセージが破棄され、フローが変数およびメッセージが定義された範囲を離れるために、オーケストレーションごとのメモリのフット プリントがより小さいを保持します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-200">This technique maintains a smaller footprint in memory for each orchestration because variables and messages are disposed of when the flow leaves the scope where the variables and messages were defined.</span></span> <span data-ttu-id="9bd71-201">この方法は、オーケストレーションが永続化ポイントでメッセージ ボックス データベースに保存されるときに特に有用です。</span><span class="sxs-lookup"><span data-stu-id="9bd71-201">This approach is particularly beneficial when orchestrations are saved to the MessageBox at persistence points.</span></span>  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a><span data-ttu-id="9bd71-202">パフォーマンスを向上させるために、オーケストレーションの開始図形とオーケストレーションの呼び出し図形を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-202">Use the Call Orchestration shape versus the Start Orchestration shape to improve performance</span></span>  
 <span data-ttu-id="9bd71-203">回避、**オーケストレーションの開始**図形し、を使用して、**オーケストレーションの呼び出し**図形を入れ子になったオーケストレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-203">Avoid the **Start Orchestration** shape and use the **Call Orchestration** shape to execute a nested orchestration.</span></span> <span data-ttu-id="9bd71-204">実際には、**オーケストレーションの呼び出し**を別のプロジェクトで参照されているオーケストレーションを同期的に呼び出す図形を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-204">In fact, The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="9bd71-205">このアプローチは、BizTalk プロジェクト間での一般的なオーケストレーション ワークフロー パターンの再利用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-205">This approach allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="9bd71-206">同期的に入れ子になった別のオーケストレーションを呼び出すと、**オーケストレーションの呼び出し**続行する前に完了する入れ子になったオーケストレーションの図形、外側のオーケストレーションを待機します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-206">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape, the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span> <span data-ttu-id="9bd71-207">入れ子になったオーケストレーションは、呼び出し元のオーケストレーションを実行している同じスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-207">The nested orchestration is executed on the same thread that runs the calling orchestration.</span></span>  
  
 <span data-ttu-id="9bd71-208">**オーケストレーションの開始**図形と似ています、**オーケストレーションの呼び出し**図形、ネストされているオーケストレーションが非同期的に呼び出されるこの場合: 呼び出し元のコントロールのフローオーケストレーションは、呼び出されたオーケストレーションの処理を完了するを待たず、次に処理されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-208">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but in this case the nested orchestration is called in an asynchronous manner: the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span> <span data-ttu-id="9bd71-209">呼び出し元から呼び出されたオーケストレーションでは、この分離を実装するために、**オーケストレーションの開始**BizTalk メッセージ ボックスへのメッセージのパブリケーションを介して実装されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-209">In order to implement this decoupling between the caller and the called orchestrations, the **Start Orchestration** is implemented via publication of a message to the BizTalk Messagebox.</span></span> <span data-ttu-id="9bd71-210">このメッセージは、入れ子になったオーケストレーションを実行するインプロセス BizTalk ホスト インスタンスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-210">This message is then consumed by an in-process BizTalk host instance which executes the nested orchestration.</span></span> <span data-ttu-id="9bd71-211">可能であればを使用して、**オーケストレーションの呼び出し**、呼び出し元のオーケストレーションが処理を続行するには、入れ子になったオーケストレーションからの結果を待機する必要がある場合に特にです。</span><span class="sxs-lookup"><span data-stu-id="9bd71-211">When possible, use **Call Orchestration**, especially if the calling orchestration needs to wait for a result from the nested orchestration in order to continue processing.</span></span>  <span data-ttu-id="9bd71-212">詳細については、オーケストレーションの呼び出し図形を使用して、BizTalk Server 2010 のドキュメントでは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd71-212">For more information about using the Call Orchestration shape, see the following topics in the BizTalk Server 2010 documentation:</span></span>  
  
-   <span data-ttu-id="9bd71-213">[オーケストレーションでの直接バインド ポートの操作](http://go.microsoft.com/fwlink/?LinkId=139902)(http://go.microsoft.com/fwlink/?LinkId=139902)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-213">[Working with Direct Bound Ports in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).</span></span>  
  
-   <span data-ttu-id="9bd71-214">[オーケストレーションを入れ子](http://go.microsoft.com/fwlink/?LinkId=139903)(http://go.microsoft.com/fwlink/?LinkId=139903)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-214">[Nesting Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).</span></span>  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a><span data-ttu-id="9bd71-215">XmlDocument を使用したオーケストレーションのパフォーマンスを向上させるために XmlReader を使用すると、XLANGMessage を XmlReader を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-215">Use XmlReader with XLANGMessage versus using XmlReader with XmlDocument to improve orchestration performance</span></span>  
 <span data-ttu-id="9bd71-216">オーケストレーションから呼び出される .NET メソッドのオーケストレーションのパフォーマンスを向上させるのには、XLANGMessage、XmlDocument ではないと XmlReader を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-216">To improve orchestration performance for .NET methods called from an orchestration, use XmlReader with XLANGMessage, not XmlDocument.</span></span> <span data-ttu-id="9bd71-217">次のコード例は、この機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="9bd71-217">The following code example illustrates this functionality.</span></span>  
  
```csharp  
// As a general rule, use XmlReader with XLANGMessage, not XmlDocument.   
// This is illustrated in the parameter passed into the following code.   
// The XLANG/s compiler doesn't allow a return value of XmlReader   
// so documents must be initially constructed as XmlDocument()  
public static XmlDocument FromMsg(XLANGMessage old)  
{  
    //get at the data  
    XmlDocument ret = new XmlDocument();  
  
    try{  
        XmlReader reader = (XmlReader)old[0].RetrieveAs(typeof(XmlReader));  
        //construct new message from old  
        //read property  
        object msgid = old.GetPropertyValue(typeof(BTS.MessageID));  
    }  
    finally {  
        // Call Dispose on the XLANGMessage object   
        // because the message doesn't belong to the   
        // .NET runtime - it belongs to the Messagebox database   
        old.Dispose();  
    }  
    return ret;  
}  
```  
  
 <span data-ttu-id="9bd71-218">別の方法は、スキーマに基づく .NET クラスを作成することです。</span><span class="sxs-lookup"><span data-stu-id="9bd71-218">Another method would be to create a .NET class based on the schema.</span></span> <span data-ttu-id="9bd71-219">これにかかる時間にドキュメントの読み込みよりもメモリが少ない、 **XmlDocument** .NET 開発者向けのスキーマ要素に簡単にアクセスを提供するだけでなく、オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9bd71-219">This takes less memory than loading the document into an **XmlDocument** object, as well as providing easy access to the schema elements for .NET developers.</span></span> <span data-ttu-id="9bd71-220">BizTalk スキーマに基づくクラスを生成するには、Visual Studio に付属する xsd.exe ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-220">To generate a class based on a BizTalk schema, you can use the xsd.exe tool provided with Visual Studio.</span></span> <span data-ttu-id="9bd71-221">たとえば、実行している**xsd.exe \<schema.xsd\> /classes** ItemB、ItemC、ItemA という名前のフィールドを含む単純なスキーマに対して、次のクラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-221">For example, running **xsd.exe \<schema.xsd\> /classes** against a simple schema containing fields named ItemA, ItemB, ItemC, will produce the following class.</span></span>  
  
```csharp  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:2.0.50727.1433  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
using System.Xml.Serialization;  
  
//   
// This source code was auto-generated by xsd, Version=2.0.50727.42.  
//  
  
/// <remarks/>  
[System.CodeDom.Compiler.GeneratedCodeAttribute("xsd", "2.0.50727.42")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://Schemas.MySchema")]  
[System.Xml.Serialization.XmlRootAttribute(Namespace="http://Schemas.MySchema", IsNullable=false)]  
public partial class MySchemaRoot {  
  
    private string itemAField;  
  
    private string itemBField;  
  
    private string itemCField;  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemA {  
        get {  
            return this.itemAField;  
        }  
        set {  
            this.itemAField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemB {  
        get {  
            return this.itemBField;  
        }  
        set {  
            this.itemBField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemC {  
        get {  
            return this.itemCField;  
        }  
        set {  
            this.itemCField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="9bd71-222">メッセージの要素にアクセスするには、.NET アセンブリでこのクラスを参照しでき、返されたオブジェクトは、メッセージに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-222">This class can then be referenced in your .NET assembly in order to access the message elements, and the returned object can be directly assigned to a message.</span></span> <span data-ttu-id="9bd71-223">上記で生成されたクラスの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-223">The following is an example use of the class generated above.</span></span>  
  
```csharp  
public static Root SetValues(Microsoft.XLANGs.BaseTypes.XLANGMessage msg)  
{  
   try  
   {  
   MySchemaRoot rootObj=(MySchemaRoot)msg[0].RetrieveAs(typeof(MySchemaRoot);  
   rootObj.ItemA="value a";  
   rootObj.ItemB="value b";  
   rootObj.ItemC="value c";  
   }  
    finally {  
        msg.Dispose();  
            }  
  
   return rootObj;  
}  
```  
  
 <span data-ttu-id="9bd71-224">この手法を使用すると、メッセージを処理するときに、オブジェクト指向のアプローチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-224">This technique allows you to use an object-oriented approach when processing messages.</span></span> <span data-ttu-id="9bd71-225">この方法は、比較的小さなメッセージで主に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-225">This technique should be used primarily with relatively small messages.</span></span> <span data-ttu-id="9bd71-226">これは、ため、この手法がときにメッセージを読み込むよりも大幅に少ないメモリを使用する場合でも、 **XmlDocument**オブジェクト、メッセージ全体をメモリに読み込まれたままです。</span><span class="sxs-lookup"><span data-stu-id="9bd71-226">This is because even though this technique uses considerably less memory than when loading the message into an **XmlDocument** object, the entire message is still loaded into memory.</span></span> <span data-ttu-id="9bd71-227">サイズの大きいメッセージを処理する際に使用して、 **XmlReader**メッセージを読み取るクラスと**XmlWriter**クラスのメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-227">When processing larger messages, use the **XmlReader** class to read messages and the **XmlWriter** class to write messages.</span></span> <span data-ttu-id="9bd71-228">使用する場合**XmlReader**と**XmlWriter**に、メッセージが含まれている、 **VirtualStream**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9bd71-228">When using **XmlReader** and **XmlWriter**, the message is contained in a **VirtualStream** object.</span></span> <span data-ttu-id="9bd71-229">メッセージのサイズが指定された値を超えた場合**サイズの大きいメッセージのしきい値 (バイト単位)** BizTalk グループのプロパティの構成 ページで、公開では、メッセージは、ファイル システムに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-229">If the message size exceeds the value specified for **Large message threshold (bytes)** that is exposed on the BizTalk Group Properties configuration page, the message is written to the file system.</span></span> <span data-ttu-id="9bd71-230">これにより、全体のパフォーマンスが低下が、メモリ不足の例外を回避できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-230">This decreases overall performance, but avoids out of memory exceptions.</span></span>  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a><span data-ttu-id="9bd71-231">物理ポートにバインドされた論理ポートの使用を最小限に抑えることによるパフォーマンスを向上します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-231">Improve performance by minimizing the use of logical ports bound to physical ports</span></span>  
 <span data-ttu-id="9bd71-232">次のアダプターを使用する物理ポートにバインドされた論理ポートの使用を最小限に抑えることでパフォーマンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-232">You can increase performance by minimizing the use of logical ports bound to physical ports that use the following adapters:</span></span>  
  
- <span data-ttu-id="9bd71-233">SQL Server、Oracle</span><span class="sxs-lookup"><span data-stu-id="9bd71-233">SQL Server, Oracle</span></span>  
  
- <span data-ttu-id="9bd71-234">WSE、HTTP の場合、WCF</span><span class="sxs-lookup"><span data-stu-id="9bd71-234">WSE, HTTP, WCF</span></span>  
  
- <span data-ttu-id="9bd71-235">MSMQ、MQSeries</span><span class="sxs-lookup"><span data-stu-id="9bd71-235">MSMQ, MQSeries</span></span>  
  
  <span data-ttu-id="9bd71-236">BizTalk Server 2010 での送信し、受信パイプラインは、Microsoft.XLANGs.Pipeline.dll に含まれている XLANGPipelineManager クラスを使用してオーケストレーションから直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-236">In BizTalk Server 2010, send and receive pipelines can be directly invoked from an orchestration using the XLANGPipelineManager class contained in the Microsoft.XLANGs.Pipeline.dll.</span></span> <span data-ttu-id="9bd71-237">したがって、パイプラインの処理に移動できますポートからオーケストレーションです。オーケストレーションの論理ポートは、式図形を持ち、特定の .NET クラスのインスタンス (たとえば、ADO.NET を使用してデータ アクセス コンポーネント) を呼び出す代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-237">Thus, the processing of pipelines can be moved from ports to orchestrations; logical ports in an orchestration can be substituted with an Expression shape, which invokes an instance of a given .NET class (for example, a Data Access component using ADO.NET).</span></span> <span data-ttu-id="9bd71-238">この手法を採用する前に、アダプターと物理ポートを使用しない場合、バッチ処理、再試行、宣言型の構成、およびセカンダリ トランスポートなど、その機能を活用する機能を紛失したこと注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-238">Before adopting this technique, you should be aware that if you do not use adapters and physical ports, you lose the ability to leverage their functions, such as batching, retries, declarative configuration, and secondary transports.</span></span>  
  
## <a name="orchestration-design-patterns"></a><span data-ttu-id="9bd71-239">オーケストレーションのデザイン パターン</span><span class="sxs-lookup"><span data-stu-id="9bd71-239">Orchestration Design Patterns</span></span>  
 <span data-ttu-id="9bd71-240">オーケストレーション デザイナーでは、さまざまなエンタープライズ統合パターンを実装できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-240">The Orchestration Designer allows developers to implement a wide range of enterprise integration patterns.</span></span> <span data-ttu-id="9bd71-241">いくつかの一般的なパターンには、アグリゲーター、例外処理し補正、メッセージ ブローカー、散布図とギャザー、シーケンシャル モードとパラレルなコンボイが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-241">Some common patterns include Aggregator, Exception Handling and Compensation, Message Broker, Scatter and Gather, and Sequential and Parallel Convoy.</span></span> <span data-ttu-id="9bd71-242">これらのパターンは、BizTalk Server での複雑なエンタープライズ アプリケーション統合 (EAI)、サービス指向アーキテクチャ (SOA)、およびビジネス プロセス管理 (BPM) ソリューションの開発を活用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-242">Those patterns can be utilized to develop complex Enterprise Application Integration (EAI), Service-Oriented Architecture (SOA), and Business Process Management (BPM) solutions with BizTalk Server.</span></span> <span data-ttu-id="9bd71-243">オーケストレーションのデザイン パターンの詳細については、トピックを参照してください[オーケストレーションのデザイン パターンを実装する](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server のドキュメントと[パターンとベスト プラクティス。エンタープライズ統合](http://go.microsoft.com/fwlink/?LinkId=140043)(http://go.microsoft.com/fwlink/?LinkId=140043)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-243">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation and [Patterns and Best Practices for Enterprise Integration](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.microsoft.com/fwlink/?LinkId=140043).</span></span>  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a><span data-ttu-id="9bd71-244">パフォーマンスを最大化するためのオーケストレーションでの .NET クラスの適切な使用を行う</span><span class="sxs-lookup"><span data-stu-id="9bd71-244">Make appropriate use of .NET classes in orchestrations to maximize performance</span></span>  
 <span data-ttu-id="9bd71-245">一般に、オーケストレーション内で使用される .NET クラスは、2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-245">In general, the .NET classes used inside an orchestration can be divided into two distinct categories:</span></span>  
  
-   <span data-ttu-id="9bd71-246">**ヘルパーとサービス -** これらのクラスは、トレース、エラー処理、キャッシュ、およびシリアル化/逆シリアル化などのオーケストレーションに共通のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-246">**Helpers and services -** These classes provide common services to orchestrations such as tracing, error handling, caching, and serialization/deserialization.</span></span> <span data-ttu-id="9bd71-247">これらのクラスのほとんどは、内部状態がないと複数のパブリック静的メソッドと静的クラスとして実装できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-247">Most of these classes can be implemented as static classes with no internal state and multiple public static methods.</span></span> <span data-ttu-id="9bd71-248">このアプローチは、ホスト プロセスの作業領域を減らすし、メモリを節約する同時に実行されている別のオーケストレーションで、同じクラスの複数のオブジェクトの作成を回避できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-248">This approach avoids creating multiple objects of the same class in different orchestrations running at the same time, which helps to reduce the working space of host processes and save memory.</span></span> <span data-ttu-id="9bd71-249">ステートレスであるクラスでは、シリアル化して、オーケストレーションが退避済みの場合は、BizTalk メッセージ ボックスに永続化される必要がある内部状態の全体的なサイズを削減できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-249">A class that is stateless helps to reduce the overall size of the internal state that must be serialized and persisted to the BizTalk MessageBox when an orchestration is dehydrated.</span></span>  
  
-   <span data-ttu-id="9bd71-250">**エンティティおよびビジネス オブジェクト -** 注文、注文番号の品目、および顧客などのエンティティを管理するこれらのクラスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-250">**Entities and Business Objects -** You can use these classes to manage entities, such as orders, order items, and customers.</span></span> <span data-ttu-id="9bd71-251">1 つのオーケストレーションは、内部的に作成し、同じ種類の複数のインスタンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-251">A single orchestration can internally create and manage multiple instances of the same type.</span></span> <span data-ttu-id="9bd71-252">これらのクラスは通常ステートフルであり、パブリック フィールドや、オブジェクトの内部状態を変更するメソッドとプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-252">These classes are typically stateful, and expose public fields and/or properties along with methods to modify the internal state of the object.</span></span> <span data-ttu-id="9bd71-253">使用して .NET オブジェクトに、XLANGMessage 部分を逆シリアル化して、これらのクラスのインスタンスを動的に作成することができます、 **XmlSerializer**または**DataContractSerializer**クラスか、を使用して**XLANGPart.RetrieveAs**メソッド。</span><span class="sxs-lookup"><span data-stu-id="9bd71-253">Instances of these classes can be dynamically created by deserializing an XLANGMessage part into a .NET object by using the **XmlSerializer** or the **DataContractSerializer** classes or by using the **XLANGPart.RetrieveAs** method.</span></span> <span data-ttu-id="9bd71-254">ステートフルなクラスのインスタンスができるだけ遅く作成され、不要にするとすぐに解放する方法で非トランザクションのスコープを使用するオーケストレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd71-254">You should structure an orchestration using non-transactional scopes in such a way that instances of stateful classes are created as late as possible and released as soon as they are no longer needed.</span></span> <span data-ttu-id="9bd71-255">このアプローチでは、ホスト プロセスの作業領域が抑制され、シリアル化し、オーケストレーションが退避済みの場合は、メッセージ ボックス データベースに永続化の内部状態の全体的なサイズを最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-255">This approach reduces the working space of host processes and minimizes the overall size of the internal state that is serialized and persisted to the MessageBox database when an orchestration is dehydrated.</span></span> <span data-ttu-id="9bd71-256">詳細については、BizTalk server オーケストレーションを使用して、記事を参照してください。 [BizTalk Server オーケストレーションのよく寄せられる質問](http://go.microsoft.com/fwlink/?LinkID=116886)(http://go.microsoft.com/fwlink/?LinkID=116886)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-256">For more information about using orchestrations in BizTalk Server, see the article [FAQ for BizTalk Server Orchestrations](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9bd71-257">この記事では、BizTalk Server 2004 および BizTalk Server 2006 用に記述されたが、説明する概念も BizTalk Server 2010 のオーケストレーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-257">While this article is written for BizTalk Server 2004 and BizTalk Server 2006, the concepts presented also apply to BizTalk Server 2010 orchestrations.</span></span>  
  
## <a name="orchestration-exception-handler-blocks"></a><span data-ttu-id="9bd71-258">オーケストレーションの例外ハンドラー ブロック</span><span class="sxs-lookup"><span data-stu-id="9bd71-258">Orchestration Exception Handler Blocks</span></span>  
 <span data-ttu-id="9bd71-259">オーケストレーションの例外ハンドラー ブロックを使用する場合は、1 つまたは複数のスコープ (可能な限り非トランザクション スコープ) にすべてのオーケストレーション図形を含めるし、少なくとも次の例外ハンドラー ブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-259">When using Orchestration exception Handler blocks, include all orchestration shapes in one or multiple scopes (non transactional scopes whenever possible) and create at least the following exception handler blocks:</span></span>  
  
- <span data-ttu-id="9bd71-260">System.Exception の一般的なエラーを処理するための例外ハンドラー ブロックします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-260">An exception handler block for handling a generic System.Exception error.</span></span>  
  
- <span data-ttu-id="9bd71-261">例外ハンドラー ブロックにキャッチして COM 例外など、管理されていないエラーを処理するために、一般的な例外を処理するためです。</span><span class="sxs-lookup"><span data-stu-id="9bd71-261">An exception handler block for handling a general exception in order to catch and handle possible unmanaged errors, such as COM exceptions.</span></span>  
  
  <span data-ttu-id="9bd71-262">詳細については、オーケストレーションの例外処理ブロックを使用して、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd71-262">For more information about using Orchestration exception handling blocks, see the following articles:</span></span>  
  
- <span data-ttu-id="9bd71-263">[BizTalk Server 例外処理を使用して](http://msdn.microsoft.com/library/aa561229.aspx)(http://msdn.microsoft.com/library/aa561229.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-263">[Using BizTalk Server Exception Handling](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).</span></span>  
  
- <span data-ttu-id="9bd71-264">[Charles Young のブログ、BizTalk Server 2006:補正モデル](http://go.microsoft.com/fwlink/?LinkId=158017)(http://go.microsoft.com/fwlink/?LinkId=158017)します。</span><span class="sxs-lookup"><span data-stu-id="9bd71-264">[Charles Young Blog, BizTalk Server 2006: The Compensation Model](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9bd71-265">このブログで書き込まれたときに[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]を考慮して、ブログで説明する原則にも適用 BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="9bd71-265">While this blog was written with [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] in mind, the principles described in the blog also apply to BizTalk Server.</span></span>  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a><span data-ttu-id="9bd71-266">オーケストレーションでマップを使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="9bd71-266">Considerations when using maps in orchestrations</span></span>  
 <span data-ttu-id="9bd71-267">オーケストレーションでマップを使用する場合は、次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9bd71-267">The following considerations apply when using maps in orchestrations:</span></span>  
  
-   <span data-ttu-id="9bd71-268">抽出または使用するプロパティを設定するマップを使用している場合、オーケストレーションでビジネス ロジックは識別フィールドを使用して、または昇格させたプロパティです。</span><span class="sxs-lookup"><span data-stu-id="9bd71-268">If you are using a map to extract or set properties used with business logic in an orchestration, use distinguished fields or promoted properties.</span></span> <span data-ttu-id="9bd71-269">この実習を抽出したり、ドキュメント マップで値の設定が読み込まれるときにメモリにただし識別フィールドまたは昇格させたプロパティを使用して、オーケストレーション エンジンがメッセージ コンテキストにアクセスして、読み込まれませんので、従う必要があります、ドキュメントをメモリにします。</span><span class="sxs-lookup"><span data-stu-id="9bd71-269">This practice should be followed because when extracting or setting values with a map the document is loaded into memory however when using distinguished fields or promoted properties, the orchestration engine accesses the message context and does not load the document into memory.</span></span>  
  
-   <span data-ttu-id="9bd71-270">いくつかのフィールドを 1 つのフィールドに集計を識別フィールドを使用して、マップを使用して結果セットを蓄積するオーケストレーション変数のプロパティを昇格するか。</span><span class="sxs-lookup"><span data-stu-id="9bd71-270">If you are using a map to aggregate several fields into one field, use distinguished fields or promoted properties with an orchestration variable to accumulate the result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd71-271">参照</span><span class="sxs-lookup"><span data-stu-id="9bd71-271">See Also</span></span>  
 [<span data-ttu-id="9bd71-272">パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="9bd71-272">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)