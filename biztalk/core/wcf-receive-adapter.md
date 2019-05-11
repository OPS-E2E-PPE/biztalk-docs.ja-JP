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
ms.openlocfilehash: 86d7f307a9c7dae45e81e8c9c1e5bcf57a6ef6b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266395"
---
# <a name="wcf-receive-adapter"></a>WCF 受信アダプター
WCF は受信要求を処理すると、WCF 受信アダプターの有効です。  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a>SOAP メッセージから BizTalk メッセージ本文の抽出  
 次のオプションのいずれかを使用して SOAP メッセージから受信 BizTalk メッセージ本文を取得できます。  
  
- SOAP Body 要素のコンテンツを抽出します。  
  
- SOAP エンベロープ全体を抽出します。  
  
- XPath 式を使用して SOAP エンベロープ内の要素のコンテンツを抽出します。  
  
  トランスポートのプロパティ ダイアログ ボックスで、これらのオプションを構成できます。  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a>SOAP Body 要素のコンテンツを抽出します。  
 このオプションを選択すると、SOAP Body 要素の内部コンテンツが、SOAP メッセージから読み取られ、BizTalk メッセージのボディ部に配置されます。  
  
#### <a name="extract-the-entire-soap-envelope"></a>全体の SOAP エンベロープを抽出します。  
 このオプションを選択すると、タグを含む SOAP エンベロープ全体が BizTalk メッセージのボディ部に配置されます。  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a>XPath 式を使用して、要素のコンテンツを抽出します。  
 このオプションを選択すると、BizTalk メッセージのボディ部には、XPath 式である SOAP Body 要素内の要素の内部コンテンツが配置されます。 本文要素のデータの残りの部分は無視されます。 ノード エンコードの種類を指定する必要があります: 例では、XML、Base64、16 進数、または文字列をエンコードするためです。  
  
> [!NOTE]
>  XML エンコーディングを選択すると、要素の外側のコンテンツは、XPath 式であるし、ボディ部に配置されます。  
  
## <a name="handling-web-services-headers"></a>処理の Web サービス ヘッダー  
 受信アダプターが BizTalk メッセージ コンテキストに簡単にアクセスを有効にするのには、標準の Web サービス ヘッダーのサブセットを昇格し、これらのヘッダーの値に基づくルーティングします。 次の表は、受信アダプターによってメッセージ コンテキストに保存されるプロパティを一覧表示します。 プロパティは、次の名前空間で定義されます:http://www.w3.org/2005/addressingと http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-propertiesします。  
  
|[ヘッダー]|BizTalk プロパティ名|昇格の有無|  
|------------|---------------------------|------------------|  
|操作|操作|はい|  
|MessageID|MessageID|いいえ|  
|目的|目的|はい|  
|ReplyTo アドレス/|ReplyTo|はい|  
|/アドレス|From|はい|  
|シーケンス識別子/|SequenceId|はい|  
|シーケンス/MessageNumber|SequenceNumber|はい|  
|シーケンス/LastMessage|SequenceLastMessage|はい|  
|\<soap ヘッダー:\>|InboundHeaders|いいえ|  
  
## <a name="see-also"></a>参照  
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 送信アダプタ](../core/wcf-send-adapter.md)   
 [WCF アダプターについて](../core/what-are-the-wcf-adapters.md)