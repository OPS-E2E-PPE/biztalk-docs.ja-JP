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
# <a name="send-adapter-operations"></a>送信アダプターの操作
送信アダプターは、次の操作を実行できます。  
  
- **再実行してください。 無効に (IBaseMessage msg, DateTime timeStamp) に再実行してください。** 転送後にエラーが発生した、メッセージをアダプターでは、適切なときに再送信されます。 これは、メッセージごとに呼び出されます。 アダプターがメッセージ、エラーの原因を特定する必要があり、別の呼び出しで失敗するバッチが発生しなかったものを再送信メッセージのバッチが正常に送信された場合**再送信**します。 このトピックの最後に呼び出したときに、メッセージ コンテキスト プロパティの値を保持する方法についての情報がある**再送信**します。  
  
- **次のトランスポートに移動: void MoveToNextTransport (IBaseMessage msg)。** 送信操作が失敗したメッセージの再試行が終了している場合は、アダプターは、再送信の次の構成済みトランスポートにメッセージを送信できます。  
  
- **中断: は void MoveToSuspendQ (IBaseMessage msg) です。** 失敗した送信メッセージを保留キューに追加のバックアップ トランスポートが構成されていない場合、アダプターに移動します。 このトピックの最後に呼び出したときに、メッセージ コンテキスト プロパティの値を保持する方法についての情報がある**Suspend**します。  
  
- **削除: は void DeleteMessage (IBaseMessage msg) です。** アダプターでは、その転送が成功したの BizTalk Server によって通知された後、メッセージを削除します。 メッセージを削除する指示 BizTalk Server アダプターがメッセージを完了したことです。 一般に、 **SubmitResponse**それに関連付けられたとして同じバッチ内で操作が完了したら**削除**操作。  
  
- **送信応答: は void SubmitResponseMessage (IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit) です。** アダプターは、BizTalk Server に送信するバッチへの応答を送信します。 この操作には、BizTalk Server は、それらを関連付けることができるため、応答と共に呼び出しで、元のメッセージが含まれます。  
  
- **[キャンセル] 応答: は void CancelResponseMessages (string correlationToken) です。** 応答メッセージの送信をバッチが送信される前にキャンセルできる必要がある場合、 **CancelResponseMessages**メソッドを使用すると、削除する関連付けられた応答メッセージの関連付けトークンを渡します。  
  
  呼び出すときに**再送信**または**Suspend**で特定のメッセージ コンテキスト プロパティの値を保持するメッセージ。 プロパティの値を XML 形式で保存することによって、これを行うことができます。 メッセージが再送信または中断時に、対応するプロパティは引き続きメッセージ コンテキストで使用できます。  
  
  次の XML 文字列には、情報が格納されている形式について説明します。  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 次のコードでは、この XML 文字列が生成されます。  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 この文字列は、このコードを使用して、メッセージ コンテキストに保存されます。  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 メッセージが再送信されたときに、アダプターは、次のコード行を使用して値を取得できます。  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```