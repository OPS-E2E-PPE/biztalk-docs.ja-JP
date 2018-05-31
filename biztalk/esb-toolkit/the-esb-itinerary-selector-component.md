---
title: ESB Itinerary セレクター コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83cdd0b2022eb7dc4ad78e5702f5c21e4c4f432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295154"
---
# <a name="the-esb-itinerary-selector-component"></a>ESB Itinerary セレクター コンポーネント
ESB 行程セレクター コンポーネントには、行程をによる競合回避モジュールのヘルプ メッセージの適切なサーバー側日程を選択すると、ESB を通過する SOAP ヘッダーがない入力方向のメッセージが可能です。 コンポーネントは、クライアントによって要求されるとおり、名前と、日程のバージョンを定義する SOAP ヘッダーを使用するメッセージも使用されます。  
  
## <a name="installation"></a>インストール  
 ESB コアを自動的にインストールするとインストール、 **ItinerarySelector**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。  
  
## <a name="how-it-works"></a>しくみ  
 ESB 行程セレクター コンポーネントは、受信パイプラインにのみ存在でく Microsoft BizTalk パイプライン コンポーネントです。 コンポーネントは、メッセージの処理に使用するためのサーバー側旅程を選択します。 コンポーネントがその構成を読み取り、使用して、メッセージが受信パイプラインのコンポーネントを通過するよう、 **ResolverConnectionString**を呼び出すときに使用する適切な旅程を検索する正しい競合回避モジュールのプロパティメッセージを処理しています。 行程セレクター コンポーネントは、メッセージを検証し、メッセージは、次の処理ステージを続けるようにするために必要なプロパティを昇格させる行程パイプライン コンポーネントと同じ手順を実行します。  
  
## <a name="using-the-esb-itinerary-selector-component"></a>ESB Itinerary セレクター コンポーネントを使用します。  
 ESB 行程コンポーネントは、受信パイプラインに追加し、受信場所、パイプラインを使用できます。 WCF 入り口、名前とバージョン (SOAP ヘッダーで表される) ように、クライアントによって要求された行程の日程静的リゾルバーでのこのコンポーネントを構成するとき、メッセージ コンテキストから取得され、適切な選択に使用行程です。  
  
## <a name="component-properties"></a>コンポーネント プロパティ  
 ESB 行程セレクター コンポーネントは、次の 3 つのパブリック プロパティを公開します。  
  
-   **IgnoreErrorKey**です。 このプロパティは定義かどうか、競合回避モジュールでエラーが返される場合は、メッセージの処理、行程なし (に設定すると**True**) または中断しています。  
  
-   **ItineraryFactKey**です。 これは、選択した日程の実際の XML を含む競合回避モジュールによって返されたディクショナリのキーを表します。 一般に、 **Resolver.Itinerary**カスタム競合回避モジュールを使用しない場合、します。  
  
-   **ResolverConnectionString**です。 これは、競合回避モジュールを使用して選択する名前と値のペアを含む競合回避モジュールの接続文字列やルックアップ日程です。