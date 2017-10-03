---
title: "アダプターを終了する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfba2b61-b89f-41cd-a014-4e96daec6516
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd2621e15803dd5f6e8f449de530e84df1bc1b9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-terminate-an-adapter"></a>アダプターを終了する方法
ここでは、アダプターの適切なシャットダウンに関するガイダンスを提供します。  
  
## <a name="terminating-an-adapter"></a>アダプターの終了  
 メッセージング エンジンがシャット ダウンとが呼び出されて**IBTTransportControl**.**終了**各インプロセス アダプターでします。 このメソッドから制御が戻ると、BizTalk Server はアダプターを破棄します。 この処理は、ネイティブ アダプターの場合は直ちに発生しますが、マネージ アダプターの場合は .NET のガベージ コレクション プロセスが関係するため正確なタイミングを特定できません。 アダプターをブロックする必要があります**Terminate**に必要なは、クリーンアップ作業が破棄する準備完了になるまでです。  
  
## <a name="terminating-isolated-receive-adapters"></a>分離受信アダプターの終了  
 分離受信アダプターはありません**Terminate**されません、BizTalk サービスでホストされているために呼び出されます。 代わりを呼び出すことによって**IBTTransportProxy**.**TerminateIsolatedReceiver**にメッセージング エンジンをシャット ダウンしようとしていることを通知します。  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a>Marshal.ReleaseComObject を使用した COM オブジェクトのクリーンアップ  
 COM オブジェクトを使用するマネージ コードを記述すると、共通言語ランタイム (CLR) により、COM オブジェクトへの参照を保持するプロキシ オブジェクトが生成されます。 このプロキシ オブジェクトはマネージ オブジェクトであり、ガベージ コレクションの通常のルールが適用されます。 ガベージ コレクターは .NET ランタイムが割り当てたメモリしか参照せず、COM オブジェクトを認識しないことから、1 つの問題が発生します。 それは、プロキシ オブジェクトは小さいため、大きい COM オブジェクトが CLR ガベージ コレクターで認識されずにメモリ内に残される可能性があるという点です。  
  
 この問題を避けるためには、明示的に解放基になる COM オブジェクトが終了したら、特に**IBTTransportBatch**オブジェクト。 呼び出すことによって、これを行う**マーシャ リング**.**ReleaseComObject**です。  
  
> [!NOTE]
>  **ReleaseComObject**残っている参照の数を返し、これは、値が 0 で返されるときにのみ、COM オブジェクトを解放します。 多くの場合、 **ReleaseComObject**はオブジェクトが解放されることを確認するループで呼び出されます。 完了後を呼び出す必要があります**SuppressFinalize**このオブジェクトの最終処理する項目がないためです。 最後の手順として、このオブジェクトが間違いなく COM オブジェクトであるかどうかの確認も行います。  
  
 上記のプロセスのコードを次に示します。  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 明示的に解放する、 **IBTTransportBatch**から返されたオブジェクト**GetBatch**パフォーマンスを大幅に向上を行うことができます。  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a>アダプターを閉じるときに常に Terminate を使用  
 BizTalk server アダプターとして、コードを認識するようと呼ばれるインターフェイスを実装する必要があります**IBTTransportControl**です。 このインターフェイスは、BizTalk Server がアダプターとどのように通信するかを定義するもので、次のように定義されます。  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 インターフェイスには、2 つのメソッドが含まれています。**初期化**と**Terminate**です。  
  
### <a name="initialize"></a>[初期化]  
 BizTalk Server を呼び出す、**初期化**メソッド、アダプター アセンブリを読み込んだ後にします。 この呼び出しは、アダプターにトランスポート プロキシ (BizTalk Server に対する主要なハンドル) を渡すために行われます。 実装**初期化**だけで、トランスポート プロキシをメンバー変数に格納します。  
  
### <a name="terminate"></a>終了  
 BizTalk Server を呼び出す、 **Terminate**サービスのシャット ダウンして、すべてのバッチの実行を終了する時間をアダプターのメソッドです。 これによりの実装、 **Terminate**メソッドをさらに複雑です。  
  
 アダプターはから返されません、 **Terminate**がすべて保留中の作業が完了するまでの呼び出しです。 BizTalk Server から呼び出されると**Terminate**アダプターがその現在のすべてのタスクを停止し、新しいタスクを開始できませんを試行します。  
  
 **Terminate**が呼び出された場合は、アダプターが永続的にブロック サービスのシャット ダウンの一部として、サービス コントロール マネージャーが、プロセスを終了**Terminate**です。 この場合は、BizTalk Server サービスの停止時にサービス コントロール マネージャーからの警告が表示されます。 このようにアダプターを途中で終了するのはできるだけ避けてください。 アダプターが終了プロセスを適切に処理せず、プロセスがシャットダウンを開始した時点でまだ実行中のスレッドがあると、シャットダウン時に BizTalk Server でアクセス違反が発生することがあります。  
  
 BizTalk Server のインターフェイスは非同期であるため、高負荷状況であっても多数のバッチが実行中 (したがって、多数のスレッドが実行中) の可能性があります。 **Terminate**アダプターが正常に実行される BizTalk Server で続行する前にすべてのバッチの終了を待機する呼び出しを実装する必要があります。 によってバッチの終了が通知される、 **BatchComplete** BizTalk Server からのコールバック。 **Terminate**呼び出しが待機する保留中の各**BatchComplete**が発生します。 ただし、バッチは正常に実行されなければなりません。 呼び出しは、 **IBTTransportBatch**::**完了**しないことが必要があります。 場合への呼び出し**IBTTransportBatch**::**完了**失敗すると、バッチ コールバックはありません。  
  
 アダプターに同期コードを追加する必要のあることを理解できれば、その実装は簡単です。  
  
 備えた複合同期オブジェクトを実装するのには、簡単な方法の 1 つ**入力**と**のままにして**、ワーカー スレッドのためのメソッドと**終了**メソッド中にブロックする、スレッドは、保護対象の実行中にまだです。 (ちなみに、ソリューションは、使い慣れた複数リーダー/単一ライター構造とよく似ていますここで、ワーカー スレッドのことができますと考えるのリーダーと**終了**メソッドをライターとして)。  
  
 **終了**メソッドを次に示します。  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 各ワーカー スレッドについて、次のように記述します。  
  
```  
If (!this.control.Enter())  
return; // we can’t enter because Terminate has been called  
try  
{  
//  create and fill batch  
batch.Done();  
}  
catch (Exception)  
{  
//  we are not expecting a callback  
This.control.Leave();  
}  
```  
  
 BizTalk Server からのコールバック  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属しているベース アダプターのサンプルには、ここで説明した同期メカニズムを示したサンプル コード ControlledTermination.cs が含まれています。