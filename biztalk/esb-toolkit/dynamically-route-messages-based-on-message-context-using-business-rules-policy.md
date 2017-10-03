---
title: "方法: 動的にビジネス ルール ポリシーを使用して、メッセージ コンテキストに基づいたメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717e0180ba92d49751342e00a4d0367832084135
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a>方法: 動的にビジネス ルール ポリシーを使用して、メッセージ コンテキストに基づいたメッセージをルーティング
## <a name="goal"></a>[目標]  
 このセクションを使用して、メッセージ コンテキスト プロパティに基づいて、メッセージのエンドポイントを決定する旅程を作成する方法を示します、[!INCLUDE[prague](../includes/prague-md.md)]ビジネス ルール エンジン (BRE) ポリシーと、ルートを使用して、メッセージ、[!INCLUDE[prague](../includes/prague-md.md)]ファイル アダプター。  
  
 このトピックでは、次の手順を行います。  
  
-   メッセージ型に評価するビジネス ルール ポリシーを作成します。  
  
-   ビジネス ルール ポリシーを使用して動的にルーティングする itinerary 回覧を作成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="steps"></a>手順  
 **メッセージ コンテキスト プロパティを使用してメッセージをルーティングする BRE ポリシーを作成するには**  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[prague](../includes/prague-md.md)]** 、順にクリック**ビジネス ルール作成ツール**です。  
  
2.  ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。 ポリシーに名前**RouteBasedOnMessageType**です。  
  
 **北米地域の注文のルーティング規則を追加するには**  
  
1.  **RouteBasedOnMessageType**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。 ルールの名前として**SetNAOrderEndpoint**です。  
  
2.  ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。  
  
3.  ファクト エクスプ ローラーで、展開、 **ESB です。ContextInfo**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**コンテキスト メッセージ型**にファクト、 **argument1**ノードの下**条件**です。  
  
    > [!NOTE]
    >  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ルールの作成に使用できるいくつかのボキャブラリが含まれています。 これらのいくつかは、交換する必要があります。 または独自のボキャブラリで補完されました。 たとえば、 **DynamicRunTimeMaptypes**ポリシーに入っているマップの定義には、 **GlobalBank**サンプルです。  
  
4.  クリックして、 **argument2**ノード、および入力**http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**  
  
5.  ファクト エクスプ ローラーで、展開、 **ESB です。EndPointInfo**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**終点送信トランスポート場所の設定**の定義を**アクション**です。  
  
6.  をクリックして**\<空の文字列 >**、し、入力**C:\HowTos\Out\NorthAmerica%MessageID%.xml**  
  
7.  ファクト エクスプ ローラーからドラッグして、**設定の終了点送信トランスポートの種類**定義**アクション**です。  
  
8.  ファクト エクスプ ローラーで、展開、 **ESB です。TansportTypes**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**アダプター プロバイダー**定義**\<空の文字列 >**です。  
  
9. [操作] ウィンドウで、展開、**アダプター プロバイダー**クリックしてドロップダウン リスト、**ファイル**です。  
  
 **発行して、ポリシーを展開するには**  
  
1.  ポリシー エクスプ ローラーで、、 **RouteBasedOnMessageType**ポリシーを右クリック**バージョン 1.0 (未保存)**、クリックして**発行**です。  
  
2.  ポリシー エクスプ ローラーで、、 **RouteBasedOnMessageType**ポリシーを右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。  
  
 **ESB itinerary ドメイン固有言語 (DSL) モデルを作成するには**  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **名前**ボックスに、入力**MessageType**、クリックして**追加**です。  
  
 **旅行計画のプロパティを構成するには**  
  
1.  Visual Studio でのデザイン画面をクリックして**MessageType.itinerary**です。 **MessageType**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  **Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\MessageType**、クリックして**保存**です。  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを itinerary のデータベースへの代わりに、ローカル ファイルの場所に日程をエクスポートできます。 このトピックの後半には、このプロセスを完了します。  
  
 **旅行計画の構造を定義するには**  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveOrders**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**BreRoute**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
        > [!NOTE]
        >  このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。 または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveOrders**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **BreRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ByMessageType**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**Bre 競合回避モジュールの拡張機能**します。  
  
    3.  **ポリシー**ドロップダウン リストをクリックして**RouteBasedOnMessageType v 1.0**です。  
  
4.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveOrders**モデル要素を**BreRoute**モデル要素。  
  
5.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **BreRoute**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendBasedOnType**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
6.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **BreRoute**モデル要素と**SendBasedOnType**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendBasedOnType**、クリックして**送信ハンドラー**です。  
  
7.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **BreRoute**モデル要素を**SendPortFilter**モデル要素。  
  
8.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendBasedOnType**モデル要素。  
  
 **行程テスト クライアントで使用するモデルをエクスポートするには**  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **MessageType**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (MessageType.xml) の作成に注意してください。  
  
 **旅行計画をテストするには**  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**MessageType.xml**、順にクリック**開く**日程を読み込めません。  
  
4.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
8.  Windows エクスプローラで、参照 C:\HowTos\Out\\です。 NorthAmerica%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [方法: 既知のメッセージの種類のポリシーをルール実装のビジネスを使用してコンテンツ ベース ルーティング](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージのルーティング パターン](../esb-toolkit/message-routing-patterns.md)  
  
-   [動的な解決を使用して、ルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)