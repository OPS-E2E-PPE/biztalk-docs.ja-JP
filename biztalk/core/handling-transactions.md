---
title: トランザクションの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d360742-e969-4651-b364-9edc6a93b8d4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c82bb8077b1a89a979a658e4bd7cd9a61220f48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980451"
---
# <a name="handling-transactions"></a>トランザクションの処理
## <a name="transacted-receivers"></a>トランザクション受信元  
 トランザクション受信元とトランザクション以外の受信元との主な違いは、トランザクション受信元の場合、明示的な MSDTC トランザクションを作成および使用することにより、データ ソースと [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースの間の原子性が確保される点にあります。 一般に、アダプターのその他の側面はすべて同じです。  
  
 要求 - 応答の受信アダプターは、メッセージング エンジンに元の要求メッセージを送信するためにのみ、トランザクションを使用します。 メッセージング エンジンからアダプターに応答が送信されるためには、別のトランザクションが必要です。 これは、最初のトランザクションのスコープが、アダプターとメッセージ ボックス データベースの間であるためです。 元の要求メッセージのトランザクションがコミットされるまで、後続の要求メッセージは、メッセージング エンジンからアダプターに送信されません。  
  
 次のオブジェクト間の対話処理図に、受信メッセージのトランザクション送信時にアダプターとメッセージング エンジンが対話するようすを示します。 この例では、次の一連の対話が行われます。  
  
1. アダプターが新しいバッチをエンジンから取得します。  
  
2. アダプターが新しい MSDTC トランザクションを作成します。  
  
3. アダプターが、トランザクションに参加しているデータ ソースの破壊的な読み取りを行います。  
  
4. アダプターがメッセージを送信します。  
  
5. アダプターが**完了**自身の MSDTC トランザクションを渡して、バッチに対して、その**BatchComplete**コールバック ポインター。 エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。  
  
6. エンジンは、バッチ処理、アダプターをコールバックにその**BatchComplete**実装し、そのメッセージをアダプターに処理の状態を伝達します。  
  
7. バッチが成功した場合、アダプター コミット トランザクションと呼び出し、 **IBTDTCCommitConfirm.DTCCommitConfirm** API を`true`値がコミットを意味します。  
  
   ![](../core/media/transactedreceiver.gif "TransactedReceiver")  
  
## <a name="transacted-transmitters"></a>トランザクション送信元  
 トランザクション アダプターは、トランザクション以外のアダプターとほぼ同様です。 主な違いは、トランザクション アダプターの場合、メッセージ内のデータを、MSDTC トランザクションに参加しているリソースに送信する点です。  
  
 **実装のヒン ト:** のトランザクション送信は、アダプターで使用する同じ MSDTC トランザクションとを通じてそれを削除するため、変換先にデータを書き込むため、 **IBTTransportBatch.DeleteMessage**メソッドの呼び出し。 トランザクションが行われる必要があるのは、この 2 つの操作だけです。 他の操作など**IBTTransportBatch.Resubmit**、 **IBTTransportBatch.MoveToNextTransport**、および**IBTTransportBatch.MoveToSuspendQ**にする必要はありませんトランザクション。 これは、エンジンが暗黙的にトランザクションを使用し、これらの操作が送信先に対してアトミックである必要がないためです。  
  
 次のオブジェクト間の対話処理図に、アダプターとエンジンが対話するようすを示します。 イベントのシーケンスは、次のとおりです。  
  
1. エンジンが新しいバッチをアダプターから取得します。  
  
2. エンジンが 2 つのメッセージを新しいバッチに追加します。  
  
3. エンジンの呼び出し**完了**バッチの原因で、スレッド プールによって提供される内部送信キューにバッチを投稿するアダプター。  
  
4. アダプターが新しい MSDTC トランザクションを作成します。  
  
5. アダプターがメッセージを送信し、MSDTC トランザクションに送信先を参加させます。 たとえば、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースに書き込む場合もあります。  
  
6. 送信後に、アダプターが新しいバッチをエンジンから取得します。  
  
7. アダプターが**DeleteMessage**が正常に送信されているメッセージ。  
  
8. アダプターが**完了**自身の DTC トランザクションを渡して batch 上でします。 エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。  
  
9. エンジンがバッチを処理し、メッセージをアプリケーション キューから削除します。  
  
10. エンジンはコールバックにアダプターの**IBTBatchCallback**削除操作の成功に関する情報を持つインターフェイスです。  
  
11. バッチが成功した場合、アダプターがトランザクションをコミットします。  
  
12. アダプターが**IBTDTCCommitConfirm.DTCCommitConfirm**トランザクションがコミットに成功したことをエンジンに通知するためにします。  
  
    ![](../core/media/transactedtransmitter.gif "Transactedtransmitter")  
  
### <a name="transacted-solicit-response-adapters"></a>送信請求 - 応答のトランザクション アダプター  
 双方向受信とは異なり、双方向送信は同じ DTC トランザクションを使用して実行できます。 トランザクション送信請求-応答アダプターを使用する必要があります、同じ**IBTTransportBatch**の**SubmitResponseMessage**と**DeleteMessage**操作。 このバッチは、送信請求 - 応答の組み合わせのメッセージの送受信時と同じ MSDTC トランザクションを使用します。 これにより、送信請求 - 応答のメッセージ交換における原子性が確保されます。  
  
## <a name="service-components-and-byot"></a>サービス コンポーネントと BYOT  
 メッセージング エンジン API は、MSDTC トランザクションの提供を必要とします。 ただし、一部の .NET コンポーネントはサービス コンポーネントとして使用されるよう設計されており、プログラムによるトランザクションのコミットや中止を許可しません。 この場合、トランザクションは、そのプラットフォームの COM+ ランタイムによって自動的にコミットされます。  
  
 このようなシナリオでは、アダプターで BYOT (Bring Your Own Transaction) を使用します。 こうすると、アダプターによる MSDTC トランザクションの作成と、このトランザクションを使用する .NET コンポーネントのインスタンス化が可能となります。このコンポーネントは作成されたトランザクションを継承するため、トランザクションを独自に作成することはありません。 .NET Framework には**System.EnterpriseServices.BYOT**この目的のためです。 ヘルパー クラスを提供する SDK の BaseAdapter **BYOTTransaction**、この目的のためです。  
  
## <a name="avoiding-race-conditions"></a>競合状態の回避  
 トランザクション オブジェクトを作成して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡すアダプターを記述する場合、次の操作を実行するコードを記述する必要があります。  
  
- バッチに関連付けられているメッセージ内のエラーを解決する。  
  
- バッチ操作に関連付けられているトランザクションの最終結果を決定する。  
  
  アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にトランザクションの最終結果を知らせて内部の追跡データを維持する必要があります。 通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]呼び出すことによって、結果の**DTCConfirmCommit**します。 アダプターがこれを行わないと、重大なメモリ リークが発生します。  
  
  上記の 2 つのタスク (エラーの解決と最終結果の決定) は単純に見えますが、実際には、これらのタスクは次に示す異なるスレッドの情報に基づいています。  
  
- アダプターによって渡された情報に基づいてエラーを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を**BatchComplete**アダプターでのコールバック。 このコールバックはアダプターのスレッド上にあります。  
  
- **DTCConfirmCommit**に、メソッドが、 **IBTDTCCommitConfirm**オブジェクト。 インスタンス、 **IBTDTCCommitConfirm**オブジェクトは、batch によって返される**ibttransportbatch::done**呼び出します。 このインスタンスが同じスレッドでは、 **ibttransportbatch::done**呼び出すには、これは、アダプターのスレッドと異なる。  
  
- アダプターがすべての呼び出しに対して**ibttransportbatch::done** 、対応するコールバックがある**BatchComplete**がの結果を報告する別のスレッドでメッセージング エンジンによって呼び出されますバッチ送信します。 **BatchComplete**アダプターのニーズをコミットまたはロールバック トランザクションかどうかに基づいて、バッチが成功または失敗します。 どちらの場合、アダプターは呼び出す必要がありますし、 **DTCConfirmCommit**メッセージング エンジンにトランザクションの状態を報告します。  
  
  競合状態が存在するためのアダプターの実装**BatchComplete**を想定できます、 **IBTDTCCommitConfirm**によって返されるオブジェクト**ibttransportbatch::done**は常に利用可能な場合に**BatchComplete**を実行します。 ただし、 **BatchComplete**前であってもに、、別のメッセージング エンジン スレッドで呼び出すこと**ibttransportbatch::done**を返します。 できるアダプターがアクセスしようとしたときに、 **IBTDTCCommitConfirm**オブジェクトの一部として、 **BatchComplete**実装では、アクセス違反があります。  
  
  次の例では、内のイベントには、問題が解決します。 この例では、イベントを使用するプロパティを通じてインターフェイス ポインターにアクセスします。 get は常に set を待機します。  
  
```  
protected IBTDTCCommitConfirm CommitConfirm  
{  
   set  
   {  
       this.commitConfirm = value;  
       this.commitConfirmEvent.Set();  
   }  
   get  
   {  
       this.commitConfirmEvent.WaitOne();  
       return this.commitConfirm;  
   }  
}  
protected IBTDTCCommitConfirm commitConfirm = null;  
private ManualResetEvent commitConfirmEvent = new ManualResetEvent(false);  
```  
  
 戻り値を割り当てるようになりました**ibttransportbatch::done**にこのプロパティでそれを使用して、 **BatchComplete**呼び出します。  
  
## <a name="see-also"></a>参照  
 [トランザクション メッセージ バッチ](../core/transactional-message-batches.md)