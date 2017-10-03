---
title: "インスタンス化と初期化、受信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5cb5ba7-e2b5-49d2-adf5-a8df0bb81def
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565712faecf11b728c4f552798b1e3daebf962f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a>受信アダプターのインスタンス化と初期化
受信アダプターは、インスタンス化されるとすぐメッセージング エンジンによって初期化されます。メッセージング エンジンはまず、IBTTransportControl の QueryInteraface を呼び出し、 IBTTransportControl 順に呼び出して**です。初期化**をメンバー変数に永続化する、アダプター、アダプターのトランスポート プロキシに渡します。 次に、エンジンを呼び出す**QueryInterface**の**IPersistPropertyBag**です。 これは省略可能なインターフェイスです。ハンドラーの構成がアダプターに渡される場合は、アダプターを実装すると、**ロード**メソッドの呼び出しです。 受信アダプターの初期化の最終段階では、エンドポイント構成がアダプターに渡されます。 このフェーズ エンジン呼び出し**IBTTransportConfig.AddReceiveEndpoint**エンドポイント、エンドポイントのアダプター固有の構成および BizTalk の構成を URI で渡すしながら、アクティブなエンドポイントごとに 1 回そのエンドポイント。  
  
 この API 呼び出しの順序は、次の図のようになります。 アダプターは、青色で示されるインターフェイスを実装します。  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 **実装のヒン ト:**一般に、アダプターをブロックしないでください呼び出しにおいてメッセージング エンジンなど**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**です。 過剰なこれらの呼び出しでの処理を実行すると、サービスの起動時にマイナスの影響があります。  
  
 受信場所が 1 つ以上関連付けられている受信アダプターはすべて、サービスの開始時に作成されます。 すべての受信アダプターは非同期であり、バッチ処理をサポートしています。 受信アダプターは、インプロセスの場合と分離の場合があります。 詳細については、受信アダプター変数を参照してください[のアダプタ変数](../core/adapter-variables.md)です。