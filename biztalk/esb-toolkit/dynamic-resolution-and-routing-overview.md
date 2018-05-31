---
title: 動的な解像度とルーティングの概要 |Microsoft ドキュメント
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
ms.openlocfilehash: 341b8389530ac85fdc459816f5691f3b814fbd56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22293994"
---
# <a name="dynamic-resolution-and-routing-overview"></a>動的な解像度とルーティングの概要
ESB 競合回避モジュールのクラスは、次の実行時の解像度をサポートします。  
  
-   メッセージ配信のエンドポイント  
  
-   変換のマップ  
  
-   エンドポイントの構成  
  
-   カスタムのサービス メタデータ  
  
-   サーバー側の日程  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが到着したときに、マップとエンドポイントの解決を試行する競合回避モジュールの接続文字列を使用します。 これらの接続文字列があります itinerary の SOAP ヘッダー メッセージの到着するは、次のパイプライン コンポーネントのいずれかを使用してカスタム パイプラインで設定することがあります: ESB 行程セレクター、ESB ディスパッチャーまたは ESB ディスパッチャーの逆アセンブルします。 解像度は、機能を使用して、「ジャストでタイム」(JIT) の解像度 ESB 競合回避モジュールとアダプターのプロバイダー フレームワーク コンポーネントの処理のライフ サイクルの後で発生します。  
  
 たとえば、動的変換エージェントをマップする必要がありますが、マップ名がまだ決定されているメッセージを受信した場合、しようと、解決を実行する、関連付けられている競合回避モジュールを使用します。 JIT 解決が失敗した場合、システムは例外メッセージを生成をエラーとして分類されるはします。  
  
 アダプター プロバイダーのフレームワークとの競合回避モジュールは、次のデータ ストア、または解決メカニズムを照会できます。  
  
-   マップのハードコーディングまたはで動的解決のケースが存在しない、エンドポイント  
  
-   ビジネス ルール エンジン (BRE) ポリシー  
  
-   実装するカスタム アセンブリ、 **IResolveProvider**インターフェイス  
  
-   メッセージに XPath クエリ  
  
-   Universal Description, Discovery, and Integration (UDDI) の参照