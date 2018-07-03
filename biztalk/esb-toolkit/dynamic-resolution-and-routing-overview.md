---
title: 動的な解決とルーティングの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab7ea6f4ddd37be8d8c2c6629d2449c2d9df5f81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018768"
---
# <a name="dynamic-resolution-and-routing-overview"></a>動的な解決とルーティングの概要
ESB リゾルバー クラスは、次の実行時の解像度をサポートします。  

- メッセージ配信のエンドポイント  

- 変換のマップ  

- エンドポイントの構成  

- カスタムのサービス メタデータ  

- サーバー側のスケジュール  

  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが届いたときに、マップとエンドポイントの解決を試行する競合回避モジュールの接続文字列を使用します。 これらの接続文字列に存在 itinerary の SOAP ヘッダー メッセージの到着、または、次のパイプライン コンポーネントのいずれかを使用してカスタム パイプラインで設定できます: ESB スケジュール セレクター、ESB ディスパッチャー、または ESB ディスパッチャー逆アセンブルします。 解像度は、ESB リゾルバーとアダプターのプロバイダー フレームワーク コンポーネントの"- just-in-time"(JIT) の解決機能を使用して処理ライフ サイクルの後半に発生します。  

  たとえばをマップする必要がありますが、マップ名が決定されていないメッセージを受信すると、動的変換エージェントに関連付けられている競合回避モジュールを使用して、解決を実行することがされます。 JIT の解決に失敗した場合、システムは例外メッセージを生成、エラーとして分類するがします。  

  リゾルバーとアダプターのプロバイダー フレームワークは、次のデータ ストアまたは解決メカニズムを照会できます。  

- ハード コーディングされたマップやエンドポイントの大文字と小文字の動的な解決は発生しません  

- ビジネス ルール エンジン (BRE) ポリシー  

- 実装するカスタム アセンブリ、 **IResolveProvider**インターフェイス  

- メッセージの上、XPath クエリ  

- Universal Description, Discovery, and Integration (UDDI) の参照
