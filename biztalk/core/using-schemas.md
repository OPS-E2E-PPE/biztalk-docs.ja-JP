---
title: "スキーマを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], schemas
ms.assetid: 07e60532-1032-422d-865e-0bd65c45dab6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a7cb71319fef61d3b6cb854b04b41e3815a6129
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-schemas"></a><span data-ttu-id="cae7b-102">スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="cae7b-102">Using Schemas</span></span>
<span data-ttu-id="cae7b-103">ここでは、スキーマの使用に関連する一般的なタスクのコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="cae7b-103">This section contains code examples for common tasks associated with using schemas.</span></span>  
  
## <a name="using-xsd-schemas"></a><span data-ttu-id="cae7b-104">XSD スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="cae7b-104">Using XSD schemas</span></span>  
 <span data-ttu-id="cae7b-105">`IDocumentSpec Interface`インターフェイスは、XML スキーマ定義言語 (XSD) スキーマで定義されているドキュメント図形を表します。 図形は、XSD の最上位の要素をルートとします。</span><span class="sxs-lookup"><span data-stu-id="cae7b-105">The `IDocumentSpec Interface` interface represents a document shape defined by an XML Schema definition language (XSD) schema; the shape is rooted by a top-level element of the XSD.</span></span> <span data-ttu-id="cae7b-106">スキーマのインストール後に呼び出すことによって取得できます、`IPipelineContext.GetDocumentSpecByType Method`または`IPipelineContext.GetDocumentSpecByName Method`内のメソッド、 **IPipelineContext**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="cae7b-106">After the schema is installed, it can be retrieved by calling the `IPipelineContext.GetDocumentSpecByType Method` or `IPipelineContext.GetDocumentSpecByName Method` methods in the **IPipelineContext** interface.</span></span>  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a><span data-ttu-id="cae7b-107">XSD フラット ファイル スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="cae7b-107">Using XSD flat file schemas</span></span>  
 <span data-ttu-id="cae7b-108">両方の**GetDocumentSpecByType**と**GetDocumentSpecByName**を返し、 **IDocumentSpec**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="cae7b-108">Both the **GetDocumentSpecByType** and **GetDocumentSpecByName** methods return the **IDocumentSpec** interface.</span></span> <span data-ttu-id="cae7b-109">型キャストできますスキーマが実際には、(1 つ追加のフラット ファイル固有の注釈が含まれている) フラット ファイル スキーマの場合、 **IDocumentSpec**に**IFFDocumentSpec**解析とシリアル化を開始そこからのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="cae7b-109">If the schema is actually a flat file schema (one that has additional flat file-specific annotations), you can typecast the **IDocumentSpec** into **IFFDocumentSpec** and initiate parsing and serializing sequences from there.</span></span>  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a><span data-ttu-id="cae7b-110">参照</span><span class="sxs-lookup"><span data-stu-id="cae7b-110">See Also</span></span>  

[<span data-ttu-id="cae7b-111">解析およびシリアル化エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="cae7b-111">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)