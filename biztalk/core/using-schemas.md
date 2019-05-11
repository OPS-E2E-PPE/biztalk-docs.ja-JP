---
title: スキーマの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], schemas
ms.assetid: 07e60532-1032-422d-865e-0bd65c45dab6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0343514562effd3de12141f5c569ece1f5de29b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395376"
---
# <a name="using-schemas"></a>スキーマの使用
このセクションでは、スキーマの使用に関連する一般的なタスクのコード例を示します。  
  
## <a name="using-xsd-schemas"></a>XSD スキーマの使用  
 `IDocumentSpec Interface`インターフェイスは、XML スキーマ定義言語 (XSD) スキーマで定義されているドキュメント図形を表します。 図形がルート、XSD の最上位要素になります。 スキーマがインストールされている場合、その後呼び出すことによって取得できます、`IPipelineContext.GetDocumentSpecByType Method`または`IPipelineContext.GetDocumentSpecByName Method`メソッド、 **IPipelineContext**インターフェイス。  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a>XSD フラット ファイル スキーマの使用  
 両方の**GetDocumentSpecByType**と**GetDocumentSpecByName**メソッドを返す、 **IDocumentSpec**インターフェイス。 型キャストできますスキーマが実際には、(1 つ追加のフラット ファイル固有の注釈が含まれている) フラット ファイル スキーマの場合、 **IDocumentSpec**に**IFFDocumentSpec**解析とシリアル化を開始そこからシーケンス。  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a>参照  

[解析エンジンおよびシリアル化エンジンの使用](../core/using-the-parsing-and-serializing-engines.md)