---
title: "解析モード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], parsing
ms.assetid: b1188720-e5ae-47ae-ab8e-16d7ed08b778
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf8f9b2618b8cafd7813f08217457227a0f21809
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="parsing-modes"></a><span data-ttu-id="a6cb3-102">解析モード</span><span class="sxs-lookup"><span data-stu-id="a6cb3-102">Parsing Modes</span></span>
<span data-ttu-id="a6cb3-103">解析モードは schemaInfo レコードの 2 つのモードでの属性: 速度と複雑度。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-103">The parsing mode is an attribute on the schemaInfo record, with two modes: speed and complexity.</span></span> <span data-ttu-id="a6cb3-104">"パーサーの最適化" プロパティは、BizTalk スキーマ エディター内で構成できます。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-104">The Parser Optimization property can be configured within the BizTalk Schema Editor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6cb3-105">例</span><span class="sxs-lookup"><span data-stu-id="a6cb3-105">Example</span></span>  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 <span data-ttu-id="a6cb3-106">speed モードの場合、パーサーはストリームで出現する順序に従ってデータの処理を試みます。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-106">In speed mode, the parser tries to fit data as they appear in the stream.</span></span> <span data-ttu-id="a6cb3-107">たとえば、次のようなスキーマがあるとします。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-107">For example, given the following schema.</span></span>  
  
```  
<schema>  
   Root ("," prefix)  
      Field1   opt  
      Field2   opt  
      Field3   opt  
      Field4   opt  
      Record ("," infix)  
            Field5  
            Field6  
</schema>  
```  
  
 <span data-ttu-id="a6cb3-108">入力メッセージは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-108">and input message.</span></span>  
  
```  
,1,2,3,4  
```  
  
 <span data-ttu-id="a6cb3-109">speed モードでは、次の XML ドキュメントが得られます。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-109">with speed mode the following XML document is obtained.</span></span>  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 <span data-ttu-id="a6cb3-110">complexity モードでは、同じスキーマで次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-110">With complexity mode, the same schema produces the following output.</span></span>  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
      <Record>  
         <Field5>3</Field5>  
         <Field6>4</Field6>  
      </Record>  
</Root>  
```  
  
 <span data-ttu-id="a6cb3-111">complexity モードの場合、フラット ファイル解析エンジンは先頭からと末尾からの両方向で解析を行い、より正確なデータの処理を試みます。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-111">In complexity mode, the flat file parsing engine uses both top-down and bottom-up parsing, and tries to fit data more accurately.</span></span> <span data-ttu-id="a6cb3-112">speed モードの場合、パーサーはストリームで出現する順序に従ってデータの処理を試みます。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-112">In speed mode, the parser tries to fit data as they appear in the stream.</span></span>  
  
 <span data-ttu-id="a6cb3-113">たとえば、次のように必須要素と省略可能要素があるとします。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-113">If you have optional elements with required elements, for example.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 <span data-ttu-id="a6cb3-114">この場合、パーサーはスキーマを内部的に次のように表現するため、データを正しく解析するには complexity モードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cb3-114">you must use complexity mode to correctly parse the data, because the parser represents the schema internally as.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6cb3-115">参照</span><span class="sxs-lookup"><span data-stu-id="a6cb3-115">See Also</span></span>  
 [<span data-ttu-id="a6cb3-116">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="a6cb3-116">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)