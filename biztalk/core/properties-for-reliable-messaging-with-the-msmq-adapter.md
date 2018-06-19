---
title: MSMQ アダプターで信頼できるメッセージング プロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: 49aebf12c86ae72d5dcb224d078c62afefcb8f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268850"
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a>MSMQ アダプターで信頼できるメッセージのプロパティ
MSMQ アダプターを適切に構成することにより、MSMQ アダプターを使用したメッセージの送受信の信頼性を向上させることができます。 このトピックでは、信頼性の高いメッセージングを実現できる、いくつかの構成プロパティの使用について説明します。  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストでの MSMQ アダプター ハンドラーの実行  
 高可用性を実現するための方法として、異なる BizTalk サーバーの複数のホスト インスタンスで、アダプター ハンドラーを同時に実行できます。 この方法は、MSMQ アダプター ハンドラーには使用しないことをお勧めします。この理由として、MSMQ ではリモートのトランザクションの読み込みがサポートされていないこと、および MSMQ 送信ハンドラーの動作が、ローカルで実行されている MSMQ サービスのインスタンスに常に依存していることが挙げられます。 MSMQ 送信ハンドラーおよび受信ハンドラーの高可用性を実現するには、MSMQ アダプター ハンドラーを BizTalk ホストのクラスター化されたインスタンスで実行することをお勧めします。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a>キューのエラーと配信不能メッセージ キュー  
 メッセージを正常に送信した後、受信キューが無効化または削除された場合、後続のメッセージにエラーは発生しません。 この状況で、メッセージの損失が発生する場合があります。  
  
 設定、**使用する配信不能キュー**構成プロパティを**True**メッセージの損失を防ぎます。 `True` (既定値) に設定した場合、キューで受信されないメッセージが配信不能メッセージ キューに格納されます。  
  
## <a name="impersonation-and-remote-queues"></a>権限借用とリモート キュー  
 設定する必要も、**配信不能キューを使用して**構成プロパティを**True**リモート キューを使用するとします。 MSMQ のアダプターによって、リモート キューを使用するアクセス許可がないユーザーの権限が借用された場合、メッセージが失われる可能性があります。  
  
 このプロパティが**True**メッセージは配信不能キューにローカルまたはリモート コンピューターのいずれか、権限を借用したユーザーには、リモート キューを使用するアクセス許可がありません。 トランザクション送信では、メッセージはローカル コンピューターの配信不能メッセージ キューに格納されます。 トランザクション以外の送信では、メッセージはリモート コンピューターの配信不能メッセージ キューに格納されます。  
  
## <a name="recoverable-and-use-journal-queue-properties"></a>"回復可能" プロパティと "ジャーナル キューの使用" プロパティ  
 両方の**回復可能な**と**使用ジャーナル キュー**プロパティが送信されたメッセージのコピーを保存します。 これらのプロパティの詳細については、次を参照してください。 [、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)と[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)です。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターで信頼できるメッセージング](../core/reliable-messaging-with-the-msmq-adapter.md)   
 [クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)