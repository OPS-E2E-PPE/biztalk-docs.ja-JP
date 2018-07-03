---
title: '方法: 既知のメッセージの種類のルール ポリシーの実装のビジネスを使用してコンテンツ ベース ルーティング |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b47fd54aaf6dc93ed26ba7efec3b14bf31401e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004915"
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a>方法: 既知のメッセージの種類のルール ポリシーの実装のビジネスを使用してコンテンツ ベース ルーティング
## <a name="goal"></a>[目標]  
 このセクションでは動的に基づくメッセージをルーティングするスケジュールを作成する方法を示します (Microsoft BizTalk Server 構成データベースに展開されたスキーマ) の既知のメッセージ型のコンテンツに対して、ビジネス規則を使用してポリシー。  
  
 このトピックでは、次の手順を行います。  
  
-   コンテンツに基づいてメッセージのルーティングに使用されるビジネス ルール ポリシーを作成します。  
  
-   BRE 競合回避モジュールにメッセージを動的にルーティングすると、スケジュール ルーティング スリップを作成します。  
  
-   旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="before-you-begin"></a>はじめに  
 この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。  
  
- GlobalBank 西部テスト メッセージを作成します。  
  
- GlobalBank 東部のテスト メッセージを作成します。  
  
  次の手順では、これらの各方法について説明します。  
  
#### <a name="to-create-the-globalbank-west-test-message"></a>GlobalBank 西部テスト メッセージを作成するには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  NAOrderDoc.xml のコピーを作成し、コピー West.xml、名前を付けます。  
  
3.  メモ帳で、West.xml を開きの値を変更、 **customerName**要素**GlobalBankWest**します。  
  
4.  West.xml を utf-8 として保存し、メモ帳を終了します。  
  
#### <a name="to-create-the-globalbank-east-test-message"></a>GlobalBank 東部テスト メッセージを作成するには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  NAOrderDoc.xml のコピーを作成し、コピー East.xml、名前を付けます。  
  
3.  メモ帳で、East.xml を開きの値を変更、 **customerName**要素**GlobalBankEast**します。  
  
4.  East.xml を utf-8 として保存し、メモ帳を終了します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a>カスタム メッセージ プロパティを使用してルーティングに BRE ポリシーを作成するには  
 このルールでは、顧客の名前を使用して、メッセージをルーティングするために使用するエンドポイントを動的に設定。  
  
1.  クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**ビジネス ルール作成ツール**します。  
  
2.  ポリシー エクスプ ローラーで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。 ポリシーの名前**RouteBasedOnCustomerKnownType**します。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a>GlobalBank 西部の顧客のルーティング規則を追加するには  
  
1. **RouteBasedOnCustomerKnownType**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリックします**新しいルールの追加**します。 ルールの名前として**SetWestEndpoint**します。  
  
2. ファクト エクスプ ローラーでクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、順にクリックします**参照**します。  
  
3. **スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas で、 **NAOrderDoc.xsd**、 をクリックし、**オープン**します。  
  
   > [!NOTE]
   >  テストに使用する西部と東部のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。  
  
4. ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**、プロパティ ペインをクリックし、**ドキュメントの種類**プロパティ、および入力**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
   > [!NOTE]
   >  これは、スキーマの完全修飾名です。  
  
5. ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**、順に展開**OrderDoc**します。  
  
6. ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、 をクリックし、**等しい**。  
  
7. ファクト エクスプ ローラーからドラッグして、 **customerName**要素を **[引数 1]** ノードの下**条件**します。  
  
8. をクリックして、 **[引数 2]** ノード、および入力**GlobalBankWest**します。  
  
9. ファクト エクスプ ローラーでクリックして、**ボキャブラリ** タブで、展開**ESB します。EndPointInfo**、順に展開**バージョン 1.0**します。  
  
   > [!NOTE]
   >  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB で使用するための規則を作成するために使用できるいくつかのボキャブラリが含まれています。 これらのいくつかは、置き換えをまたは独自のボキャブラリで補強します。 たとえば、 **DynamicRunTimeMaptypes**で用意されているマップの定義が含まれて、 **GlobalBank**サンプル。  
  
10. ファクト エクスプ ローラーからドラッグして、**終点の送信トランスポート場所の設定**の定義を**アクション**します。  
  
11. クリックして**\<空の文字列\>** し入力**C:\HowTos\Out\West%MessageID%.xml**します。  
  
12. ファクト エクスプ ローラーからドラッグして、**設定の終了点送信トランスポートの種類**の定義を**アクション**します。  
  
13. ファクト エクスプ ローラーで、 **ESB します。TransportTypes**、展開**バージョン 1.0**、し、ドラッグ、**アダプター プロバイダー**の定義を**\<空の文字列\>**.  
  
14. **アクション**ウィンドウで、展開、**アダプター プロバイダー**ドロップダウン リスト、およびクリック**ファイル**します。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a>GlobalBank 東部の顧客のルーティング規則を追加するには  
  
1.  ポリシー エクスプ ローラーで右クリックし、 **SetWestEndpoint**ルールは、クリックして**コピー**します。  
  
2.  右クリック**バージョン 1.0 (未保存)**、 をクリックし、**貼り付け**します。  
  
3.  **新しいルール名**ダイアログ ボックスに「 **SetEastEndpoint**、順にクリックします**OK**します。  
  
4.  ポリシー エクスプ ローラーでクリックして、 **SetEastEndpoint**ルール。  
  
5.  **条件**セクションを右クリックして**GlobalBankWest**、 をクリックし、**引数の再設定**します。  
  
6.  クリックして **[引数 2]**、し、入力**GlobalBankEast**します。  
  
7.  **アクション**セクションで、右クリック**C:\HowTos\Out\West%MessageID%.xml**、 をクリックし、**引数の再設定**します。  
  
8.  クリックして**\<空の文字列\>**、し、入力**C:\HowTos\Out\East%MessageID%.xml**します。  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a>不明な顧客のルーティング規則を追加するには  
  
1.  RouteBasedOnCustomerKnownType ポリシーでは、バージョン 1.0 (未保存) を右クリックし、新しいルールの追加を順にクリックします。 SetUnknownCustomerEndpoint 規則の名前を付けます。  
  
2.  ルール ウィンドウで、条件を右クリックし、追加論理 and。  
  
3.  ルール] ウィンドウを右クリックし、[述語をポイントし、NotEqual 順にクリックします。  
  
4.  ファクト エクスプ ローラーでは、XML スキーマ タブをクリックして、NAOrderDoc.xsd を展開し、OrderDoc を展開します。  
  
5.  ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。  
  
6.  [引数 2] のノードをクリックして、GlobalBankWest を入力します。  
  
7.  ルール] ウィンドウを右クリックし、[述語をポイントし、NotEqual 順にクリックします。  
  
8.  ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。  
  
9. [引数 2] のノードをクリックして、GlobalBankEast を入力します。  
  
10. ファクト エクスプ ローラーで、[ボキャブラリ] タブをクリックして、ESB を展開します。EndPointInfo、バージョン 1.0 を順に展開します。  
  
11. ファクト エクスプ ローラーからは、アクションに終点の送信トランスポート場所の設定の定義をドラッグします。  
  
12. クリックして\<空の文字列\>、し C:\HowTos\Out\CustomerUnknown%MessageID%.xml を入力します。  
  
13. ファクト エクスプ ローラーからは、アクションに、設定の終了点送信トランスポートの種類の定義をドラッグします。  
  
14. ファクト エクスプ ローラーでは、ESB を展開します。TransportTypes がバージョン 1.0 を展開し、アダプターのプロバイダー定義をドラッグ\<空の文字列\>します。  
  
15. [操作] ウィンドウで、アダプター プロバイダーのボックスの一覧を展開し、ファイルをクリックします。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>発行して、ポリシーをデプロイするには  
  
1.  ポリシー エクスプ ローラーで [、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 (未保存)**、] をクリックし、**発行**します。  
  
2.  ポリシー エクスプ ローラーで [、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 - 公開済み**、] をクリックし、**デプロイ**。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB スケジュール オンランプ DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに「 **CbrKnownType**、 をクリックし、**追加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **CbrKnownType.itinerary**します。 **CbrKnownType**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  
  
    2.  **エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  
  
    3.  **XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\CbrKnownType**で、**ファイル名**ボックスをクリック**保存**します。  
  
        > [!NOTE]
        >  この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。 行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。 この操作方法に関するトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
2.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendRegionalOrders**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
3.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendRegionalOrders**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendRegionalOrders**、順にクリックします**送信ハンドラー**します。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**RouteRegionalOrders**します。  
  
    2.  **トランスポート名**ドロップダウン リストでは、をクリックして**BRE**します。  
  
    3.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**Bre 競合回避モジュールの拡張機能**します。  
  
    4.  **ポリシー**ドロップダウン リストでは、をクリックして**RouteBasedOnCustomerKnownType**します。  
  
    5.  **メッセージ形式を認識**ドロップダウン リストをクリックして**True**します。  
  
    6.  **UseMsg**ドロップダウン リストでは、をクリックして**True**します。  
  
        > [!NOTE]
        >  オーケストレーションから BRE 競合回避モジュールの拡張機能を使用する場合、 **recognizeMessageFormat**にプロパティを設定する必要があります**False**します。  
  
5.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **SendPortFilter**モデル要素。  
  
6.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendRegionalOrders**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **CbrKnownType**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (CbrKnownType.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a>スケジュール オンランプとビジネス ルールをテストするには  
  
1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**CbrKnownType.xml**、順にクリックします**オープン**旅行プランを読み込めません。  
  
4.  をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。  
  
5.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  
  
6.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。 選択**West.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。  
  
7.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  
  
8.  Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。West%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
9. East.xml メッセージを使用して、テスト プロセスを繰り返します。  
  
10. Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。East%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
11. NAOrderDoc.xml メッセージを使用して、テスト プロセスを繰り返します。  
  
12. Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。CustomerUnknown%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [方法: ビジネス ルール ポリシーを利用し、メッセージ コンテキストに基づき、メッセージの経路を動的に決定する](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)