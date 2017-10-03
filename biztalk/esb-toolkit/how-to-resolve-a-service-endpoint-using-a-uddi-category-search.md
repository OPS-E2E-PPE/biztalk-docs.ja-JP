---
title: "方法: UDDI カテゴリの検索を使用してサービス エンドポイントを解決するには |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ac5d37-5529-4509-a948-415453944e01
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3953baf4a60e2863f986ec54fe9c12663b2b587d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-category-search"></a>方法: UDDI カテゴリの検索を使用してサービス エンドポイントを解決するには
## <a name="goal"></a>[目標]  
 このセクションで、ESB デザイナー ドメイン固有言語 (DSL) を使用して、行程ベース回覧 Universal Description, Discovery, を使用するを作成する方法と、カテゴリを使用してサービス エンドポイントを検索する Integration (UDDI) 3 競合回避モジュールを検索します。 このシナリオでは、UDDI で公開されるファイル エンドポイントがサービス エンドポイントになります。  
  
 このトピックでは、次の手順を行います。  
  
-   サービス エンドポイントを解決するのには itinerary 回覧を作成します。  
  
-   UDDI 3 競合回避モジュールを使用してサービス エンドポイントにメッセージをルーティングする旅程を構成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-itinerary-model"></a>Itinerary モデルを作成するには  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、「 **UDDI3CategorySearch**で、**名前**ボックスをクリックしてして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**UDDI3CategorySearch.itinerary**です。 **UDDI3CategorySearch**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  下にある、 **Extender の設定**セクションで、次に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\UDDI3CategorySearch**で、**ファイル名**ボックスをクリックして**を保存**.  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**CategoryRoute**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**  
  
3.  右クリックし、**リゾルバー**のコレクション、 **CategoryRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**CategorySearch**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**Uddi3 競合回避モジュールの拡張機能**します。  
  
    3.  **リゾルバー モニカー**ドロップダウン リストをクリックして**UDDI3**です。  
  
    4.  をクリックして、**カテゴリの検索**プロパティ、省略記号ボタン (...) をクリックします。  
  
    5.  **名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**です。  
  
    6.  クリックして、**名前**プロパティ、および入力**uddi:esb:biztalkapplication**です。  
  
    7.  クリックして、**値**プロパティ、および入力**GlobalBank.ESB**です。  
  
    8.  **名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**です。  
  
    9. クリックして、**名前**プロパティ、および入力**uddi:esb:portname**です。  
  
    10. クリックして、**値**プロパティ、および入力**OrderFileServicev3**です。  
  
    11. **名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**です。  
  
    12. クリックして、**名前**プロパティ、および入力**uddi:esb:version**です。  
  
    13. クリックして、**値**プロパティ、および入力**1**です。  
  
    14. をクリックして**OK**を閉じる、**名前値のプロパティ エディター**  ダイアログ ボックス。  
  
4.  右クリックし、 **CategorySearch**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。  
  
    > [!NOTE]
    >  出力ウィンドウに表示される出力を確認します。  
  
5.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**CategoryRoute**モデル要素。  
  
6.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **CategoryRoute**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
7.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **CategoryRoute**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。  
  
8.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **CategoryRoute**モデル要素を**SendPortFilter**モデル要素。  
  
9. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **UDDI3CategorySearch**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (UDDI3CategorySearch.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**UDDI3CategorySearch.xml**、順にクリック**開く**日程を読み込めません。  
  
4.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 NAOrderDoc.xml を選択し、クリックして**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
8.  Windows エクスプ ローラーで参照**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out**ことを確認し、 **%MessageID%.xml**にメッセージが書き込まれた、ディレクトリです。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: キーの検索をバインド UDDI を使用してサービス エンドポイントを解決するには](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的な解決を使用して、ルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)