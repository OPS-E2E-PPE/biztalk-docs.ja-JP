---
title: "BizTalk オーケストレーション エンジンに関する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac12012f-6253-4589-84b3-c1bb102ce8dd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e4e686f066c2fcde921e45d08b60d6386e86640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-biztalk-orchestration-engine"></a><span data-ttu-id="98c16-102">BizTalk オーケストレーション エンジンについて</span><span class="sxs-lookup"><span data-stu-id="98c16-102">About the BizTalk Orchestration Engine</span></span>
<span data-ttu-id="98c16-103">実行時に、BizTalk オーケストレーション エンジンは、BizTalk オーケストレーション デザイナーによって生成された xlang/s ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="98c16-103">At run time, the BizTalk Orchestration Engine executes XLANG/s files that are produced by BizTalk Orchestration Designer.</span></span> <span data-ttu-id="98c16-104">オーケストレーション デザイナーは、ビジネス プロセスを視覚的にデザインするための機能豊富なグラフィカル ツールです。</span><span class="sxs-lookup"><span data-stu-id="98c16-104">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="98c16-105">オーケストレーション デザイナーは、.odx という拡張子を持つ XLANG/s ファイルを生成します。このファイルのヘッダーには追加のビジュアル情報が格納され、本文にはカスタム属性情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="98c16-105">It generates XLANG/s files that have an .odx extension and contain additional visualization information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98c16-106">XLANG/s は、C# の表現機能を備えたメッセージング言語と見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="98c16-106">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span>  
  
 <span data-ttu-id="98c16-107">オーケストレーション エンジンには、主に次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="98c16-107">The primary functions of the orchestration engine are:</span></span>  
  
-   <span data-ttu-id="98c16-108">永続化</span><span class="sxs-lookup"><span data-stu-id="98c16-108">Persistence</span></span>  
  
-   <span data-ttu-id="98c16-109">.NET コンポーネントのホスト</span><span class="sxs-lookup"><span data-stu-id="98c16-109">Hosting the .NET components</span></span>  
  
-   <span data-ttu-id="98c16-110">トランザクション</span><span class="sxs-lookup"><span data-stu-id="98c16-110">Transactions</span></span>  
  
-   <span data-ttu-id="98c16-111">サイズの大きいメッセージのサポート</span><span class="sxs-lookup"><span data-stu-id="98c16-111">Large message support</span></span>  
  
-   <span data-ttu-id="98c16-112">実行時の検証</span><span class="sxs-lookup"><span data-stu-id="98c16-112">Runtime validation</span></span>  
  
-   <span data-ttu-id="98c16-113">負荷の制限</span><span class="sxs-lookup"><span data-stu-id="98c16-113">Load throttling</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98c16-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="98c16-114">In This Section</span></span>  
  
-   [<span data-ttu-id="98c16-115">永続化し、オーケストレーション エンジン</span><span class="sxs-lookup"><span data-stu-id="98c16-115">Persistence and the Orchestration Engine</span></span>](../core/persistence-and-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="98c16-116">オーケストレーションの退避と復元</span><span class="sxs-lookup"><span data-stu-id="98c16-116">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)  
  
-   [<span data-ttu-id="98c16-117">オーケストレーション エンジンの実行時の検証</span><span class="sxs-lookup"><span data-stu-id="98c16-117">Runtime Validation for the Orchestration Engine</span></span>](../core/runtime-validation-for-the-orchestration-engine.md)  
  
-   [<span data-ttu-id="98c16-118">オーケストレーション エンジンの構成</span><span class="sxs-lookup"><span data-stu-id="98c16-118">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="98c16-119">参照</span><span class="sxs-lookup"><span data-stu-id="98c16-119">See Also</span></span>  
 <span data-ttu-id="98c16-120">[BizTalk Server アーキテクチャ](../core/biztalk-server-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="98c16-120">[BizTalk Server Architecture](../core/biztalk-server-architecture.md) </span></span>  
 <span data-ttu-id="98c16-121">[XLANG の言語](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="98c16-121">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="98c16-122">[ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md) </span><span class="sxs-lookup"><span data-stu-id="98c16-122">[Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) </span></span>  
 [<span data-ttu-id="98c16-123">BizTalk Server がサイズの大きいメッセージを処理する方法</span><span class="sxs-lookup"><span data-stu-id="98c16-123">How BizTalk Server Processes Large Messages</span></span>](../core/how-biztalk-server-processes-large-messages.md)