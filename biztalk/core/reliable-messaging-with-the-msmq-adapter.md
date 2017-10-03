---
title: "MSMQ アダプターで信頼性の高いメッセージング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, reliability
- reliability
- reliability, MSMQ adapters
- MSMQ adapters, reliability
- reliability, messages
ms.assetid: 1a4b4f77-c508-4c3f-82f9-5722d0af6c63
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc90ce4619527a6c53cbaf5a2546cb8708362b65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reliable-messaging-with-the-msmq-adapter"></a><span data-ttu-id="54a5c-102">MSMQ アダプターで信頼できるメッセージング</span><span class="sxs-lookup"><span data-stu-id="54a5c-102">Reliable Messaging with the MSMQ Adapter</span></span>
<span data-ttu-id="54a5c-103">特定の構成設定とトランザクションを使用することにより、MSMQ アダプタを使用したメッセージの送受信の信頼性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="54a5c-103">You can improve the reliability of sending and receiving messages with the MSMQ adapter by using particular configuration settings and by using transactions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54a5c-104">トランザクションを使用しないと、コンピュータでエラーが発生したときに、クラスタ構成ではメッセージが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54a5c-104">If you do not use transactions, you can lose messages in clustered configurations if a computer fails.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54a5c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="54a5c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="54a5c-106">MSMQ アダプターで信頼できるメッセージのプロパティ</span><span class="sxs-lookup"><span data-stu-id="54a5c-106">Properties for Reliable Messaging with the MSMQ Adapter</span></span>](../core/properties-for-reliable-messaging-with-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="54a5c-107">トランザクション MSMQ アダプターで処理</span><span class="sxs-lookup"><span data-stu-id="54a5c-107">Transaction Handling with the MSMQ Adapter</span></span>](../core/transaction-handling-with-the-msmq-adapter.md)