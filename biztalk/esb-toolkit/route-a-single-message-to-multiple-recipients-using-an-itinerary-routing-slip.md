---
title: 操作方法:1 つのメッセージをスケジュール ルーティング スリップを使用して複数の受信者にルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c30493-4fe1-4fd5-8bc7-af091535b091
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9eb1118850c46215ebd57f25956ce3581eee844
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395893"
---
# <a name="how-to-route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip"></a>操作方法:1 つのメッセージをスケジュール ルーティング スリップを使用して複数の受信者にルーティングします。
## <a name="goal"></a>[目標]  
 このセクションでは、デザイナー: ドメイン固有言語 (DSL) を使用して静的な競合回避モジュールと、BizTalk Server ファイル アダプターを使用して 3 つの異なる受信者にメッセージをルーティングする旅行プランを作成する方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   複数の受信者にメッセージをルーティングの 3 つの静的リゾルバーを旅行プランを作成します。  
  
-   旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB スケジュール オンランプ DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、 をクリックし、**新しいスケジュール**します。  
  
3.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。  
  
4.  **名前**ボックスに「 **RecipientList**、 をクリックし、**追加**します。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio で、RecipientList.itinerary のデザイン画面をクリックします。 RecipientList [プロパティ] ウィンドウでは、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  
  
    2.  **エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\RecipientList**、順にクリックします**保存**します。  
  
        > [!NOTE]
        >  この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。 行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。 この操作方法に関するトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**ランプで Extender**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
2.  ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**RouteToThreeRecipients**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。  
  
        > [!NOTE]
        >  このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。 または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNaOrderDoc**、 をクリックし、**受信ハンドラー**。  
  
    4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**FirstResolver**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\First%MessageID%.xml**します。  
  
        > [!NOTE]
        >  このスケジュール サービスの 3 つの競合回避モジュールの最初の数値が追加されました。 追加の受信者にメッセージをルーティングする 2 つ以上のリゾルバーを追加します。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SecondResolver**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Second%MessageID%.xml**します。  
  
5.  右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ThirdResolver**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Third%MessageID%.xml**します。  
  
6.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteToThreeRecipients**モデル要素。  
  
7.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteToThreeRecipients**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendThreeMessages**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
8.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteToThreeRecipients**モデル要素と**SendThreeMessages**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendThreeMessages**、順にクリックします**送信ハンドラー**します。  
  
9. ツールボックス、**コネクタ**します。 接続をドラッグして、 **RouteToThreeRecipients**モデル要素に、 **SendPortFilter**モデル要素。  
  
10. ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendThreeMessages**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **RecipientList**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照して、旅行プラン XML (RecipientList.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行プランをテストするには  
  
1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**RecipientList.xml**、順にクリックします**オープン**旅行プランを読み込めません。  
  
4.  をクリックして**OK**をオフに、"スケジュールが正常に読み込まれました: メッセージ。  
  
5.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  
  
6.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\Patterns を参照します。 NAOrderDoc.xml を選択し、クリックして**オープン**テスト メッセージを読み込めません。  
  
7.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  
  
8.  Windows エクスプ ローラーで参照 C:\HowTos\Out\\します。 次のメッセージが、ディレクトリに書き込まれたことを確認します。  
  
    -   First%MessageID%.xml  
  
    -   Second%MessageID%.xml  
  
    -   Third%MessageID%.xml  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)