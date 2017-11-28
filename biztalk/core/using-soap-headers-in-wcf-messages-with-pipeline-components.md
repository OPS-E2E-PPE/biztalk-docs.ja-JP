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
ms.openlocfilehash: bf40cf5a81188dae0174199f16229daf61115796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a><span data-ttu-id="29804-102">パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="29804-102">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>
<span data-ttu-id="29804-103">パイプライン コンポーネントの WCF アダプタでカスタム SOAP ヘッダーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="29804-103">You can set the custom SOAP headers with the WCF adapters in pipeline components.</span></span> <span data-ttu-id="29804-104">コンテキスト プロパティ名の組み合わせを使用する**OutboundCustomHeaders**、およびターゲットの名前空間**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**です。</span><span class="sxs-lookup"><span data-stu-id="29804-104">You use a combination of the context property name, **OutboundCustomHeaders**, and the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span></span> <span data-ttu-id="29804-105">使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー**> 要素をルート要素として。</span><span class="sxs-lookup"><span data-stu-id="29804-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**> element as the root element.</span></span> <span data-ttu-id="29804-106">内のすべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー**> 要素。</span><span class="sxs-lookup"><span data-stu-id="29804-106">All of the custom SOAP headers must be placed inside the \<**headers**> element.</span></span> <span data-ttu-id="29804-107">カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**>\</**ヘッダー**> または\< **ヘッダー**/> に、 **OutboundCustomHeaders**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="29804-107">If the custom SOAP header value is an empty string, you must assign \<**headers**>\</**headers**> or \<**headers**/> to the **OutboundCustomHeaders** property.</span></span> <span data-ttu-id="29804-108">WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、with the WCF Adapters」カスタム SOAP ヘッダーを使用して、SDK サンプルから[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)です。</span><span class="sxs-lookup"><span data-stu-id="29804-108">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="29804-109">次のコード例は、という名前のプロパティの送信パイプライン コンポーネントでカスタム SOAP ヘッダーを設定**OutboundCustomHeaders**:</span><span class="sxs-lookup"><span data-stu-id="29804-109">The following code example sets custom SOAP headers in a send pipeline component for a property named **OutboundCustomHeaders**:</span></span>  
  
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
  
 <span data-ttu-id="29804-110">パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="29804-110">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29804-111">WCF インフラストラクチャが WS-Addressing、WS-Security、WS-AtomicTransaction などの Web サービス標準に対して使用する標準 SOAP ヘッダーは設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="29804-111">You must not set the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29804-112">参照</span><span class="sxs-lookup"><span data-stu-id="29804-112">See Also</span></span>  
 <span data-ttu-id="29804-113">[オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="29804-113">[Using SOAP Headers in WCF Messages with Orchestrations](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span></span>  
 <span data-ttu-id="29804-114">[消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="29804-114">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 <span data-ttu-id="29804-115">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="29804-115">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="29804-116">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="29804-116">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)