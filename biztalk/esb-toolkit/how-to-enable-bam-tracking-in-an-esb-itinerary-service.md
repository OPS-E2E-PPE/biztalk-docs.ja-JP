---
title: 操作方法:ESB スケジュール サービスで BAM の追跡を有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b685c1d1e670bec50f925c615a3a17222e0bfc92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258481"
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a>操作方法:ESB スケジュール サービスで BAM の追跡を有効にします。
## <a name="goal"></a>[目標]  
 このセクションでは、ビジネス アクティビティ監視 (BAM) が既存のスケジュールの追跡を有効にする方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   旅行プランをビジネスの利用状況モニターを使用してサービスを追跡するために使用されるプロパティを有効にします。  
  
-   旅行プランのテスト用クライアントのサンプル アプリケーションを使用して BAM の追跡をテストします。  
  
-   SQL クエリを使用して BAM の結果を確認します。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="before-you-begin"></a>はじめに  
 この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。  
  
- ESB スケジュール オンランプ ドメイン固有言語 (DSL) モデルを作成します。  
  
- 旅行プランのプロパティを構成します。  
  
- 旅行プランの構造を定義します。  
  
  次の手順では、これらの各方法について説明します。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB スケジュール オンランプ DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。  
  
4.  **名前**ボックスに「 **BamTracking**、 をクリックし、**追加**します。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **BamTracking.itinerary**します。 **BamTracking**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  
  
    2.  **エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\BamTracking**順にクリックします**保存**します。  
  
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
  
    2.  **旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**旅行プラン サービスの拡張機能をメッセージング**。  
  
        > [!NOTE]
        >  このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。 または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション スケジュール サービス拡張**します。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。  
  
    4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Transform**します。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **型の変換**ドロップダウン リストでは、をクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**します。  
  
    4.  **TransportName**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
4.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **MapNAOrderToCNOrder**モデル要素。  
  
5.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **MapNAOrderToCNOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendCNOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
6.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendCNOrder**、順にクリックします**送信ハンドラー**します。  
  
7.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\BAM%MessageID%.xml**  
  
        > [!NOTE]
        >  各オフ-ごとの傾斜増加はそれに関連付けられているスケジュールのサービスにはスケジュール サービスのプロパティとオフ ランプのプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。  
  
8.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素に、 **SendPortFilter**モデル要素。  
  
9. ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendCNOrder**モデル要素。  
  
10. すべてのプロジェクト成果物を保存します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-modify-the-itinerary"></a>旅行プランを変更するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーでダブルクリック**BamTracking.itinerary**します。  
  
3.  をクリックして、 **MapNAOrderToCNOrder**スケジュール サービス要素。  
  
4.  **MapNAOrderToCNOrder**プロパティ ウィンドウで、をクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。  
  
5.  をクリックして、 **SendPortFilter**スケジュール サービス要素。  
  
6.  **SendPortFilter**プロパティ ウィンドウで、をクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **BamTracking**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (BamTracking.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行プランをテストするには  
  
1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**BamTracking.xml**、順にクリックします**オープン**旅行プランを読み込めません。  
  
4.  をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。  
  
5.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  
  
6.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。  
  
7.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  
  
8.  Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。BAM%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
#### <a name="to-verify-message-tracking"></a>メッセージの追跡を確認するには  
  
1. クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]、順にクリックします**SQL Server Management Studio**します。  
  
2. **[新しいクエリ]** をクリックします。  
  
3. クエリ ペインで、次のように入力します。  
  
   ```  
   SELECT *  
   FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
   GO  
   ```  
  
4. **[実行]** をクリックします。  
  
5. 結果ウィンドウで、使用して、**タイムスタンプ**最新のエントリを検索する列。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)