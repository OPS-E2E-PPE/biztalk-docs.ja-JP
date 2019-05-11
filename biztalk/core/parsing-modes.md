---
title: 解析モード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], parsing
ms.assetid: b1188720-e5ae-47ae-ab8e-16d7ed08b778
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72955f1dd560a442e011e176007defa236d39386
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395050"
---
# <a name="parsing-modes"></a><span data-ttu-id="3238c-102">解析モード</span><span class="sxs-lookup"><span data-stu-id="3238c-102">Parsing Modes</span></span>
<span data-ttu-id="3238c-103">解析モードは schemaInfo レコードの 2 つのモードでの属性: 速度と複雑さです。</span><span class="sxs-lookup"><span data-stu-id="3238c-103">The parsing mode is an attribute on the schemaInfo record, with two modes: speed and complexity.</span></span> <span data-ttu-id="3238c-104">パーサーの最適化のプロパティは、BizTalk スキーマ エディター内で構成できます。</span><span class="sxs-lookup"><span data-stu-id="3238c-104">The Parser Optimization property can be configured within the BizTalk Schema Editor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3238c-105">例</span><span class="sxs-lookup"><span data-stu-id="3238c-105">Example</span></span>  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 <span data-ttu-id="3238c-106">Speed モードの場合、パーサーはストリームに表示されるデータに合わせてしようとします。</span><span class="sxs-lookup"><span data-stu-id="3238c-106">In speed mode, the parser tries to fit data as they appear in the stream.</span></span> <span data-ttu-id="3238c-107">たとえば、次のスキーマを与えられます。</span><span class="sxs-lookup"><span data-stu-id="3238c-107">For example, given the following schema.</span></span>  
  
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
  
 <span data-ttu-id="3238c-108">入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="3238c-108">and input message.</span></span>  
  
```  
,1,2,3,4  
```  
  
 <span data-ttu-id="3238c-109">speed モード、次の XML では、ドキュメントが取得されます。</span><span class="sxs-lookup"><span data-stu-id="3238c-109">with speed mode the following XML document is obtained.</span></span>  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 <span data-ttu-id="3238c-110">Complexity モードでは、同じスキーマには、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3238c-110">With complexity mode, the same schema produces the following output.</span></span>  
  
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
  
 <span data-ttu-id="3238c-111">Complexity モードの場合、フラット ファイル解析エンジンは、上から下へとボトムアップの両方の解析、使用より正確にデータを格納しようとします。</span><span class="sxs-lookup"><span data-stu-id="3238c-111">In complexity mode, the flat file parsing engine uses both top-down and bottom-up parsing, and tries to fit data more accurately.</span></span> <span data-ttu-id="3238c-112">Speed モードの場合、パーサーはストリームに表示されるデータに合わせてしようとします。</span><span class="sxs-lookup"><span data-stu-id="3238c-112">In speed mode, the parser tries to fit data as they appear in the stream.</span></span>  
  
 <span data-ttu-id="3238c-113">たとえばがある必須の要素と省略可能な要素です。 場合、</span><span class="sxs-lookup"><span data-stu-id="3238c-113">If you have optional elements with required elements, for example.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 <span data-ttu-id="3238c-114">パーサーは、スキーマを表すために、データを正しく解析する complexity モードを使用する必要がありますとして内部的にします。</span><span class="sxs-lookup"><span data-stu-id="3238c-114">you must use complexity mode to correctly parse the data, because the parser represents the schema internally as.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a><span data-ttu-id="3238c-115">参照</span><span class="sxs-lookup"><span data-stu-id="3238c-115">See Also</span></span>  
 [<span data-ttu-id="3238c-116">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="3238c-116">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)