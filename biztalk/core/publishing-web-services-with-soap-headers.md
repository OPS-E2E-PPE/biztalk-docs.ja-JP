---
title: "SOAP ヘッダーによる Web サービスを発行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, pipelines
- SOAP headers, BizTalk Web Services Publishing Wizard
- pipelines, SOAP headers
- orchestrations, SOAP headers
ms.assetid: c362caff-b75f-4c1b-9013-d2b9c74f5c65
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7baf6af0e4505e448a854fe6def372614bfdaa49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-web-services-with-soap-headers"></a>SOAP ヘッダーで Web サービスの公開
BizTalk Web サービス公開ウィザードを実行すると、Web サービスに SOAP ヘッダーが追加されます。 SOAP ヘッダーをサポートする Web サービスを公開すると、追加されたヘッダーは、SOAP ヘッダーの文字列表記を含むコンテキスト プロパティとして、オーケストレーションおよびパイプライン コンポーネントに対して使用可能となります。  
  
## <a name="defined-soap-headers"></a>定義済みの SOAP ヘッダー  
 ウィザードを使用して、定義済みの SOAP ヘッダーを追加すると、ウィザードによってコンテキスト プロパティが作成されます。このプロパティには、SOAP ヘッダーのルート要素に対応する名前が付けられます。 定義済みのすべての SOAP ヘッダー コンテキスト プロパティは、名前空間を持つ**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**です。 SOAP ヘッダーのコンテキスト プロパティは、SOAP アダプタによって SOAP 要求が BizTalk メッセージに変換されるときに作成されます。  
  
 簡単な SOAP 要求の例を次に示します。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
       <soap:Header>  
             <OrigDest xmlns="http://SOAPHeaderWS.ItemAvailability">  
                    <Origination>Work</Origination>  
                    <Destination>Home</Destination>  
             </OrigDest>  
       </soap:Header>  
       <soap:Body>  
  
       </soap:Body>  
</soap:Envelope>  
```  
  
 SOAP アダプターが 1 つの SOAP ヘッダー コンテキスト プロパティを BizTalk メッセージを作成、単純な SOAP 要求を**OrigDest**および文字列。  
  
 次の例は、SOAP アダプタによって作成される文字列を示しています。  
  
```  
"<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader"><Origination xmlns="">Home</Origination><Destination xmlns="">Work</Destination> </OrigDest>"  
```  
  
## <a name="unknown-soap-headers"></a>不明な SOAP ヘッダー  
 ウィザードが名前を持つコンテキスト プロパティを作成する場合は、ウィザードで不明な SOAP ヘッダーをサポートするために選択すると、 **UnknownHeaders**と名前空間**http://schemas.microsoft.com/BizTalk/2003/soap-properties**. **UnknownHeaders**コンテキスト プロパティには、すべての受信の不明な SOAP ヘッダーが含まれています。  
  
 たとえば、ルート要素名を持つの不明な SOAP ヘッダーを受信する**CustomerGroup**、 **UnknownHeaders**コンテキスト プロパティには、文字列が含まれています。  
  
```  
"<?xml version="1.0" encoding="utf-16"?><UnknownHeaders><CustomerGroup xmlns="http://SOAPHeaderWS/CustomerGroup"><Id xmlns="">My Customer</Id>  
</CustomerGroup></UnknownHeaders>"  
```  
  
 定義の追加の詳細については、SOAP ヘッダーまたは不明な SOAP ヘッダーをサポートするを参照してください[オーケストレーション Web サービスとして公開](../core/publishing-an-orchestration-as-a-web-service.md)です。 参照してください[Web サービスとして公開スキーマ](../core/publishing-schemas-as-a-web-service.md)です。  
  
## <a name="see-also"></a>参照  
 [公開済み Web サービスでの SOAP ヘッダー](../core/soap-headers-with-published-web-services.md)