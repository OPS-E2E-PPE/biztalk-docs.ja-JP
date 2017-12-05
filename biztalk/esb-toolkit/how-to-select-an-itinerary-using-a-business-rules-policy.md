---
title: "方法: ビジネス ルール ポリシーを使用して、日程の選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 521b3768251cfcd31defe271a21d4b2d0bc771e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a>方法: ビジネス ルール ポリシーを使用して、日程を選択
## <a name="goal"></a>[目標]  
 このセクションでは、受信したメッセージの内容に基づく日程を選択するために使用するビジネス ルールを作成する方法と、汎用 itinerary 入り口をこれらのルールを呼び出す内行程セレクター パイプライン コンポーネントを構成する方法を示します。 このセクションをメッセージのルーティングが異なり、顧客が存在する領域に基づいたビジネス シナリオについて説明します。  
  
 このトピックでは、次の手順を行います。  
  
-   グローバル銀行の顧客の Western と東部部門の日程をモデル。  
  
-   要求の処理の日程を選択するために使用するビジネス ルール ポリシーを作成します。  
  
-   ビジネス ルール ポリシーを使用して、適切な旅程を選択、行程セレクター パイプライン コンポーネントを構成します。  
  
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
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>カスタム メッセージ プロパティを使用して、日程を選択するビジネス ルール エンジン (BRE) ポリシーを作成するには  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**ビジネス ルール作成ツール**です。  
  
2.  ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。 ポリシーに名前**ResolveItineraryBasedOnCustomer**です。  
  
    > [!NOTE]
    >  この操作方法に関するトピック」で作成されたものと同じビジネス ルール ポリシーと旅程を使用して[する方法: インターチェンジを分割し、結果として得られるメッセージをルーティング、複数ファイルの場所を使用して個別旅程](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)です。 そのセクションを完了している場合は、このトピックの「"を作成し、ESB 入り口を構成する」の手順にスキップできます。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>GlobalBank 西部の顧客の選択ルールを追加するには  
  
1.  **ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。 ルールの名前として**SetGlobalBankWestItinerary**です。  
  
2.  ファクト エクスプ ローラーで、をクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、クリックして**参照**です。  
  
3.  **スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas、select **NAOrderDoc.xsd**、クリックして**開く**です。  
  
    > [!NOTE]
    >  これは、テストに使用する左右のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。  
  
4.  ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**をクリックして、**ドキュメントの種類**のプロパティ] ウィンドウと [入力プロパティ**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  これは、スキーマの完全修飾名です。  
  
5.  ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**の順に展開および**OrderDoc**です。  
  
6.  ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。  
  
7.  ファクト エクスプ ローラーからドラッグして、 **customerName**要素を**argument1**ノードの下**条件**です。  
  
8.  をクリックして、 **argument2**ノード、および入力**GlobalBankWest**です。  
  
9. ファクト エクスプ ローラーで、をクリックして、**ボキャブラリ**タブです。展開して、 **ESB です。行程**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**行程名の設定**定義**アクション**です。  
  
10. をクリックして**\<空の文字列\>**、し、入力**GlobalBankWestItinerary**です。  
  
    > [!NOTE]
    >  このトピックの後半 GlobalBank 西からメッセージを処理するこの日程を作成します。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>GlobalBank 東部の顧客の選択ルールを追加するには  
  
1.  ポリシー エクスプ ローラーで右クリックし、 **SetGlobalBankWestItinerary**ルールは、クリックして**コピー**です。  
  
2.  右クリック**バージョン 1.0 (未保存)**、クリックして**貼り付け**です。  
  
3.  **新しいルールの名前** ダイアログ ボックスで、「 **SetGlobalBankEastItinerary**、順にクリック**OK**です。  
  
4.  ポリシー エクスプ ローラーで、をクリックして、 **SetGlobalBankEastItinerary**ルール。  
  
5.  **条件**セクションを右クリックして**GlobalBankWest**、クリックして**引数の再設定**です。  
  
6.  をクリックして**argument2**、し、入力**GlobalBankEast**です。  
  
7.  **アクション**セクションを右クリックして**GlobalBankWestItinerary**、クリックして**引数の再設定**です。  
  
8.  をクリックして**\<空の文字列\>**し入力**GlobalBankEastItinerary**です。  
  
    > [!NOTE]
    >  操作方法に関するトピックの後半 GlobalBank 東部からメッセージを処理するこの行程を作成します。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>発行して、ポリシーを展開するには  
  
1.  ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 (未保存)**、クリックして**発行**です。  
  
2.  ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a>GlobalBank 西部メッセージの ESB itinerary ドメイン固有言語 (DSL) モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**です。  
  
4.  **名前**ボックスに、入力**GlobalBankWestItinerary**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a>GlobalBank 西部旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**GlobalBankWestItinerary.itinerary**です。 **GlobalBankWestItinerary**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。  
  
    2.  横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。  
  
    3.  **接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。  
  
2.  **行程ステータス**ドロップダウン リストをクリックして**配置済み**です。  
  
    > [!NOTE]
    >  この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージの受信時にこのリポジトリからアタッチされます。 後で、ビジネス ルール エンジンは、(BRI) 競合回避モジュールを使用して受信メッセージを評価し、このリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
3.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteMessage**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**StaticResolver**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\West%MessageID%.xml**です。  
  
5.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessage**モデル要素。  
  
6.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **RouteMessage**モデル要素を**SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>行程データベースにモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>GlobalBank 東部メッセージの ESB itinerary DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**です。  
  
4.  **名前**ボックスに、入力**GlobalBankEastItinerary**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a>GlobalBank 東部旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**GlobalBankEastItinerary.itinerary**です。 **GlobalBankEastItinerary**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。  
  
    2.  横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。  
  
    3.  **接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。  
  
2.  **行程ステータス**ドロップダウン リストをクリックして**配置済み**です。  
  
    > [!NOTE]
    >  この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージが受信したときに、このリポジトリからアタッチされます。 後で、BRI 競合回避モジュールを使用して受信メッセージを評価し、このリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
3.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteMessage**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**StaticResolver**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\East%MessageID%.xml**です。  
  
5.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessage**モデル要素。  
  
6.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **RouteMessage**モデル要素を**SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>行程データベースにモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成し、ESB 入り口を構成します。  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**Microsoft.Practices.ESB**です。  
  
3.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、クリックして**[ok]**です。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**OnRamp.Itinerary.HowTo**です。  
  
6.  **型**ドロップダウン リストをクリックして**ファイル**、順にクリック**構成**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、入力**C:\HowTos\DropFolder**、クリックして**ok**です。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>行程セレクター パイプライン コンポーネントを構成するには  
  
1.  **受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストをクリックして**ItinerarySelectReceiveXml**、省略記号ボタン (... をクリックして).  
  
2.  使用して、**パイプラインの構成**、次を構成するダイアログ ボックス**行程セレクター**コンポーネントのプロパティ。  
  
    1.  クリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**です。  
  
    2.  クリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true です。**  
  
    3.  をクリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。  
  
3.  をクリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
4.  BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**です。  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>Itinerary セレクターとビジネス ルールをテストするには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください)、East.xml と West.xml フォルダーにファイルを DropFolder です。  
  
3.  C:\HowTos\Out を参照します。East%MessageID%.xml と West%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
    > [!NOTE]
    >  顧客の要素の値を除いて同一でも、行程セレクター パイプライン コンポーネントの解像度に基づいて、別の日程を使用して、メッセージが処理されました。  
  
4.  BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を無効にする**です。  
  
5.  後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、をクリックして**削除**です。 **受信場所のことを確認して削除**ダイアログ ボックスで、をクリックして**はい**です。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: 別個のスケジュールを利用し、インターチェンジを分割して結果的に生成されたメッセージを複数のファイルの場所に送る](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的解決サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)