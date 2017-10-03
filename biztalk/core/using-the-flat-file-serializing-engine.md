---
title: "使用して、フラット ファイルのシリアル化エンジン |Microsoft ドキュメント"
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
ms.assetid: 0a519f0f-392b-4fa3-ab08-f09012d033af
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4f39f42c3513932b54a92946e448d821ee362a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-flat-file-serializing-engine"></a>フラット ファイルのシリアル化エンジンを使用します。
フラット ファイルのシリアル化エンジンが呼び出すことによって呼び出される、 **Serialize**のメソッド、 **IFFDocumentSpec**インターフェイスです。 により、カスタマイズされた**XmlReader**メソッドの引数、最後のデータをシリアル化を制御することができます。 データは任意の形式にできます。また、単純に XmlDocument で作成したデータ リーダーにすることもできます。  
  
## <a name="example"></a>例  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a>参照  
 [Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx)   
 [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)