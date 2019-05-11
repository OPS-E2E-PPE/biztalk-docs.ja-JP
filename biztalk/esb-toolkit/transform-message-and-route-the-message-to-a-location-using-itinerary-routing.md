---
title: 操作方法:メッセージを変換し、スケジュール ルーティング スリップを使用してファイルの場所に、結果のメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c27749ba-c228-4cd4-827e-e8009a0c999d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e671e48ea2da80783b714a8be6c503b80b95f27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399663"
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a>操作方法:メッセージを変換し、スケジュール ルーティング スリップを使用してファイルの場所に、結果のメッセージをルーティング
## <a name="goal"></a>[目標]  
 このセクションで、ESB デザイナー ドメイン固有言語 (DSL) を使用して、BizTalk マップを呼び出すことによってメッセージの変換を実装するスケジュールを作成する方法を示すし、を使用してメッセージをルーティングし、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ファイル アダプター。  
  
 このトピックでは、次の手順を行います。  
  
-   BizTalk マップを実装する変換のスケジュール サービスで、スケジュール ルーティング スリップを作成します。  
  
-   ファイルの場所に変換されたメッセージをルーティングするスケジュールを構成します。  
  
-   旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB スケジュール オンランプ DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。  
  
4.  **名前**ボックスに「 **DataModelTransformation**、 をクリックし、**追加**します。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **DataModelTransformation.itinerary**します。 **DataModelTransformation**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  
  
    2.  **エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  
  
    3.  **XML ファイルの** ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\DataModelTransformation**、 をクリックし、 **を保存**.  
  
        > [!NOTE]
        >  この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。 行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。 この操作方法に関するトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
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
  
    4.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
4.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **MapNAOrderToCNOrder**モデル要素。  
  
5.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **MapNAOrderToCNOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendCNOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
6.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendCNOrder**、順にクリックします**送信ハンドラー**します。  
  
7.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**します。  
  
    2.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    3.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\\%MessageID%.xml**します。  
  
        > [!NOTE]
        >  それに関連付けられているスケジュール サービスをそれぞれオフ-ごとの傾斜増加が必要があります。旅行プラン サービスのプロパティとオフ ランプのプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。  
  
8.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素に、 **SendPortFilter**モデル要素。  
  
9. ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendCNOrder**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (DataModelTransformation.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行プランをテストするには  
  
1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**DataModelTransformation.xml**、順にクリックします**オープン**旅行プランを読み込めません。  
  
4.  をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。  
  
5.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  
  
6.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。  
  
7.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  
  
8.  Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。いることを確認、 **%MessageID%.xml**メッセージが、ディレクトリに書き込まれました。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、これらの関連トピックを参照してください。  
  
1.  [方法: インターチェンジを分割し、個別のスケジュールを使用して複数のファイルの場所に作成されるメッセージをルーティング](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
3.  [メッセージ変換パターン](../esb-toolkit/message-transformation-patterns.md)