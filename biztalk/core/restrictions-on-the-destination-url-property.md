---
title: "送信先 URL のプロパティに関する制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0788b693027fb803b121b1b732cb3ee126897e7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-the-destination-url-property"></a>送信先 URL のプロパティに関する制限事項
送信先 URL とは、HTTP プロトコルを使用して送信するメッセージの送信先となる HTTP サーバーのアドレスを指定する文字列です。  
  
 送信先 URL のプロパティには、次の規則および制限が適用されます。  
  
-   送信先 URL のプロパティは、次の形式で指定する必要があります。  
  
     http [s]://\<ホスト > [:\<ポート >] [/\<パス > [/\<ファイル > [?\<クエリ文字列 >]]  
  
-   文字列全体は、URI でエンコードできますが、しなくてもかまいません。  
  
-   クエリ文字列を除き、文字列全体には、次の文字を含めることはできません: \< >: \ & #124 です。" ? *.  
  
-   プロパティは区別されません。  
  
-   この文字列の長さは 256 文字以下にする必要があります。  
  
## <a name="see-also"></a>参照  
 [HTTP 送信ポートの構成](../core/configuring-an-http-send-port.md)