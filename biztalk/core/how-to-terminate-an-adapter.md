---
title: アダプターを終了する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfba2b61-b89f-41cd-a014-4e96daec6516
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8e6fcf862ba52c1ae742ff48ff985ef801c0b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383760"
---
# <a name="how-to-terminate-an-adapter"></a>アダプターを終了する方法
次のトピックでは、アダプターの適切なシャット ダウン時にガイダンスを提供します。  
  
## <a name="terminating-an-adapter"></a>アダプターの終了  
 メッセージング エンジンがシャット ダウン時に呼び出す**IBTTransportControl**.**終了**各インプロセス アダプター。 このメソッドが返された後に、BizTalk Server は、アダプターを破棄します。 ネイティブ アダプターが、すぐに、マネージ アダプターをまったく発生この場合は、.NET ガベージ コレクション プロセス関係するためです。 アダプターをブロックする必要があります**Terminate**に必要な操作を破棄する準備ができるまで、クリーンアップ作業します。  
  
## <a name="terminating-isolated-receive-adapters"></a>受信アダプターの分離を終了しています  
 分離受信アダプターはありません**Terminate**での BizTalk サービスがホストされていないために呼び出されます。 代わりに、呼び出す必要がある**IBTTransportProxy**.**TerminateIsolatedReceiver**シャット ダウンしようとしていることをメッセージング エンジンに通知します。  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a>Marshal.ReleaseComObject を使用した COM オブジェクトをクリーンアップします。  
 COM オブジェクトを使用するマネージ コードを記述する場合、共通言語ランタイム (CLR) は、COM オブジェクトへの参照を保持するプロキシ オブジェクトを生成します。 プロキシ オブジェクトは管理対象のオブジェクトであるため、ガベージ コレクションの通常の規則が適用されます。 ガベージ コレクターでは、.NET ランタイムで、割り当て、および、COM オブジェクトを認識しないことのメモリしか参照せずに、問題が発生します。 プロキシ オブジェクトは、小さいために、CLR のガベージ コレクターは、認識しないため、大きい COM オブジェクトはメモリに残り可能性があります。  
  
 この問題を避けるためを明示的に解放基になる COM オブジェクトを終了すると、特に**IBTTransportBatch**オブジェクト。 呼び出すことによって、これを行う**マーシャ リング**.**ReleaseComObject**します。  
  
> [!NOTE]
>  **ReleaseComObject**残っている参照の数を返し、この戻り値が 0 の場合にのみ、COM オブジェクトを解放します。 多くの場合、 **ReleaseComObject**は、オブジェクトが解放されることを確認するループで呼び出されます。 完了後を呼び出す必要があります**SuppressFinalize**このオブジェクトの最終処理を何もないためです。 最後の 1 つの手順では、実際に COM オブジェクトであるかどうかを確認します。  
  
 次のコードは、上記のプロセスを示しています。  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 明示的に解放する、 **IBTTransportBatch**から返されるオブジェクト**GetBatch**パフォーマンスを大幅に改善を行うことができます。  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a>アダプターを閉じるとき、常に使用が終了します。  
 BizTalk server のアダプターとして、コードを認識する、というインターフェイスを実装する必要があります**IBTTransportControl**します。 このインターフェイスは、BizTalk Server のアダプターと通信して次のように定義されているを定義します。  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 インターフェイスには、2 つのメソッドが含まれています。**初期化**と**Terminate**します。  
  
### <a name="initialize"></a>[初期化]  
 BizTalk Server によって、**初期化**後に、アダプター アセンブリを読み込みます。 これは、アダプターにトランスポート プロキシ (BizTalk Server にメインのハンドル) を渡す。 実装**初期化**単に、トランスポート プロキシをメンバー変数に格納します。  
  
### <a name="terminate"></a>終了  
 BizTalk Server によって、 **Terminate**メソッドのすべてのバッチの実行を終了する時間をアダプターを提供するサービスのシャット ダウンします。 これにより、実装、 **Terminate**メソッドをさらに複雑にします。  
  
 アダプターから返しません、 **Terminate**が任意の保留中の作業が完了するまでの呼び出し。 BizTalk Server を呼び出すと**Terminate**の現在のすべてのタスクを停止し、新規を起動しないように、アダプターしてください。  
  
 **Terminate**と呼びますアダプターが永続的にブロック場合、サービスのシャット ダウンの一環として、サービス コントロール マネージャーがプロセスを終了**Terminate**します。 ここでは、BizTalk Server サービスの停止時にサービス コントロール マネージャーから警告が表示されます。 可能であれば、このような処理の途中でアダプターを終了しないでください。 場合は、アダプターは、終了プロセスが適切に処理しないと、プロセスがシャット ダウンを開始すると実行中のスレッドがまだ、シャット ダウン時に BizTalk Server からアクセス違反随時表示があります。  
  
 BizTalk Server へのインターフェイスの非同期性質上、負荷がある多くのバッチしたがってスレッドが実行中に高くなります。 **Terminate**続行する前に、アダプターが正常に実行 BizTalk Server のすべてのバッチの終了を待機する呼び出しを実装する必要があります。 バッチの終了がによって通知、 **BatchComplete** BizTalk Server からのコールバック。 **Terminate**で呼び出しを待機する必要があります保留中の各**BatchComplete**発生します。 ただし、バッチの実行は成功である必要があります。 呼び出しは、 **IBTTransportBatch**::**完了**失敗する必要があります。 場合に呼び出し**IBTTransportBatch**::**完了**失敗すると、バッチ コールバックはありません。  
  
 アダプターに同期コードを追加する必要があることを理解できれば、実装は非常に簡単です。  
  
 備えた複合同期オブジェクトを実装する 1 つの簡単な方法は、**入力**と**のままに**ワーカー スレッドのメソッドと**終了**メソッド中にブロックする、スレッドとは、保護された実行内であります。 (ちなみに、ソリューションは、使い慣れた複数リーダー、単一のライターの構造とよく似ています、ワーカー スレッド見なすことができますのリーダーとして、**終了**メソッドをライターとします)。  
  
 **終了**メソッドを次に示します。  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 各ワーカー スレッド。  
  
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
  
 BizTalk Server からのコールバック。  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ベース アダプター サンプルでは、ここで説明した同期メカニズムを示すサンプル コード ControlledTermination.cs が付属しています。