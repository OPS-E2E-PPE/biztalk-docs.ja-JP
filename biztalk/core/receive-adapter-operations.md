---
title: "受信アダプターの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b61ea356-f2a1-4604-8e52-13d2961399d0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804a136841c33977b350b8d59dfbf18c7108cc79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-adapter-operations"></a><span data-ttu-id="08b13-102">受信アダプターの操作</span><span class="sxs-lookup"><span data-stu-id="08b13-102">Receive Adapter Operations</span></span>
<span data-ttu-id="08b13-103">受信アダプターでは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="08b13-103">Receive adapters can perform the following operations:</span></span>  
  
-   <span data-ttu-id="08b13-104">**一方向の送信: void SubmitMessage (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="08b13-104">**One-way submit: void SubmitMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="08b13-105">受信ポートからメッセージを受信した後、アダプターに送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サブスクライブを行うオーケストレーションで処理や送信ポートにします。</span><span class="sxs-lookup"><span data-stu-id="08b13-105">After receiving a message from a receive port, the adapter submits it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be processed by a subscribing orchestration or send port.</span></span>  
  
-   <span data-ttu-id="08b13-106">**Suspend: は void MoveToSuspendQ (IBaseMessage msg) です。**</span><span class="sxs-lookup"><span data-stu-id="08b13-106">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="08b13-107">解析エラー、送信エラー、シリアル化エラーなどが送信後に発生したと判断した場合、受信アダプターは、メッセージを保留キューに移動します。</span><span class="sxs-lookup"><span data-stu-id="08b13-107">When the adapter determines a parsing, transmission, serialization, or other applicable failure has occurred after submission, it moves the message to the Suspended queue.</span></span>  
  
-   <span data-ttu-id="08b13-108">**要求を送信: void SubmitRequestMessage (IBaseMessage requestMsg、文字列 correlationToken、[MarshalAs(UnmanagedType.Bool)] bool firstResponseOnly、DateTime expirationTime、IBTTransmitter responseCallback)。**</span><span class="sxs-lookup"><span data-stu-id="08b13-108">**Submit request: void SubmitRequestMessage(IBaseMessage requestMsg, string correlationToken, [MarshalAs(UnmanagedType.Bool)]bool firstResponseOnly, DateTime expirationTime, IBTTransmitter responseCallback).**</span></span> <span data-ttu-id="08b13-109">受信アダプター、受信メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求-応答の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="08b13-109">A receive adapter submits an incoming message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a request-response pair.</span></span> <span data-ttu-id="08b13-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、この要求メッセージを適切に処理した後、応答を受信アダプターに送信します。この応答は、受信アダプターから特定のエンドポイントに転送されます。</span><span class="sxs-lookup"><span data-stu-id="08b13-110">After [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] successfully processes this request message, it sends the response to the adapter to transmit it to the specific endpoint.</span></span>