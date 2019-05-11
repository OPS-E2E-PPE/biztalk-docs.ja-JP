---
title: 操作方法:UDDI バインド キー検索を使用してサービス エンドポイントを解決する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a685641-2beb-4153-a9ba-c766679ce48e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ce78a9637a09754e5cdb065fb25369b2ccac28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258548"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a>操作方法:UDDI バインド キー検索を使用してサービス エンドポイントを解決するには
## <a name="goal"></a>[目標]  
 このセクションでは、ESB デザイナー: ドメイン固有言語 (DSL) を使用して、スケジュールに基づくルーティング スリップ Universal Description, Discovery, を使用するを作成する方法を示しますとバインド キーを使用してサービス エンドポイントを検索する Integration (UDDI) 3 競合回避モジュール検索します。 このシナリオでは、UDDI で公開されているファイルのエンドポイントがサービス エンドポイントになります。  
  
 このトピックでは、次の手順を行います。  
  
-   サービス エンドポイントを解決するのにはのスケジュール ルーティング スリップを作成します。  
  
-   UDDI 3 競合回避モジュールを使用してサービス エンドポイントにメッセージをルーティングするスケジュールを構成します。  
  
-   旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-itinerary-model"></a>スケジュール オンランプ モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに「 **UDDI3BindingKeySearch**、 をクリックし、**追加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **UDDI3BindingKeySearch.itinerary**します。 **UDDI3BindingKeySearch**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  
  
    2.  下、**エクステンダー設定**セクションで、横に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  
  
    3.  **XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\UDDI3BindingKeySearch**で、**ファイル名**ボックスをクリック**保存**.  
  
        > [!NOTE]
        >  この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。 行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。 この操作方法に関するトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
2.  ツールボックスからドラッグして、**スケジュール サービス**デザイン サーフェイスにモデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**BindingKeyRoute**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。  
  
    4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **BindingKeyRoute**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**BindingKeySearch**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**Uddi3 競合回避モジュールの拡張機能**します。  
  
    3.  **リゾルバー モニカー**ドロップダウン リストでは、をクリックして**UDDI3**します。  
  
    4.  をクリックして、**バインド キー**プロパティ、および入力**uddi:esb:orderfileservicev3.1**します。  
  
4.  右クリックし、 **BindingKeySearch**リゾルバー、およびクリック**テスト構成の競合回避モジュール**します。  
  
    > [!NOTE]
    >  出力ウィンドウに表示される出力を確認します。  
  
5.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **BindingKeyRoute**モデル要素。  
  
6.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **BindingKeyRoute**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
7.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **BindingKeyRoute**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。  
  
8.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **BindingKeyRoute**モデル要素に、 **SendPortFilter**モデル要素。  
  
9. ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **UDDI3BindingKeySearch**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (UDDI3BindingKeySearch.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行プランをテストするには  
  
1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。  
  
3.  旅行プラン ファイルを開く ダイアログ ボックスでは、C:\HowTos\Itineraries を参照します。 UDDI3BindingKeySearch.xml を選択し、旅行プランを読み込む をクリックします。  
  
4.  をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。  
  
5.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  
  
6.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。  
  
7.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  
  
8.  Windows エクスプ ローラーでは、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out を参照します。%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: UDDI カテゴリ検索を使用してサービス エンドポイントを解決するには](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)