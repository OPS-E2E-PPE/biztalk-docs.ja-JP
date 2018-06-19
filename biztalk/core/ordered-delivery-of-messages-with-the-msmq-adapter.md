---
title: MSMQ アダプターでメッセージの配信を順序付け |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MSMQ adapters, ordered delivery
ms.assetid: e8dafc76-e894-4120-9cea-d014d635850e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac842fcd1e9b386fa885844f3a797504ed7c4c3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263586"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a>MSMQ アダプターでメッセージの配信を順序付け
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供、**順次配送**オプション静的送信ポート。 設定、**順次配送**オプションで、送信ポートを**True** BizTalk Server がメッセージ ボックス データベースにパブリッシュされる順序と同じ順序で送信ポートにメッセージを配信することを確認します。 エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。  
  
-   メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。  
  
-   持つ送信ポートでこれらのメッセージをサブスクライブする必要があります、**順次配送**オプションを**True**です。  
  
-   シーケンシャルなコンボイを使用するオーケストレーションを構成する必要があります、オーケストレーションがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますプロセスに使用されている場合、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**です。  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a>メッセージの順次配送を目的とした MSMQ アダプタの使用  
 MSMQ 受信アダプタでは、BizTalk Server に送信するメッセージの順序を保持する機能がサポートされています。 エンド ツー エンドのメッセージが構成されている送信ポートによって処理される場合、MSMQ アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できますが順序付け、**順次配送**にセットのオプション**True**です。  
  
## <a name="see-also"></a>参照  
 [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)   
 [MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)