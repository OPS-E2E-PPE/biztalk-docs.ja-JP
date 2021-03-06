---
title: 送信パーティ解決の AS2 コンテキスト プロパティの書き込み |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 603d4ce029f3518f262274767da2a2da3e819eb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262055"
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a>送信パーティ解決の AS2 コンテキスト プロパティの書き込み
送信 AS2 メッセージのアグリーメントの解決は、AS2To コンテキスト プロパティまたは AS2To プロパティを使用して実行できる、`Http.UserHttpHeaders`コンテキスト プロパティ。 ただし、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 メッセージを受信すると、コンテキストに AS2To プロパティを書き込みません。 AS2To または UserHttpHeaders コンテキスト プロパティでアグリーメントの解決を実行する場合は、カスタム オーケストレーションまたはカスタム パイプライン コンポーネントを記述があります。 これは、機能は、送信ポートがアグリーメントにリンクされていない場合にのみ必要です。  
  
 カスタム オーケストレーションでは、AS2 を追加することができます-を既存の先頭に`Http.UserHttpHeaders`次のコードを使用してコンテキストのプロパティ。  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 カスタム パイプライン コンポーネントでは、AS2 を追加することができます-を既存の先頭に`Http.UserHttpHeaders`コンテキスト プロパティを次のコードを使用します。 AS2 を追加する必要があるのに`Http.UserHttpHeaders`コンテキスト プロパティ、メッセージが As2Encoder コンポーネントによって処理される前にします。  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 昇格の詳細については、`EDIIntAS.AS2To`プロパティまたは`BTS.UseHttpHeaders`コンテキストにプロパティの「AS2 ヘッダー コンテキスト プロパティの昇格」を参照してください、 [FILE 送信ポートを経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)します。  
  
 コード用 HTTP からヘッダーを書き込むためのカスタム パイプライン コンポーネントに追加することができます。メッセージに UserHttpHeaders コンテキスト プロパティを参照してください[FILE 送信ポートを経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)