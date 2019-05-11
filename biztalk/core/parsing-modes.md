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
# <a name="parsing-modes"></a>解析モード
解析モードは schemaInfo レコードの 2 つのモードでの属性: 速度と複雑さです。 パーサーの最適化のプロパティは、BizTalk スキーマ エディター内で構成できます。  
  
## <a name="example"></a>例  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 Speed モードの場合、パーサーはストリームに表示されるデータに合わせてしようとします。 たとえば、次のスキーマを与えられます。  
  
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
  
 入力メッセージ。  
  
```  
,1,2,3,4  
```  
  
 speed モード、次の XML では、ドキュメントが取得されます。  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 Complexity モードでは、同じスキーマには、次の出力が生成されます。  
  
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
  
 Complexity モードの場合、フラット ファイル解析エンジンは、上から下へとボトムアップの両方の解析、使用より正確にデータを格納しようとします。 Speed モードの場合、パーサーはストリームに表示されるデータに合わせてしようとします。  
  
 たとえばがある必須の要素と省略可能な要素です。 場合、  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 パーサーは、スキーマを表すために、データを正しく解析する complexity モードを使用する必要がありますとして内部的にします。  
  
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