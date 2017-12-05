---
title: "パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, WCF services
- WCF services, pipeline components
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: 5e24afa3-b2e6-472e-8890-a47b59573304
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8bc9c2c17172cb29ee75bfbfc4aaee841848fa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a>パイプライン コンポーネントにおける WCF メッセージでの SOAP ヘッダーへのアクセス
コンテキスト プロパティ名の組み合わせを使用するパイプライン コンポーネントにおける WCF アダプターで SOAP ヘッダーにアクセスする**InboundHeaders**、およびターゲットの名前空間**http://schemas.microsoft.com/BizTalk/2006/01、アダプター、WCF-プロパティ**です。 WCF アダプタを受信メッセージのカスタム SOAP ヘッダーと標準 SOAP ヘッダーのコピー、 **InboundHeaders**プロパティです。 WCF アダプターを使用すると、プログラムによってコンテキスト プロパティへの昇格または書き込みを行うプロパティを選択することもできます。 参照してください[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)詳細についてはします。  
  
 コンテキスト プロパティに含まれる値は、使用した XML データを含む文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。 WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてを参照してください「を使用してカスタム SOAP ヘッダー with the WCF Adapters」の SDK サンプル[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)です。  
  
 カスタム パイプライン コンポーネントの次のコードでは、要求 SOAP ヘッダーを取得での受信パイプライン コンポーネント、 **InboundHeaders**プロパティ。  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
   {  
   string stringVar = inmsg.Context.Read("InboundHeaders",    "http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties").ToString();  
   }  
   catch (Exception ex)  
   {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
   }  
return inmsg;  
}  
```  
  
 パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでの WCF メッセージにおける SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)