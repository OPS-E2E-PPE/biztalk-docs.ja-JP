---
title: サービス仲介パターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfda54db-75fa-4bc2-9f48-11d8b3cde65b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b11d58393ea90f840a1193106c4c01376a5c1a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268943"
---
# <a name="service-mediation-patterns"></a><span data-ttu-id="117b6-102">サービス仲介パターン</span><span class="sxs-lookup"><span data-stu-id="117b6-102">Service Mediation Patterns</span></span>
## <a name="vetovetro"></a><span data-ttu-id="117b6-103">拒否/VETRO</span><span class="sxs-lookup"><span data-stu-id="117b6-103">VETO/VETRO</span></span>  
 <span data-ttu-id="117b6-104">VETRO パターンは、受信したときに、メッセージで行われた複数の操作を結合する一般的な複合パターンです。</span><span class="sxs-lookup"><span data-stu-id="117b6-104">The VETRO pattern is a common composite pattern that combines multiple actions taken on a message when it is received.</span></span> <span data-ttu-id="117b6-105">用語 VETRO は、検証、強化、変換、ルート操作を表す頭字語です。</span><span class="sxs-lookup"><span data-stu-id="117b6-105">The term VETRO is an acronym that stands for Validate, Enrich, Transform, Route, Operate.</span></span> <span data-ttu-id="117b6-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、受信場所に関連付けられたパイプライン内の個々 の段階としてこれらのアクションを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="117b6-106">In the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], these actions can be handled as individual stages in the pipeline associated with the receive location.</span></span> <span data-ttu-id="117b6-107">これらの各段階を実装する方法の詳細については、主要なシナリオおよび開発タスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="117b6-107">For more information about how each of these stages can be implemented, see Key Scenarios and Development Tasks.</span></span>  
  
## <a name="request-response"></a><span data-ttu-id="117b6-108">要求-応答</span><span class="sxs-lookup"><span data-stu-id="117b6-108">Request-Response</span></span>  
 <span data-ttu-id="117b6-109">要求-応答パターンでは、要求をサービス、またはパーティに送信しますがメッセージし、応答メッセージを転送先サービスからの戻り値が必要ですが、ソリューションを定義します。</span><span class="sxs-lookup"><span data-stu-id="117b6-109">The Request-Response pattern defines a solution in which a service or party sends a request message and expects a reply message in return from the destination service.</span></span> <span data-ttu-id="117b6-110">このパターンの詳細については、次を参照してください。[要求/応答](http://go.microsoft.com/fwlink/?LinkId=186849)([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849))、エンタープライズ統合パターン サイト。</span><span class="sxs-lookup"><span data-stu-id="117b6-110">For a detailed description of this pattern, see [Request-Reply](http://go.microsoft.com/fwlink/?LinkId=186849) ([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849)) on the Enterprise Integration Patterns site.</span></span>  
  
 <span data-ttu-id="117b6-111">このパターンを実装する方法の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="117b6-111">For more information about how to implement this pattern, see the following resources:</span></span>  
  
-   [<span data-ttu-id="117b6-112">方法: メッセージと要求-応答のメッセージ交換パターンを使用してサービス エンドポイントへのルートを変換します。</span><span class="sxs-lookup"><span data-stu-id="117b6-112">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
-   [<span data-ttu-id="117b6-113">スケジュール オンランプ サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="117b6-113">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)