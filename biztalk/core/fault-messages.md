---
title: エラー メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe3ab052612166b55fb966507a4a4c95b1b8f81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388079"
---
# <a name="fault-messages"></a><span data-ttu-id="98dd4-102">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="98dd4-102">Fault Messages</span></span>
<span data-ttu-id="98dd4-103">要求-応答ポートは、問題が発生した要求が送信される場合、応答サービスは、要求元の応答の代わりにエラーを通信できるように、それらに関連付けられているエラー メッセージを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="98dd4-103">Request-response ports can have fault messages associated with them, so that if something goes wrong after a request is sent, the responding service can communicate the error to the requester, in lieu of the response.</span></span>  
  
 <span data-ttu-id="98dd4-104">要求-応答ポートの各操作では、任意の数の異なるエラーを処理できます。</span><span class="sxs-lookup"><span data-stu-id="98dd4-104">Each operation of a request-response port can handle an arbitrary number of different faults.</span></span> <span data-ttu-id="98dd4-105">エラー メッセージは、任意のメッセージ型を持つことができますが、メッセージの種類は、操作に対して一意である必要があり、そのポート操作の応答で使用される型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="98dd4-105">A fault message can have any message type, but the message type must be unique for the operation, and it must not be the type used by the response in that port operation.</span></span>  
  
## <a name="receiving-fault-messages"></a><span data-ttu-id="98dd4-106">エラー メッセージの受信</span><span class="sxs-lookup"><span data-stu-id="98dd4-106">Receiving fault messages</span></span>  
 <span data-ttu-id="98dd4-107">ポート操作で要求を送信応答を受信する場合は、1 つまたは複数の異なるエラー メッセージの種類の受信に使用できます。</span><span class="sxs-lookup"><span data-stu-id="98dd4-107">If your port operation sends a request, then receives a response, you can use it to receive one or more different fault message types.</span></span>  
  
 <span data-ttu-id="98dd4-108">構成することができます、**例外のキャッチ**例外オブジェクト型と要求-応答ポート操作から適切なエラーを選択して、受信したエラー メッセージを処理するためにブロックします。</span><span class="sxs-lookup"><span data-stu-id="98dd4-108">You can configure a **Catch Exception** block to handle an incoming fault message by selecting the appropriate fault from the request-response port operation as its Exception Object Type.</span></span>  
  
## <a name="sending-fault-messages"></a><span data-ttu-id="98dd4-109">エラー メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="98dd4-109">Sending fault messages</span></span>  
 <span data-ttu-id="98dd4-110">ポート操作の応答を受信要求を送信する場合は、1 つまたは複数の異なるエラー メッセージの種類の送信に使用できます。</span><span class="sxs-lookup"><span data-stu-id="98dd4-110">If your port operation receives a response, then sends a request, you can use it to send one or more different fault message types.</span></span>  
  
 <span data-ttu-id="98dd4-111">たとえば、オーケストレーションは、エラー状態が発生し、例外をスローする場合、内からエラー メッセージを送信することができます、**例外のキャッチ**例外を処理するブロック。</span><span class="sxs-lookup"><span data-stu-id="98dd4-111">If for example your orchestration encounters an error condition and throws an exception, you can send a fault message from within the **Catch Exception** block that handles the exception.</span></span> <span data-ttu-id="98dd4-112">参加しているサービスに状況を伝達するために適切な種類のエラー メッセージを構築し、ポート操作で対応するフォールトが使用する送信図形にそのエラー メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="98dd4-112">You construct a fault message of an appropriate type to convey the situation to the participating service, and specify that fault message on a Send shape that will use the corresponding fault in the port operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98dd4-113">参照</span><span class="sxs-lookup"><span data-stu-id="98dd4-113">See Also</span></span>  
 [<span data-ttu-id="98dd4-114">例外</span><span class="sxs-lookup"><span data-stu-id="98dd4-114">Exceptions</span></span>](../core/exceptions.md)