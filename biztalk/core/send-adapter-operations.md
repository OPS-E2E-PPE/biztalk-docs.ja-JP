---
title: 送信アダプターの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf4e0430-e3dc-4884-8411-bbcb579bd21e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e4fbc0458fa9c433c585143bcada38e0e25c3c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250869"
---
# <a name="send-adapter-operations"></a><span data-ttu-id="d2fc0-102">送信アダプターの操作</span><span class="sxs-lookup"><span data-stu-id="d2fc0-102">Send Adapter Operations</span></span>
<span data-ttu-id="d2fc0-103">送信アダプターは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-103">Send adapters can perform the following operations:</span></span>  
  
- <span data-ttu-id="d2fc0-104">**再実行してください。 無効に (IBaseMessage msg, DateTime timeStamp) に再実行してください。**</span><span class="sxs-lookup"><span data-stu-id="d2fc0-104">**Resubmit: void Resubmit(IBaseMessage msg, DateTime timeStamp).**</span></span> <span data-ttu-id="d2fc0-105">転送後にエラーが発生した、メッセージをアダプターでは、適切なときに再送信されます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-105">After a transmission failure occurs on a message, an adapter resubmits it when appropriate.</span></span> <span data-ttu-id="d2fc0-106">これは、メッセージごとに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-106">This is called on a per-message basis.</span></span> <span data-ttu-id="d2fc0-107">アダプターがメッセージ、エラーの原因を特定する必要があり、別の呼び出しで失敗するバッチが発生しなかったものを再送信メッセージのバッチが正常に送信された場合**再送信**します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-107">If a batch of messages was submitted unsuccessfully, the adapter must determine the messages causing the failure, and resubmit the ones that did not cause the batch to fail in separate calls to **Resubmit**.</span></span> <span data-ttu-id="d2fc0-108">このトピックの最後に呼び出したときに、メッセージ コンテキスト プロパティの値を保持する方法についての情報がある**再送信**します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-108">There is information at the end of this topic about how to preserve message context property values when you call **Resubmit**.</span></span>  
  
- <span data-ttu-id="d2fc0-109">**次のトランスポートに移動: void MoveToNextTransport (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="d2fc0-109">**Move to Next Transport: void MoveToNextTransport(IBaseMessage msg).**</span></span> <span data-ttu-id="d2fc0-110">送信操作が失敗したメッセージの再試行が終了している場合は、アダプターは、再送信の次の構成済みトランスポートにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-110">If a message fails during a send operation and its retry attempts have been exhausted, the adapter can send the message to the next configured transport for retransmission.</span></span>  
  
- <span data-ttu-id="d2fc0-111">**中断: は void MoveToSuspendQ (IBaseMessage msg) です。**</span><span class="sxs-lookup"><span data-stu-id="d2fc0-111">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="d2fc0-112">失敗した送信メッセージを保留キューに追加のバックアップ トランスポートが構成されていない場合、アダプターに移動します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-112">The adapter moves a failed send message to the Suspended queue if no additional backup transport is configured.</span></span> <span data-ttu-id="d2fc0-113">このトピックの最後に呼び出したときに、メッセージ コンテキスト プロパティの値を保持する方法についての情報がある**Suspend**します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-113">There is information at the end of this topic about how to preserve message context property values when you call **Suspend**.</span></span>  
  
- <span data-ttu-id="d2fc0-114">**削除: は void DeleteMessage (IBaseMessage msg) です。**</span><span class="sxs-lookup"><span data-stu-id="d2fc0-114">**Delete: void DeleteMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="d2fc0-115">アダプターでは、その転送が成功したの BizTalk Server によって通知された後、メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-115">The adapter deletes a message after being notified by BizTalk Server of its successful transmission.</span></span> <span data-ttu-id="d2fc0-116">メッセージを削除する指示 BizTalk Server アダプターがメッセージを完了したことです。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-116">Deleting a message tells BizTalk Server that the adapter is finished with the message.</span></span> <span data-ttu-id="d2fc0-117">一般に、 **SubmitResponse**それに関連付けられたとして同じバッチ内で操作が完了したら**削除**操作。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-117">Generally the **SubmitResponse** operation is done in the same batch as its associated **Delete** operation.</span></span>  
  
- <span data-ttu-id="d2fc0-118">**送信応答: は void SubmitResponseMessage (IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit) です。**</span><span class="sxs-lookup"><span data-stu-id="d2fc0-118">**Submit Response: void SubmitResponseMessage(IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit).**</span></span> <span data-ttu-id="d2fc0-119">アダプターは、BizTalk Server に送信するバッチへの応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-119">The adapter submits a response to the batch to be sent back to BizTalk Server.</span></span> <span data-ttu-id="d2fc0-120">この操作には、BizTalk Server は、それらを関連付けることができるため、応答と共に呼び出しで、元のメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-120">This operation includes the original message in the call along with the response so that BizTalk Server can correlate them.</span></span>  
  
- <span data-ttu-id="d2fc0-121">**[キャンセル] 応答: は void CancelResponseMessages (string correlationToken) です。**</span><span class="sxs-lookup"><span data-stu-id="d2fc0-121">**Cancel Response: void CancelResponseMessages(string correlationToken).**</span></span> <span data-ttu-id="d2fc0-122">応答メッセージの送信をバッチが送信される前にキャンセルできる必要がある場合、 **CancelResponseMessages**メソッドを使用すると、削除する関連付けられた応答メッセージの関連付けトークンを渡します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-122">If the sending of a response message needs to be canceled before the batch is submitted, the **CancelResponseMessages** method is used, passing in the correlation token for the associated response message to be deleted.</span></span>  
  
  <span data-ttu-id="d2fc0-123">呼び出すときに**再送信**または**Suspend**で特定のメッセージ コンテキスト プロパティの値を保持するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-123">When calling **Resubmit** or **Suspend** on a message you may want to preserve the values of certain message context properties.</span></span> <span data-ttu-id="d2fc0-124">プロパティの値を XML 形式で保存することによって、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-124">You can do this by saving property values in XML format.</span></span> <span data-ttu-id="d2fc0-125">メッセージが再送信または中断時に、対応するプロパティは引き続きメッセージ コンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-125">When the message is resubmitted or suspended the corresponding properties remain available in the message context.</span></span>  
  
  <span data-ttu-id="d2fc0-126">次の XML 文字列には、情報が格納されている形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-126">The following XML string describes the format in which the information is stored:</span></span>  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 <span data-ttu-id="d2fc0-127">次のコードでは、この XML 文字列が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-127">This XML string is generated by the following code:</span></span>  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 <span data-ttu-id="d2fc0-128">この文字列は、このコードを使用して、メッセージ コンテキストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-128">This string is then saved to the message context by using this code:</span></span>  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 <span data-ttu-id="d2fc0-129">メッセージが再送信されたときに、アダプターは、次のコード行を使用して値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d2fc0-129">When the message is resubmitted, the adapter can read this property by using the following line of code:</span></span>  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```