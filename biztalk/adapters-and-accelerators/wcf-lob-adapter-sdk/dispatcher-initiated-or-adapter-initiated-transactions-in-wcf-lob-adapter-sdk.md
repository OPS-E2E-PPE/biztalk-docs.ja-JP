---
title: "WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85b9ef8d-3922-4838-a41a-32db5e005dc0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa8105b4b6f8eb77d68471faf9b702419f6a1f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションを構成します。
## <a name="inbound-transactions"></a>受信トランザクション  
 受信操作でトランザクションを実装する 2 つの方法がある: ディスパッチャーによって開始されるか、アダプターが開始します。 アダプターの要件をディクテーションするメソッドを使用する必要があります。 値、`SupportsTransactedInbound`プロパティは、アダプターで実装するトランザクションの種類を示します。  
  
 次の表と比較してディスパッチャーによって開始されたアダプターで開始されたトランザクション。  
  
|SupportsTransactedInbound|トランザクションの動作|  
|-------------------------------|----------------------------|  
|True (ディスパッチャーによって開始される)|-TryReceive は、トランザクションのコンテキスト内で常に呼び出されます。<br />にサービスの実装にメッセージが返された後、トランザクションはコミットされます。<br />は、新しいトランザクションが作成されます IInputChannel.Receive 呼び出しごとにします。 受信トランザクションを複数にまたがるよう、サービス ホストおよびアダプター開発者ではなくに依存します。 **注:**ホストが受け入れる必要がある場合は、ホストは、WCF ディスパッチャー (サービスのホスト) が使用されていないと、チャネル レベルのプログラミングを使用する代わりには、 **TransactedReceiveEnabled** WCF バインドのプロパティと、すべてで行う必要がありますトランザクション内で IInputChannel.Receive への呼び出しです。 **注:**場合は、アダプターは、ディスパッチャーによって開始されたトランザクションを使用し、Biztalk Server で使用されます、設定、`SupportedInboundChannels`プロパティを`SupportedInboundChannels.IInputChannel`アダプターがのみ一方向チャネルをサポートしていることを示すためにします。 これが設定されていない場合、BizTalk Server は双方向チャネルを使用しようとします。|  
|False (アダプターによって開始される)|-アダプター開発者は、アダプター内のトランザクション ロジックを実装する必要があります。<br />-アダプターで開始されたトランザクションは、双方向のメッセージング (応答チャネル) モデルでのみ操作できます。<br />-1 つのトランザクションは、依存クローンは、ディスパッチャーがメッセージごとに作成されますので、複数のメッセージをまたがることができます。|  
  
### <a name="dispatcher-initiated-transactions"></a>ディスパッチャーで開始されたトランザクション  
 SupportsTransactedInbound に設定すると**true**、WCF ディスパッチャーは、自動的にトランザクションを作成の呼び出し時に、 **TryReceive**アダプターのメソッドのトランザクションをコミットし、後、サービス実装では、メッセージが返されます。 設定する以外、アダプター内の任意の特定のトランザクション コード実装しないため、`SupportsTransactedInbound`プロパティを**true**です。 ただし、これは、WCF ディスパッチャーを使用するサービス ホスト内でホストされるアダプターに依存、チャネル レベルのプログラミングを使用している場合は発生しません。 ホストが受け入れる必要があるチャネル レベルのプログラミングを使用する場合、`TransactedReceiveEnabled`プロパティの WCF バインドと、トランザクション内で受信するすべての呼び出しを作成します。  
  
 トランザクションを作成し、チャネル レベルのプログラミングを使用してアダプターを呼び出すクライアントを次に示します。  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a>アダプターで開始されたトランザクション  
 ときに、`SupportsTransactedInbound`プロパティに設定されている**false**、新しいトランザクションを作成することで、アダプター コード内でトランザクションのサポートを実装する必要があります。 メッセージを返す前に**TryReceive**、トランザクションは、呼び出すことによって、メッセージに添付する必要があります、**設定**のメソッド、 **TransactionMessageProperty**クラスです。 この実装では、アダプター コード内の明示的なトランザクションのサポートを必要とし、アダプターのトランザクションの動作をより細かく制御を提供します。  
  
 依存のトランザクションを作成して、クライアントに返される前に、メッセージに添付するこれを次に示します。  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a>参照  
 [開発アクティビティ](../../esb-toolkit/development-activities.md)