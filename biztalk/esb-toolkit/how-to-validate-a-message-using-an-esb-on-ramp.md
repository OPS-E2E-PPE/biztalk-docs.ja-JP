---
title: '方法: ESB 入り口を使用して、メッセージの検証 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43dfc791-7cb6-45a4-898f-f53def199c08
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62df8ec8628353aa127ed6cde8380e5724ddf12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020570"
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a>方法: ESB 入り口を使用して、メッセージの検証
## <a name="goal"></a>[目標]  
 このセクションでは、ESB 入り口に送信された XML メッセージのメッセージの検証を実行する ESB ディスパッチャー逆アセンブル パイプライン コンポーネントを構成する方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   ESB 入り口を使用するを作成、 **ItinerarySelectReceiveXml**パイプライン。  
  
-   メッセージの内容を検証する ESB ディスパッチャー逆アセンブル パイプライン コンポーネントを構成します。  
  
-   適切なスケジュールを解決するのには、スケジュール セレクターのパイプライン コンポーネントを構成します。  
  
-   有効なメッセージと、無効なメッセージを使用してメッセージの検証をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="before-you-begin"></a>はじめに  
 この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。  
  
- 無効なテスト メッセージを作成します。  
  
- ESB スケジュール オンランプ ドメイン固有言語 (DSL) モデルを作成します。  
  
- 旅行プランのプロパティを構成します。  
  
- 旅行プランの構造を定義します。  
  
- モデルは、行程データベースをエクスポートします。  
  
  次の手順では、これらの各方法について説明します。  
  
#### <a name="to-create-an-invalid-test-message"></a>無効なテスト メッセージを作成するには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  NAOrderDoc.xml のコピーを作成して、コピー Invalid.xml を変更します。  
  
3.  メモ帳で Invalid.xml を開きます。  
  
4.  変更**\<ns0:requestType\>10\</ns0:requestType\>に\<ns0:requestType\>10\</ns0:requestType\>**.  
  
5.  Invalid.xml を utf-8 として保存し、メモ帳を終了します。  
  
    > [!NOTE]
    >  この要素の数値をテキストに変更すると、メッセージできなくスキーマに対して無効です。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB スケジュール オンランプ DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、 をクリックし、**新しいスケジュール**します。  
  
3.  **新しい項目の追加**ダイアログ ボックスに「**検証**で、**名前**ボックスをクリックして**追加**します。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **Validation.itinerary**します。 **検証**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。  
  
    2.  横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。  
  
    3.  **接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。  
  
2.  **行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。  
  
    > [!NOTE]
    >  この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージが受信したときに、このリポジトリからアタッチします。 後で、静的な競合回避モジュールを使用してこのリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1.  ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
    4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
2.  ツールボックスからドラッグ、**傾斜をオフ**デザイン画面に要素をモデル化し、既存のモデル要素の右側に配置します。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。  
  
    2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
    4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
3.  ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**要素、およびクリック**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**ConfigureOffRamp**します。  
  
    2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。  
  
    3.  **トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。  
  
    4.  をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Validated%MessageID%.xml**します。  
  
5.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **SendPortFilter**モデル要素。  
  
6.  ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>行程データベースにモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、**検証**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランは、行程データベースにエクスポートされ、旅程セレクターのパイプライン コンポーネントで使用できるようになりました。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成および ESB 入り口を構成するには  
  
1.  クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、順に展開**Microsoft.Practices.ESB**します。  
  
3.  右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。  
  
5.  **受信場所のプロパティ**ダイアログ ボックスに「 **OnRamp.Itinerary.HowTo**で、**名前**ボックス。  
  
6.  **型**ドロップダウン リストでは、をクリックして**ファイル**、順にクリックします**構成**します。  
  
7.  **FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\HowTos\DropFolder**で、**受信フォルダー**ボックスをクリック**OK**。  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a>構成に導入メッセージ検証を実行するには  
  
1.  **受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストでは、をクリックして**ItinerarySelectReceiveXml**、省略記号ボタン (... を順にクリックします).  
  
2.  使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**XML 逆アセンブラー**コンポーネントのプロパティ。  
  
    1.  GlobalBank.Esb アプリケーションを展開し、クリックして**スキーマ**します。 右クリックして**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**、 をクリックし、**プロパティ**します。 コピー、**名前**と**アセンブリ**プロパティのテキスト ファイルに貼り付けます。  
  
    2.  **逆アセンブル**コンポーネント、 をクリックして**True**で、 **ValidateDocument**ドロップダウン リスト。  
  
    3.  をクリックして、 **DocumentSpecNames**プロパティ、およびスキーマの完全修飾名を入力します。 完全修飾名が名前で始まるし、コンマと手順で抽出されたアセンブリの情報が続きますをします。 以下に例を示します。  
  
         GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc、GlobalBank.ESB.DynamicResolution.Schemas、バージョン 2.0.0.0、Culture = neutral, PublicKeyToken = c2c8b2b87f54180a を =  
  
        > [!NOTE]
        >  これは、スキーマ検証の完全修飾名です。スキーマ名と 4 つのアセンブリ プロパティで構成されています。 アセンブリ名、バージョン、カルチャ、および公開キー トークン。 複数の値が許可されます。複数のスキーマをパイプで区切ります (&#124;) シンボル。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>旅行プラン セレクターのパイプライン コンポーネントを構成するには  
  
1.  **パイプラインの構成** ダイアログ ボックスで、次の構成**スケジュール セレクター**コンポーネントのプロパティ。  
  
    1.  をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。  
  
    2.  をクリックして、 **ResolverConnectionString**プロパティ、および入力**行程:\\\name=Validation;** します。  
  
    3.  クリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。  
  
2.  クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
3.  右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**します。  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a>メッセージの検証とスケジュールの選択をテストするには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください) NAOrderDoc.xml DropFolder フォルダーにします。  
  
3.  C:\HowTos\Out に移動します。Validated%MessageID%.xml がディレクトリに書き込まれたことを確認します。  
  
    > [!NOTE]
    >  期待どおりに、有効なメッセージは、そのスケジュールに基づくルーティングを完了します。  
  
4.  Validated%MessageID%.xml を Out フォルダから削除します。  
  
5.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
6.  コピー (移動しないでください) Invalid.xml DropFolder フォルダーにします。  
  
7.  C:\HowTos\Out に移動します。新しいメッセージが配信されないことを確認します。  
  
    > [!NOTE]
    >  メッセージを検証できませんでした。そのため、スケジュールに基づくルーティングできませんでした。  
  
8.  をクリックして**開始**タスク バーで、をポイント**管理ツール**、 をクリックし、**イベント ビューアー**します。  
  
9. イベント ビューアーで、展開**Windows ログ**、 をクリックし、**アプリケーション**します。  
  
10. 最近のイベントを検索場所、**ソース**は**BizTalk Server**、および**イベント ID**は**5719**します。  
  
    > [!NOTE]
    >  送信と、無効なメッセージの失敗、アプリケーション イベント ログに例外のエントリでが発生しました。  
  
11. 右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を無効にする**します。  
  
12. 後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。 **削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的解決サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)