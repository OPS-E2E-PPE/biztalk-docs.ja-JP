---
title: "呼び出す、フラット ファイルの解析エンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- IFFDocumentSpec interface
- pipeline components [custom], flat file documents
- pipeline components [custom], engines
ms.assetid: 9c5d325e-2fae-4291-af13-3fb06657ec0e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90108ff2ade354c51f87499a388ae54135f14c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoking-the-flat-file-parsing-engine"></a>フラット ファイル解析エンジンの呼び出し
呼び出すことによって、フラット ファイル解析エンジンを呼び出すことができます、**解析**のメソッド、 **IFFDocumentSpec**インターフェイスで、型キャストからは、さらに、`IDocumentSpec Interface`から取得した、 **この**です。 **XmlReader**から返される、**解析**メソッドにより、一度に 1 つのノードを取得するクライアントは、これは、パーサーをカスタマイズする良い機会です。  
  
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