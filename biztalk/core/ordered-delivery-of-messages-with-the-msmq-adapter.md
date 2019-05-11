---
title: MSMQ アダプターでメッセージの配信を順序付けられた |Microsoft Docs
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
ms.openlocfilehash: 54395febdadb62584d0a8d6422b9fd05ab3821d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322273"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a>MSMQ アダプターでメッセージの配信を順序付け
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供、**順次配送**オプションの静的送信ポート。 設定、**順次配送**オプションへの送信ポートで**True**により、BizTalk Server がメッセージ ボックス データベースに公開されることと同じ順序で送信ポートにメッセージを配信します。 エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。  
  
-   メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。  
  
-   これらのメッセージを持つ送信ポートをサブスクライブする必要があります、**順次配送**オプションを**True**します。  
  
-   プロセスがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますにオーケストレーションを使用する場合、オーケストレーションを構成して、シーケンシャルなコンボイを使用する必要がある、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**します。  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a>メッセージの順次配送の MSMQ アダプターを使用  
 MSMQ 受信アダプターが BizTalk Server に送信するメッセージの順序を保持する機能のサポートを提供します。 エンド ツー エンドの順序で構成されている送信ポートでメッセージが処理された場合、MSMQ アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できる、**順次配送**に設定するオプション**True**します。  
  
## <a name="see-also"></a>参照  
 [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)   
 [MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)