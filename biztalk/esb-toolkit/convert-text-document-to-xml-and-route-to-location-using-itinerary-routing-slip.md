---
title: '方法: XML と旅程のルーティング先を使用してファイルの場所へのルートに、テキスト ドキュメントを変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8284c1623329133533fe03aab567b1281f07c1a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010195"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a>方法: テキスト ドキュメントを XML と旅程のルーティング先を使用してファイルの場所へのルートに変換
## <a name="goal"></a>[目標]  
 セクションでは、テキスト ドキュメントを XML に変換し、適切な旅程を選択し、ファイルの場所にメッセージをルーティングするパイプラインを作成する方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   フラット ファイル ドキュメントを受信し、XML に変換するには、パイプラインを使用します。  
  
-   適切な回覧を解決するのには、行程セレクター パイプライン コンポーネントを構成します。  
  
-   入り口、カスタム パイプラインを使用するを作成します。  
  
-   行程ベースのフラット ファイル メッセージのルーティングをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="before-you-begin"></a>はじめに  
 このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。  
  
-   展開、 **DataFormatTransformation**行程です。  
  
-   テスト メッセージを作成します。  
  
 次の手順では、これらの各を行う方法について説明します。  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a>DataFormatTransformation 旅程を展開するには  
  
1.  Visual Studio で、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで、 **Itinerary.Library**プロジェクトをダブルクリックして**DataFormatTransformation.itinerary**行程デザイナーで開きます。  
  
3.  Visual Studio でのデザイン画面をクリックして**DataFormatTransformation.itinerary**です。 **DataFormatTransformation.itinerary**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **行程ステータス**ドロップダウン リストをクリックして**配置済み**です。  
  
    2.  **モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。  
  
    3.  横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。  
  
    4.  **接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。  
  
4.  すべてのプロジェクトの成果物を保存します。  
  
5.  Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**行程をクリックして**モデルのエクスポート**です。  
  
#### <a name="to-create-the-receive-pipeline"></a>受信パイプラインを作成するには  
  
1.  Visual Studio を右クリックして**DataFormatTransformation.Schemas**、クリックして**プロパティ**です。 をクリックして**アプリケーション**、し、入力**GlobalBank.ESB.DataFormatTransformation.Schemas**で、**アセンブリ名**ボックス。  
  
2.  右クリック**DataFormatTransformation.Schemas**、クリックして**プロパティ**です。 をクリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す **.\\.\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**です。  
  
3.  右クリック**DataFormatTransformation.Pipelines**、クリックして**削除**です。  
  
4.  右クリック**DataFormatTransformation**、 をポイント**追加**、クリックして**新しいプロジェクト**です。 をクリックして**Biztalk プロジェクト**、クリックして**空の Biztalk Server プロジェクト**です。 **名前**ボックスに、入力**DataFormatTransformationReceive.Pipeline**です。  
  
5.  右クリック**DataFormatTransformationReceive.Pipeline**、クリックして**プロパティ**です。 をクリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**です。  
  
6.  右クリック**DataFormatTransformationReceive.Pipeline**、 をポイント**追加**、クリックして**新しい項目の**します。  
  
7.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**受信パイプライン**テンプレート ペインでします。 **名前**ボックスに、入力**ItinerarySelectReceiveFF**、クリックして**追加**です。  
  
8.  右クリック**参照**DataFormatTransformationReceive.Pipeline プロジェクト、およびクリック**参照の追加**です。 クリックして、**プロジェクト** タブをクリックして**DataFormatTransformation.Schemas**です。 をクリックして**OK**参照を追加します。  
  
9. ツールボックスからドラッグして、**フラット ファイル逆アセンブラー**パイプライン コンポーネントを**逆アセンブル**パイプラインのステージ。  
  
10. 逆アセンブル、フラット ファイルのプロパティ ウィンドウで、をクリックして**DataModelTransformation.Schemas.NAOrderDocFF**で、**ドキュメント スキーマ**ドロップダウン リスト。  
  
11. ツールボックスからドラッグして、 **ESB 行程セレクター**パイプライン コンポーネントを**パーティの解決**パイプラインのステージ。  
  
12. ツールボックスからドラッグ、 **ESB ディスパッチャー**パイプライン コンポーネントを**パーティの解決**、パイプラインのステージの下に配置し、 **ESB 行程セレクター**パイプラインコンポーネント。  
  
13. すべてのプロジェクトの成果物を保存します。  
  
## <a name="to-create-the-test-message"></a>テスト メッセージを作成するには  
  
1.  DataFormatTransformation.Schemas プロジェクトの NAOrderDocFF.xsd スキーマ ファイルで 1 回クリックします。 Visual Studio の [プロパティ] ペインで、次の 2 つのプロパティを変更します。  
  
    -   **インスタンスの出力の種類の生成**です。 変更するには、このプロパティのドロップダウン リストをクリックして**ネイティブ**です。  
  
    -   **出力インスタンス ファイル名**です。 このプロパティの省略記号ボタン (...) をクリックし、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation の既定のパスをそのまま使用します。 **ファイル名**ボックスに、入力**NAOrderDocFF**、クリックして**保存**です。  
  
2.  右クリック**NAOrderDocFF.xsd**  **DataFormatTransformation.Schemas**、クリックして**インスタンスの生成**です。 この時点では、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation ディレクトリに生成された新しいファイルが必要です。  
  
3.  コピー (移動しないでください)、ファイルに C:\HowTos C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation から NAOrderDocFF.txt です。  
  
    > [!NOTE]
    >  これは、メッセージはメッセージを受信して、XML に変換します。 このドキュメントでは、North American 注文ドキュメントのフラット ファイル バージョンを表します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a>受信パイプラインとスキーマを展開するには  
  
1.  右クリック**DataFormatTransformationReceive.Pipeline**、クリックして**プロパティ**です。 をクリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。  
  
2.  右クリックし、 **DataFormatTransformation.Schemas**プロジェクトをクリックして**プロパティ**です。 をクリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。  
  
3.  両方のプロパティ ウィンドウを閉じる**DataFormatTransformationReceive.Pipeline**と**DataFormatTransformation.Schemas**です。  
  
4.  ソリューション エクスプ ローラーで右クリックし、 **DataFormatTransformation**プロジェクトをクリックして**ソリューションの配置**です。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成し、ESB 入り口を構成します。  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、クリックして**Microsoft.Practices.ESB**です。  
  
3.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、クリックして **[ok]** です。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**OnRamp.Itinerary.FlatFile.FILE**です。  
  
6.  **型**ドロップダウン リストをクリックして**ファイル**、順にクリック**構成**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、入力**C:\HowTos\DropFolder**です。  
  
8.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**ファイル マスク**ボックスに、入力 **\*.txt**、クリックして**ok**です。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>行程セレクター パイプライン コンポーネントを構成するには  
  
1.  **受信場所のプロパティ**ダイアログ ボックスで、 をクリックして**ItinerarySelectReceiveFF**で、**受信パイプライン**ドロップダウン リストで、省略記号ボタン (...) をクリックします。  
  
2.  使用して、**パイプラインの構成**、次を構成するダイアログ ボックス**行程セレクター**コンポーネントのプロパティ。  
  
    1.  クリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**です。  
  
    2.  クリックして、 **ResolverConnectionString**プロパティ、型**行程:\\\name=DataFormatTransformation;** 順にクリック **[ok]** です。  
  
3.  をクリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
4.  BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を有効にする**です。  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a>行程ベースのフラット ファイル メッセージのルーティングをテストするには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください) NAOrderDocFF.txt C:\HowTos\DropFolder にします。  
  
3.  C:\HowTos\Out を参照します。DFT%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
4.  BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を無効にする**です。  
  
5.  後に、 **OnRamp.Itinerary.FlatFile.FILE**受信場所が無効になっている、右クリックし、をクリックして**削除**です。 **受信場所のことを確認して削除**ダイアログ ボックスで、をクリックして**はい**です。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: メッセージを変換し、スケジュール ルーティング スリップを利用してファイルの場所に送信する](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [方法: スケジュール ルーティング スリップを利用し、1 つのメッセージを複数の受信者に送信する](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ変換パターン](../esb-toolkit/message-transformation-patterns.md)