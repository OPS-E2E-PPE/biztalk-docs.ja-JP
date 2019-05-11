---
title: BizTalk オーケストレーション エンジンについて |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac12012f-6253-4589-84b3-c1bb102ce8dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5ba658a0df6675992601ecb55796e606791b6af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362315"
---
# <a name="about-the-biztalk-orchestration-engine"></a><span data-ttu-id="b2c39-102">BizTalk オーケストレーション エンジンについて</span><span class="sxs-lookup"><span data-stu-id="b2c39-102">About the BizTalk Orchestration Engine</span></span>
<span data-ttu-id="b2c39-103">実行時に、BizTalk オーケストレーション エンジンは、BizTalk オーケストレーション デザイナーによって生成される xlang/s ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2c39-103">At run time, the BizTalk Orchestration Engine executes XLANG/s files that are produced by BizTalk Orchestration Designer.</span></span> <span data-ttu-id="b2c39-104">オーケストレーション デザイナーは、ビジネス プロセスを視覚的に設計するための豊富なグラフィカル ツールです。</span><span class="sxs-lookup"><span data-stu-id="b2c39-104">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="b2c39-105">Xlang/s ファイルを .odx という拡張子を持ち、ヘッダー内の視覚エフェクトの追加情報と、本文にカスタム属性情報が含まれますが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b2c39-105">It generates XLANG/s files that have an .odx extension and contain additional visualization information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2c39-106">一部の式の機能を備えたメッセージング言語として XLANG/秒を表示できますC#します。</span><span class="sxs-lookup"><span data-stu-id="b2c39-106">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span>  
  
 <span data-ttu-id="b2c39-107">オーケストレーション エンジンの主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2c39-107">The primary functions of the orchestration engine are:</span></span>  
  
-   <span data-ttu-id="b2c39-108">永続化</span><span class="sxs-lookup"><span data-stu-id="b2c39-108">Persistence</span></span>  
  
-   <span data-ttu-id="b2c39-109">.NET コンポーネントをホストしています。</span><span class="sxs-lookup"><span data-stu-id="b2c39-109">Hosting the .NET components</span></span>  
  
-   <span data-ttu-id="b2c39-110">トランザクション</span><span class="sxs-lookup"><span data-stu-id="b2c39-110">Transactions</span></span>  
  
-   <span data-ttu-id="b2c39-111">サイズの大きいメッセージのサポート</span><span class="sxs-lookup"><span data-stu-id="b2c39-111">Large message support</span></span>  
  
-   <span data-ttu-id="b2c39-112">実行時の検証</span><span class="sxs-lookup"><span data-stu-id="b2c39-112">Runtime validation</span></span>  
  
-   <span data-ttu-id="b2c39-113">負荷の制限</span><span class="sxs-lookup"><span data-stu-id="b2c39-113">Load throttling</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2c39-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b2c39-114">In This Section</span></span>  
  
-   [<span data-ttu-id="b2c39-115">永続性とオーケストレーション エンジン</span><span class="sxs-lookup"><span data-stu-id="b2c39-115">Persistence and the Orchestration Engine</span></span>](../core/persistence-and-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="b2c39-116">オーケストレーションの退避と復元</span><span class="sxs-lookup"><span data-stu-id="b2c39-116">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)  
  
-   [<span data-ttu-id="b2c39-117">オーケストレーション エンジンの実行時の検証</span><span class="sxs-lookup"><span data-stu-id="b2c39-117">Runtime Validation for the Orchestration Engine</span></span>](../core/runtime-validation-for-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="b2c39-118">オーケストレーション エンジンの構成</span><span class="sxs-lookup"><span data-stu-id="b2c39-118">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2c39-119">参照</span><span class="sxs-lookup"><span data-stu-id="b2c39-119">See Also</span></span>  
 <span data-ttu-id="b2c39-120">[BizTalk Server アーキテクチャ](../core/biztalk-server-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="b2c39-120">[BizTalk Server Architecture](../core/biztalk-server-architecture.md) </span></span>  
 <span data-ttu-id="b2c39-121">[Xlang-s 言語](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="b2c39-121">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="b2c39-122">[ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md) </span><span class="sxs-lookup"><span data-stu-id="b2c39-122">[Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) </span></span>  
 [<span data-ttu-id="b2c39-123">BizTalk Server がサイズの大きなメッセージを処理する方法</span><span class="sxs-lookup"><span data-stu-id="b2c39-123">How BizTalk Server Processes Large Messages</span></span>](../core/how-biztalk-server-processes-large-messages.md)