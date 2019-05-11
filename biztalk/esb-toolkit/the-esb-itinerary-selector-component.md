---
title: ESB スケジュール セレクター コンポーネント |Microsoft Docs
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
ms.openlocfilehash: fcce1fb4ab067e4620bbbca9134e5ac5f5c58889
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399770"
---
# <a name="the-esb-itinerary-selector-component"></a>ESB スケジュール セレクター コンポーネント
ESB スケジュール セレクター コンポーネントは、旅行プランの競合回避モジュールのヘルプのメッセージに対して適切なサーバー側日程を選択して、ESB を通過する SOAP ヘッダーを持たない、受信メッセージを使用できます。 コンポーネントは、クライアントによって要求されると、SOAP ヘッダーを使用して、日程のバージョンと名前を定義するメッセージも使用されます。  
  
## <a name="installation"></a>インストール  
 ESB コアを自動的にインストールするインストール、 **ItinerarySelector**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。  
  
## <a name="how-it-works"></a>しくみ  
 ESB スケジュール セレクター コンポーネントは、受信パイプラインにのみ配置できる Microsoft BizTalk パイプライン コンポーネントです。 コンポーネントは、メッセージの処理で使用するためのサーバー側旅行プランを選択します。 コンポーネントがその構成が読み込まれを使用して、メッセージが受信パイプラインでコンポーネントを通過すると、 **ResolverConnectionString**を呼び出すときに使用する適切な旅行プランを検索する適切な競合回避モジュールのプロパティメッセージを処理します。 スケジュール セレクター コンポーネントは、行程のパイプライン コンポーネントを検証して、メッセージ、メッセージは、次の処理ステージを続けるようにするために必要なプロパティを昇格させると、同じ手順を実行します。  
  
## <a name="using-the-esb-itinerary-selector-component"></a>ESB スケジュール セレクター コンポーネントを使用します。  
 ESB スケジュール コンポーネントを受信パイプラインに追加し、受信場所のパイプラインを使用できます。 WCF の傾斜、名とバージョン (SOAP ヘッダーで表される) ように、クライアントによって要求されたスケジュールの旅程静的リゾルバーでこのコンポーネントを構成するときに、メッセージ コンテキストから取得され、適切な選択に使用旅行プラン。  
  
## <a name="component-properties"></a>コンポーネント プロパティ  
 ESB スケジュール セレクター コンポーネントは、3 つのパブリック プロパティを公開します。  
  
-   **IgnoreErrorKey**します。 このプロパティが定義かどうか、競合回避モジュールでエラーが返された場合、メッセージの処理、スケジュールなし (に設定すると**True**) または中断します。  
  
-   **ItineraryFactKey**します。 これは、選択したスケジュールの実際の XML を格納した競合回避モジュールによって返されたディクショナリのキーを表します。 一般に、 **Resolver.Itinerary**カスタム競合回避モジュールを使用しない限り、します。  
  
-   **ResolverConnectionString**します。 これは、競合回避モジュールを使用する名前と値のペアを含む競合回避モジュールの接続文字列や、旅行プランを検索します。