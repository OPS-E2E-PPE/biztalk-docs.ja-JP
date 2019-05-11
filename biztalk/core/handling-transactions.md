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
ms.openlocfilehash: ea7601fdb2a11927cee0a9ffcbcb00b5c689e70b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387585"
---
# <a name="handling-transactions"></a>トランザクションの処理
## <a name="transacted-receivers"></a>トランザクション受信元  
 トランザクション受信元とトランザクション以外の受信の主な違いは、トランザクション受信元を作成し、明示的な MSDTC トランザクションを使用して、そのデータ ソース間の原子性が確保、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。 一般に、アダプターの他のすべての側面は、同じです。  
  
 要求-応答の受信に注意する必要がありますのみ、アダプターは、メッセージング エンジンに元の要求メッセージを送信するため、トランザクションを使用します。 メッセージング エンジンからアダプターに送信される応答を送信するためには、別のトランザクションが必要です。 これは、最初のトランザクションのスコープが、アダプターと、メッセージ ボックス データベース間にあるためです。 後続の要求メッセージは送信されません、アダプターにメッセージング エンジンから元の要求メッセージのトランザクションがコミットされるまで。  
  
 次のオブジェクト相互作用の図は、受信メッセージのトランザクション送信中に、アダプターとメッセージング エンジン間の相互作用を示しています。 この例では、次の一連の相互作用が行わをれます。  
  
1. アダプターは、エンジンから新しいバッチを取得します。  
  
2. アダプターは、新しい MSDTC トランザクションを作成します。  
  
3. アダプターは、そのトランザクションに参加しているデータ ソースからの破壊的な読み取りが。  
  
4. アダプターは、メッセージを送信します。  
  
5. アダプターが**完了**自身の MSDTC トランザクションを渡して、バッチに対して、その**BatchComplete**コールバック ポインター。 エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。  
  
6. エンジンは、バッチ処理、アダプターをコールバックにその**BatchComplete**実装し、そのメッセージをアダプターに処理の状態を伝達します。  
  
7. バッチが成功した場合、アダプター コミット トランザクションと呼び出し、 **IBTDTCCommitConfirm.DTCCommitConfirm** API を`true`値がコミットを意味します。  
  
   ![](../core/media/transactedreceiver.gif "TransactedReceiver")  
  
## <a name="transacted-transmitters"></a>トランザクション送信元  
 トランザクション アダプターは、ほとんどの場合、トランザクション以外のアダプターに非常に似ています。 主な違いは、トランザクション アダプターが、MSDTC トランザクションに参加しているリソースにメッセージのデータを送信します。  
  
 **実装のヒン ト:** トランザクションの送信のアダプターで使用する同じ MSDTC トランザクションとを通じてそれを削除するため、変換先にデータを書き込むため、 **IBTTransportBatch.DeleteMessage**メソッドの呼び出し。 これら 2 つの操作だけでは、トランザクションが行われる必要があります。 他の操作など**IBTTransportBatch.Resubmit**、 **IBTTransportBatch.MoveToNextTransport**、および**IBTTransportBatch.MoveToSuspendQ**にする必要はありませんトランザクション。 これは、エンジンが暗黙的にトランザクションを使用し、これらの種類の操作は、送信先に対してアトミックである必要はありません。  
  
 次のオブジェクト相互作用の図は、アダプターとエンジン間の相互作用を示しています。 イベントの順序は次のとおりです。  
  
1. エンジンは、アダプターから新しいバッチを取得します。  
  
2. エンジンは、新しいバッチに 2 つのメッセージを追加します。  
  
3. エンジンの呼び出し**完了**バッチの原因で、スレッド プールによって提供される内部送信キューにバッチを投稿するアダプター。  
  
4. アダプターは、新しい MSDTC トランザクションを作成します。  
  
5. アダプターが送信メッセージの送信先を MSDTC トランザクションに参加させます。 たとえば、このでしたに書き込む場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。  
  
6. 送信後に、アダプターは、新しいバッチをエンジンから取得します。  
  
7. アダプターが**DeleteMessage**が正常に送信されているメッセージ。  
  
8. アダプターが**完了**自身の DTC トランザクションを渡して batch 上でします。 エンジンが返す、 **IBTDTCCommitConfirm**インターフェイス。  
  
9. エンジンは、アプリケーション キューからメッセージを削除するバッチを処理します。  
  
10. エンジンはコールバックにアダプターの**IBTBatchCallback**削除操作の成功に関する情報を持つインターフェイスです。  
  
11. バッチが成功した場合、アダプターは、トランザクションをコミットします。  
  
12. アダプターが**IBTDTCCommitConfirm.DTCCommitConfirm**トランザクションがコミットに成功したことをエンジンに通知するためにします。  
  
    ![](../core/media/transactedtransmitter.gif "Transactedtransmitter")  
  
### <a name="transacted-solicit-response-adapters"></a>トランザクション送信請求-応答アダプター  
 異なり、双方向受信、双方向の送信は同じ DTC トランザクションを使用して実行する可能性があります。 トランザクション送信請求-応答アダプターを使用する必要があります、同じ**IBTTransportBatch**の**SubmitResponseMessage**と**DeleteMessage**操作。 このバッチには、送信請求-応答の組み合わせのメッセージの送受信に使用される同じ MSDTC トランザクションを使用する必要があります。 これにより、送信請求-応答のメッセージ交換の原子性です。  
  
## <a name="service-components-and-byot"></a>サービス コンポーネントと BYOT  
 メッセージング エンジン Api では、MSDTC トランザクションに指定する必要があります。 ただし一部の .NET コンポーネントは、サービス コンポーネントとして使用するように設計されてし、トランザクションのコミットまたは中止するプログラムを使用できないようにします。 代わりに、そのプラットフォームで COM + ランタイムによって、トランザクションを自動的にコミットします。  
  
 これらのシナリオについて、アダプターは、Bring Your Own トランザクション BYOT () を使用してください。 これにより、アダプターは MSDTC トランザクションを作成、トランザクションを使用する .NET コンポーネントをインスタンス化し、独自のトランザクションを作成するのではなく、作成されたトランザクションを継承するには、そのコンポーネントを許可できます。 .NET Framework には**System.EnterpriseServices.BYOT**この目的のためです。 ヘルパー クラスを提供する SDK の BaseAdapter **BYOTTransaction**、この目的のためです。  
  
## <a name="avoiding-race-conditions"></a>競合状態の回避  
 トランザクション オブジェクトを作成しに渡すアダプターを記述するとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、実行すると、次のコードの記述を担当することになります。  
  
- バッチに関連付けられているメッセージ内のエラーを解決します。  
  
- バッチ操作に関連付けられたトランザクションの最終結果を決定します。  
  
  アダプターに通知する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の内部で維持するために、トランザクションの最終的な結果に関するデータを追跡します。 通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]呼び出すことによって、結果の**DTCConfirmCommit**します。 アダプターがこれにもいない場合は、大量のメモリ リークが発生します。  
  
  上記 2 つのタスク (エラーの解決し、最終結果の決定) が、単純に見えますが、実際に別のスレッドからの情報に依存します。  
  
- アダプターによって渡された情報に基づいてエラーを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を**BatchComplete**アダプターでのコールバック。 このコールバックはアダプターのスレッドでは。  
  
- **DTCConfirmCommit**に、メソッドが、 **IBTDTCCommitConfirm**オブジェクト。 インスタンス、 **IBTDTCCommitConfirm**オブジェクトは、batch によって返される**ibttransportbatch::done**呼び出します。 このインスタンスが同じスレッドでは、 **ibttransportbatch::done**呼び出すには、これは、アダプターのスレッドと異なる。  
  
- アダプターがすべての呼び出しに対して**ibttransportbatch::done** 、対応するコールバックがある**BatchComplete**がの結果を報告する別のスレッドでメッセージング エンジンによって呼び出されますバッチ送信します。 **BatchComplete**アダプターのニーズをコミットまたはロールバック トランザクションかどうかに基づいて、バッチが成功または失敗します。 どちらの場合、アダプターは呼び出す必要がありますし、 **DTCConfirmCommit**メッセージング エンジンにトランザクションの状態を報告します。  
  
  競合状態が存在するためのアダプターの実装**BatchComplete**を想定できます、 **IBTDTCCommitConfirm**によって返されるオブジェクト**ibttransportbatch::done**は常に利用可能な場合に**BatchComplete**を実行します。 ただし、 **BatchComplete**前であってもに、、別のメッセージング エンジン スレッドで呼び出すこと**ibttransportbatch::done**を返します。 できるアダプターがアクセスしようとしたときに、 **IBTDTCCommitConfirm**オブジェクトの一部として、 **BatchComplete**実装では、アクセス違反があります。  
  
  次の例では、内のイベントには、問題が解決します。 ここでインターフェイス ポインターは、イベントを使用するプロパティを通じてアクセスされます。 Get では、セットが常に待機します。  
  
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