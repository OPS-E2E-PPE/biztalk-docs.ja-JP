---
title: '方法: UDDI 3.0 サービスを発行レジストリ |Microsoft Docs'
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
ms.openlocfilehash: eb5ab38da9c78831b319d8c64e789b442fb6eef5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008019"
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a>方法: UDDI 3.0 サービスを発行レジストリ
## <a name="goal"></a>[目標]  
 このセクションでは、UDDI サービス サイトを使用してから、ESB のメッセージをルーティングするために、旅行プラン内で解決できる Web サービス エンドポイントを公開する方法を示します。 現在、レジストリに発行された既存の PurchaseOrderSubmitOrderService サービスが複製されます。  

 このトピックでは、次の手順を行います。  

-   Universal Description, Discovery, and Integration (UDDI) 3 にサービスを発行する UDDI 発行者のツールを使用してレジストリ。  

-   UDDI3 リゾルバーを使用してサービス エンドポイントを解決する、スケジュール ルーティング スリップを使用してサービスの公開をテストします。  

## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)と (でインストールできるように、%esb インストール Folder%\Bin\ UDDI 発行者のツールの実行Microsoft.Practices.ESB.UDDIPublisher.exe)。  

## <a name="steps"></a>手順  

#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a>UDDI レジストリで、NewPOService を作成するには  

1.  Internet Explorer で、UDDI サービス サイトを参照 (この URL は、既定では、http://localhost/uddi)します。  

2.  **Uddi Services** ] ページで [**発行**します。  

3.  発行 ウィンドウで右クリック**Microsoft.Practices.ESB**、 をクリックし、**サービスの追加**します。  

4.  次のページで選択**を使用するキーを指定**、 をクリックし、**続行**。  

5.  次のページでは、をクリックして、 **esb**パーティション キーします。 **キー サフィックス**ボックスに「 **newposervice**、 をクリックし、**続行**します。  

6.  次のページの横に (**新しいサービス名**)、 をクリックして**編集**します。 サービスの名前を付けます**NewPOService**、順にクリックします**Update**します。  

7.  をクリックして**説明の追加**、サービスの説明を入力 (たとえば、**サンプル サービス**)、順にクリックします**更新**します。  

#### <a name="to-add-a-binding-for-the-newposervice"></a>NewPOService のバインドを追加するには  

1.  をクリックして、**バインド**タブをクリックし、をクリックし、**バインドの追加**します。  

2.  選択**を使用するキーを指定**、 をクリックし、**続行**します。  

3.  次のページでは、をクリックして、 **esb**パーティション キーします。 **キー サフィックス**ボックスに「 **newposervicebinding**、 をクリックし、**続行**します。  

4.  [**アクセス ポイント**、] をクリックして**編集**、次の手順と。  

    1.  **アクセス ポイント**ボックスに「  **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**します。  

    2.  **使用の種類**ドロップダウン リストでは、をクリックして**エンドポイント**、順にクリックします**更新**します。  

#### <a name="to-configure-the-binding-instance-information"></a>バインディングのインスタンス情報を構成するには  

1. をクリックして、**インスタンス情報**タブをクリックし、をクリックし、**インスタンス情報の追加**します。  

2. **検索含む tModel 名を**ボックスに「 **% esb**順にクリックします**検索**します。  

3. 見つけてクリックして、 **tModel**の**transporttype**します。  

   > [!NOTE]
   >  この手順の残りの手順を完了するには、1 ページ目と 2 ページ間で変更する必要する可能性があります。  

4. **説明**セクションで、**説明の追加**します。  

5. **説明**ボックスに「 **ESB 行程使用するためトランスポートの種類**、 をクリックし、 **Update**。  

6. をクリックして、**インスタンスの詳細**タブをクリックし、をクリックし、**編集**します。  

7. **インスタンス パラメーター**ボックスに「 **Wcf-basichttp**、 をクリックし、**更新**。  

8. **説明**セクションで、**説明の追加**します。  

9. **説明**ボックスに「 **HTTP トランスポートの基本的な WCF** をクリックし、**更新**。  

10. [発行] ウィンドウで [ **NewPOService**、] をクリックして **http://localhost/esb.canadianservices/submitposervice.asmx**します。  

11. **インスタンス情報**] タブで [**インスタンス情報の追加**します。  

12. 前述の手順を使用して、次の表に示した値に従って、次のインスタンス情報を追加します。  


    |                           tModel                           |       説明        |                          パラメーター                           |         パラメーターの説明          |
    |------------------------------------------------------------|--------------------------|--------------------------------------------------------------|----------------------------------------|
    | microsoft-com:esb:runtimeresolution:messageexchangepattern | メッセージ交換パターン |                           双方向                            |           双方向の操作            |
    |      microsoft-com:esb:runtimeresolution:cachetimeout      |      キャッシュのタイムアウト       |                              -1                              |           現在無効になっています           |
    |     microsoft-com:esb:runtimeresolution:jaxrpcresponse     |      JaxRpcResponse      |                            false                             |                                        |
    |         microsoft-com:esb:runtimeresolution:action         |      サービス アクション      |                         submitOrder                          | 呼び出すサービス メソッドを指定します |
    |    microsoft-com:esb:runtimeresolution:targetnamespace     |    Service Namespace     | http://globalbank.esb.dynamicresolution.com/canadianservices |            ターゲットの名前空間            |

#### <a name="to-configure-the-binding-categorization"></a>バインドの分類を構成するには  

1.  [発行] ウィンドウで [ **NewPOService**、] をクリックして **http://localhost/esb.canadianservices/submitposervice.asmx**します。  

2.  **カテゴリ**] タブで [**カスタム カテゴリの追加**します。  

3.  **検索**ボックスに「 **% esb**  をクリックし、**検索**します。  

4.  見つけてクリックして、 **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel します。  

5.  **キー名**ボックスに「 **BizTalk アプリケーション**します。  

6.  **キー値**ボックスに「 **Microsoft.Practices.ESB**、 をクリックし、**カテゴリの追加**します。  

7.  前述の手順を使用して、次の表に示した値に従って、次のカスタム カテゴリを追加します。  

    |tModel|キー名|キーの値|  
    |------------|--------------|---------------|  
    |microsoft-com:esb:runtimeresolution:portname|ポート名|NewPOService|  
    |microsoft-com:esb:runtimeresolution:transporttype|トランスポートの種類|WCF-BasicHttp|  

#### <a name="to-locate-the-service-in-the-uddi-registry"></a>UDDI レジストリ内でサービスを検索するには  

1.  Internet Explorer で、上、 **uddi サービス**] ページで [**検索**します。  

2.  をクリックして、**サービス**タブ。  

3.  **サービス名**ボックスに「 **% PO** をクリックし、**検索**します。  

4.  **検索**ウィンドウで、**結果**] タブで [ **NewPOService**。  

    > [!NOTE]
    >  これは、サービスは、レジストリに正常に発行されたことを確認します。  

#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a>UDDI サービスの公開をテストするスケジュールのモデルを作成するには  

1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  

2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  

3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに「 **NewBindingKeySearch**、 をクリックし、**追加**。  

#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  

1.  Visual Studio でのデザイン画面をクリックします。 **NewBindingKeySearch.itinerary**します。 **NewBindingKeySearch**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  **は Request Response**ドロップダウン リストでは、をクリックして**True**します。  

    2.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  

    3.  **エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  

    4.  **XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\NewBindingKeySearch**で、**ファイル名**ボックスをクリック**保存**.  

        > [!NOTE]
        >  この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。 行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。 この操作方法に関するトピックの後半には、このプロセスを完了します。  

#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  

1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  

    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。  

    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  

    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary.Response**します。  

2.  ツールボックスからドラッグして、**スケジュール サービス**デザイン サーフェイスにモデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  をクリックして、**名前**プロパティ、および入力**TransformNAOrder**します。  

    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。  

    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。  

    4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Transform**します。  

3.  右クリックし、**リゾルバー**のコレクション、 **TransformNAOrder**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  をクリックして、**名前**プロパティ、および入力**NAOrder_to_CNOrder**します。  

    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  

    3.  **型の変換**ドロップダウン リストでは、をクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**します。  

4.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **TransformNAOrder**モデル要素。  

5.  ツールボックスからドラッグして、**スケジュール サービス**デザイン サーフェイスにモデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  をクリックして、**名前**プロパティ、および入力**BindingKeyRoute**します。  

    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。  

    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。  

    4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。  

6.  右クリックし、**リゾルバー**のコレクション、 **BindingKeyRoute**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  をクリックして、**名前**プロパティ、および入力**BindingKeySearch**します。  

    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**Uddi3 競合回避モジュールの拡張機能**します。  

    3.  **リゾルバー モニカー**ドロップダウン リストでは、をクリックして**UDDI3**します。  

    4.  をクリックして、**バインド キー**プロパティ、および入力**uddi:esb:newposervicebinding**します。 キーの値を調べるには、http://localhost/ESB.CanadianServices/SubmitPOService.asmxで、UDDI サービスを詳細 をクリックします。  

7.  右クリックし、 **BindingKeySearch**リゾルバー、およびクリック**テスト構成の競合回避モジュール**します。  

    > [!NOTE]
    >  出力ウィンドウに表示される出力を確認します。  

8.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **TransformNAOrder**モデル要素に、 **BindingKeyRoute**モデル要素。  

9. ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **BindingKeyRoute**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  をクリックして、**名前**プロパティ、および入力**SendCNOrder**します。  

    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  

    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  

    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionSolicitResp**します。  

10. ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **BindingKeyRoute**モデル要素と**SendCNOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  

    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  

    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  

    3.  **傾斜オフ**ドロップダウン リストで、展開**SendCNOrder**、順にクリックします**送信ハンドラー**します。  

11. ツールボックス、**コネクタ**します。 接続をドラッグして、 **BindingKeyRoute**モデル要素に、 **SendPortFilter**モデル要素。  

12. ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendNAOrder**モデル要素。  

#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  

1.  Visual Studio でのデザイン画面を右クリックし、 **NewBindingKeySearch**旅行プランをクリックして**モデルのエクスポート**します。  

    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  

2.  すべてのプロジェクト成果物を保存します。  

3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (NewBindingKeySearch.xml) の作成に注意してください。  

#### <a name="to-test-the-itinerary"></a>旅行プランをテストするには  

1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  

2.  旅行プランのテスト クライアントで、 **Web サービス オプション**グループ、クリア、 **WCF サービスを使用して**ボックスを選び、**双方向サービス**チェック ボックスをオンします。  

3.  をクリックして、**ロード行程**ボタンをクリックします。  

4.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**NewBindingKeySearch.xml**、順にクリックします**オープン**旅行プランを読み込めません。  

5.  をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。  

6.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  

7.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。  

8.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  

9. 適切な応答メッセージが表示されることを確認、**結果**のテキスト ボックス、 **Itineray テスト クライアント**します。  

## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  

-   [方法: UDDI バインド キー検索を利用し、サービス エンドポイントを解決する](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  

-   [方法: UDDI カテゴリ検索を利用し、サービス エンドポイントを解決する](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  

-   [開発アクティビティ](../esb-toolkit/development-activities.md)