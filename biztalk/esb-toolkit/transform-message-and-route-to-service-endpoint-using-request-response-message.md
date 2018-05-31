---
title: '方法: メッセージを変換して、要求-応答メッセージ交換パターンを使用してサービス エンドポイントへのルート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 071227182eb9b5550b23e23463800cc7dd5a22c4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010355"
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a>方法: メッセージを変換して、要求-応答メッセージ交換パターンを使用してサービス エンドポイントへのルート
## <a name="goal"></a>[目標]  
 このセクションでは、ESB デザイナー ドメイン固有言語 (DSL) を使用して、双方向に着手で使用できる要求-応答旅程を作成する方法を示します。 回覧、メッセージを受信、メッセージを変換、サービスにメッセージを送信し、サービス応答メッセージを元のメッセージの送信者に返すを作成します。  
  
 このトピックでは、次の手順を行います。  
  
-   Microsoft BizTalk Server マップを実装する変換 itinerary サービスと旅程回覧を作成します。  
  
-   サービス エンドポイントに変換されたメッセージをルーティングする旅程を構成します。  
  
-   サービス応答メッセージを元の送信元パーティに返す旅程を構成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB itinerary DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**RequestResponse**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**RequestResponse.itinerary**です。 **RequestResponse**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **は要求の応答**ドロップダウン リストをクリックして**True**です。  
  
    2.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    3.  **Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    4.  **[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\RequestResponse**、クリックして**保存**です。  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary.Response**です。  
  
2.  ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
        > [!NOTE]
        >  このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。 または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。  
  
4.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**MapNAOrderToCNOrder**モデル要素。  
  
5.  ツールボックスからドラッグして、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、 **MapNAOrderToCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteToCNService**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
        > [!NOTE]
        >  このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。 または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。  
  
6.  右クリックし、**リゾルバー**のコレクション、 **RouteToCNService**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheService**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**Wcf-basichttp**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**です。  
  
    5.  クリックして、 **Target Namespace**プロパティ、および入力**http://globalbank.esb.dynamicresolution.com/canadianservices**です。  
  
    6.  クリックして、**アクション**プロパティ、および入力**submitOrder**です。  
  
7.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素を**RouteToCNService**モデル要素。  
  
8.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteToCNService**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**InvokeCNService**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionSolicitResp**です。  
  
9. ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteToCNService**モデル要素と**InvokeCNService**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**InvokeCNService**、クリックして**送信ハンドラー**です。  
  
10. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **RouteToCNService**モデル要素を**SendPortFilter**モデル要素。  
  
11. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**InvokeCNService**モデル要素。  
  
12. デザイン サーフェイスを右クリックし、をクリックして**検証**です。  
  
    > [!NOTE]
    >  旅行計画を検証します。要求元のパーティに応答メッセージを送信するために、入り口に戻す、出口を接続する必要はありません。 双方向での傾斜を使用すると、要求元のパーティに最後のメッセージが自動的に返されます。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **RequestResponse**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照します。 旅程 XML (RequestResponse.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、消去、**を使用して WCF サービス**チェック ボックスをオンします。  
  
3.  **Web サービス オプション** セクションで、選択、**方法の 2 つのサービス**チェック ボックスをクリックして**ロード行程**です。  
  
4.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**RequestResponse.xml**、順にクリック**開く**日程を読み込めません。  
  
5.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
6.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
7.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
8.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
9. **結果**ボックスでは、メッセージのルート ノードに**submitOrderResponse**既定の名前空間としています.**canadianservices**です。  
  
    > [!NOTE]
    >  応答メッセージでは、要求元のパーティに応答を送信する前に、追加の変換が必要とする場合は、ESB フォワーダー コンポーネントを含むパイプラインを使用する必要があります。 この機能の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)です。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: メッセージを変換し、スケジュール ルーティング スリップを利用してファイルの場所に送信する](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)  
  
-   [複数の Web サービス サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)