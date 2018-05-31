---
title: BizTalk メッセージ ボックス データベースに永続化せず変換 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5b4caf-88e9-41dd-a644-e229e411a4a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 407725509121948619e4eb05b583f6c8c1362f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294986"
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a><span data-ttu-id="d6dcd-102">BizTalk メッセージ ボックス データベースに永続化せず変換</span><span class="sxs-lookup"><span data-stu-id="d6dcd-102">Transformation Without Persisting to the BizTalk Message Box Database</span></span>
<span data-ttu-id="d6dcd-103">このユース ケースで Web サービスへの呼び出しが適用するには、適切なマップの実行時の解像度に基づいて、メッセージのリアルタイムの変換を実行し、変換後の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="d6dcd-103">In this use case, a call to a Web service performs real-time transformation of a message, based on run-time resolution of the appropriate map to apply, and returns the transformed result.</span></span> <span data-ttu-id="d6dcd-104">図 1 は、プロセスの概略を示します。</span><span class="sxs-lookup"><span data-stu-id="d6dcd-104">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="d6dcd-105">![永続化せず変換](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3 TransformationWithout")</span><span class="sxs-lookup"><span data-stu-id="d6dcd-105">![Transformation Without Persisting](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3-TransformationWithout")</span></span>  
  
 <span data-ttu-id="d6dcd-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="d6dcd-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="d6dcd-107">**Microsoft BizTalk Server メッセージ ボックス データベースに保存することがなく、メッセージを変換します。**</span><span class="sxs-lookup"><span data-stu-id="d6dcd-107">**Transforming a message without persisting to the Microsoft BizTalk Server Message Box database**</span></span>  
  
 <span data-ttu-id="d6dcd-108">含まれる変換サービスのサンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="d6dcd-108">The Transformation Service sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="d6dcd-109">使用すると、ESB 変換サービスを呼び出すことができます。これにより、コンポーネントと、BizTalk Server ビジネス ルール エンジンのポリシーを開発しているように、変換とマッピングをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6dcd-109">By using it, you can call the ESB Transformation Service; this enables you to test transformations and mappings as you are developing components and policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="d6dcd-110">詳細については、次を参照してください。[をインストールすると、変換サービスのサンプルを実行している](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="d6dcd-110">For more information, see [Installing and Running the Transformation Service Sample](../esb-toolkit/installing-and-running-the-transformation-service-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6dcd-111">ここでは、BizTalk Server の変換エージェントによって実行される動的変換操作で参照変換のサービスを混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="d6dcd-111">Do not confuse the Transformation Service referred to here with the dynamic transformation operations performed by the BizTalk Server Transformation Agent.</span></span> <span data-ttu-id="d6dcd-112">変換サービスは、高パフォーマンス Web サービスを BizTalk Server を直接呼び出すことによって、メッセージ ボックス データベースを通過せずに待機時間を大幅に短縮します。</span><span class="sxs-lookup"><span data-stu-id="d6dcd-112">The Transformation Service is a high-performance Web service that significantly reduces latency by calling directly into BizTalk Server without going through the Message Box database.</span></span>