---
title: '方法: ビジネス ルール ポリシーを使用するスケジュールを選択します |。Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12496da0de4057e96be0b714ad1af048ee6b8ef1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976963"
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a>方法: ビジネス ルール ポリシーを使用するスケジュールを選択します。
## <a name="goal"></a>[目標]  
 このセクションでは、受信したメッセージの内容に基づいて、旅行プランを選択するのに使用できるビジネス ルールを作成する方法と、汎用的なスケジュールに導入これらのルールの呼び出し内での旅程セレクター パイプライン コンポーネントを構成する方法を示します。 このセクションでメッセージがルーティングされる異なる方法で、顧客が存在するリージョンに基づくビジネス シナリオについて説明します。  
  
 このトピックでは、次の手順を行います。  
  
-   西と東 Global 銀行の顧客の事業部のモデルのスケジュール。  
  
-   要求を処理するスケジュールを選択するために使用するビジネス ルール ポリシーを作成します。  
  
-   ビジネス ルール ポリシーを使用して、適切なスケジュールを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。  
  
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
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>カスタム メッセージ プロパティを使用するスケジュールを選択するビジネス ルール エンジン (BRE) ポリシーを作成するには  
  
1.  クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**ビジネス ルール作成ツール**します。  
  
2.  ポリシー エクスプ ローラーで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。 ポリシーの名前**ResolveItineraryBasedOnCustomer**します。  
  
    > [!NOTE]
    >  このトピックのトピックで作成されたものと同じビジネス ルール ポリシーとスケジュールを使用して[方法: インターチェンジを分割し、結果として得られるメッセージをルーティング、複数ファイルの場所を使用して異なる日程](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)します。 そのセクションを完了している場合は、このトピックの「"を作成して、ESB 入り口を構成する 手順を省略できます。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>GlobalBank 西部の顧客の選択規則を追加するには  
  
1.  **ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリックします**新しいルールの追加**します。 ルールの名前として**SetGlobalBankWestItinerary**します。  
  
2.  ファクト エクスプ ローラーでクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、順にクリックします**参照**します。  
  
3.  **スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas で、 **NAOrderDoc.xsd**、 をクリックし、**オープン**します。  
  
    > [!NOTE]
    >  テストに使用する西部と東部のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。  
  
4.  ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**、クリックして、**ドキュメントの種類**プロパティのプロパティ ウィンドウと入力し、 **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  これは、スキーマの完全修飾名です。  
  
5.  ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**、順に展開**OrderDoc**します。  
  
6.  ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、 をクリックし、**等しい**。  
  
7.  ファクト エクスプ ローラーからドラッグして、 **customerName**要素を **[引数 1]** ノードの下**条件**します。  
  
8.  をクリックして、 **[引数 2]** ノード、および入力**GlobalBankWest**します。  
  
9. ファクト エクスプ ローラーでクリックして、**ボキャブラリ**タブ。展開、 **ESB します。旅行プラン**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**旅行プラン名の設定**の定義を**アクション**します。  
  
10. クリックして**\<空の文字列\>**、し、入力**GlobalBankWestItinerary**します。  
  
    > [!NOTE]
    >  このトピックの後半では、GlobalBank 西部からメッセージを処理するこの旅行プランが作成されます。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>GlobalBank 東部の顧客の選択規則を追加するには  
  
1.  ポリシー エクスプ ローラーで右クリックし、 **SetGlobalBankWestItinerary**ルールは、クリックして**コピー**します。  
  
2.  右クリック**バージョン 1.0 (未保存)**、 をクリックし、**貼り付け**します。  
  
3.  **新しいルール名**ダイアログ ボックスに「 **SetGlobalBankEastItinerary**、順にクリックします**OK**します。  
  
4.  ポリシー エクスプ ローラーでクリックして、 **SetGlobalBankEastItinerary**ルール。  
  
5.  **条件**セクションを右クリックして**GlobalBankWest**、 をクリックし、**引数の再設定**します。  
  
6.  クリックして **[引数 2]**、し、入力**GlobalBankEast**します。  
  
7.  **アクション**セクションで、右クリック**GlobalBankWestItinerary**、 をクリックし、**引数の再設定**します。  
  
8.  クリックして**\<空の文字列\>** し入力**GlobalBankEastItinerary**します。  
  
    > [!NOTE]
    >  に関する「方法」トピックの後半では、GlobalBank 東部からメッセージを処理するこの旅行プランを作成されます。 します  
  
#### <a name="to-publish-and-deploy-the-policy"></a>発行して、ポリシーをデプロイするには  
  
1.  ポリシー エクスプ ローラーで [、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 (未保存)**、] をクリックし、**発行**します。  
  
2.  ポリシー エクスプ ローラーで [、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 - 公開済み**、] をクリックし、**デプロイ**。  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a>GlobalBank 西部メッセージの ESB 行程ドメイン固有言語 (DSL) モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**します。  
  
4.  **名前**ボックスに「 **GlobalBankWestItinerary**、 をクリックし、**追加**します。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a>GlobalBank 西部スケジュールのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **GlobalBankWestItinerary.itinerary**します。 **GlobalBankWestItinerary**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。  
  
    2.  横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。  
  
    3.  **接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。  
  
2.  **行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。  
  
    > [!NOTE]
    >  この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージの受信時にこのリポジトリからアタッチされました。 後で、ビジネス ルール エンジンは、(BRI) 競合回避モジュールを使用して、受信メッセージを評価し、このリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
2.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
3.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**RouteMessage**します。  
  
    2.  **旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**StaticResolver**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\West%MessageID%.xml**します。  
  
5.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessage**モデル要素。  
  
6.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **RouteMessage**モデル要素に、 **SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>行程データベースにモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>GlobalBank 東部メッセージの ESB 行程 DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**します。  
  
4.  **名前**ボックスに「 **GlobalBankEastItinerary**、 をクリックし、**追加**します。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a>GlobalBank 東部スケジュールのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **GlobalBankEastItinerary.itinerary**します。 **GlobalBankEastItinerary**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。  
  
    2.  横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。  
  
    3.  **接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。  
  
2.  **行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。  
  
    > [!NOTE]
    >  この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージが受信したときに、このリポジトリからアタッチします。 後で BRI 競合回避モジュールを使用して、受信メッセージを評価し、このリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
2.  ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
3.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**RouteMessage**します。  
  
    2.  **旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**StaticResolver**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\East%MessageID%.xml**します。  
  
5.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessage**モデル要素。  
  
6.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **RouteMessage**モデル要素に、 **SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>行程データベースにモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成および ESB 入り口を構成するには  
  
1.  クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、順に展開**Microsoft.Practices.ESB**します。  
  
3.  右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OnRamp.Itinerary.HowTo**します。  
  
6.  **型**ドロップダウン リストでは、をクリックして**ファイル**、順にクリックします**構成**します。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに「 **C:\HowTos\DropFolder**、順にクリックします**OK**します。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>旅行プラン セレクターのパイプライン コンポーネントを構成するには  
  
1.  **受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストでは、をクリックして**ItinerarySelectReceiveXml**、省略記号ボタン (... を順にクリックします).  
  
2.  使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**スケジュール セレクター**コンポーネントのプロパティ。  
  
    1.  をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。  
  
    2.  をクリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  クリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。  
  
3.  クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
4.  右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**します。  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>スケジュール セレクターとビジネス ルールをテストするには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください) ファイル East.xml と West.xml DropFolder フォルダーにします。  
  
3.  C:\HowTos\Out に移動します。East%MessageID%.xml と West%MessageID%.xml メッセージが、ディレクトリに書き込まれたことを確認します。  
  
    > [!NOTE]
    >  Customer 要素の値を除いて同一です、ただしスケジュール セレクターのパイプライン コンポーネントの解像度に基づく別のスケジュールを使用して、メッセージが処理されました。  
  
4.  右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を無効にする**します。  
  
5.  後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。 **削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: 別個のスケジュールを利用し、インターチェンジを分割して結果的に生成されたメッセージを複数のファイルの場所に送る](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的解決サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)