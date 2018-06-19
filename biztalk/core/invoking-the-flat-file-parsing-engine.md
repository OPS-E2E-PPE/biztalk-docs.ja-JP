---
title: 呼び出す、フラット ファイルの解析エンジン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- IFFDocumentSpec interface
- pipeline components [custom], flat file documents
- pipeline components [custom], engines
ms.assetid: 9c5d325e-2fae-4291-af13-3fb06657ec0e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90108ff2ade354c51f87499a388ae54135f14c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261842"
---
# <a name="invoking-the-flat-file-parsing-engine"></a><span data-ttu-id="fd238-102">フラット ファイル解析エンジンの呼び出し</span><span class="sxs-lookup"><span data-stu-id="fd238-102">Invoking the Flat File Parsing Engine</span></span>
<span data-ttu-id="fd238-103">呼び出すことによって、フラット ファイル解析エンジンを呼び出すことができます、**解析**のメソッド、 **IFFDocumentSpec**インターフェイスで、型キャストからは、さらに、`IDocumentSpec Interface`から取得した、 **この**です。</span><span class="sxs-lookup"><span data-stu-id="fd238-103">The flat file parsing engine can be invoked by calling the **Parse** method of the **IFFDocumentSpec** interface, which in turn is typecast from the `IDocumentSpec Interface` retrieved from the **PipelineContext**.</span></span> <span data-ttu-id="fd238-104">**XmlReader**から返される、**解析**メソッドにより、一度に 1 つのノードを取得するクライアントは、これは、パーサーをカスタマイズする良い機会です。</span><span class="sxs-lookup"><span data-stu-id="fd238-104">Because the **XmlReader** returned from the **Parse** method allows clients to retrieve one node at a time, this is a good opportunity to customize the parser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd238-105">例</span><span class="sxs-lookup"><span data-stu-id="fd238-105">Example</span></span>  
  
```  
XmlReader xr = docspec.Parse(new DataReader());  
while (xr.Read())  
{  
   switch(xr.NodeType)  
   {  
      case XmlNodeType.Element :  
         // Customize the element  
         //   
         break;  
      case XmlNodeType.Attribute :  
         // Customize the attribute  
         //   
         break;  
      // Customize other types of nodes  
      //   
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd238-106">参照</span><span class="sxs-lookup"><span data-stu-id="fd238-106">See Also</span></span>  
 [<span data-ttu-id="fd238-107">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="fd238-107">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)