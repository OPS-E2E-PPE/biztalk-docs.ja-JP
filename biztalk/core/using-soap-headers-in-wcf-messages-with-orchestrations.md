---
title: "オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7492ac6e1f8e43559fa921f9ddd3b60d644fe5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a>オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用
コンテキスト プロパティを使用するオーケストレーションでの送信 WCF メッセージでは、カスタムの SOAP ヘッダーを送信する**WCF です。OutboundCustomHeaders**です。 WCF アダプタは、カスタムの SOAP ヘッダーを、WCF インフラストラクチャが WS-Addressing、WS-Security、WS-AtomicTransaction などの Web サービス標準に使用する標準 SOAP ヘッダーと組み合わせて送信します。 使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー**> 要素をルート要素として。 内のすべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー**> 要素。 カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**>\</**ヘッダー**> または\< **ヘッダー**/> に、 **OutboundCustomHeaders**プロパティです。  
  
 オーケストレーションでは、SOAP ヘッダーのコンテキスト プロパティは、XML データを含む文字列に設定されます。 BizTalk 式エディターを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形です。 WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、with the WCF Adapters」カスタム SOAP ヘッダーを使用して、SDK サンプルから[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)です。  
  
 次の (メッセージの割り当て図形または式図形の) 例は、コンテキスト プロパティの設定方法を示しています。  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>XmlDocument の作成によるコンテキスト プロパティの設定  
 設定することができます、 **WCF です。OutboundCustomHeaders**コンテキスト プロパティを作成して、 **XmlDocument**と書き込みの文字列値、 **XmlDocument**をコンテキスト プロパティです。 型の変数を宣言する**XMLDocument**し、XML データを割り当てます。  
  
 次の例は、型の変数を宣言することを示しています。 **XMLDocument**と XML データの割り当て。  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 次の例は、コンテキスト プロパティの設定方法を示しています。  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。 呼び出し元の詳細については[!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)]クラスを参照してください[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)   
 [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)