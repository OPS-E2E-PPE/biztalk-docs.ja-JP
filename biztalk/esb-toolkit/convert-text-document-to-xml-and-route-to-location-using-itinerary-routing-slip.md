---
title: '方法: XML や、スケジュール ルーティング スリップを使用してファイルの場所へのルートに、テキスト ドキュメントを変換 |Microsoft Docs'
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
ms.openlocfilehash: 27e6690af0cd326853fc0f96254aaaf7083ccd15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982571"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a>方法: テキスト ドキュメントを XML と、スケジュール ルーティング スリップを使用してファイルの場所へのルートに変換
## <a name="goal"></a>[目標]  
 セクションでは、テキスト ドキュメントを XML に変換し、適切な旅行プランを選択し、ファイルの場所にメッセージをルーティングするパイプラインを作成する方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   パイプラインを使用して、フラット ファイル ドキュメントを受信し、XML に変換します。  
  
-   適切なルーティング スリップを解決するのには、スケジュール セレクターのパイプライン コンポーネントを構成します。  
  
-   入り口カスタム パイプラインを使用するを作成します。  
  
-   スケジュールに基づくフラット ファイル メッセージのルーティングをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="before-you-begin"></a>はじめに  
 この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。  
  
- 展開、 **DataFormatTransformation**スケジュールします。  
  
- テスト メッセージを作成します。  
  
  次の手順では、これらの各方法について説明します。  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a>DataFormatTransformation 旅行プランをデプロイするには  
  
1.  Visual Studio で、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで、 **Itinerary.Library**プロジェクトをダブルクリックします**DataFormatTransformation.itinerary**旅行プラン デザイナーで開きます。  
  
3.  Visual Studio でのデザイン画面をクリックします。 **DataFormatTransformation.itinerary**します。 **DataFormatTransformation.itinerary**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。  
  
    2.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。  
  
    3.  横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。  
  
    4.  **接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。  
  
4.  すべてのプロジェクト成果物を保存します。  
  
5.  Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**旅行プランをクリックして**モデルのエクスポート**します。  
  
#### <a name="to-create-the-receive-pipeline"></a>受信パイプラインを作成するには  
  
1.  Visual Studio で、右クリックして**DataFormatTransformation.Schemas**、 をクリックし、**プロパティ**します。 クリックして**アプリケーション**、し、入力**GlobalBank.ESB.DataFormatTransformation.Schemas**で、**アセンブリ名**ボックス。  
  
2.  右クリックして**DataFormatTransformation.Schemas**、 をクリックし、**プロパティ**します。 クリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す **.\\.\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**します。  
  
3.  右クリック**DataFormatTransformation.Pipelines**、 をクリックし、**削除**します。  
  
4.  右クリック**DataFormatTransformation**、 をポイント**追加**、 をクリックし、**新しいプロジェクト**します。 クリックして**Biztalk プロジェクト**、 をクリックし、**空の Biztalk Server プロジェクト**します。 **名前**ボックスに「 **DataFormatTransformationReceive.Pipeline**します。  
  
5.  右クリックして**DataFormatTransformationReceive.Pipeline**、 をクリックし、**プロパティ**します。 クリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**します。  
  
6.  右クリック**DataFormatTransformationReceive.Pipeline**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
7.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**受信パイプライン**テンプレート ペインでします。 **名前**ボックスに「 **ItinerarySelectReceiveFF**、 をクリックし、**追加**します。  
  
8.  右クリックして**参照**DataFormatTransformationReceive.Pipeline プロジェクト、およびクリック**参照の追加**します。 をクリックして、**プロジェクト**タブをクリックし、をクリックし、 **DataFormatTransformation.Schemas**します。 クリックして**OK**参照を追加します。  
  
9. ツールボックスからドラッグして、**フラット ファイル逆アセンブラー**パイプライン コンポーネントを**逆アセンブル**パイプラインのステージ。  
  
10. 逆アセンブル、フラット ファイルのプロパティ ウィンドウで、をクリックして**DataModelTransformation.Schemas.NAOrderDocFF**で、**ドキュメント スキーマ**ドロップダウン リスト。  
  
11. ツールボックスからドラッグして、 **ESB スケジュール セレクター**パイプライン コンポーネントを**パーティの解決**パイプラインのステージ。  
  
12. ツールボックスからドラッグ、 **ESB ディスパッチャー**パイプライン コンポーネントを**パーティの解決**、パイプラインのステージと、下に配置し、 **ESB スケジュール セレクター**パイプラインコンポーネント。  
  
13. すべてのプロジェクト成果物を保存します。  
  
## <a name="to-create-the-test-message"></a>テスト メッセージを作成するには  
  
1.  DataFormatTransformation.Schemas プロジェクトの NAOrderDocFF.xsd スキーマ ファイルで 1 回クリックします。 Visual Studio の [プロパティ] ペインでは、次の 2 つのプロパティを変更します。  
  
    -   **インスタンスの出力の種類の生成**します。 ドロップダウン リストに変更するには、このプロパティをクリックして**ネイティブ**します。  
  
    -   **出力インスタンス ファイル名**します。 このプロパティの省略記号ボタン (…) をクリックし、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation の既定のパスをそのまま使用します。 **ファイル名**ボックスに「 **NAOrderDocFF**、 をクリックし、**保存**します。  
  
2.  右クリック**NAOrderDocFF.xsd** [ **DataFormatTransformation.Schemas**、] をクリックし、**インスタンスの生成**します。 この時点では、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation ディレクトリに生成された新しいファイルが必要です。  
  
3.  コピー (移動しないでください) に C:\HowTos C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation から NAOrderDocFF.txt ファイル。  
  
    > [!NOTE]
    >  これは、メッセージはメッセージを受信して XML に変換します。 このドキュメントでは、North American 注文ドキュメントのフラット ファイルのバージョンを表します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a>受信パイプラインとスキーマを展開するには  
  
1.  右クリックして**DataFormatTransformationReceive.Pipeline**、 をクリックし、**プロパティ**します。 クリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。  
  
2.  右クリックし、 **DataFormatTransformation.Schemas**プロジェクトをクリックして**プロパティ**します。 クリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。  
  
3.  両方のプロパティ ウィンドウを閉じる**DataFormatTransformationReceive.Pipeline**と**DataFormatTransformation.Schemas**します。  
  
4.  ソリューション エクスプ ローラーで右クリックし、 **DataFormatTransformation**プロジェクトをクリックして**ソリューションの配置**します。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成および ESB 入り口を構成するには  
  
1.  クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。  
  
2.  BizTalk Server 管理コンソールで [ **BizTalk グループ**、展開**アプリケーション**、] をクリックし、 **Microsoft.Practices.ESB**します。  
  
3.  右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OnRamp.Itinerary.FlatFile.FILE**します。  
  
6.  **型**ドロップダウン リストでは、をクリックして**ファイル**、順にクリックします**構成**します。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに「 **C:\HowTos\DropFolder**します。  
  
8.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**ファイル マスク**ボックスに「  **\*.txt**順にクリックします**OK**します。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>旅行プラン セレクターのパイプライン コンポーネントを構成するには  
  
1.  **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**ItinerarySelectReceiveFF**で、**受信パイプライン**ドロップダウン リストで、省略記号ボタン (…) をクリックします。  
  
2.  使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**スケジュール セレクター**コンポーネントのプロパティ。  
  
    1.  をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。  
  
    2.  をクリックして、 **ResolverConnectionString**プロパティに、入力**行程:\\\name=DataFormatTransformation;** 順にクリックします**OK**。  
  
3.  クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
4.  右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を有効にする**します。  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a>スケジュールに基づくフラット ファイル メッセージのルーティングをテストするには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください) NAOrderDocFF.txt C:\HowTos\DropFolder にします。  
  
3.  C:\HowTos\Out に移動します。DFT%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
4.  右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を無効にする**します。  
  
5.  後に、 **OnRamp.Itinerary.FlatFile.FILE**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。 **削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: メッセージを変換し、スケジュール ルーティング スリップを利用してファイルの場所に送信する](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [方法: スケジュール ルーティング スリップを利用し、1 つのメッセージを複数の受信者に送信する](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージ変換パターン](../esb-toolkit/message-transformation-patterns.md)