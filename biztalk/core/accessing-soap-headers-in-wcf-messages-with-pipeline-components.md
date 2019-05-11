---
title: パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, WCF services
- WCF services, pipeline components
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: 5e24afa3-b2e6-472e-8890-a47b59573304
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97488def0187f64c9bdaf0190f891add747c77f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361891"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a>パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス
コンテキスト プロパティ名の組み合わせを使用するパイプライン コンポーネントにおける WCF アダプタで SOAP ヘッダーにアクセスする**InboundHeaders**、ターゲットの名前空間 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**します。 WCF アダプタを受信メッセージのカスタム SOAP ヘッダーと標準 SOAP ヘッダーのコピー、 **InboundHeaders**プロパティ。 WCF アダプタでは、プログラムによって昇格または書き込みをコンテキスト プロパティをプログラムで行うプロパティを選択することもできます。 参照してください[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)の詳細。  
  
 コンテキスト プロパティに含まれる値は、XML データを格納している文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。 WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてで、SDK サンプルの「を使用してカスタム SOAP ヘッダー with the WCF Adapters」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。  
  
 カスタム パイプライン コンポーネントから次のコードでは、要求 SOAP ヘッダーを取得での受信パイプライン コンポーネント、 **InboundHeaders**プロパティ。  
  
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
 [オーケストレーションで WCF メッセージにおける SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)