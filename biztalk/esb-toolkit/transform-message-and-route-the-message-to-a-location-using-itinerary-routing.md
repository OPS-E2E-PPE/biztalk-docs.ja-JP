---
title: '方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング |Microsoft ドキュメント'
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
ms.openlocfilehash: 01a20c7c4a58a12f242cbd412c23e2d2fa9fe24f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010547"
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a>方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング
## <a name="goal"></a>[目標]  
 このセクションで、ESB デザイナー ドメイン固有言語 (DSL) を使用して、BizTalk マップを呼び出すことによってメッセージの変換を実装する旅程を作成する方法とを使用してメッセージをルーティングし、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ファイル アダプター。  
  
 このトピックでは、次の手順を行います。  
  
-   BizTalk マップを実装する変換 itinerary サービスと旅程回覧を作成します。  
  
-   ファイルの場所に変換されたメッセージをルーティングする旅程を構成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB itinerary DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。  
  
4.  **名前**ボックスに、入力**DataModelTransformation**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**DataModelTransformation.itinerary**です。 **DataModelTransformation**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  **Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\DataModelTransformation**、クリックして**を保存**.  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
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
  
    4.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
4.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**MapNAOrderToCNOrder**モデル要素。  
  
5.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **MapNAOrderToCNOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendCNOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
6.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendCNOrder**、クリックして**送信ハンドラー**です。  
  
7.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**です。  
  
    2.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
    3.  クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\\%MessageID%.xml**です。  
  
        > [!NOTE]
        >  各出口がそれに関連付けられている行程サービスが行程サービスのプロパティと、出口のプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。  
  
8.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素を**SendPortFilter**モデル要素。  
  
9. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendCNOrder**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (DataModelTransformation.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**DataModelTransformation.xml**、順にクリック**開く**日程を読み込めません。  
  
4.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
8.  Windows エクスプローラで、C:\HowTos\Out を参照します。いることを確認、 **%MessageID%.xml**ディレクトリに書き込まれたメッセージ。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、これらの関連するトピックを参照してください。  
  
1.  [方法: 別個のスケジュールを利用し、インターチェンジを分割して結果的に生成されたメッセージを複数のファイルの場所に送る](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
3.  [メッセージ変換パターン](../esb-toolkit/message-transformation-patterns.md)