---
title: メッセージのルーティング パターン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d95c5ba0-122f-4793-bfce-a95830dfe094
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a332a8ab942363ff5224f34149b345c9c7d40698
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296890"
---
# <a name="message-routing-patterns"></a>メッセージのルーティング パターン
メッセージのルーティング パターンでは、メッセージをそのターゲットのエンドポイントにルーティングするための実証済みのガイドラインを定義します。 静的構成の結果であることができますルーティングまたは動的に構成できるさまざまな条件とさまざまなメソッドを使用してに基づいています。  
  
## <a name="message-router"></a>メッセージ ルーター  
 メッセージ ルーター パターンでは、一連の条件に基づいて、メッセージの受信者を決定します。 このパターンの詳細については、次を参照してください。[メッセージ ルーター](http://go.microsoft.com/fwlink/?LinkId=186844) ([http://go.microsoft.com/fwlink/?LinkId=186844](http://go.microsoft.com/fwlink/?LinkId=186844)) エンタープライズ統合パターン サイトです。  
  
 行程デザイナーでは、このパターンの実装の組み合わせでは、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary ルーティング サービスと 1 つのコンテンツに基づく競合回避モジュール。 Itinerary ルーティング サービスは Microsoft BizTalk メッセージ コンテキストでメッセージのルーティング プロパティを昇格する場合に、またはメッセージの明示的なルーティングします。  
  
 Itinerary ルーティング サービスによって提供されることができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のようにします。  
  
-   行程デザイナーを使用して BizTalk パイプラインで実行するためのメッセージング エクステンダー itinerary、ルーティング サービスを定義します。  
  
-   BizTalk 送信ポートを使用してルーティングを実行する行程デザイナーを使用してオーケストレーションとして実行するオーケストレーション extender 使用して、itinerary ルーティング サービスを定義します。  
  
 Itinerary ルーティング サービスに関連付けられている競合回避モジュールでは、メッセージの内容に基づいて、メッセージの受信者を決定します。 そのサポートのコンテンツ ベースのルーティングによって提供される競合回避モジュールから選択できます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、独自のリゾルバーを実装することもできます。  
  
 このパターンの実装の例については、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、次のリソースを参照してください。  
  
-   [方法: キーの検索をバインド UDDI を使用してサービス エンドポイントを解決するには](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [方法: UDDI カテゴリの検索を使用してサービス エンドポイントを解決するには](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
## <a name="content-based-router"></a>コンテンツ ベースのルーター  
 コンテンツ ベースのルーター パターンでは、メッセージの内容に基づいて、メッセージの受信者を決定します。 このパターンの詳細については、次を参照してください。[コンテンツ ベースのルーター](http://go.microsoft.com/fwlink/?LinkId=186839) ([http://go.microsoft.com/fwlink/?LinkId=186839](http://go.microsoft.com/fwlink/?LinkId=186839)) エンタープライズ統合パターン サイトです。  
  
 行程デザイナーでは、このパターンの実装の組み合わせでは、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary ルーティング サービスと 1 つのコンテンツに基づく競合回避モジュール。 Itinerary ルーティング サービスは BizTalk メッセージ コンテキストでメッセージのルーティング プロパティを昇格する場合に、または明示的にメッセージをルーティングします。  
  
 Itinerary ルーティング サービスによって提供されることができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のようにします。  
  
-   行程デザイナーを使用して BizTalk パイプラインで実行するためのメッセージング エクステンダーの itinerary ルーティング サービスを定義します。  
  
-   BizTalk 送信ポートを使用してルーティングを実行する行程デザイナーを使用してオーケストレーションとして実行するオーケストレーション エクステンダーの itinerary のルーティング サービスを定義します。  
  
-   行程デザイナーを使用して BizTalk パイプラインで実行するためのブローカー メッセージ extender を使用、itinerary broker サービスを定義します。  
  
 Itinerary ルーティング サービスに関連付けられている競合回避モジュールでは、メッセージの内容に基づいて、メッセージの受信者を決定します。 そのサポートのコンテンツ ベースのルーティングによって提供される次の競合回避モジュールから選択できます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
-   **XPATH リゾルバー**です。 この競合回避モジュールを使用すると、XPATH クエリを使用してメッセージの内容をルーティングすることができます。  
  
-   **BRE リゾルバー**です。 この競合回避モジュールを使用すると、BizTalk ルール エンジンを使用してメッセージの内容からルーティング情報を取得できます。  
  
-   **メッセージのコンテキストの競合回避モジュール**です。 この競合回避モジュールを使用すると、するコンテンツを取得できる、メッセージの BizTalk メッセージ コンテキストから関連付けられているときに、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary broker サービス。  
  
    > [!NOTE]
    >  上記の実装のシナリオに加えてメッセージングまたはオーケストレーションに基づくサービスとして、カスタムの内容に基づく競合回避モジュールと旅程ルーティング ソリューションを開発できます。 ここでは、エクステンダーを実装する必要がありますに可能性があります、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程デザイナーとの相互運用型リゾルバーと旅程サービス。  
  
 たとえば、この実装の次のリソースを参照してください。  
  
-   [インストールして、Itinerary ランプでサンプルを実行します。](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [方法: 既知のメッセージの種類のポリシーをルール実装のビジネスを使用してコンテンツ ベース ルーティング](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [方法: 動的にビジネス ルール ポリシーを使用して、メッセージ コンテキストに基づいたメッセージをルーティング](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
## <a name="routing-slip"></a>回覧  
 明細のルーティング パターンでは、一連の可能性がありますが、デザイン時に認識されていない定義済みの順序でコンポーネントをメッセージをルーティングする必要がありますシナリオについて説明します。 このパターンの詳細については、次を参照してください。[ルーティング スリップ](http://go.microsoft.com/fwlink/?LinkId=186840)([http://go.microsoft.com/fwlink/?LinkId=186840](http://go.microsoft.com/fwlink/?LinkId=186840)) エンタープライズ統合パターン サイトです。  
  
 によって提供されるこのパターンの実装、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]; その実装は、行程ベースの処理のメッセージを送信するクライアント アプリケーションの種類によって異なります。  
  
-   **サービス プロキシ**です。 この種類のアプリケーションでは、構成、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]入り口行程セレクター パイプライン コンポーネントを使用し、適切な選択を itinerary の競合回避モジュールを関連付ける[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程です。 行程リゾルバーを使用して静的なプロパティとして itinerary プロパティを構成する場合がありますか、これらは、BizTalk ルール エンジンと BRI 競合回避モジュールを使用して動的なプロパティとして構成できます。  
  
-   **アドバンスト クライアント**です。 この種類のアプリケーションでは、構成、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]の日程セレクター パイプライン コンポーネントと、日程静的競合回避モジュールに着手します。 クライアント アプリケーションでは、itinerary 名前、バージョン、および追跡 id が含まれていますが、itinerary 参照ヘッダーを持つメッセージを送信します。  
  
-   **アダプティブ クライアント**です。 このタイプのアプリケーションでは、クライアント アプリケーションは、さらに、要求メッセージとしてクライアントの状態を渡すことによって、itinerary 参照を識別するリゾルバー サービスを呼び出します。 Itinerary が解決した場合、クライアント アプリケーションは、上記のクライアントの高度なシナリオの場合と同じ方法で itinerary の参照を含むメッセージを送信します。  
  
 このパターンの実装の詳細については、次のリソースを参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
    > [!NOTE]
    >  上記のシナリオに加えて、カスタム itinerary 競合回避モジュールと旅程ルーティング サービスを開発できます。 行程デザイナーで使用するためのカスタムの itinerary サービスのエクステンダーをデザイナーの作成を検討する可能性があります。  
  
## <a name="scatter-gather"></a>スキャッター/ギャザー  
 スキャッター/ギャザー パターンでは、複数の受信者に送信しての応答を集計メッセージこの結果、1 つのメッセージ。 このパターンの詳細については、次を参照してください。[スキャッター/ギャザー](http://go.microsoft.com/fwlink/?LinkId=186841) ([http://go.microsoft.com/fwlink/?LinkId=186841](http://go.microsoft.com/fwlink/?LinkId=186841)) エンタープライズ統合パターン サイトです。  
  
 このパターンの実装の例は、次を参照してください。、[をインストールすると、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)サンプルです。  
  
## <a name="recipient-list"></a>受信者の一覧  
 受信者リスト パターンでは、1 つまたは複数の受信者には、メッセージのルーティング シナリオのソリューションを説明します。 受信者一覧には、静的に定義されているいずれか (受信者の固定リストがあることを意味) または動的にします。 このパターンの詳細については、次を参照してください。[受信者リスト](http://go.microsoft.com/fwlink/?LinkId=186842)([http://go.microsoft.com/fwlink/?LinkId=186842](http://go.microsoft.com/fwlink/?LinkId=186842)) エンタープライズ統合パターン サイトです。  
  
 行程デザイナーでは、このパターンの実装の組み合わせでは、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary ルーティング サービスと複数の競合回避モジュール。 Itinerary ルーティング サービスは、メッセージの複製と明示的にメッセージをルーティングする、BizTalk メッセージ コンテキスト プロパティを使用します。  
  
 Itinerary ルーティング サービスによって提供されることができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のようにします。  
  
-   行程デザイナーを使用して、BizTalk パイプラインで実行するためのメッセージング エクステンダー itinerary、ルーティング サービスを定義します。  
  
-   BizTalk 送信ポートを使用してルーティングを実行する行程デザイナーを使用してオーケストレーションとして実行するメッセージング エクステンダー itinerary、ルーティング サービスを定義します。  
  
 Itinerary ルーティング サービスに関連付けられている競合回避モジュールでは、メッセージの内容に基づいて、メッセージの受信者を決定します。 一連の競合回避モジュールによって提供されることができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このシナリオを実装します。 このパターンの実装の詳細については、次のリソースを参照してください。  
  
-   [方法: Itinerary ルーティング先を使用して複数の受信者を 1 つのメッセージをルーティング](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
## <a name="splitter"></a>スプリッター  
 分割パターンは、1 つのメッセージは、複数のメッセージに分割する必要がある場合に、問題を解決します。 このパターンの詳細については、次を参照してください。[スプリッター](http://go.microsoft.com/fwlink/?LinkId=186843) ([http://go.microsoft.com/fwlink/?LinkId=186843](http://go.microsoft.com/fwlink/?LinkId=186843)) エンタープライズ統合パターン サイトです。 このパターンの実装の詳細については、次のリソースを参照してください。  
  
-   [方法: インターチェンジを分割し、結果として得られるメッセージをルーティング、個別の日程を使用して複数のファイルの場所](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)