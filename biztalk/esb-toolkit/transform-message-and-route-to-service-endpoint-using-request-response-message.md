---
title: 操作方法:メッセージを変換して、要求-応答のメッセージ交換パターンを使用してサービス エンドポイントへのルート |Microsoft Docs
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
ms.openlocfilehash: e7bea07435e4d9bf10df8e47fda319a0fd106ed9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399647"
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a>操作方法:メッセージと要求-応答のメッセージ交換パターンを使用してサービス エンドポイントへのルートを変換します。
## <a name="goal"></a>[目標]  
 このセクションでは、ESB デザイナー: ドメイン固有言語 (DSL) を使用して、双方向の入り口で使用できる要求-応答の旅行プランを作成する方法を示します。 メッセージを受信、メッセージを変換、サービスにメッセージを送信し、サービス応答メッセージを元のメッセージの送信者に返す回覧先を作成します。  
  
 このトピックでは、次の手順を行います。  
  
-   Microsoft BizTalk Server マップを実装する変換のスケジュール サービスで、スケジュール ルーティング スリップを作成します。  
  
-   サービス エンドポイントに変換されたメッセージをルーティングするスケジュールを構成します。  
  
-   サービスの応答メッセージを元の送信元パーティに返す旅行プランを構成します。  
  
-   旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB スケジュール オンランプ DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに「 **RequestResponse**、 をクリックし、**追加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **RequestResponse.itinerary**します。 **RequestResponse**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **は Request Response**ドロップダウン リストでは、をクリックして**True**します。  
  
    2.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  
  
    3.  **エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  
  
    4.  **[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\RequestResponse**、順にクリックします**保存**します。  
  
        > [!NOTE]
        >  この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。 行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。 この操作方法に関するトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary.Response**します。  
  
2.  ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。  
  
        > [!NOTE]
        >  このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。 または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。  
  
    4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Transform**します。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **型の変換**ドロップダウン リストでは、をクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**します。  
  
4.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **MapNAOrderToCNOrder**モデル要素。  
  
5.  ツールボックスからドラッグして、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、 **MapNAOrderToCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**RouteToCNService**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。  
  
        > [!NOTE]
        >  このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。 または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。  
  
    4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。  
  
6.  右クリックし、**リゾルバー**のコレクション、 **RouteToCNService**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**StaticallySpecifyTheService**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**Wcf-basichttp**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力 **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**します。  
  
    5.  をクリックして、 **Target Namespace**プロパティ、および入力 **http://globalbank.esb.dynamicresolution.com/canadianservices**します。  
  
    6.  をクリックして、**アクション**プロパティ、および入力**submitOrder**します。  
  
7.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素に、 **RouteToCNService**モデル要素。  
  
8.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteToCNService**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**InvokeCNService**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionSolicitResp**します。  
  
9. ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteToCNService**モデル要素と**InvokeCNService**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**InvokeCNService**、順にクリックします**送信ハンドラー**します。  
  
10. ツールボックス、**コネクタ**します。 接続をドラッグして、 **RouteToCNService**モデル要素に、 **SendPortFilter**モデル要素。  
  
11. ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **InvokeCNService**モデル要素。  
  
12. デザイン サーフェイスを右クリックし、**検証**です。  
  
    > [!NOTE]
    >  旅行プランを検証します。要求元のパーティに応答メッセージを送信するには 傾斜にオフ傾斜を接続する必要はありません。 双方向での傾斜を使用すると、要求元のパーティに最後のメッセージが自動的に返されます。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **RequestResponse**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照します。 XML (RequestResponse.xml)、スケジュールの作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行プランをテストするには  
  
1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  
  
2.  旅行プランのテスト クライアントでクリア、 **WCF サービスを使用して**チェック ボックスをオンします。  
  
3.  **Web サービス オプション**セクションで、**方法の 2 つのサービス**チェック ボックスをオンにして**ロード行程**します。  
  
4.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**RequestResponse.xml**、順にクリックします**オープン**旅行プランを読み込めません。  
  
5.  をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。  
  
6.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  
  
7.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。  
  
8.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  
  
9. **結果**ボックスに、メッセージのルート ノードは**submitOrderResponse**既定の名前空間としています.**canadianservices**します。  
  
    > [!NOTE]
    >  応答メッセージでは、応答が要求元のパーティに送信される前に、追加の変換が必要とする場合は、ESB フォワーダー コンポーネントを含むパイプラインを使用する必要があります。 この機能の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: メッセージを変換し、スケジュール ルーティング スリップを使用してファイルの場所に、結果のメッセージをルーティング](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)  
  
-   [複数の Web サービス サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)