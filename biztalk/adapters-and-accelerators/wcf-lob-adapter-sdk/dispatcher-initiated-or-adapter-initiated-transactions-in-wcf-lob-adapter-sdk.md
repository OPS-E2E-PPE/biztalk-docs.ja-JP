---
title: WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85b9ef8d-3922-4838-a41a-32db5e005dc0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98ad767d0da4816e1d0c0658db898ebec282ffa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363609"
---
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションを構成します。
## <a name="inbound-transactions"></a>トランザクションを受信します。  
 受信操作でトランザクションを実装する 2 つの方法がある: ディスパッチャー開始またはアダプターが開始します。 アダプターの要件をディクテーションするメソッドを使用する必要があります。 値、`SupportsTransactedInbound`プロパティは、アダプターで実装するトランザクションの種類を示します。  
  
 次の表は、ディスパッチャー開始を比較とアダプター開始トランザクションとします。  
  
|SupportsTransactedInbound|トランザクションの動作|  
|-------------------------------|----------------------------|  
|True (ディスパッチャー開始)|-TryReceive は、常にトランザクションのコンテキスト内で呼び出されます。<br />にサービスの実装にメッセージが返された後、トランザクションはコミットされます。<br />-新しいトランザクションが作成されます IInputChannel.Receive 呼び出しごとにします。 受信トランザクションを複数にまたがるはサービス ホストとアダプターは開発者向けに依存します。 **注:** ホストが受け入れる必要がある場合は、ホストは、WCF ディスパッチャー (サービスのホスト) を使用していないと、チャネル レベルのプログラミングを使用して、代わりに、 **TransactedReceiveEnabled** WCF のバインドのプロパティと、すべての呼び出しを行う必要がありますトランザクション内で IInputChannel.Receive します。 **注:** アダプターがディスパッチャーによって開始されたトランザクションを使用、Biztalk Server と共に使用される場合は、設定、`SupportedInboundChannels`プロパティを`SupportedInboundChannels.IInputChannel`をアダプターがのみ一方向チャネルをサポートしていることを示します。 これが設定されていない場合は、BizTalk Server は双方向チャネルを使用しようとします。|  
|False (アダプターが開始した)|アダプター開発者は、アダプター内でのトランザクション ロジックを実装する必要があります。<br />-アダプター開始トランザクションは、双方向メッセージング (応答チャネル) モデルでのみ使用できます。<br />-1 つのトランザクションは、ディスパッチャーによって各メッセージに依存する複製が作成されますので、複数のメッセージをまたがることができます。|  
  
### <a name="dispatcher-initiated-transactions"></a>ディスパッチャー開始トランザクション  
 SupportsTransactedInbound に設定すると**true**、WCF ディスパッチャーは、自動的にトランザクションを作成を呼び出すときに、 **TryReceive**アダプターのメソッドのトランザクションをコミットし、後のメッセージには、サービスの実装が返されます。 アダプターの設定以外の任意の特定のトランザクション コード実装する必要はありません、`SupportsTransactedInbound`プロパティを**true**します。 ただし、これは、WCF ディスパッチャーを使用するサービス ホスト内でホストされるアダプターに依存し、チャネル レベルのプログラミングを使用している場合は発生しません。 チャネル レベルのプログラミングを使用する場合、ホストが受け入れる必要がある、`TransactedReceiveEnabled`プロパティの WCF バインドと、トランザクション内で受信する呼び出しはすべて作成します。  
  
 トランザクションを作成し、チャネル レベルのプログラミングを使用して、アダプターを呼び出すクライアントを次に示します。  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a>アダプターによって開始されたトランザクション  
 ときに、`SupportsTransactedInbound`プロパティに設定されて**false**、新しいトランザクションを作成してアダプター コード内でトランザクションのサポートを実装する必要があります。 メッセージを返す前に**TryReceive**、トランザクションは、呼び出すことによって、メッセージに添付する必要があります、**設定**のメソッド、 **TransactionMessageProperty**クラス。 この実装は、アダプター コード内の明示的なトランザクションのサポートが必要ですし、アダプターのトランザクションの動作をより細かく制御を提供します。  
  
 依存トランザクションを作成し、クライアントに返される前に、メッセージに添付するこれを次に示します。  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a>参照  
 [開発アクティビティ](../../esb-toolkit/development-activities.md)