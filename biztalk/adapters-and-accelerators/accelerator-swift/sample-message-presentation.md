---
title: サンプル メッセージ プレゼンテーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, SWIFT message block
- SWIFT messages, message block example
ms.assetid: 3136a7da-658d-4100-bbe5-2186ee8bafd1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4223127d483ee4ded16e657a1214161e7f8b6791
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530097"
---
# <a name="sample-message-presentation"></a>サンプル メッセージ プレゼンテーション
SWIFT メッセージのブロック レイアウトの例を次の表に示します。  
  
|[ブロック]|例|  
|-----------|-------------|  
|**ブロック 1**基本ヘッダー|{1:F01BCITITMMAXXX0012000123}|  
|**ブロック 2** (I) (SWIFT) にアプリケーション ヘッダーの入力<br /><br /> または<br /><br /> **ブロック 2** (SWIFT) から (O) アプリケーション ヘッダーを出力|{2:I103VBOEATWWXXXXN} Or {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3|  
|**ブロック 3**ユーザー ヘッダー|{3: {108:BCITITMMA950906}}|  
|**ブロック 4**テキスト|{4:\<CRLF\> : 20:1234567890\<CRLF\> : 23B:CRED\<CRLF\> : 32A:010605GBP45000、\<CRLF\> : 33B:GBP45000、\<CRLF\> : 50K:MASTERS インポート\<CRLF\> RUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> : 52A:BNPAFRPPCAM\<CRLF\> : 53A:POCIITMM680\<CRLF\> : 57A:BCITITMM680\<CRLF\> : 59:/P03452032022819 30\<CRLF\>総計インポート\<CRLF\> PESCARA\<CRLF\> : 70:/ドキュメントを RFB/INV 5591\<CRLF\> : 71A:SHA\<CRLF\> -}|  
|**ブロック 5**トレーラー|{5: {MAC: 12345678} {CHK:123456789ABC}}|  
  
## <a name="see-also"></a>参照  
 [SWIFT スキーマ](../../adapters-and-accelerators/accelerator-swift/swift-schemas.md)