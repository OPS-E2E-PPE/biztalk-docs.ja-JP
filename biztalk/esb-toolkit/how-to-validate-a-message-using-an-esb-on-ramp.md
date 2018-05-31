---
title: '方法: ESB 入り口を使用して、メッセージの検証 |Microsoft ドキュメント'
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
ms.openlocfilehash: 4e14fd3f433609da7748197a8b67112d815da153
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009523"
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a>方法: ESB 入り口を使用して、メッセージの検証
## <a name="goal"></a>[目標]  
 このセクションでは、ESB 入り口に送信された XML メッセージのメッセージ検証を実行する ESB ディスパッチャーの逆アセンブル パイプライン コンポーネントを構成する方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   ESB 入り口を使用するを作成、 **ItinerarySelectReceiveXml**パイプライン。  
  
-   メッセージの内容を検証する ESB ディスパッチャーの逆アセンブル パイプライン コンポーネントを構成します。  
  
-   適切な旅程を解決するのには、行程セレクター パイプライン コンポーネントを構成します。  
  
-   有効なメッセージと、無効なメッセージを使用してメッセージの検証をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="before-you-begin"></a>はじめに  
 このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。  
  
-   無効なテスト メッセージを作成します。  
  
-   ESB itinerary ドメイン固有言語 (DSL) モデルを作成します。  
  
-   旅行計画のプロパティを構成します。  
  
-   旅行計画の構造を定義します。  
  
-   行程データベースにモデルをエクスポートします。  
  
 次の手順では、これらの各を行う方法について説明します。  
  
#### <a name="to-create-an-invalid-test-message"></a>無効なテスト メッセージを作成するには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  NAOrderDoc.xml のコピーを作成し、コピー Invalid.xml の名前を変更します。  
  
3.  メモ帳で、Invalid.xml を開きます。  
  
4.  変更 **\<ns0:requestType\>10\</ns0:requestType\>に\<ns0:requestType\>10\</ns0:requestType\>** .  
  
5.  Utf-8 として Invalid.xml を保存し、メモ帳を閉じます。  
  
    > [!NOTE]
    >  この要素の数値をテキストに変更すると、メッセージが不要になったスキーマに従って有効になります。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB itinerary DSL モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、「**検証**で、**名前**ボックスをクリックしてして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**Validation.itinerary**です。 **検証**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。  
  
    2.  横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。  
  
    3.  **接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。  
  
2.  **行程ステータス**ドロップダウン リストをクリックして**配置済み**です。  
  
    > [!NOTE]
    >  この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージが受信したときに、このリポジトリからアタッチされます。 後で静的な競合回避モジュールを使用してこのリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化し、既存のモデル要素の右側に配置します。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
3.  ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。  
  
4.  右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**要素、およびクリック**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ConfigureOffRamp**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Validated%MessageID%.xml**です。  
  
5.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**SendPortFilter**モデル要素。  
  
6.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**SendNAOrder**モデル要素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>行程データベースにモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、**検証**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  Itinerary は行程データベースにエクスポートされてし、旅程セレクター パイプライン コンポーネントによって使用されるようになりました。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成し、ESB 入り口を構成します。  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**Microsoft.Practices.ESB**です。  
  
3.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、クリックして **[ok]** です。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、「 **OnRamp.Itinerary.HowTo**で、**名前**ボックス。  
  
6.  **型**ドロップダウン リストをクリックして**ファイル**、順にクリック**構成**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\HowTos\DropFolder**で、**受信フォルダー**ボックスし、 をクリックして**OK**です。  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a>入り口メッセージ検証を実行するを構成するには  
  
1.  **受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストをクリックして**ItinerarySelectReceiveXml**、省略記号ボタン (... をクリックして).  
  
2.  使用して、**パイプラインの構成**、次を構成するダイアログ ボックス**XML 逆アセンブラー**コンポーネントのプロパティ。  
  
    1.  GlobalBank.Esb アプリケーションを展開し、クリックして**スキーマ**です。 右クリック**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**、クリックして**プロパティ**です。 コピー、**名前**と**アセンブリ**プロパティし、テキスト ファイルに貼り付けます。  
  
    2.  **逆アセンブル**コンポーネントをクリックして**True**で、 **ValidateDocument**ドロップダウン リスト。  
  
    3.  クリックして、 **DocumentSpecNames**プロパティ、およびスキーマの完全修飾名を入力します。 完全修飾名が名前で始まるし、コンマと手順で抽出されたアセンブリ情報が続く、します。 以下に例を示します。  
  
         GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc、GlobalBank.ESB.DynamicResolution.Schemas、バージョン 2.0.0.0、Culture = neutral, PublicKeyToken = c2c8b2b87f54180a を =  
  
        > [!NOTE]
        >  これは、検証、スキーマの完全修飾名スキーマ名と 4 つのアセンブリ プロパティで構成されています。 アセンブリ名、バージョン、カルチャ、および公開キー トークンです。 複数の値が許可されます。パイプ (&#124;) で複数のスキーマを区切る記号。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>行程セレクター パイプライン コンポーネントを構成するには  
  
1.  **パイプラインの構成** ダイアログ ボックスで、次の構成、**行程セレクター**コンポーネントのプロパティ。  
  
    1.  クリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**です。  
  
    2.  クリックして、 **ResolverConnectionString**プロパティ、および入力**行程:\\\name=Validation;** です。  
  
    3.  をクリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。  
  
2.  をクリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
3.  BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**です。  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a>メッセージの検証と旅程選択範囲をテストするには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください) NAOrderDoc.xml DropFolder フォルダーにします。  
  
3.  C:\HowTos\Out を参照します。Validated%MessageID%.xml がディレクトリに書き込まれたことを確認します。  
  
    > [!NOTE]
    >  有効なメッセージは、期待どおりにその行程ベースのルーティングを完了します。  
  
4.  Out フォルダーから Validated%MessageID%.xml を削除します。  
  
5.  Windows エクスプローラで、C:\HowTos を参照します。  
  
6.  コピー (移動しないでください) Invalid.xml DropFolder フォルダーにします。  
  
7.  C:\HowTos\Out を参照します。新しいメッセージが配信されていないことを確認します。  
  
    > [!NOTE]
    >  メッセージを検証できませんでした。したがって、行程ベースのルーティングを完了できませんでした。  
  
8.  をクリックして**開始**タスク バーで、をポイント**管理ツール**、クリックして**イベント ビューアー**です。  
  
9. イベント ビューアーで、展開**Windows ログ**、クリックして**アプリケーション**です。  
  
10. 最近のイベントを見つける場所、**ソース**は**BizTalk Server**、および**イベント ID**は**5719**です。  
  
    > [!NOTE]
    >  送信と、無効なメッセージのエラーが発生しました例外のエントリをアプリケーション イベント ログ。  
  
11. BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を無効にする**です。  
  
12. 後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、をクリックして**削除**です。 **受信場所のことを確認して削除**ダイアログ ボックスで、をクリックして**はい**です。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的解決サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)