---
title: WCF アダプターの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- receive adapters, Web service headers
- SOAP messages, extracting information
- SOAP messages, WCF adapters
- WCF adapters, receive adapters
- messages, SOAP
- receive adapters, WCF adapters
- Web services, headers
- headers [messages]
- SOAP messages, receive adapters
ms.assetid: 6b3d5df1-5d9d-4240-a98f-ea29c3272e38
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c30d858c08da8a0f8d71d56397e43d591b3d773
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965835"
---
# <a name="wcf-receive-adapter"></a>WCF 受信アダプタ
WCF 受信アダプターを使用すると、WCF サービス要求を受信できます。  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a>SOAP メッセージからの BizTalk メッセージ本文の抽出  
 受信 BizTalk メッセージ本文を SOAP メッセージから抽出するには、次のいずれかのオプションを使用します。  
  
- SOAP Body 要素のコンテンツを抽出する  
  
- SOAP エンベロープ全体を抽出する  
  
- XPath 式を使用して SOAP エンベロープ内の要素のコンテンツを抽出する  
  
  [トランスポートのプロパティ] ダイアログ ボックスで、これらのオプションを構成できます。  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a>SOAP Body 要素のコンテンツを抽出します。  
 このオプションを選択すると、SOAP Body 要素の内部コンテンツが、SOAP メッセージから読み込まれ、BizTalk メッセージのボディ部に挿入されます。  
  
#### <a name="extract-the-entire-soap-envelope"></a>全体の SOAP エンベロープを抽出します。  
 このオプションを選択すると、SOAP エンベロープ全体 (タグを含む) が BizTalk メッセージのボディ部に挿入されます。  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a>EXPath 式を使用して要素のコンテンツを抽出する  
 このオプションを選択すると、XPath 式で見つかった、SOAP Body 要素内にある要素の内部コンテンツが、BizTalk メッセージのボディ部に挿入されます。 Body 要素内の残りのデータは無視されます。 ノード エンコードの種類を指定する必要があります: 例では、XML、Base64、16 進数、または文字列をエンコードするためです。  
  
> [!NOTE]
>  XML エンコードを選択すると、要素の外部コンテンツが、XPath 式で検出され、ボディ部に挿入されます。  
  
## <a name="handling-web-services-headers"></a>Web サービス ヘッダーの処理  
 受信アダプターでは、標準 Web サービス ヘッダーのサブセットを BizTalk メッセージ コンテキストに昇格させて、これらのヘッダーの値に基づいたアクセスおよびルーティングを容易にします。 次の表に、受信アダプターによってメッセージ コンテキストに保存されるプロパティを示します。 プロパティは、次の名前空間で定義されます:http://www.w3.org/2005/addressingとhttp://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-propertiesします。  
  
|[ヘッダー]|BizTalk プロパティ名|昇格の有無|  
|------------|---------------------------|------------------|  
|操作|操作|はい|  
|MessageID|MessageID|いいえ|  
|変換先|変換先|はい|  
|ReplyTo/Address|ReplyTo|はい|  
|From/Address|From|はい|  
|Sequence/Identifier|SequenceId|はい|  
|Sequence/MessageNumber|SequenceNumber|はい|  
|Sequence/LastMessage|SequenceLastMessage|はい|  
|\<soap ヘッダー:\>|InboundHeaders|いいえ|  
  
## <a name="see-also"></a>参照  
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 送信アダプタ](../core/wcf-send-adapter.md)   
 [WCF アダプターについて](../core/what-are-the-wcf-adapters.md)