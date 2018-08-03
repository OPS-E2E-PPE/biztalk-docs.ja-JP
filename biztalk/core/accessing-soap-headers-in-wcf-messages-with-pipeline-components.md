---
title: パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス |Microsoft ドキュメント
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
ms.openlocfilehash: bf8bc9c2c17172cb29ee75bfbfc4aaee841848fa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965104"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a><span data-ttu-id="b304a-102">パイプライン コンポーネントにおける WCF メッセージでの SOAP ヘッダーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="b304a-102">Accessing SOAP Headers in WCF Messages with Pipeline Components</span></span>
<span data-ttu-id="b304a-103">コンテキスト プロパティ名の組み合わせを使用するパイプライン コンポーネントにおける WCF アダプターで SOAP ヘッダーにアクセスする**InboundHeaders**、およびターゲットの名前空間**http://schemas.microsoft.com/BizTalk/2006/01、アダプター、WCF-プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="b304a-103">To access the SOAP headers with the WCF adapters in pipeline components, you use a combination of the context property name, **InboundHeaders**, and the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span></span> <span data-ttu-id="b304a-104">WCF アダプタを受信メッセージのカスタム SOAP ヘッダーと標準 SOAP ヘッダーのコピー、 **InboundHeaders**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b304a-104">The WCF adapters copy custom SOAP headers and standard SOAP headers in the inbound messages to the **InboundHeaders** property.</span></span> <span data-ttu-id="b304a-105">WCF アダプターを使用すると、プログラムによってコンテキスト プロパティへの昇格または書き込みを行うプロパティを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="b304a-105">The WCF adapters also allow you to programmatically select the properties you would like to promote or write to the context properties programmatically.</span></span> <span data-ttu-id="b304a-106">参照してください[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="b304a-106">See [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md) for more details.</span></span>  
  
 <span data-ttu-id="b304a-107">コンテキスト プロパティに含まれる値は、使用した XML データを含む文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。</span><span class="sxs-lookup"><span data-stu-id="b304a-107">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="b304a-108">WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてを参照してください「を使用してカスタム SOAP ヘッダー with the WCF Adapters」の SDK サンプル[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)です。</span><span class="sxs-lookup"><span data-stu-id="b304a-108">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample "Using Custom SOAP Headers with the WCF Adapters" at [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="b304a-109">カスタム パイプライン コンポーネントの次のコードでは、要求 SOAP ヘッダーを取得での受信パイプライン コンポーネント、 **InboundHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b304a-109">The following code from a custom pipeline component gets the request SOAP header in a receive pipeline component for the **InboundHeaders** property:</span></span>  
  
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
  
 <span data-ttu-id="b304a-110">パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="b304a-110">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b304a-111">参照</span><span class="sxs-lookup"><span data-stu-id="b304a-111">See Also</span></span>  
 <span data-ttu-id="b304a-112">[オーケストレーションでの WCF メッセージにおける SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="b304a-112">[Accessing SOAP Headers in WCF Messages with Orchestrations](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md) </span></span>  
 <span data-ttu-id="b304a-113">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b304a-113">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="b304a-114">消費済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b304a-114">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)