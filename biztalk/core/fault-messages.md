---
title: エラー メッセージ |Microsoft ドキュメント
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
ms.openlocfilehash: e4127fd5718ee910cb298436c0d0f7058ccba55b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245898"
---
# <a name="fault-messages"></a><span data-ttu-id="b6c52-102">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="b6c52-102">Fault Messages</span></span>
<span data-ttu-id="b6c52-103">要求 – 応答ポートにはエラー メッセージを関連付けることができます。これにより、要求の送信後に問題が発生した場合、応答サービスは応答の代わりにエラーを要求側に通知することができます。</span><span class="sxs-lookup"><span data-stu-id="b6c52-103">Request-response ports can have fault messages associated with them, so that if something goes wrong after a request is sent, the responding service can communicate the error to the requester, in lieu of the response.</span></span>  
  
 <span data-ttu-id="b6c52-104">要求 – 応答ポートの各操作では、任意の数の異なるエラーを処理できます。</span><span class="sxs-lookup"><span data-stu-id="b6c52-104">Each operation of a request-response port can handle an arbitrary number of different faults.</span></span> <span data-ttu-id="b6c52-105">エラー メッセージには任意の種類のメッセージを含めることができます。ただし、メッセージの種類は操作ごとに一意である必要があります。また、そのポート操作の応答で使用されない種類でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b6c52-105">A fault message can have any message type, but the message type must be unique for the operation, and it must not be the type used by the response in that port operation.</span></span>  
  
## <a name="receiving-fault-messages"></a><span data-ttu-id="b6c52-106">エラー メッセージの受信</span><span class="sxs-lookup"><span data-stu-id="b6c52-106">Receiving fault messages</span></span>  
 <span data-ttu-id="b6c52-107">ポート操作で要求を送信して応答を受信する場合、そのポート操作を使用して複数の異なるエラー メッセージの種類を受信できます。</span><span class="sxs-lookup"><span data-stu-id="b6c52-107">If your port operation sends a request, then receives a response, you can use it to receive one or more different fault message types.</span></span>  
  
 <span data-ttu-id="b6c52-108">構成することができます、**例外のキャッチ**例外オブジェクト型と要求-応答ポート操作から適切なエラーを選択して、受信したエラー メッセージを処理するブロック。</span><span class="sxs-lookup"><span data-stu-id="b6c52-108">You can configure a **Catch Exception** block to handle an incoming fault message by selecting the appropriate fault from the request-response port operation as its Exception Object Type.</span></span>  
  
## <a name="sending-fault-messages"></a><span data-ttu-id="b6c52-109">エラー メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="b6c52-109">Sending fault messages</span></span>  
 <span data-ttu-id="b6c52-110">ポート操作で応答を受信して要求を送信する場合、そのポート操作を使用して複数の異なるエラー メッセージの種類を送信できます。</span><span class="sxs-lookup"><span data-stu-id="b6c52-110">If your port operation receives a response, then sends a request, you can use it to send one or more different fault message types.</span></span>  
  
 <span data-ttu-id="b6c52-111">たとえば、オーケストレーションは、エラー状態が発生し、例外をスローする場合、内からエラー メッセージを送信することができます、**例外のキャッチ**例外を処理するブロック。</span><span class="sxs-lookup"><span data-stu-id="b6c52-111">If for example your orchestration encounters an error condition and throws an exception, you can send a fault message from within the **Catch Exception** block that handles the exception.</span></span> <span data-ttu-id="b6c52-112">適切な種類のエラー メッセージを構築して、参加しているサービスに状況を伝達し、ポート操作の対応するエラーを使用する送信図形にそのエラー メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6c52-112">You construct a fault message of an appropriate type to convey the situation to the participating service, and specify that fault message on a Send shape that will use the corresponding fault in the port operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c52-113">参照</span><span class="sxs-lookup"><span data-stu-id="b6c52-113">See Also</span></span>  
 [<span data-ttu-id="b6c52-114">例外</span><span class="sxs-lookup"><span data-stu-id="b6c52-114">Exceptions</span></span>](../core/exceptions.md)