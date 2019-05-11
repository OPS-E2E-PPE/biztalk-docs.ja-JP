---
title: 送信先 URL のプロパティに関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98220fbc5ec99780d230c46751b903cf34167d8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254876"
---
# <a name="restrictions-on-the-destination-url-property"></a>送信先 URL のプロパティに関する制限事項
リンク先の URL は、HTTP プロトコルを使用してメッセージを送信する HTTP サーバーのアドレスを指定する文字列です。  
  
 送信先 URL のプロパティには、次の規則と制限事項が適用されます。  
  
-   常に次の形式で送信先 URL のプロパティを指定する必要があります。  
  
     http [s]://\<ホスト\>[:\<ポート\>] [/\<パス\>[/\<ファイル\>[でしょうか\<。クエリ文字列\>]]  
  
-   文字列全体または可能性がありますいない URI でエンコードします。  
  
-   クエリ文字列を除く、全体の文字列には、次の文字を含めることはできません: \< \> : \ &#124; "でしょうか。 *.  
  
-   プロパティは区別されません。  
  
-   文字列の長さは 256 文字を超えない必要があります。  
  
## <a name="see-also"></a>参照  
 [HTTP 送信ポートの構成](../core/configuring-an-http-send-port.md)