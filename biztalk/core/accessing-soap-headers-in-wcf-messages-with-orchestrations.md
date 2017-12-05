---
title: "オーケストレーションでの WCF メッセージにおける SOAP ヘッダーへのアクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- orchestrations, WCF services
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: fe02fb02-18d6-4fc6-89e0-b06bdbfa5cb4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bfd1dd4e09071c3d7bcccf28878f19e13acad8a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a>オーケストレーションにおける WCF メッセージでの SOAP ヘッダーへのアクセス
オーケストレーションにおける受信 WCF メッセージの SOAP ヘッダーの値にアクセスするにはコンテキスト プロパティを使用する**WCF です。InboundHeaders**です。 WCF アダプタを受信メッセージのカスタム SOAP ヘッダーと標準 SOAP ヘッダーのコピー、 **WCF です。InboundHeaders**プロパティです。 WCF アダプタを使用すると、プログラムによってコンテキスト プロパティへの昇格または書き込みを行うプロパティを選択することもできます。 参照してください[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)詳細についてはします。  
  
 コンテキスト プロパティに含まれる値は、使用した XML データを含む文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。 このデータにアクセスする最も簡単な方法で BizTalk 式エディタを使用する、**メッセージの割り当て**または**式**図形、内の文字列を読み込み、 **XmlDocument**、および使用特定のフィールドにアクセスする XPath クエリです。 BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [XLANG-s 言語](../core/xlang-s-language.md)します。  
  
 次のコード例は、要求 SOAP ヘッダーを取得、**メッセージの割り当て**または**式**図形、 **WCF です。InboundHeaders**プロパティ。  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 コンテキスト プロパティは、特定のメッセージに関連付けられています。 メッセージング エンジンでは SOAP ヘッダー値を要求メッセージから応答メッセージに自動的にマップしません。 WCF サービスの応答メッセージを作成するときに経由の SOAP ヘッダーの値を明示的に設定する必要があります、 **WCF です。OutboundCustomHeaders**プロパティです。 次のコマンドは、SOAP ヘッダー コンテキスト プロパティの設定の最も単純なメソッドを示します。  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 作成することで、コンテキスト プロパティを設定することも、 **XmlDocument**と書き込みの文字列値、 **XmlDocument**をコンテキスト プロパティです。  
  
 WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてを参照してください「を使用してカスタム SOAP ヘッダー with the WCF Adapters」の SDK サンプル[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)です。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)   
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)