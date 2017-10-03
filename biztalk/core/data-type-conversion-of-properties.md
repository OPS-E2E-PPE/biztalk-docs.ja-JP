---
title: "データ型のプロパティの変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f1d0a20a48f0683a15588891ef3fe60889cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-conversion-of-properties"></a>プロパティのデータ型の変換
MQSeries メッセージのヘッダー プロパティは、そのメッセージ自体に含まれているデータ構造です。 MQSeries アダプタでは、メッセージの送受信時に MQSeries メッセージ ヘッダーの特定の値を自動的に検証および変換します。  
  
 次の表では、MQSeries データ型と、それらの検証および変換について説明します。  
  
|MQSeries データ型|検証と変換|  
|------------------------|-------------------------------|  
|MQLONG|MQSeries によって検証が行われます。 長整数に変換されます。 値が無効である場合、メッセージは MQSeries キューに送信されません。|  
|MQCHAR|文字列に変換されます。|  
|MQBYTE|数字の 16 進値を表す、文字 0 ～ 9、a ～ f、または A ～ F が含まれた文字列に変換されます。|  
  
 ほとんどの MQSeries プロパティは、32 ビット (4 バイト) の符号なし整数です。 **Uint**共通言語仕様 (CLS) ではありません-準拠型で、割り当てる必要がありますに**オブジェクト**.NET メソッドで使用する前に型です。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)   
 [BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md)   
 [MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)