---
title: "JMS MQRFH2 コンポーネント サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44f4b48c-398a-4ec1-a033-1fc4a76a305c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fcea4bca324f73ee37b63e78673140eae250692
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-jms-mqrfh2-component-sample"></a><span data-ttu-id="da8a5-102">JMS MQRFH2 コンポーネント サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="da8a5-102">Running the JMS MQRFH2 Component Sample</span></span>
<span data-ttu-id="da8a5-103">JMS MQRFH2 コンポーネント サンプルは、3 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="da8a5-103">The JMS MQRFH2 Component sample consists of three parts:</span></span>  
  
-   <span data-ttu-id="da8a5-104">[JMS MQRFH2 ヘッダーの保存のサンプルを実行して](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="da8a5-104">[Running the JMS MQRFH2 Header Preservation Sample](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md).</span></span> <span data-ttu-id="da8a5-105">この部分は、ESB と Microsoft BizTalk Server を使用して IBM WebSphere MQ に戻る、IBM WebSphere MQ からメッセージが移動するように完全に忠実なヘッダーの保存を示しています。</span><span class="sxs-lookup"><span data-stu-id="da8a5-105">This part demonstrates full-fidelity header preservation as a message travels from IBM WebSphere MQ, through ESB and Microsoft BizTalk Server, and back to IBM WebSphere MQ.</span></span>  
  
-   <span data-ttu-id="da8a5-106">[オーケストレーションのサンプルからのヘッダー プロパティへのアクセスを実行している](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="da8a5-106">[Running the Header Property Access from an Orchestration Sample](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md).</span></span> <span data-ttu-id="da8a5-107">この部分では、ESB オーケストレーション内でコードが MQRFH2 ヘッダー プロパティにアクセスする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="da8a5-107">This part demonstrates how code within an ESB orchestration can access MQRFH2 header properties.</span></span> <span data-ttu-id="da8a5-108">ここで、コードは、送信先のキュー名を指定するのにヘッダーのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8a5-108">In this case, the code uses a header property to specify the destination queue name.</span></span>  
  
-   <span data-ttu-id="da8a5-109">[コンテンツ ベース ルーティングのサンプルを読み込む一括を実行している](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="da8a5-109">[Running the Bulk Load Content-Based Routing Sample](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md).</span></span> <span data-ttu-id="da8a5-110">この部分での一括読み込み、メッセージのキューについて説明し、アプリケーションがメッセージの内容の一部として指定された送信先キューにメッセージをルーティングする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="da8a5-110">This part demonstrates bulk loading a queue with messages, and it shows how the application routes messages to the destination queues specified as part of the message content.</span></span>