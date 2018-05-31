---
title: '方法: 3.0 uddi サービスを発行レジストリ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c3bd0ed-e5f1-43eb-98d1-e3247a565ba2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da3d2dc400c031ab5febda1568cb18ce5180366b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009915"
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a>方法: 3.0 uddi サービスを発行レジストリ
## <a name="goal"></a>[目標]  
 このセクションでは、UDDI サービス サイトを使用して、ESB メッセージをルーティングするために、行程内から解決できる Web サービスのエンドポイントを公開する方法を示します。 既存の PurchaseOrderSubmitOrderService サービス レジストリに現在発行が複製されます。  
  
 このトピックでは、次の手順を行います。  
  
-   Universal Description, Discovery, and Integration (UDDI) 3 に、サービスを発行レジストリ UDDI 発行者のツールを使用します。  
  
-   UDDI3 競合回避モジュールを使用してサービス エンドポイントを解決する itinerary 回覧を使用してサービスの公開をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)と (でインストールできるように、%esb インストール Folder%\Bin\ UDDI 発行者のツールの実行Microsoft.Practices.ESB.UDDIPublisher.exe)。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a>UDDI レジストリで、NewPOService を作成するには  
  
1.  Internet Explorer で、UDDI サービス サイトを参照 (既定では、この URL は http://localhost/uddi)。  
  
2.  **Uddi Services** ] ページで [**発行**です。  
  
3.  発行のウィンドウで  **Microsoft.Practices.ESB**、順にクリック**サービスの追加**です。  
  
4.  次のページで次のように選択します。**を使用するキーを指定**、クリックして**続行**です。  
  
5.  次のページでは、をクリックして、 **esb**パーティション キーです。 **キー サフィックス**ボックスに、入力**newposervice**、クリックして**続行**です。  
  
6.  次のページの横に (**新しいサービス名前**)、 をクリックして**編集**です。 サービスの名前を付けます**NewPOService**、順にクリック**更新**です。  
  
7.  をクリックして**説明の追加**、サービスの説明を入力 (たとえば、**サンプル サービス**)、順にクリック**更新**です。  
  
#### <a name="to-add-a-binding-for-the-newposervice"></a>NewPOService のバインディングを追加するには  
  
1.  クリックして、**バインド** タブをクリックして**バインドの追加**です。  
  
2.  選択**を使用するキーを指定**、クリックして**続行**です。  
  
3.  次のページでは、をクリックして、 **esb**パーティション キーです。 **キー サフィックス**ボックスに、入力**newposervicebinding**、クリックして**続行**です。  
  
4.  [**アクセス ポイント**、] をクリックして**編集**、次を完了します。  
  
    1.  **アクセス ポイント**ボックスに、入力**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**です。  
  
    2.  **の型を使用**ドロップダウン リストをクリックして**エンドポイント**、順にクリック**更新**です。  
  
#### <a name="to-configure-the-binding-instance-information"></a>バインディングのインスタンス情報を構成するには  
  
1.  クリックして、**インスタンス情報** タブをクリックして**インスタンス情報の追加**です。  
  
2.  **を含む tModel 名の検索**ボックスに、入力 **%esb**  をクリックし、**検索**です。  
  
3.  見つけてクリックして、 **tModel**の**transporttype**です。  
  
    > [!NOTE]
    >  この手順の残りの手順を完了するには、は、1 ページ目と 2 ページ目の間で変更する必要可能性があります。  
  
4.  **説明**セクションで、**説明の追加**です。  
  
5.  **説明**ボックスに、入力**ESB 行程使用するためのトランスポートの種類**、クリックして**更新**です。  
  
6.  クリックして、**インスタンスの詳細** タブをクリックして**編集**です。  
  
7.  **インスタンス パラメーター**ボックスに、入力**Wcf-basichttp**、クリックして**更新**です。  
  
8.  **説明**セクションで、**説明の追加**です。  
  
9. **説明**ボックスに、入力**HTTP トランスポートの基本的な WCF**、クリックして**更新**です。  
  
10. [発行] ウィンドウで [ **NewPOService**、] をクリックして**http://localhost/esb.canadianservices/submitposervice.asmx**です。  
  
11. **インスタンス情報** タブで、をクリックして**インスタンス情報の追加**です。  
  
12. 既に説明した手順を使用して、次の表に示した値に従って、次のインスタンス情報を追加します。  
  
    |tModel|Description|パラメーター|パラメーターの説明|  
    |------------|-----------------|---------------|---------------------------|  
    |microsoft-com:esb:runtimeresolution:messageexchangepattern|メッセージ交換パターン|双方向|双方向の操作|  
    |microsoft-com:esb:runtimeresolution:cachetimeout|キャッシュのタイムアウト|-1|現在無効になっています|  
    |microsoft-com:esb:runtimeresolution:jaxrpcresponse|JaxRpcResponse|オプション||  
    |microsoft-com:esb:runtimeresolution:action|サービス操作|submitOrder|呼び出すサービス メソッドを指定します|  
    |microsoft-com:esb:runtimeresolution:targetnamespace|Service Namespace|http://globalbank.esb.dynamicresolution.com/canadianservices|ターゲットの名前空間|  
  
#### <a name="to-configure-the-binding-categorization"></a>バインディングの分類を構成するには  
  
1.  [発行] ウィンドウで [ **NewPOService**、] をクリックして**http://localhost/esb.canadianservices/submitposervice.asmx**です。  
  
2.  **カテゴリ** タブで、をクリックして**カスタム カテゴリの追加**です。  
  
3.  **検索**ボックスに、入力 **%esb**  をクリックし、**検索**です。  
  
4.  見つけてクリックして、 **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel です。  
  
5.  **キー名**ボックスに、入力**BizTalk アプリケーション**です。  
  
6.  **キー値**ボックスに、入力**Microsoft.Practices.ESB**、クリックして**カテゴリの追加**です。  
  
7.  既に説明した手順を使用して、次の表に示した値に従って、次のカスタム カテゴリを追加します。  
  
    |tModel|キー名|キーの値|  
    |------------|--------------|---------------|  
    |microsoft-com:esb:runtimeresolution:portname|ポート名|NewPOService|  
    |microsoft-com:esb:runtimeresolution:transporttype|トランスポートの種類|WCF-BasicHttp|  
  
#### <a name="to-locate-the-service-in-the-uddi-registry"></a>UDDI レジストリ内でサービスを検索するには  
  
1.  Internet Explorer で、上、 **uddi サービス**] ページで [**検索**です。  
  
2.  クリックして、 **Services**タブです。  
  
3.  **サービス名**ボックスに、入力 **%po**、クリックして**検索**です。  
  
4.  **検索** ウィンドウで、**結果** タブで、をクリックして**NewPOService**です。  
  
    > [!NOTE]
    >  これは、サービスがレジストリに正常に発行されたを確認します。  
  
#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a>UDDI サービスの公開をテストする itinerary モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**NewBindingKeySearch**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**NewBindingKeySearch.itinerary**です。 **NewBindingKeySearch**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **は要求の応答**ドロップダウン リストをクリックして**True**です。  
  
    2.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    3.  **Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    4.  **[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\NewBindingKeySearch**で、**ファイル名**ボックスをクリックして**を保存**.  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary.Response**です。  
  
2.  ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**TransformNAOrder**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **TransformNAOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**NAOrder_to_CNOrder**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。  
  
4.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**TransformNAOrder**モデル要素。  
  
5.  ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**BindingKeyRoute**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。  
  
6.  右クリックし、**リゾルバー**のコレクション、 **BindingKeyRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**BindingKeySearch**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**Uddi3 競合回避モジュールの拡張機能**します。  
  
    3.  **リゾルバー モニカー**ドロップダウン リストをクリックして**UDDI3**です。  
  
    4.  クリックして、**バインド キー**プロパティ、および入力**uddi:esb:newposervicebinding**です。 キーの値を見つけて http://localhost/ESB.CanadianServices/SubmitPOService.asmx、UDDI サービスをクリックして [詳細設定] をクリックします。  
  
7.  右クリックし、 **BindingKeySearch**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。  
  
    > [!NOTE]
    >  出力ウィンドウに表示される出力を確認します。  
  
8.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **TransformNAOrder**モデル要素を**BindingKeyRoute**モデル要素。  
  
9. ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **BindingKeyRoute**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendCNOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionSolicitResp**です。  
  
10. ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **BindingKeyRoute**モデル要素と**SendCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendCNOrder**、クリックして**送信ハンドラー**です。  
  
11. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **BindingKeyRoute**モデル要素を**SendPortFilter**モデル要素。  
  
12. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **NewBindingKeySearch**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (NewBindingKeySearch.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントでの**Web サービスのオプション**グループ、クリア、**を使用して WCF サービス**ボックスし、、**双方向サービス**チェック ボックスをオンします。  
  
3.  クリックして、**ロード行程**ボタンをクリックします。  
  
4.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**NewBindingKeySearch.xml**、順にクリック**開く**日程を読み込めません。  
  
5.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
6.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
7.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
8.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
9. 正しい応答メッセージが表示されることを確認してください、**結果**のテキスト ボックス、 **Itineray テスト用クライアント**です。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: UDDI バインド キー検索を利用し、サービス エンドポイントを解決する](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [方法: UDDI カテゴリ検索を利用し、サービス エンドポイントを解決する](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)