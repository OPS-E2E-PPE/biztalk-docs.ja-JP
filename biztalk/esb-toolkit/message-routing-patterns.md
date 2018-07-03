---
title: メッセージ ルーティング パターン |Microsoft Docs
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
ms.openlocfilehash: 7233c5d5f5a3669cf23931afc29dfaac8548dc3d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022088"
---
# <a name="message-routing-patterns"></a>メッセージのルーティング パターン
メッセージのルーティング パターンでは、メッセージをそのターゲット エンドポイントにルーティングするための実証済みのガイドラインを定義します。 静的構成の結果であることができますルーティングまたは動的に構成できるさまざまな条件とさまざまなメソッドを使用してに基づいています。  
  
## <a name="message-router"></a>メッセージのルーター  
 メッセージのルーター パターンは、一連の条件に基づいてメッセージの受信者を決定します。 このパターンの詳細については、次を参照してください。[メッセージ ルーター](http://go.microsoft.com/fwlink/?LinkId=186844) ([http://go.microsoft.com/fwlink/?LinkId=186844](http://go.microsoft.com/fwlink/?LinkId=186844))、エンタープライズ統合パターン サイト。  
  
 旅行プラン デザイナーでは、このパターンの実装の組み合わせでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュール ルーティング サービスと 1 つのコンテンツ ベースのリゾルバー。 スケジュールのルーティング サービスは、Microsoft BizTalk メッセージ コンテキストでメッセージのルーティング プロパティの昇格またはメッセージの明示的なルーティングの責任を負う。  
  
 スケジュール オンランプ ルーティング サービスによって提供されることができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のようにします。  
  
- 旅行プラン デザイナーを使用して BizTalk パイプラインで実行するメッセージング extender でスケジュール ルーティング サービスを定義します。  
  
- BizTalk 送信ポートを使用してルーティングを実行するスケジュールのデザイナーを使用してオーケストレーションとして実行するオーケストレーション エクステンダーでスケジュール ルーティング サービスを定義します。  
  
  スケジュールのルーティング サービスに関連付けられている競合回避モジュールは、メッセージの内容に基づいて、メッセージの受信者を決定します。 そのサポート コンテンツ ベース ルーティングによって提供される、リゾルバーから選択できます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、独自のリゾルバーを実装することができます。  
  
  このパターンの実装の例については、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、次のリソースを参照してください。  
  
- [方法: UDDI バインド キー検索を利用し、サービス エンドポイントを解決する](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
- [方法: UDDI カテゴリ検索を利用し、サービス エンドポイントを解決する](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
## <a name="content-based-router"></a>コンテンツ ベースのルーター  
 コンテンツ ベースのルーター パターンは、メッセージの内容に基づいてメッセージの受信者を決定します。 このパターンの詳細については、次を参照してください。[コンテンツ ベースのルーター](http://go.microsoft.com/fwlink/?LinkId=186839) ([http://go.microsoft.com/fwlink/?LinkId=186839](http://go.microsoft.com/fwlink/?LinkId=186839))、エンタープライズ統合パターン サイト。  
  
 旅行プラン デザイナーでは、このパターンの実装の組み合わせでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュール ルーティング サービスと 1 つのコンテンツ ベースのリゾルバー。 スケジュール オンランプ ルーティング サービスは、BizTalk メッセージ コンテキストでメッセージのルーティング プロパティを昇格する場合に、または明示的にメッセージをルーティングします。  
  
 スケジュール オンランプ ルーティング サービスによって提供されることができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のようにします。  
  
- 旅行プラン デザイナーを使用して BizTalk パイプラインで実行するメッセージング extender でスケジュール ルーティング サービスを定義します。  
  
- BizTalk 送信ポートを使用してルーティングを実行する、旅行プラン デザイナーを使用してオーケストレーションとして実行するオーケストレーション エクステンダーでスケジュール ルーティング サービスを定義します。  
  
- 旅行プラン デザイナーを使用して BizTalk パイプラインで実行するブローカー メッセージング エクステンダーで、スケジュール オンランプ broker サービスを定義します。  
  
  スケジュールのルーティング サービスに関連付けられている競合回避モジュールは、メッセージの内容に基づいてメッセージの受信者を決定します。 そのサポート コンテンツ ベース ルーティングによって提供される次の競合回避モジュールから選択できます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
- **XPATH の競合回避モジュール**します。 この競合回避モジュールを使用すると、XPATH クエリを使用してメッセージの内容をルーティングすることができます。  
  
- **BRE リゾルバー**します。 この競合回避モジュールを使用すると、BizTalk ルール エンジンを使用してメッセージの内容からルーティング情報を取得できます。  
  
- **メッセージのコンテキストの競合回避モジュール**します。 この競合回避モジュールを使用するから取得できます、メッセージの内容、BizTalk メッセージ コンテキストが関連付けられているときに、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary broker サービス。  
  
  > [!NOTE]
  >  前の実装シナリオに加えメッセージング ベースまたはオーケストレーションに基づくサービスとして、カスタム コンテンツに基づく競合回避モジュールとスケジュールのルーティング ソリューションを開発できます。 ここでは、エクステンダーを実装する必要がありますに可能性があります、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]旅行プラン デザイナーを使用した相互運用する競合回避モジュールと旅行プランのサービスです。  
  
  たとえば、この実装の次のリソースを参照してください。  
  
- [スケジュール オンランプ サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
- [方法: 既知のメッセージ タイプに関するビジネス ルール ポリシーを利用し、コンテンツベースのルーティングを実装する](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
- [方法: ビジネス ルール ポリシーを利用し、メッセージ コンテキストに基づき、メッセージの経路を動的に決定する](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
## <a name="routing-slip"></a>回覧  
 ルーティング スリップ パターンでは、一連のデザイン時に認識されていない可能性があります、事前定義された順序でコンポーネントをメッセージをルーティングする必要がありますシナリオについて説明します。 このパターンの詳細については、次を参照してください。[回覧用紙](http://go.microsoft.com/fwlink/?LinkId=186840)([http://go.microsoft.com/fwlink/?LinkId=186840](http://go.microsoft.com/fwlink/?LinkId=186840))、エンタープライズ統合パターン サイト。  
  
 このパターンの実装によって提供されます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]; その実装は、スケジュールに基づく処理のためのメッセージを送信するクライアント アプリケーションの種類によって異なります。  
  
- **サービス プロキシ**します。 この種類のアプリケーションでは、構成、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュール セレクターのパイプライン コンポーネントに着手し、適切な選択をスケジュールに競合回避モジュールを関連付ける[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュール。 スケジュールのリゾルバーを使用して静的なプロパティとしてスケジュールのプロパティを構成することがあります。 または BizTalk ルール エンジン、および BRI リゾルバーを使用して動的プロパティとして構成できます。  
  
- **高度なクライアント**します。 この種類のアプリケーションでは、構成、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュール セレクターのパイプライン コンポーネントと旅程静的競合回避モジュールに着手します。 クライアント アプリケーションでは、スケジュールの名前、バージョン、および追跡識別子が含まれていますが、スケジュールの参照をヘッダーを使ってメッセージを送信します。  
  
- **アダプティブ クライアント**します。 このタイプのアプリケーションでは、クライアント アプリケーションは、により、さらに、要求メッセージとしてクライアントの状態を渡すことによって、スケジュールの参照を識別するリゾルバー サービスを呼び出します。 場合は、スケジュールを解決すると、クライアント アプリケーションは、上記のクライアントの高度なシナリオと同じ方法でスケジュールの参照を含むメッセージを送信します。  
  
  このパターンの実装の詳細については、次のリソースを参照してください。  
  
- [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
- [方法: メッセージを変換し、スケジュール ルーティング スリップを利用してファイルの場所に送信する](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
  > [!NOTE]
  >  前述のシナリオだけでなく、カスタム スケジュール オンランプ競合回避モジュールとスケジュールのルーティング サービスを開発できます。 旅行プラン デザイナーでカスタム スケジュール サービスとして使用するためのデザイナーのエクステンダーを作成を検討することがあります。  
  
## <a name="scatter-gather"></a>スキャッター/ギャザー  
 スキャッター/ギャザー パターンでは、複数の受信者に送信してへの応答を集計するメッセージを使用できます。これにより、1 つのメッセージ。 このパターンの詳細については、次を参照してください。[スキャッター/ギャザー](http://go.microsoft.com/fwlink/?LinkId=186841) ([http://go.microsoft.com/fwlink/?LinkId=186841](http://go.microsoft.com/fwlink/?LinkId=186841))、エンタープライズ統合パターン サイト。  
  
 このパターンの実装の例は、次を参照してください。、[をインストールすると、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)サンプル。  
  
## <a name="recipient-list"></a>受信者の一覧  
 受信者リスト パターンでは、1 つまたは複数の受信者には、メッセージのルーティング シナリオのソリューションを説明します。 受信者の一覧は、静的に定義されているいずれか (受信者の固定リストがあることを意味) または動的にします。 このパターンの詳細については、次を参照してください。[受信者リスト](http://go.microsoft.com/fwlink/?LinkId=186842)([http://go.microsoft.com/fwlink/?LinkId=186842](http://go.microsoft.com/fwlink/?LinkId=186842))、エンタープライズ統合パターン サイト。  
  
 旅行プラン デザイナーでは、このパターンの実装の組み合わせでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュール ルーティング サービスと複数の競合回避モジュール。 スケジュールのルーティング サービスは、メッセージのクローンを作成し、明示的にメッセージをルーティングする、BizTalk メッセージ コンテキスト プロパティを使用します。  
  
 スケジュール オンランプ ルーティング サービスによって提供されることができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のようにします。  
  
- 旅行プラン デザイナーを使用して BizTalk パイプラインで実行するメッセージング extender でスケジュール ルーティング サービスを定義します。  
  
- メッセージングのエクステンダーとして BizTalk 送信ポートを使用してルーティングを実行する、旅行プラン デザイナーを使用してオーケストレーションを実行するスケジュールのルーティング サービスを定義します。  
  
  スケジュールのルーティング サービスに関連付けられている競合回避モジュールは、メッセージの内容に基づいてメッセージの受信者を決定します。 によって提供される競合回避モジュールのセットを選択することができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このシナリオを実装します。 このパターンの実装の詳細については、次のリソースを参照してください。  
  
- [方法: スケジュール ルーティング スリップを利用し、1 つのメッセージを複数の受信者に送信する](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
## <a name="splitter"></a>スプリッター  
 分割パターンは、1 つのメッセージは、複数のメッセージに分割する必要がある場合、問題を解決します。 このパターンの詳細については、次を参照してください。[スプリッター](http://go.microsoft.com/fwlink/?LinkId=186843) ([http://go.microsoft.com/fwlink/?LinkId=186843](http://go.microsoft.com/fwlink/?LinkId=186843))、エンタープライズ統合パターン サイト。 このパターンの実装の詳細については、次のリソースを参照してください。  
  
-   [方法: 別個のスケジュールを利用し、インターチェンジを分割して結果的に生成されたメッセージを複数のファイルの場所に送る](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)