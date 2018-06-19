---
title: スキーマを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 6a7cb71319fef61d3b6cb854b04b41e3815a6129
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287242"
---
# <a name="using-schemas"></a>スキーマの使用
ここでは、スキーマの使用に関連する一般的なタスクのコード例を示します。  
  
## <a name="using-xsd-schemas"></a>XSD スキーマの使用  
 `IDocumentSpec Interface`インターフェイスは、XML スキーマ定義言語 (XSD) スキーマで定義されているドキュメント図形を表します。 図形は、XSD の最上位の要素をルートとします。 スキーマのインストール後に呼び出すことによって取得できます、`IPipelineContext.GetDocumentSpecByType Method`または`IPipelineContext.GetDocumentSpecByName Method`内のメソッド、 **IPipelineContext**インターフェイスです。  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a>XSD フラット ファイル スキーマの使用  
 両方の**GetDocumentSpecByType**と**GetDocumentSpecByName**を返し、 **IDocumentSpec**インターフェイスです。 型キャストできますスキーマが実際には、(1 つ追加のフラット ファイル固有の注釈が含まれている) フラット ファイル スキーマの場合、 **IDocumentSpec**に**IFFDocumentSpec**解析とシリアル化を開始そこからのシーケンス。  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a>参照  

[解析およびシリアル化エンジンを使用します。](../core/using-the-parsing-and-serializing-engines.md)