---
title: "パイプライン コンポーネントにおける SOAP ヘッダーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
- Web services, SOAP headers
- creating, SOAP headers
ms.assetid: 5b4a8902-e8f5-44a4-88f7-17f47a9deecd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c11b74aafe53150ced42d0c53a2e19a2c5080fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-pipeline-components"></a><span data-ttu-id="a5faf-102">パイプライン コンポーネントにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="a5faf-102">Using SOAP Headers in Pipeline Components</span></span>
<span data-ttu-id="a5faf-103">パイプライン コンポーネントでは、SOAP ヘッダー コンテキスト プロパティにアクセスするに使用するコンテキスト プロパティ名とターゲットの名前空間の組み合わせで説明したよう[オーケストレーションの SOAP ヘッダーを使用して](../core/using-soap-headers-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="a5faf-103">To access the SOAP header context properties in pipeline components, you use a combination of the context property name and target namespace as discussed in [Using SOAP Headers in Orchestrations](../core/using-soap-headers-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="a5faf-104">次のコード例では、要求 SOAP ヘッダーを設定、プロパティ名の送信パイプライン コンポーネントで**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="a5faf-104">The following code example sets the request SOAP header in a send pipeline component for a property name **OrigDest**:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<?xml version=\"1.0\"?>  
          <OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </OrigDest>";  
inmsg.Context.Write("OrigDest","http://schemas.microsoft.com/BizTalk/2003/SOAPHeader", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 <span data-ttu-id="a5faf-105">パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="a5faf-105">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5faf-106">オーケストレーションから Web サービスを使用する (呼び出す) 場合、SOAP アダプタは、パススルー スタイルの受信パイプラインおよび送信パイプラインのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a5faf-106">When you consume (call) Web services from an orchestration, the SOAP adapter only supports pass-through style receive and send pipelines.</span></span> <span data-ttu-id="a5faf-107">カスタム パイプラインを使用できますが、メッセージのボディ部を変更するコンポーネントを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="a5faf-107">You can use a custom pipeline, but it cannot contain components that modify the body parts of the message.</span></span> <span data-ttu-id="a5faf-108">これらのコンポーネントには、XML アセンブラ、XML 逆アセンブラ、および XML 検証の各コンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5faf-108">These components include the XML Assembler, XML Disassembler, and XML Validator components.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5faf-109">参照</span><span class="sxs-lookup"><span data-stu-id="a5faf-109">See Also</span></span>  
 <span data-ttu-id="a5faf-110">[既定のパイプライン](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="a5faf-110">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 [<span data-ttu-id="a5faf-111">使用する Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a5faf-111">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)