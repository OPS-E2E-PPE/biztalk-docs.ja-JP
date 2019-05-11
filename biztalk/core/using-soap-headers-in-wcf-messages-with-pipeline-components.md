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
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a><span data-ttu-id="779fc-102">パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="779fc-102">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>
<span data-ttu-id="779fc-103">パイプライン コンポーネントにおける WCF アダプタでは、カスタム SOAP ヘッダーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="779fc-103">You can set the custom SOAP headers with the WCF adapters in pipeline components.</span></span> <span data-ttu-id="779fc-104">コンテキスト プロパティ名の組み合わせを使用する**OutboundCustomHeaders**、ターゲットの名前空間 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**します。</span><span class="sxs-lookup"><span data-stu-id="779fc-104">You use a combination of the context property name, **OutboundCustomHeaders**, and the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span></span> <span data-ttu-id="779fc-105">使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー** \>ルート要素としての要素。</span><span class="sxs-lookup"><span data-stu-id="779fc-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="779fc-106">内ですべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。</span><span class="sxs-lookup"><span data-stu-id="779fc-106">All of the custom SOAP headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="779fc-107">カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** / \>を**OutboundCustomHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="779fc-107">If the custom SOAP header value is an empty string, you must assign \<**headers**\>\</**headers**\> or \<**headers**/\> to the **OutboundCustomHeaders** property.</span></span> <span data-ttu-id="779fc-108">WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルから[ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。</span><span class="sxs-lookup"><span data-stu-id="779fc-108">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="779fc-109">次のコード例では、カスタム SOAP ヘッダーを設定という名前のプロパティの送信パイプライン コンポーネントで**OutboundCustomHeaders**:</span><span class="sxs-lookup"><span data-stu-id="779fc-109">The following code example sets custom SOAP headers in a send pipeline component for a property named **OutboundCustomHeaders**:</span></span>  
  
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
  
 <span data-ttu-id="779fc-110">パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="779fc-110">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="779fc-111">WCF インフラストラクチャが Ws-addressing などの Web サービス標準を使用する標準 SOAP ヘッダーを設定する必要がありますできません、Ws-security、WS-AtomicTransaction します。</span><span class="sxs-lookup"><span data-stu-id="779fc-111">You must not set the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="779fc-112">参照</span><span class="sxs-lookup"><span data-stu-id="779fc-112">See Also</span></span>  
 <span data-ttu-id="779fc-113">[オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="779fc-113">[Using SOAP Headers in WCF Messages with Orchestrations](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span></span>  
 <span data-ttu-id="779fc-114">[消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="779fc-114">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 <span data-ttu-id="779fc-115">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="779fc-115">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="779fc-116">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="779fc-116">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)