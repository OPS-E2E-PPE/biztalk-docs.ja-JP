---
title: "パイプライン コンポーネントでの SOAP ヘッダーへのアクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
ms.assetid: a2fb074e-0fde-487e-a6ec-7e2b543b7c8b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e484b221df54f00b02f20ef89466fed6b99cd69d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="accessing-soap-headers-in-pipeline-components"></a><span data-ttu-id="5dd43-102">パイプライン コンポーネントでの SOAP ヘッダーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5dd43-102">Accessing SOAP Headers in Pipeline Components</span></span>
<span data-ttu-id="5dd43-103">パイプライン コンポーネントでは、SOAP ヘッダーのコンテキスト プロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5dd43-103">You can access SOAP header context properties in pipeline components.</span></span> <span data-ttu-id="5dd43-104">コンテキスト プロパティ名とターゲットの名前空間の組み合わせを使用する**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**です。</span><span class="sxs-lookup"><span data-stu-id="5dd43-104">You use a combination of the context property name and the target namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.</span></span>  
  
 <span data-ttu-id="5dd43-105">次のコード例は、要求 SOAP ヘッダーを受信パイプライン コンポーネントのプロパティの取得**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="5dd43-105">The following code example gets the request SOAP header in a receive pipeline component for the property **OrigDest**:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
   {  
   string stringVar = inmsg.Context.Read("OrigDest",    "http://schemas.microsoft.com/BizTalk/2003/SOAPHeader").ToString();  
   }  
   catch (Exception ex)  
   {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
   }  
return inmsg;  
}  
```  
  
 <span data-ttu-id="5dd43-106">パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="5dd43-106">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd43-107">参照</span><span class="sxs-lookup"><span data-stu-id="5dd43-107">See Also</span></span>  
 [<span data-ttu-id="5dd43-108">公開済み Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="5dd43-108">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)