---
title: 受信アダプターの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b61ea356-f2a1-4604-8e52-13d2961399d0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d4e5ee9d9afbbb687f415b42652d76a50bac4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980123"
---
# <a name="receive-adapter-operations"></a><span data-ttu-id="afebe-102">受信アダプターの操作</span><span class="sxs-lookup"><span data-stu-id="afebe-102">Receive Adapter Operations</span></span>
<span data-ttu-id="afebe-103">受信アダプターでは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="afebe-103">Receive adapters can perform the following operations:</span></span>  

- <span data-ttu-id="afebe-104">**一方向の送信: void SubmitMessage (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="afebe-104">**One-way submit: void SubmitMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="afebe-105">受信ポートからメッセージを受信した後、アダプターに送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サブスクライブを行うオーケストレーションで処理または送信ポートにします。</span><span class="sxs-lookup"><span data-stu-id="afebe-105">After receiving a message from a receive port, the adapter submits it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be processed by a subscribing orchestration or send port.</span></span>  

- <span data-ttu-id="afebe-106">**中断: は void MoveToSuspendQ (IBaseMessage msg) です。**</span><span class="sxs-lookup"><span data-stu-id="afebe-106">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="afebe-107">解析エラー、送信エラー、シリアル化エラーなどが送信後に発生したと判断した場合、受信アダプターは、メッセージを保留キューに移動します。</span><span class="sxs-lookup"><span data-stu-id="afebe-107">When the adapter determines a parsing, transmission, serialization, or other applicable failure has occurred after submission, it moves the message to the Suspended queue.</span></span>  

- <span data-ttu-id="afebe-108">**要求を送信: void SubmitRequestMessage (IBaseMessage requestMsg、文字列 correlationToken、[MarshalAs(UnmanagedType.Bool)] bool firstResponseOnly、DateTime expirationTime、IBTTransmitter responseCallback)。**</span><span class="sxs-lookup"><span data-stu-id="afebe-108">**Submit request: void SubmitRequestMessage(IBaseMessage requestMsg, string correlationToken, [MarshalAs(UnmanagedType.Bool)]bool firstResponseOnly, DateTime expirationTime, IBTTransmitter responseCallback).**</span></span> <span data-ttu-id="afebe-109">受信アダプターの送信、受信メッセージを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求-応答の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="afebe-109">A receive adapter submits an incoming message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a request-response pair.</span></span> <span data-ttu-id="afebe-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、この要求メッセージを適切に処理した後、応答を受信アダプターに送信します。この応答は、受信アダプターから特定のエンドポイントに転送されます。</span><span class="sxs-lookup"><span data-stu-id="afebe-110">After [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] successfully processes this request message, it sends the response to the adapter to transmit it to the specific endpoint.</span></span>
