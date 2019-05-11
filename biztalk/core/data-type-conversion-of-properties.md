---
title: データ型のプロパティの変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3846fa8cb6fe30e1cae561f7652aba0a02944a28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353040"
---
# <a name="data-type-conversion-of-properties"></a>プロパティのデータ型変換
MQSeries メッセージ ヘッダー プロパティは、メッセージ自体に含まれているデータ構造です。 MQSeries アダプターは自動的に検証し、メッセージを送受信するときに、MQSeries メッセージ ヘッダーで特定の値に変換します。  
  
 次の表では、MQSeries データ型と、検証と変換について説明します。  
  
|MQSeries データ型|検証と変換|  
|------------------------|-------------------------------|  
|MQLONG|MQSeries は、検証を実行します。 長整数に変換します。 無効な値では、メッセージが MQSeries キューに移動できなくなります。|  
|MQCHAR|文字列に変換します。|  
|MQBYTE|0 ~ 9 および a ~ f、または A ~ F、16 進数の値を表すを含む文字列に変換します。|  
  
 MQSeries プロパティの多くは、32 ビット (4 バイト) 符号なし整数です。 **Uint**共通言語仕様 (CLS) ではありません-準拠型で、割り当てる必要がありますに**オブジェクト**型 .NET メソッドで使用する前にします。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)   
 [BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md)   
 [MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)