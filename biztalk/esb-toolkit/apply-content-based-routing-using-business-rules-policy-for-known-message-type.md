---
title: "方法: 既知のメッセージの種類のポリシーをルール実装のビジネスを使用してコンテンツ ベース ルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878a6e180aaf7e5f37c5cf98ca0a67790917859a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a>方法: 既知のメッセージの種類のポリシーをルール実装のビジネスを使用してコンテンツ ベース ルーティング
## <a name="goal"></a>[目標]  
 このセクションでは、動的に基づいたメッセージをルーティングする旅程を作成する方法を示します (Microsoft BizTalk Server 構成データベースに展開されたスキーマ) の既知のメッセージ型のコンテンツに対するビジネス規則を使用してポリシー。  
  
 このトピックでは、次の手順を行います。  
  
-   コンテンツに基づいてメッセージのルーティングに使用されるビジネス ルール ポリシーを作成します。  
  
-   動的にメッセージをルーティングする BRE リゾルバーを itinerary 回覧を作成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="before-you-begin"></a>はじめに  
 このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。  
  
-   GlobalBank 西部テスト メッセージを作成します。  
  
-   GlobalBank 東部テスト メッセージを作成します。  
  
 次の手順では、これらの各を行う方法について説明します。  
  
#### <a name="to-create-the-globalbank-west-test-message"></a>GlobalBank 西部テスト メッセージを作成するには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  NAOrderDoc.xml のコピーを作成し、コピー West.xml を名前します。  
  
3.  メモ帳で、West.xml を開きの値を変更、 **customerName**要素**GlobalBankWest**です。  
  
4.  Utf-8 として West.xml を保存し、メモ帳を閉じます。  
  
#### <a name="to-create-the-globalbank-east-test-message"></a>GlobalBank 東部テスト メッセージを作成するには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  NAOrderDoc.xml のコピーを作成し、コピー East.xml を名前します。  
  
3.  メモ帳で、East.xml を開きの値を変更、 **customerName**要素**GlobalBankEast**です。  
  
4.  Utf-8 として East.xml を保存し、メモ帳を閉じます。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a>カスタム メッセージ プロパティを使用してルーティングする BRE ポリシーを作成するには  
 このルールは動的にメッセージをルーティングするのにために使用するエンドポイントを設定するのに顧客の名前を使用します。  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**ビジネス ルール作成ツール**です。  
  
2.  ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。 ポリシーに名前**RouteBasedOnCustomerKnownType**です。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a>顧客 GlobalBank 西部のルーティング規則を追加するには  
  
1.  **RouteBasedOnCustomerKnownType**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。 ルールの名前として**SetWestEndpoint**です。  
  
2.  ファクト エクスプ ローラーで、をクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、クリックして**参照**です。  
  
3.  **スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas、select **NAOrderDoc.xsd**、クリックして**開く**です。  
  
    > [!NOTE]
    >  これは、テストに使用する左右のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。  
  
4.  ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**、プロパティ ペインをクリックし、**ドキュメントの種類**プロパティ、および入力**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  これは、スキーマの完全修飾名です。  
  
5.  ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**の順に展開および**OrderDoc**です。  
  
6.  ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。  
  
7.  ファクト エクスプ ローラーからドラッグして、 **customerName**要素を**argument1**ノードの下**条件**です。  
  
8.  をクリックして、 **argument2**ノード、および入力**GlobalBankWest**です。  
  
9. ファクト エクスプ ローラーで、をクリックして、**ボキャブラリ** タブで、展開**ESB です。EndPointInfo**の順に展開および**バージョン 1.0**です。  
  
    > [!NOTE]
    >  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB の使用規則を作成するために使用できるいくつかのボキャブラリが含まれています。 これらのいくつかは、交換する必要があります。 または独自のボキャブラリで補完されました。 たとえば、 **DynamicRunTimeMaptypes**で用意されているマップの定義を持つ、 **GlobalBank**サンプルです。  
  
10. ファクト エクスプ ローラーからドラッグして、**終点送信トランスポート場所の設定**の定義を**アクション**です。  
  
11. をクリックして**\<空の文字列\>**し入力**C:\HowTos\Out\West%MessageID%.xml**です。  
  
12. ファクト エクスプ ローラーからドラッグして、**設定の終了点送信トランスポートの種類**定義**アクション**です。  
  
13. ファクト エクスプ ローラーで、 **ESB です。TransportTypes**、展開**バージョン 1.0**、し、ドラッグ、**アダプター プロバイダー**定義**\<空の文字列\>**.  
  
14. **アクション** ウィンドウで、展開、**アダプター プロバイダー**クリックしてドロップダウン リスト、**ファイル**です。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a>GlobalBank 東部の顧客のルーティング規則を追加するには  
  
1.  ポリシー エクスプ ローラーで右クリックし、 **SetWestEndpoint**ルールは、クリックして**コピー**です。  
  
2.  右クリック**バージョン 1.0 (未保存)**、クリックして**貼り付け**です。  
  
3.  **新しいルールの名前** ダイアログ ボックスで、「 **SetEastEndpoint**、順にクリック**OK**です。  
  
4.  ポリシー エクスプ ローラーで、をクリックして、 **SetEastEndpoint**ルール。  
  
5.  **条件**セクションを右クリックして**GlobalBankWest**、クリックして**引数の再設定**です。  
  
6.  をクリックして**argument2**、し、入力**GlobalBankEast**です。  
  
7.  **アクション**セクションを右クリックして**C:\HowTos\Out\West%MessageID%.xml**、クリックして**引数の再設定**です。  
  
8.  をクリックして**\<空の文字列\>**、し、入力**C:\HowTos\Out\East%MessageID%.xml**です。  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a>不明な顧客のルーティング規則を追加するには  
  
1.  RouteBasedOnCustomerKnownType ポリシーでは、バージョン 1.0 (未保存) を右クリックし、[新しい規則の追加] をクリックします。 SetUnknownCustomerEndpoint ルールの名前を付けます。  
  
2.  ルール ウィンドウで、条件を右クリックし、追加 をクリックして論理 and。  
  
3.  ルール ウィンドウを右クリックし、述語をポイントし、NotEqual をクリックします。  
  
4.  ファクト エクスプ ローラーで、XML スキーマ] タブをクリックして、[NAOrderDoc.xsd を展開し、OrderDoc を展開します。  
  
5.  ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。  
  
6.  [引数 2] ノードをクリックし、GlobalBankWest を入力します。  
  
7.  ルール ウィンドウを右クリックし、述語をポイントし、NotEqual をクリックします。  
  
8.  ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。  
  
9. [引数 2] ノードをクリックし、GlobalBankEast を入力します。  
  
10. ファクト エクスプ ローラーで、[ボキャブラリ] タブをクリックして、ESB を展開します。EndPointInfo、バージョン 1.0 を順に展開します。  
  
11. ファクト エクスプ ローラーからアクションを終点送信トランスポート場所の設定の定義をドラッグします。  
  
12. をクリックして\<空の文字列\>C:\HowTos\Out\CustomerUnknown%MessageID%.xml を入力します。  
  
13. ファクト エクスプ ローラーからアクションを設定の終了点送信トランスポートの種類の定義をドラッグします。  
  
14. ファクト エクスプ ローラーで、ESB を展開します。TransportTypes、バージョン 1.0 を展開し、アダプターのプロバイダー定義をドラッグ\<空の文字列\>です。  
  
15. [操作] ウィンドウで、アダプター プロバイダーのボックスの一覧を展開し、[ファイル] をクリックします。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>発行して、ポリシーを展開するには  
  
1.  ポリシー エクスプ ローラーで、、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 (未保存)**、クリックして**発行**です。  
  
2.  ポリシー エクスプ ローラーで、、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB itinerary DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**CbrKnownType**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**CbrKnownType.itinerary**です。 **CbrKnownType**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  **Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\CbrKnownType**で、**ファイル名**ボックスをクリックして**保存**です。  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendRegionalOrders**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
3.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendRegionalOrders**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendRegionalOrders**、クリックして**送信ハンドラー**です。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteRegionalOrders**です。  
  
    2.  **トランスポート名**ドロップダウン リストをクリックして**BRE**です。  
  
    3.  **リゾルバーの実装**ドロップダウン リストをクリックして**Bre 競合回避モジュールの拡張機能**します。  
  
    4.  **ポリシー**ドロップダウン リストをクリックして**RouteBasedOnCustomerKnownType**です。  
  
    5.  **メッセージ形式を認識**ドロップダウン リストをクリックして**True**です。  
  
    6.  **UseMsg**ドロップダウン リストをクリックして**True**です。  
  
        > [!NOTE]
        >  オーケストレーションへの BRE リゾルバー拡張機能を使用する場合、 **recognizeMessageFormat**プロパティに設定する必要があります**False**です。  
  
5.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**SendPortFilter**モデル要素。  
  
6.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendRegionalOrders**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **CbrKnownType**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (CbrKnownType.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a>Itinerary とビジネス ルールをテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**CbrKnownType.xml**、順にクリック**開く**日程を読み込めません。  
  
4.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**West.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
8.  Windows エクスプローラで、C:\HowTos\Out を参照します。West%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
9. East.xml メッセージを使用して、テスト プロセスを繰り返します。  
  
10. Windows エクスプローラで、C:\HowTos\Out を参照します。East%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
11. NAOrderDoc.xml メッセージを使用して、テスト プロセスを繰り返します。  
  
12. Windows エクスプローラで、C:\HowTos\Out を参照します。CustomerUnknown%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [方法: ビジネス ルール ポリシーを利用し、メッセージ コンテキストに基づき、メッセージの経路を動的に決定する](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)