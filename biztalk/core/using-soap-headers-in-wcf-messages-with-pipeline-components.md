---
title: パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: b02f2913-4948-4de9-bc59-73bab40aa1a0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6501a08e66c6ef66fbe89ae08117c8db23eacbd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321816"
---
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a>パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用
パイプライン コンポーネントにおける WCF アダプタでは、カスタム SOAP ヘッダーを設定できます。 コンテキスト プロパティ名の組み合わせを使用する**OutboundCustomHeaders**、ターゲットの名前空間 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**します。 使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー** \>ルート要素としての要素。 内ですべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。 カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** / \>を**OutboundCustomHeaders**プロパティ。 WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルから[ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。  
  
 次のコード例では、カスタム SOAP ヘッダーを設定という名前のプロパティの送信パイプライン コンポーネントで**OutboundCustomHeaders**:  
  
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
>  WCF インフラストラクチャが Ws-addressing などの Web サービス標準を使用する標準 SOAP ヘッダーを設定する必要がありますできません、Ws-security、WS-AtomicTransaction します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)   
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)