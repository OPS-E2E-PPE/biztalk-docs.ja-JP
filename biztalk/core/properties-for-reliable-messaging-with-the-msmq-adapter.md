---
title: MSMQ アダプターを使用した信頼性の高いメッセージング用のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, properties
- queues, MSMQ adapters
- MSMQ adapters, dead letters
- queues, failures [MSMQ adapters]
- MSMQ adapters, impersonation
- MSMQ adapters, remote queues
- queues
- reliability, MSMQ adapters
- impersonation, MSMQ adapters
- MSMQ adapters, queue failures
- clustering, MSMQ adapters
- queues, remote
- MSMQ adapters, reliability
- MSMQ adapters, clustering
ms.assetid: 34bfe028-b2aa-4816-a437-3679d19dffb2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54a33fdd3ced15230d2b0c1417d1f5398678f183
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398493"
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a>MSMQ アダプターを使用した信頼性の高いメッセージング用のプロパティ
MSMQ アダプターを構成する方法での MSMQ アダプターでメッセージを送受信の信頼性を向上させることができます。 このトピックでは、いくつかの構成プロパティを信頼性の高いメッセージングの使用について説明します。  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーの実行  
 高可用性を実現方法の 1 つの異なる BizTalk server で複数のホスト インスタンスでアダプター ハンドラーを同時に実行することです。 MSMQ はリモート トランザクション読み取りをサポートしないと、MSMQ 送信ハンドラーは、MSMQ サービスをローカルで実行中のインスタンスへの依存関係を維持するため、このアプローチは、MSMQ アダプター ハンドラーの推奨されません。 高可用性は、MSMQ 送信ハンドラーと受信ハンドラーには、BizTalk ホストのクラスター化されたインスタンスで MSMQ アダプター ハンドラーを実行することをお勧めします。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a>キューのエラーと配信不能キュー  
 メッセージを正常に送信するには後、はありませんエラー後続のメッセージの受信キューが無効または削除された場合です。 このような状況では、メッセージの損失を発生させる可能性があります。  
  
 設定、**配信不能キューを使用して**構成プロパティを**True**メッセージの損失を防ぎます。 プロパティが`True`(既定)、キューを受信しないメッセージは配信不能キューに入ります。  
  
## <a name="impersonation-and-remote-queues"></a>権限借用とリモート キュー  
 設定する必要も、**を使用して、配信不能キュー**構成プロパティを**True**リモート キューを使用するとします。 MSMQ アダプタでは、リモート キューを使用するアクセス許可がないユーザーを偽装する場合は、メッセージが失われる可能性があります。  
  
 プロパティが**True**ローカルまたはリモート コンピューターのいずれかで、メッセージが配信不能キューには、権限を借用したユーザーには、リモート キューを使用するアクセス許可はありません。 トランザクション送信では、メッセージは、ローカル コンピューターの配信不能キューに移動します。 トランザクション以外の送信、メッセージは、リモート コンピューターの配信不能キューに移動します。  
  
## <a name="recoverable-and-use-journal-queue-properties"></a>回復可能なジャーナル キューのプロパティを使用して、  
 両方の**回復可能な**と**ジャーナル キューを使用して**プロパティが送信されたメッセージのコピーを保存します。 これらのプロパティの詳細については、次を参照してください。 [、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)と[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)します。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターを使用した信頼性の高いメッセージング](../core/reliable-messaging-with-the-msmq-adapter.md)   
 [クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)