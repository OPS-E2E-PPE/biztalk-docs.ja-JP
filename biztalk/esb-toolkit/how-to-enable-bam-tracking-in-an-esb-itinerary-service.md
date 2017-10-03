---
title: "方法: ESB Itinerary サービスで BAM の追跡を有効にする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6245ec69e1c8224ccbe9a39c3c2be9eea9237ee8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a>方法: ESB Itinerary サービスで BAM の追跡を有効にします。
## <a name="goal"></a>[目標]  
 このセクションでは、ビジネス アクティビティ監視 (BAM) が既存旅程を追跡を有効にする方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   ビジネスの利用状況モニターを使用してサービスを旅程を追跡するために使用されるプロパティを有効にします。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して BAM の追跡をテストします。  
  
-   SQL クエリを使用して、BAM の結果を確認します。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="before-you-begin"></a>はじめに  
 このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。  
  
-   ESB itinerary ドメイン固有言語 (DSL) モデルを作成します。  
  
-   旅行計画のプロパティを構成します。  
  
-   旅行計画の構造を定義します。  
  
 次の手順では、これらの各を行う方法について説明します。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB itinerary DSL モデルを作成するには  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。  
  
4.  **名前**ボックスに、入力**BamTracking**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**BamTracking.itinerary**です。 **BamTracking**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  **Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    3.  **XML ファイルの** ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\BamTracking**  をクリックし、**保存**です。  
  
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
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**行程サービス拡張のメッセージング**です。  
  
        > [!NOTE]
        >  このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。 または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション行程サービス拡張**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。  
  
    4.  **TransportName**ドロップダウン リストをクリックして**ファイル**です。  
  
4.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**MapNAOrderToCNOrder**モデル要素。  
  
5.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **MapNAOrderToCNOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendCNOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
6.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendCNOrder**、クリックして**送信ハンドラー**です。  
  
7.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\BAM%MessageID%.xml**  
  
        > [!NOTE]
        >  各出口がそれに関連付けられている itinerary サービスされています。itinerary サービスのプロパティと、出口のプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。  
  
8.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素を**SendPortFilter**モデル要素。  
  
9. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendCNOrder**モデル要素。  
  
10. すべてのプロジェクトの成果物を保存します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-modify-the-itinerary"></a>旅行計画を変更するには  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで、 **BamTracking.itinerary**です。  
  
3.  クリックして、 **MapNAOrderToCNOrder** itinerary サービス要素。  
  
4.  **MapNAOrderToCNOrder**プロパティ ウィンドウでをクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。  
  
5.  クリックして、 **SendPortFilter** itinerary サービス要素。  
  
6.  **SendPortFilter**プロパティ ウィンドウでをクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **BamTracking**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (BamTracking.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**BamTracking.xml**、順にクリック**開く**日程を読み込めません。  
  
4.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
8.  Windows エクスプローラで、C:\HowTos\Out を参照します。BAM%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
#### <a name="to-verify-message-tracking"></a>メッセージの追跡を確認するには  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]、順にクリック**SQL Server Management Studio**です。  
  
2.  **[新しいクエリ]**をクリックします。  
  
3.  クエリ ウィンドウで、次のように入力します。  
  
    ```  
    SELECT *  
    FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
    GO  
    ```  
  
4.  **[実行]**をクリックします。  
  
5.  結果ウィンドウで、使用、**タイムスタンプ**最新のエントリを検索する列。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージのルーティング パターン](../esb-toolkit/message-routing-patterns.md)  
  
-   [動的な解決を使用して、ルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)