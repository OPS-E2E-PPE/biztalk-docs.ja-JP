---
title: 解析モード |Microsoft ドキュメント
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
ms.openlocfilehash: cf8f9b2618b8cafd7813f08217457227a0f21809
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263306"
---
# <a name="parsing-modes"></a>解析モード
解析モードは schemaInfo レコードの 2 つのモードでの属性: 速度と複雑度。 "パーサーの最適化" プロパティは、BizTalk スキーマ エディター内で構成できます。  
  
## <a name="example"></a>例  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 speed モードの場合、パーサーはストリームで出現する順序に従ってデータの処理を試みます。 たとえば、次のようなスキーマがあるとします。  
  
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
  
 入力メッセージは次のとおりです。  
  
```  
,1,2,3,4  
```  
  
 speed モードでは、次の XML ドキュメントが得られます。  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 complexity モードでは、同じスキーマで次の出力が生成されます。  
  
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
  
 complexity モードの場合、フラット ファイル解析エンジンは先頭からと末尾からの両方向で解析を行い、より正確なデータの処理を試みます。 speed モードの場合、パーサーはストリームで出現する順序に従ってデータの処理を試みます。  
  
 たとえば、次のように必須要素と省略可能要素があるとします。  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 この場合、パーサーはスキーマを内部的に次のように表現するため、データを正しく解析するには complexity モードを使用する必要があります。  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a>参照  
 [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)