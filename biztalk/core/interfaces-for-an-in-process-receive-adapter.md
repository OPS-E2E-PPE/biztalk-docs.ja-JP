---
title: 受信アダプターをインプロセスで用のインターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7135471700cf640f61b56506ad159b5c47c7d877
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257650"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a>インプロセス受信アダプター用のインターフェイス
メッセージング エンジンは、インプロセス アダプターをインスタンス化して構成し、トランスポート プロキシに渡して、アダプターがその機能にアクセスできるようにします。 構成およびトランスポート プロキシへのバインドを有効にするには、アダプターに次の構成インターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBTTransportControl**  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
 必要に応じて、アダプターが初期化中にハンドラー情報を受信する場合に必要な実装**IPersistPropertyBag**です。  
  
 メッセージング エンジンは、アダプターのインスタンスを作成し、初期化して、受信場所の構成を設定します。 メッセージング エンジンが上のアダプターにプロパティ バッグを渡します、 **AddReceiveEndpoint**メソッドの呼び出しです。 プロパティ バッグには、受信場所と受信ハンドラーの構成が含まれます。 構成は、XML スタイルのプロパティ バッグの形式で、データベースに格納されます。 メッセージング エンジンは、XML を読み取り、XML からプロパティ バッグを復元します。 少なくとも 1 つのエンドポイント (受信場所) が追加されたら、アダプターはメッセージの送信を開始できます。  
  
> [!NOTE]
>  アダプターがメッセージング エンジンなどの呼び出しはブロックされません**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**. 過剰なこれらの呼び出しでの処理を実行すると、サービスの起動時、影響します。  
  
 インプロセス受信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")  
インプロセス受信アダプターのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [受信アダプターの分離用のインターフェイス](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [アダプターの受信要求-応答の同期用のインターフェイス](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)