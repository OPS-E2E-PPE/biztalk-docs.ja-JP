---
title: 受信アダプターの分離インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c6b195e-76bf-4c3e-a324-5513bc24fed1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7848e5c808ad2e7517d0e850e449f8a8575ec5da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257770"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a>分離受信アダプター用のインターフェイス
分離受信アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以外のプロセス領域でホストされます。 メッセージング エンジンと連携するために、分離受信アダプターは、エンジンが分離受信アダプターを構成および制御できるように、起動時に分離受信アダプター自体を登録します。 アダプターが、トランスポート プロキシを作成し、インターフェイスの照会**IBTTransportProxy**、および呼び出し**IBTTransportProxy.RegisterIsolatedReceiver**を登録する、 **IBTTransportConfig**メッセージング エンジンにコールバック インターフェイス。 この同期呼び出しは、アダプターが最初のメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信する前に発生します。 これによって、メッセージ エンジンは、アダプターへのコールバックを行い、どのエンドポイントがアクティブであるか、および受信メッセージの待ち受けの対象となる必要があるかをアダプターに示すことができます。 分離アダプターは次のインターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
-   **IPersistPropertyBag**  
  
 アダプターの登録では、構成および有効化された受信場所をアダプターが渡す必要があります。 アダプターのホスト プロセスは、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。 また、クラス ID が正しく、実行するように構成されているホスト インスタンスに対応したコンピューターで実行中であることを確認するための照会が、アダプターに対して行われます。  
  
 登録した後、アダプターが正常にトランスポート プロキシを使用して、メッセージング エンジンは、構成情報を渡しますおよび、他の受信場所のアダプターに戻し、呼び出すことによって、**ロード**のメソッド、 **IPersistPropertyBag**インターフェイスおよび**AddReceiveEndpoint**のメソッド、 **IBTTransportConfig**それぞれインターフェイスです。  
  
 分離受信アダプターがメッセージの処理を終了し、終了すると、呼び出す必要があります、 **TerminateIsolatedReceiver**のメソッド、 **IBTTransportProxy**インターフェイスです。  
  
 分離受信アダプターを作成するときのオブジェクト間の対話処理を次の図に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")  
分離受信アダプターの初期化のワークフロー  
  
> [!NOTE]
>  アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に対して現在実行している要求を追跡することをお勧めします。 アダプターをブロックする必要があります、 **Terminate**作業数が 0 に到達するまでメソッドです。 受信側では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に対して公開されていない未処理の要求がこの作業に含まれます。 応答メッセージは通常配信されることは後に受信アダプターに注意してください**Terminate**と呼びます。 一般に、アダプターの呼び出し後に、 **Terminate**メソッド、メッセージング エンジンでは送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを公開要求が受け付けられません。  
  
> [!NOTE]
>  1 つのプロセスは 1 つのアダプターしかホストできませんが、分離アダプターの複数のインスタンスをホストできます。  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [アダプターの受信要求-応答の同期用のインターフェイス](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)