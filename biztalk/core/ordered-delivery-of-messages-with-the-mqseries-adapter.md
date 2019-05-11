---
title: MQSeries アダプターを使用したメッセージの配信を順序付けられた |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MQSeries adapters, ordered delivery
ms.assetid: 517ff2a4-7315-43b5-8d4b-7494adf141e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8442d5f23f7259d9f13f7f60034d0ca871537e50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262630"
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a>MQSeries アダプターを使用したメッセージの配信を順序付け
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供、**順次配送**オプションの静的送信ポート。 設定、**順次配送**オプションへの送信ポートで**True**により、BizTalk Server が BizTalk メッセージ ボックス データベースに公開されることと同じ順序で送信ポートにメッセージを配信します。 エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。  
  
-   メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。 など MQSeries 受信アダプタでメッセージを受信するときに、受信場所が構成オプションを使用して**停止順序**または**注文 Suspend**します。  
  
-   これらのメッセージを持つ送信ポートをサブスクライブする必要があります、**順次配送**オプションを**True**します。  
  
-   プロセスがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますにオーケストレーションを使用する場合、オーケストレーションを構成して、シーケンシャルなコンボイを使用する必要がある、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**します。  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a>メッセージの順次配送の MQSeries アダプタの使用  
 MQSeries 受信アダプタは BizTalk Server に送信するメッセージの順序を保持するサポートを提供します。 エンド ツー エンドの順序で構成されている送信ポートでメッセージが処理された場合、MQSeries アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できる、**順次配送**オプションに設定**True**します。  
  
## <a name="see-also"></a>参照  
 [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)   
 [アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)