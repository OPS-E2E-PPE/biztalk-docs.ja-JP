---
title: "送信パーティ解決の AS2 コンテキスト プロパティの書き込み |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c89804c42554825e387d01ff592e3a628e8225b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a>送信パーティ解決のための AS2 コンテキスト プロパティの記述
発信 AS2 メッセージのアグリーメント解決は、AS2To コンテキスト プロパティ、または `Http.UserHttpHeaders` コンテキスト プロパティの AS2To プロパティを使用して実行できます。 しかし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が AS2 メッセージを受信したとき、AS2To プロパティはコンテキストに書き込まれません。 AS2To コンテキスト プロパティまたは UserHttpHeaders コンテキスト プロパティでアグリーメント解決を実行する場合は、アグリーメント解決を実行するカスタム オーケストレーションまたはカスタム パイプライン コンポーネントを記述する必要があります。 これは、送信ポートがアグリーメントにリンクされていない場合にのみ必要です。  
  
 カスタム オーケストレーションでは、次のコードを使用して、AS2-To を既存の `Http.UserHttpHeaders` コンテキスト プロパティの先頭に追加できます。  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 カスタム パイプライン コンポーネントでは、次のコードを使用して、AS2-To を既存の `Http.UserHttpHeaders` コンテキスト プロパティの先頭に追加できます。 AS2-To は、メッセージが As2Encoder コンポーネントによって処理される前に `Http.UserHttpHeaders` コンテキスト プロパティに追加する必要があります。  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 昇格の詳細については、`EDIIntAS.AS2To`プロパティまたは`BTS.UseHttpHeaders`、コンテキスト プロパティの AS2 ヘッダー コンテキスト プロパティの昇格」を参照してください、 [FILE 送信ポート経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)です。  
  
 HTTP ヘッダーを書き込むためのカスタム パイプライン コンポーネントに追加できるコードです。メッセージに UserHttpHeaders コンテキスト プロパティを参照してください[FILE 送信ポート経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)です。  
  
## <a name="see-also"></a>参照  
 [開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)