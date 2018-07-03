---
title: オーケストレーション経由でルーティングするときに、JMS ヘッダーを保持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9a59ff3-0cbf-499f-92b2-cf5b808d8b3f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 142bd0d2e5ff86362fe3c3ffa7ef8ec256202708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979715"
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a><span data-ttu-id="60565-102">オーケストレーション経由でルーティングするときに、JMS ヘッダーを保持</span><span class="sxs-lookup"><span data-stu-id="60565-102">Preserving JMS Headers When Routing Through an Orchestration</span></span>
<span data-ttu-id="60565-103">このユース ケースでは、コンポーネントがで提供される[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージから Java Message Service (JMS) ヘッダーを抽出し、送信メッセージの再構築します。</span><span class="sxs-lookup"><span data-stu-id="60565-103">In this use case, components provided with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extract Java Message Service (JMS) headers from an incoming message and then reconstructs them in the outgoing message.</span></span> <span data-ttu-id="60565-104">JMS メッセージのヘッダー情報保持図 1 に示すようには、オーケストレーション内からヘッダーのコンテキストへのアクセスを示します。</span><span class="sxs-lookup"><span data-stu-id="60565-104">This demonstrates JMS message header preservation and access to header context from inside an orchestration, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="60565-105">![JMS の維持](../esb-toolkit/media/ch3-preservingjms.gif "Ch3 PreservingJMS")</span><span class="sxs-lookup"><span data-stu-id="60565-105">![Preserving JMS](../esb-toolkit/media/ch3-preservingjms.gif "Ch3-PreservingJMS")</span></span>  
  
 <span data-ttu-id="60565-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="60565-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="60565-107">**ESB オーケストレーション全体でヘッダー情報を JMS の維持および処理**</span><span class="sxs-lookup"><span data-stu-id="60565-107">**Preserving JMS header information throughout an ESB orchestration and processing**</span></span>  
  
 <span data-ttu-id="60565-108">JMS MQRFH2 コンポーネント サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示し、次の 3 つの部分で構成されています。</span><span class="sxs-lookup"><span data-stu-id="60565-108">The JMS MQRFH2 Component sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case and consists of the following three parts:</span></span>  
  
- <span data-ttu-id="60565-109">第 1 部は、IBM WebSphere MQ、ESB および BizTalk Server と IBM WebSphere MQ のメッセージが移動完全に忠実なヘッダー情報の保持を示します。</span><span class="sxs-lookup"><span data-stu-id="60565-109">Part 1 demonstrates full-fidelity header preservation as a message travels from IBM WebSphere MQ, through ESB and BizTalk Server, and back to IBM WebSphere MQ.</span></span>  
  
- <span data-ttu-id="60565-110">第 2 部では、ESB オーケストレーション内のコードを使用して MQRFH2 ヘッダー プロパティにアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="60565-110">Part 2 demonstrates how code in an ESB orchestration can access MQRFH2 header properties.</span></span> <span data-ttu-id="60565-111">この場合、コードは、送信先のキュー名を指定する JMS ヘッダー プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="60565-111">In this case, the code modifies a JMS header property to specify the destination queue name.</span></span>  
  
- <span data-ttu-id="60565-112">第 3 部は、一括読み込みのキューでメッセージを示し、アプリケーションがメッセージの内容の一部として指定された送信先キューにメッセージをルーティングする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="60565-112">Part 3 demonstrates bulk loading a queue with messages and shows how the application routes messages to the destination queues specified as part of the message content.</span></span>  
  
  <span data-ttu-id="60565-113">詳細については、次を参照してください。[インストールして、JMS MQRFH2 コンポーネント サンプルを実行する](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="60565-113">For more information, see [Installing and Running the JMS MQRFH2 Component Sample](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md).</span></span>