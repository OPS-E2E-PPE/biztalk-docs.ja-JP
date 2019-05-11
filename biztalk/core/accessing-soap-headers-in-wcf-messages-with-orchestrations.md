---
title: オーケストレーションで WCF メッセージにおける SOAP ヘッダーへのアクセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- orchestrations, WCF services
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: fe02fb02-18d6-4fc6-89e0-b06bdbfa5cb4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 747e92359bf894eb96229cc8e1f1d227db8d5cb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361875"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a>オーケストレーションで WCF メッセージにおける SOAP ヘッダーへのアクセス
オーケストレーションにおける受信 WCF メッセージの SOAP ヘッダーの値にアクセスするには、コンテキスト プロパティを使用する**WCF です。InboundHeaders**します。 WCF アダプタを受信メッセージのカスタム SOAP ヘッダーと標準 SOAP ヘッダーのコピー、 **WCF です。InboundHeaders**プロパティ。 WCF アダプタでは、プロパティの昇格または書き込みをプログラムによってコンテキスト プロパティにする を選択することもできます。 参照してください[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)の詳細。  
  
 コンテキスト プロパティに含まれる値は、XML データを格納している文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。 このデータにアクセスする最も簡単な方法は、BizTalk 式エディターを使用する、**メッセージの割り当て**または**式**図形、内の文字列を読み込み、 **XmlDocument**、および使用特定のフィールドにアクセスする XPath クエリです。 BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [xlang-s 言語](../core/xlang-s-language.md)します。  
  
 次のコード例、要求 SOAP ヘッダーを取得する、**メッセージの割り当て**または**式**図形、 **WCF です。InboundHeaders**プロパティ。  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 コンテキスト プロパティは、特定のメッセージに関連付けられます。 メッセージング エンジンは、要求メッセージから応答メッセージに SOAP ヘッダーの値を自動的にマップしません。 経由の SOAP ヘッダーの値を設定する必要があります具体的には、WCF サービスの応答メッセージを作成するときに、 **WCF です。OutboundCustomHeaders**プロパティ。 次のコマンドは、SOAP ヘッダー コンテキスト プロパティの設定の最も簡単なメソッドを示します。  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 作成して、コンテキスト プロパティを設定することも、 **XmlDocument**の文字列値の書き込みと、 **XmlDocument**をコンテキスト プロパティ。  
  
 WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてで、SDK サンプルの「を使用してカスタム SOAP ヘッダー with the WCF Adapters」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)   
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)