---
title: インターフェイスの分離受信アダプター |Microsoft Docs
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
ms.openlocfilehash: 2d0db026534a15b1c1e3cfe2f5582db8b9e1078f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331489"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a>分離受信アダプター用のインターフェイス
分離受信アダプターが以外のプロセス空間内でホストされる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス。 をメッセージング エンジンと対話するには、分離受信アダプターのレジスタ自体の起動時に、エンジンの構成および制御できるようにします。 アダプターのトランスポート プロキシを作成、インターフェイスのクエリ**IBTTransportProxy**、および呼び出し**IBTTransportProxy.RegisterIsolatedReceiver**を登録するその**IBTTransportConfig**メッセージング エンジンとコールバック インターフェイス。 アダプターは、その最初のメッセージを送信する前に、この同期呼び出しが発生した[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 これにより、メッセージング エンジンでアダプターにコールバックして、エンドポイントがアクティブと受信メッセージをリッスンする必要があります。 分離アダプターは、次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
  アダプターを登録するには、アダプターが渡す、構成されている必要があり、有効になっている受信場所。 アダプターのホスト プロセスは、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。 さらに、アダプターを照会して、id が正しいクラスと、そのホスト インスタンス用に構成されたコンピューターで実行していることを確認します。  
  
  メッセージング エンジンは、構成情報を渡すし、呼び出すことによって、その他の受信場所、アダプターをアダプターがトランスポート プロキシで正常に登録した後、**ロード**のメソッド、 **IPersistPropertyBag**インターフェイスと**AddReceiveEndpoint**のメソッド、 **IBTTransportConfig**それぞれインターフェイスします。  
  
  呼び出す必要があります、分離受信アダプターがメッセージの処理を終了および終了する、 **TerminateIsolatedReceiver**のメソッド、 **IBTTransportProxy**インターフェイス。  
  
  次の図は、受信アダプターの分離の作成に関連するオブジェクトの相互作用を示しています。  
  
  ![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")  
  受信アダプターの分離を初期化するためのワークフロー。  
  
> [!NOTE]
>  あるアダプターの追跡を現在実行中の要求をお勧めします。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 アダプターをブロックする必要があります、 **Terminate**作業数が 0 に到達するまでメソッド。 受信側では、この作業に公開されていない、未処理の要求が含まれています[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 応答メッセージは通常できませんに配信されたこと後に受信アダプターに注意してください。 **Terminate**が呼び出されます。 一般に、アダプターの呼び出し後、 **Terminate**メソッド、メッセージング エンジンでは送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを発行する要求が受け付けられません。  
> 
> [!NOTE]
>  1 つだけのプロセスが 1 つのアダプターをホスト中に、1 つのプロセスは、分離アダプターの複数のインスタンスをホストできます。  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [要求 - 応答の同期受信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)