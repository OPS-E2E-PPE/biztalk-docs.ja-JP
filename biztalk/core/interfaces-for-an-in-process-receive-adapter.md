---
title: 受信アダプターをインプロセスで用のインターフェイス |Microsoft Docs
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
ms.openlocfilehash: 1a222f41d28b57053c192db3235e2fa7f4f710ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381729"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a>インプロセス受信アダプター用のインターフェイス
メッセージング エンジンはインスタンス化して、インプロセス アダプター、アダプターがその機能にアクセスできるように、トランスポート プロキシに渡すことを構成します。 構成とバインディングを有効にする、トランスポート プロキシには、アダプターが次の構成インターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBTTransportControl**  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
  必要に応じて、アダプターが初期化中にハンドラー情報を受信する場合は、する必要がある実装**IPersistPropertyBag**します。  
  
  メッセージング エンジン アダプターのインスタンスを作成、初期化し、および設定の構成の場所を受信します。 メッセージング エンジンがアダプター プロパティ バッグを渡します、 **AddReceiveEndpoint**メソッドの呼び出し。 プロパティ バッグには、受信場所と受信ハンドラーの構成が含まれています。 構成は、XML スタイルのプロパティ バッグの形式でデータベースに格納されます。 メッセージング エンジンでは、XML を読み取り、XML からプロパティ バッグを復元します。 後は、少なくとも 1 つのエンドポイント (受信場所) が追加すると、アダプターがメッセージの送信を開始することができます。  
  
> [!NOTE]
>  アダプターがメッセージング エンジンなどの呼び出しはブロックされません**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**. 過度のこれらの呼び出しで処理を実行すると、サービスの開始時に影響します。  
  
 次の図は、プロセスの作成に関連するオブジェクトの相互作用の受信アダプターを示します。  
  
 ![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")  
受信アダプター プロセス内のワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [インターフェイスの分離受信アダプター](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [要求 - 応答の同期受信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)