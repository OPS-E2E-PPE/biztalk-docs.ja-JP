---
title: "方法: メッセージ コンテキスト プロパティを使用してコンテンツ ベース ルーティングの実装 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e47235978960ac89f4ea276c4c4a60c8ddf16e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a>方法: メッセージ コンテキスト プロパティを使用してコンテンツ ベース ルーティングの実装
## <a name="goal"></a>[目標]  
 このセクションでは、使用する方法を示します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程デザイナーは、メッセージ コンテキスト プロパティに基づいてメッセージの受信者を選択し、メッセージング サービス行程ブローカーを使用してその受信者にメッセージをルーティングする旅程を作成します。  
  
 このトピックでは、次の手順を行います。  
  
-   Itinerary ブローカーと静的な競合回避モジュールで次の 2 つのルーティング サービスでは、日程を作成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
> [!NOTE]
>  現在の実装では、オーケストレーションに基づくブローカー サービスは用意されていません。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>ESB 行程 DSL モデルを作成するには  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。  
  
4.  **名前**ボックスに、入力**ChoiceRouter**、クリックして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして、 **ChoiceRouter**行程です。 **ChoiceRouter**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  **Extender 設定**セクションで、横にある省略記号ボタン (...) をクリックして、**行程 XML ファイル**プロパティです。  
  
    3.  **エクスポート モード**プロパティ ボックスの一覧をクリックして**Strict**です。  
  
    4.  **[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\ChoiceRouter**で、**ファイル名**ボックスをクリックして**保存**です。  
  
    > [!NOTE]
    >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB テスト用クライアント アプリケーションを使用して旅程をテストできます。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 OnRamp1 [プロパティ] ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグして、**行程ブローカー サービス**の右側に配置し、デザイナー画面に要素をモデル化し、**入り口**モデル要素。 **ItineraryBrokerService1**、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteBrokerService**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**メッセージング ブローカー Extender**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**です。  
  
3.  右クリックし、**フィルター**コレクション、およびクリック**新しいフィルターの追加**です。 **Filter1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ASMXFilter**です。  
  
    2.  クリックして、**フィルター**クリックしてドロップダウン リストの実装、 **XPath フィルター**です。  
  
    3.  クリックして、**式**プロパティ、および入力**カウント (ContextProperties/プロパティ [@name= 'InboundTransportLocation'] [が含まれています (.、'ProcessItinerary.asmx')]) > 0**します。  
  
4.  右クリックし、**フィルター**コレクション、およびクリック**新しいフィルターの追加**です。 **Filter1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**WCFFilter**です。  
  
    2.  クリックして、**フィルター実装**ドロップダウン リストをクリック**XPath フィルター**です。  
  
    3.  クリックして、**式**プロパティ、および入力**カウント (ContextProperties/プロパティ [@name= 'InboundTransportLocation'] [が含まれています (.、' ESB です。ItineraryServices.WCF')]) > 0**します。  
  
5.  右クリックし、**リゾルバー**のコレクション、 **RouteBrokerService**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ResolverBrokerRoute**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**MessageContext 競合回避モジュールの拡張機能**します。  
  
6.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteBrokerService**モデル要素。  
  
7.  ツールボックスからドラッグして、**行程サービス**の下に配置し、デザイン画面に要素をモデル化し、 **RouteBrokerService**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteToFileFromASMX**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
        > [!NOTE]
        >  このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。 または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。  
  
8.  右クリックし、**リゾルバー**のコレクション、 **RouteToFileFromASMX**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ResolverFromAsmx**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**c:\howtos\out\asmx%MessageId%.xml**です。  
  
9. ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteToFileFromASMX**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendASMXOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
10. ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteToFileFromASMX**モデル要素と**SendASMXOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilterASMX**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendASMXOrder**、クリックして**送信ハンドラー**です。  
  
11. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **RouteToFileFromASMX**モデル要素を**SendPortFilterASMX**モデル要素。  
  
12. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilterASMX**モデル要素を**SendASMXOrder**モデル要素。  
  
13. ツールボックスからドラッグして、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、 **RouteBrokerService**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteToFileFromWCF**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
        > [!NOTE]
        >  このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。 または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。  
  
14. 右クリックし、**リゾルバー**のコレクション、 **RouteToFileFromWCF**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ResolverFromWCF**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**ファイル**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**c:\howtos\out\wcf%MessageId%.xml**です。  
  
15. ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteToFileFromWCF**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendWCFOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
16. ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteToFileFromWCF**モデル要素と**SendWCFOrder**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilterWCF**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**SendWCFOrder**、クリックして**送信ハンドラー**です。  
  
17. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **RouteToFileFromWCF**モデル要素を**SendPortFilterWCF**モデル要素。  
  
18. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilterWCF**モデル要素を**SendWCFOrder**モデル要素。  
  
19. ツールボックスからドラッグして、**行程 Outport**モデル要素の右側の境界線を**RouteBrokerService**です。 **ItineraryBrokerOutPort1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**WCF ポート**です。  
  
    2.  **フィルター**ドロップダウン リストをクリックして**WCFFilter**です。  
  
    3.  **リゾルバー**ドロップダウン リストをクリックして**ResolverBrokerRoute**です。  
  
20. ツールボックスからドラッグして、**行程 Outport**モデル要素の下枠に**RouteBrokerService**です。 **ItineraryBrokerOutPort1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ASMX ポート**です。  
  
    2.  **フィルター**ドロップダウン リストをクリックして**ASMXFilter**です。  
  
    3.  **リゾルバー**ドロップダウン リストをクリックして**ResolverBrokerRoute**です。  
  
21. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **WCF ポート**モデル要素を**RouteToFileFromWCF**モデル要素。  
  
22. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ASMX ポート**モデル要素を**RouteToFileFromASMX**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
> [!NOTE]
>  2 回、日程をエクスポートする必要があります: ブローカー経由のルーティングをテストするデータベースに 1 回は XML で、いずれかの時刻します。  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  Windows エクスプ ローラーで、C:\HowTos\Itineraries を参照し、旅程 XML (ChoiceRouter.xml) の作成を確認します。  
  
3.  Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**行程をクリックして**モデルのエクスポート**です。  
  
4.  [プロパティ] ウィンドウでをクリックして**データベース行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。  
  
5.  [プロパティ] ウィンドウで、設定、**行程データベース**行程データベースを指す接続文字列のプロパティです。  
  
6.  **行程ステータス**プロパティのドロップダウン リストを選択**配置済み**です。  
  
7.  Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**行程をクリックして**モデルのエクスポート**です。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**ChoiceRouter.xml**、順にクリック**開く**日程を読み込めません。  
  
4.  をクリックして**OK** 「行程正しく読み込まれました」メッセージを閉じます。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\Patterns\HowTos を参照します。 NAOrderDoc.xml を選択し、クリックして**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを閉じます。  
  
8.  Windows エクスプローラで、C:\HowTos\Out を参照します。ASMX%MessageID%.xml メッセージがこのディレクトリに書き込まれたことを確認します。  
  
9. 行程テスト クライアント をクリックして**を使用して WCF サービス**チェック ボックスをオンします。 **行程名前**ボックスに、入力**ChoiceRouter**、をクリックし、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**確認メッセージを閉じます。  
  
10. Windows エクスプローラで、C:\HowTos\Out を参照します。WCF%MessageID%.xml メッセージがこのディレクトリに書き込まれたことを確認します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [方法: 動的にビジネス ルール ポリシーを使用して、メッセージ コンテキストに基づいたメッセージをルーティング](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [メッセージのルーティング パターン](../esb-toolkit/message-routing-patterns.md)