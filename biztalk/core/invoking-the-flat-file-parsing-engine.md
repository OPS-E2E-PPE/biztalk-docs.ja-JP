---
title: 解析エンジンを呼び出し、フラット ファイル |Microsoft Docs
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
ms.openlocfilehash: 66142e4d70f317d0baeba75cae6b1f1bcb528140
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380852"
---
# <a name="invoking-the-flat-file-parsing-engine"></a>フラット ファイル解析エンジンの呼び出し
フラット ファイル解析エンジンを呼び出すことによって呼び出すことができます、**解析**のメソッド、 **IFFDocumentSpec**から型キャストはさらに、インターフェイス、`IDocumentSpec Interface`から取得した、 **した**します。 **XmlReader**から返される、**解析**メソッド クライアントを一度に 1 つのノードを取得できるように、これは、パーサーをカスタマイズするよい機会です。  
  
## <a name="example"></a>例  
  
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
  
## <a name="see-also"></a>参照  
 [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)