---
title: MQSeries アダプタでメッセージの配信を順序付け |Microsoft ドキュメント
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
ms.openlocfilehash: 8f8b602adf93152f6af1e5dbbc576180d570a4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264530"
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a>MQSeries アダプタを使用したメッセージの順次配送
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供、**順次配送**オプション静的送信ポート。 設定、**順次配送**オプションで、送信ポートを**True** BizTalk Server が BizTalk メッセージ ボックス データベースにパブリッシュされる順序と同じ順序で送信ポートにメッセージを配信することを確認します。 エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。  
  
-   メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。 たとえば、MQSeries 受信アダプタでメッセージを受信するときに、受信場所を構成オプション**が停止すると注文**または**中断の順序**です。  
  
-   持つ送信ポートでこれらのメッセージをサブスクライブする必要があります、**順次配送**オプションを**True**です。  
  
-   シーケンシャルなコンボイを使用するオーケストレーションを構成する必要があります、オーケストレーションがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますプロセスに使用されている場合、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**です。  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a>メッセージの順次配送を目的とした MQSeries アダプタの使用  
 MQSeries 受信アダプタでは、BizTalk Server に送信するメッセージの順序を保持する機能がサポートされています。 エンド ツー エンドのメッセージが構成されている送信ポートによって処理される場合、MQSeries アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できますが順序付け、**順次配送**オプションに設定**True**です。  
  
## <a name="see-also"></a>参照  
 [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)   
 [アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)