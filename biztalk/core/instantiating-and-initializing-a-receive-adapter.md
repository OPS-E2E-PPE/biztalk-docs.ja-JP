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
ms.openlocfilehash: 73bb52934483cc47ea45cd0e6ff72e8e57752ffd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331821"
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a>受信アダプターのインスタンス化と初期化
受信アダプターがインスタンス化された後は、メッセージング エンジンによって初期化は、すぐに、エンジンは、IBTTransportControl の QueryInteraface を呼び出します。 呼び出して IBTTransportControl<strong>します。初期化</strong>をメンバー変数が解決しないアダプター、アダプターのトランスポート プロキシに渡します。 次に、エンジンが呼び出す**QueryInterface**の**IPersistPropertyBag**します。 これは省略可能なインターフェイスです。ハンドラーの構成がアダプターに渡される場合は、アダプターを実装すると、**ロード**メソッドの呼び出し。 受信アダプターの初期化の最終段階では、エンドポイント構成をアダプターに渡す必要があります。 このフェーズ エンジン呼び出し**IBTTransportConfig.AddReceiveEndpoint**エンドポイント、エンドポイントのアダプター固有の構成、および BizTalk の構成の URI を渡すしながら、アクティブなエンドポイントごとに 1 回そのエンドポイント。  
  
 次の図は、この一連の API 呼び出しを示しています。 アダプターは、青色で示されるインターフェイスを実装します。  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 **実装のヒン ト:** 一般に、アダプターをブロックしないでください呼び出しにおいてメッセージング エンジンなど**IBTTransportControl.Initialize**、 **IPersistPropertyBag.Load**、および**IBTTransportConfig.AddReceiveEndpoint**します。 過度のこれらの呼び出しで処理を実行するサービスの開始時に悪影響を及ぼすことができます。  
  
 すべての受信アダプターが、関連付けられている以上の受信場所またはサービスの開始時に作成されます。 すべての受信アダプターは非同期とバッチ処理をサポートします。 インプロセスまたは分離できます。 詳細については、受信アダプター変数を参照してください[のアダプタ変数](../core/adapter-variables.md)します。