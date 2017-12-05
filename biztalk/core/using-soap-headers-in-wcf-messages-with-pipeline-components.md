---
title: "パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: b02f2913-4948-4de9-bc59-73bab40aa1a0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce166c5d05b8ce48f513420e247e8f35ca1d509
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a>パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用
パイプライン コンポーネントの WCF アダプタでカスタム SOAP ヘッダーを設定できます。 コンテキスト プロパティ名の組み合わせを使用する**OutboundCustomHeaders**、およびターゲットの名前空間**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**です。 使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー** \>ルート要素としての要素。 内のすべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。 カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** / \>を**OutboundCustomHeaders**プロパティです。 WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、with the WCF Adapters」カスタム SOAP ヘッダーを使用して、SDK サンプルから[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)です。  
  
 次のコード例は、という名前のプロパティの送信パイプライン コンポーネントでカスタム SOAP ヘッダーを設定**OutboundCustomHeaders**:  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<headers>  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </headers>";  
inmsg.Context.Write("OutboundCustomHeaders","http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。  
  
> [!NOTE]
>  WCF インフラストラクチャが WS-Addressing、WS-Security、WS-AtomicTransaction などの Web サービス標準に対して使用する標準 SOAP ヘッダーは設定しないでください。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)   
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)