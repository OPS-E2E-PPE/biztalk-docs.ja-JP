---
title: '方法: キーの検索をバインド UDDI を使用してサービス エンドポイントを解決するには |Microsoft ドキュメント'
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
ms.openlocfilehash: d286f3dd48daa7cc0ddd16f4abda601cf9e8a5f7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010563"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a>方法: キーの検索をバインド UDDI を使用してサービス エンドポイントを解決するには
## <a name="goal"></a>[目標]  
 このセクションでは、ESB デザイナー ドメイン固有言語 (DSL) を使用して、行程ベース回覧 Universal Description, Discovery, を使用するを作成する方法を示しますとバインド キーを使用してサービス エンドポイントを検索する Integration (UDDI) 3 競合回避モジュール検索します。 このシナリオでは、UDDI で公開されるファイル エンドポイントがサービス エンドポイントになります。  
  
 このトピックでは、次の手順を行います。  
  
-   サービス エンドポイントを解決するのには itinerary 回覧を作成します。  
  
-   UDDI 3 競合回避モジュールを使用してサービス エンドポイントにメッセージをルーティングする旅程を構成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-itinerary-model"></a>Itinerary モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**UDDI3BindingKeySearch**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**UDDI3BindingKeySearch.itinerary**です。 **UDDI3BindingKeySearch**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  下にある、 **Extender の設定**セクションで、次に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\UDDI3BindingKeySearch**で、**ファイル名**ボックスをクリックして**を保存**.  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**BindingKeyRoute**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **BindingKeyRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**BindingKeySearch**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**Uddi3 競合回避モジュールの拡張機能**します。  
  
    3.  **リゾルバー モニカー**ドロップダウン リストをクリックして**UDDI3**です。  
  
    4.  クリックして、**バインド キー**プロパティ、および入力**uddi:esb:orderfileservicev3.1**です。  
  
4.  右クリックし、 **BindingKeySearch**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。  
  
    > [!NOTE]
    >  出力ウィンドウに表示される出力を確認します。  
  
5.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**BindingKeyRoute**モデル要素。  
  
6.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **BindingKeyRoute**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
7.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **BindingKeyRoute**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。  
  
8.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **BindingKeyRoute**モデル要素を**SendPortFilter**モデル要素。  
  
9. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **UDDI3BindingKeySearch**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (UDDI3BindingKeySearch.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  行程ファイルを開く ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 UDDI3BindingKeySearch.xml を選択し、日程を読み込む をクリックします。  
  
4.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
8.  Windows エクスプローラで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out を参照します。%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: UDDI カテゴリ検索を利用し、サービス エンドポイントを解決する](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)