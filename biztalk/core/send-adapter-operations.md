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
ms.openlocfilehash: ae8f638d2e9875883224dbfbf0a9d7d44851b8c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012987"
---
# <a name="send-adapter-operations"></a>送信アダプターの操作
送信アダプターでは次の操作を実行できます。  
  
- **再実行してください。 無効に (IBaseMessage msg, DateTime timeStamp) に再実行してください。** 転送後にエラーが発生した、メッセージをアダプターでは、適切なときに再送信されます。 呼び出しはメッセージ単位です。 アダプターがメッセージ、エラーの原因を特定する必要があり、別の呼び出しで失敗するバッチが発生しなかったものを再送信メッセージのバッチが正常に送信された場合**再送信**します。 このトピックの最後に呼び出したときに、メッセージ コンテキスト プロパティの値を保持する方法についての情報がある**再送信**します。  
  
- **次のトランスポートに移動: void MoveToNextTransport (IBaseMessage msg)。** 送信操作が失敗したメッセージの再試行が終了している場合は、アダプターは、再送信の次の構成済みトランスポートにメッセージを送信できます。  
  
- **中断: は void MoveToSuspendQ (IBaseMessage msg) です。** 他にバックアップ トランスポートが構成されていない場合、アダプターでは、失敗した送信メッセージを保留キューに移動します。 このトピックの最後に呼び出したときに、メッセージ コンテキスト プロパティの値を保持する方法についての情報がある**Suspend**します。  
  
- **削除: は void DeleteMessage (IBaseMessage msg) です。** アダプターでは、その転送が成功したの BizTalk Server によって通知された後、メッセージを削除します。 メッセージを削除すると、アダプターでメッセージの処理が完了したことが BizTalk Server に通知されます。 一般に、 **SubmitResponse**それに関連付けられたとして同じバッチ内で操作が完了したら**削除**操作。  
  
- **送信応答: は void SubmitResponseMessage (IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit) です。** アダプターは、BizTalk Server に送信するバッチへの応答を送信します。 この操作には呼び出し内の元のメッセージと応答が含まれるので、BizTalk Server ではこれらを関連付けることができます。  
  
- **[キャンセル] 応答: は void CancelResponseMessages (string correlationToken) です。** 応答メッセージの送信をバッチが送信される前にキャンセルできる必要がある場合、 **CancelResponseMessages**メソッドを使用すると、削除する関連付けられた応答メッセージの関連付けトークンを渡します。  
  
  呼び出すときに**再送信**または**Suspend**で特定のメッセージ コンテキスト プロパティの値を保持するメッセージ。 これには、XML 形式でプロパティ値を保存します。 メッセージの再送信時や中断時には、メッセージ コンテキスト内の該当プロパティを使用できます。  
  
  次の XML 文字列は、情報を格納する形式を表しています。  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 この XML 文字列は次のコードで生成されます。  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 この文字列をメッセージ コンテキストに保存するには、次のコードを使用します。  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 メッセージの再送信時、アダプターでは次のコード行を使用して、このプロパティを読み取ることができます。  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```