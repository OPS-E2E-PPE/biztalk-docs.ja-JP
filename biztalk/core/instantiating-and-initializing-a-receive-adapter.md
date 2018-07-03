---
title: インスタンス化と初期化、アダプターの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5cb5ba7-e2b5-49d2-adf5-a8df0bb81def
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f14a6262a8f0ed816700f3e3c34307487874d25
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983339"
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a>受信アダプターのインスタンス化と初期化
受信アダプターは、インスタンス化されるとすぐメッセージング エンジンによって初期化されます。メッセージング エンジンはまず、IBTTransportControl の QueryInteraface を呼び出し、 呼び出して IBTTransportControl<strong>します。初期化</strong>をメンバー変数が解決しないアダプター、アダプターのトランスポート プロキシに渡します。 次に、エンジンが呼び出す**QueryInterface**の**IPersistPropertyBag**します。 これは省略可能なインターフェイスです。ハンドラーの構成がアダプターに渡される場合は、アダプターを実装すると、**ロード**メソッドの呼び出し。 受信アダプターの初期化の最終段階では、エンドポイント構成がアダプターに渡されます。 このフェーズ エンジン呼び出し**IBTTransportConfig.AddReceiveEndpoint**エンドポイント、エンドポイントのアダプター固有の構成、および BizTalk の構成の URI を渡すしながら、アクティブなエンドポイントごとに 1 回そのエンドポイント。  
  
 この API 呼び出しの順序は、次の図のようになります。 アダプターは、青色で示されるインターフェイスを実装します。  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 **実装のヒン ト:** 一般に、アダプターをブロックしないでください呼び出しにおいてメッセージング エンジンなど**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**します。 過度のこれらの呼び出しで処理を実行するサービスの開始時に悪影響を及ぼすことができます。  
  
 受信場所が 1 つ以上関連付けられている受信アダプターはすべて、サービスの開始時に作成されます。 すべての受信アダプターは非同期であり、バッチ処理をサポートしています。 受信アダプターは、インプロセスの場合と分離の場合があります。 詳細については、受信アダプター変数を参照してください[のアダプタ変数](../core/adapter-variables.md)します。