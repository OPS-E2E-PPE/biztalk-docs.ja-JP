---
title: オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 664f009c1dbbbc37c619f81471ad1675ddd258c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395199"
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a>オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用
オーケストレーションの送信 WCF メッセージでは、カスタムの SOAP ヘッダーを送信する、コンテキスト プロパティを使用して**WCF です。OutboundCustomHeaders**します。 WCF アダプタは、WCF インフラストラクチャが Ws-addressing などの Web サービス標準を使用する標準 SOAP ヘッダーと組み合わせるカスタム SOAP ヘッダーを送信し、Ws-security、WS-AtomicTransaction します。 使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー** \>ルート要素としての要素。 内ですべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。 カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** / \>を**OutboundCustomHeaders**プロパティ。  
  
 オーケストレーションで SOAP ヘッダー コンテキスト プロパティは、XML データを含む文字列に設定されます。 BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形。 WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルから[ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。  
  
 (メッセージの割り当てまたは式図形) から次の例は、コンテキスト プロパティを設定する文字列を示しています。  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>コンテキスト プロパティを設定する XmlDocument の作成  
 設定することができます、 **WCF です。OutboundCustomHeaders**コンテキスト プロパティを作成して、 **XmlDocument**との文字列値を書き込み、 **XmlDocument**をコンテキスト プロパティ。 型の変数を宣言する**XMLDocument**し、XML データを割り当てます。  
  
 次の例は、型の変数を宣言することを示しています。 **XMLDocument**と XML データの割り当て。  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 次の例では、コンテキスト プロパティの設定を示しています。  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)します。 呼び出し元の詳細については[!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)]クラスを参照してください[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)   
 [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)