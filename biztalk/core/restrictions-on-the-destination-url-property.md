---
title: 送信先 URL のプロパティに関する制限事項 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7966fccca324a1453f0ea84e79cd7d9d3d55ad
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="restrictions-on-the-destination-url-property"></a>送信先 URL のプロパティに関する制限事項
送信先 URL とは、HTTP プロトコルを使用して送信するメッセージの送信先となる HTTP サーバーのアドレスを指定する文字列です。  
  
 送信先 URL のプロパティには、次の規則および制限が適用されます。  
  
-   送信先 URL のプロパティは、次の形式で指定する必要があります。  
  
     http [s]://\<ホスト\>[:\<ポート\>] [/\<パス\>[/\<ファイル\>[?\<クエリ文字列\>]]  
  
-   文字列全体は、URI でエンコードできますが、しなくてもかまいません。  
  
-   クエリ文字列を除き、文字列全体には、次の文字を含めることはできません: \< \> : \ &#124; "しますか? *.  
  
-   このプロパティは区別されません。  
  
-   この文字列の長さは 256 文字以下にする必要があります。  
  
## <a name="see-also"></a>参照  
 [HTTP 送信ポートの構成](../core/configuring-an-http-send-port.md)