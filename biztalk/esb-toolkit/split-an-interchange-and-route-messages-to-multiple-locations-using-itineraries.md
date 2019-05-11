---
title: 操作方法:インターチェンジを分割し、個別のスケジュールを使用して複数のファイルの場所に作成されるメッセージをルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36287f22290f30b687e90e9a111a3ae79aa53d5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268905"
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a>操作方法:インターチェンジを分割し、個別のスケジュールを使用して複数のファイルの場所に作成されるメッセージをルーティング
## <a name="goal"></a>[目標]  
 このセクションでは、ESB 入り口を使用するを作成する方法を示します、 **ItinerarySelectReceiveXml**の明細のパイプラインと受信インターチェンジを分割し、適切なルーティングを選択するパイプラインのコンポーネントを構成する方法メッセージごとに結果として得られる、メッセージ コンテキストに基づきます。 スケジュールの選択は、ビジネス ルール ポリシーを使用して解決して、顧客が存在するリージョンに基づいて異なる方法でメッセージをルーティングします。  
  
 このトピックでは、次の手順を行います。  
  
-   ESB 入り口 XML インターチェンジを分割するを作成します。  
  
-   ビジネス ルール ポリシーを使用して、適切なスケジュールを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
## <a name="before-you-begin"></a>はじめに  
 この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。  
  
-   必要なアーティファクトを作成します。  
  
-   パターンのソリューションをスキーマ プロジェクトを追加します。  
  
-   成果物をスキーマ プロジェクトに追加します。  
  
-   カスタム メッセージ プロパティを使用するスケジュールを選択する BRE ポリシーを作成します。  
  
-   GlobalBank 西部の顧客の選択規則を追加します。  
  
-   GlobalBank 東部の顧客の選択規則を追加します。  
  
-   発行し、ポリシーを展開します。  
  
-   GlobalBank 西部メッセージの ESB オンランプ ドメイン固有言語 (DSL) モデルを作成します。  
  
-   GlobalBank 西部スケジュールのプロパティを構成します。  
  
-   GlobalBank 西部旅行プランの構造を定義します。  
  
-   行程データベースを GlobalBank 西部モデルをエクスポートします。  
  
-   GlobalBank 東部メッセージの ESB 行程 DSL モデルを作成します。  
  
-   GlobalBank 東部スケジュールのプロパティを構成します。  
  
-   GlobalBank 東部旅行プランの構造を定義します。  
  
-   行程データベースを GlobalBank 東部モデルをエクスポートします。  
  
     次の手順では、これらの各方法について説明します。  
  
#### <a name="to-create-the-required-artifacts"></a>必要なアーティファクトを作成するには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  OrderDocEnvelope.xsd という名前の新しいテキスト ドキュメントを作成します。  
  
3.  OrderDocEnvelope.xsd スキーマは、メモ帳で開きます。  
  
4.  次のコードを使用してドキュメントを編集します。  
  
    ```  
    <?xml version="1.0" ?>  
    <xs:schema xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://ESB.BizUnit.Map.Test" targetNamespace="http://ESB.BizUnit.Map.Test" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
      <xs:import schemaLocation="GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc" namespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
      <xs:annotation>  
        <xs:appinfo>  
          <b:schemaInfo is_envelope="yes" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
          <b:references>  
            <b:reference targetNamespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
          </b:references>  
        </xs:appinfo>  
      </xs:annotation>  
      <xs:element name="OrderEnvelope">  
        <xs:annotation>  
          <xs:appinfo>  
            <b:recordInfo body_xpath="/*[local-name()='OrderEnvelope' and namespace-uri()='http://ESB.BizUnit.Map.Test']" />  
          </xs:appinfo>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element ref="ns0:OrderDoc" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
5.  OrderDocEnvelope.xsd を utf-8 として保存し、メモ帳を終了します。  
  
6.  C:\HowTos フォルダーでは、Batch.xml という名前の新しいテキスト ドキュメントを作成します。  
  
7.  メモ帳で Batch.xml を開きます。  
  
8.  次のコードを使用してドキュメントを編集します。  
  
    ```  
    <?xml version="1.0" ?>  
    <ns0:OrderEnvelope xmlns:ns0="http://ESB.BizUnit.Map.Test">  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankWest</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>10</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>11</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>12</ns0:requestType>  
      </ns0:OrderDoc>  
    </ns0:OrderEnvelope>  
    ```  
  
9. 保存して Batch.xml を閉じます。  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a>パターンのソリューションにスキーマ プロジェクトを追加するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリック**ソリューション 'パターン'**、 をポイント**追加**、 をクリックし、**新しいプロジェクト**します。  
  
3.  **新しいプロジェクトの追加** ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**BizTalk プロジェクト**、し、次の操作を行います。  
  
    1.  [テンプレート] ペインで次のようにクリックします。**空の BizTalk Server プロジェクト**します。  
  
    2.  **名前**ボックスに「 **Patterns.Schemas**、順にクリックします**OK**します。  
  
4.  ソリューション エクスプ ローラーで右クリックして**Patterns.Schemas**、 をクリックし、**プロパティ**します。  
  
5.  [プロパティ] ウィンドウで、**署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。  
  
6.  **厳密な名前キー ファイルを選択して**ドロップダウン リストでは、をクリックして**\<新規.\>**.  
  
7.  **厳密な名前キーの作成** ダイアログ ボックスで、次のプロパティを構成します。  
  
    1.  **キー ファイル名**ボックスに「**分割**します。  
  
    2.  クリア、**キーファイルをパスワードで保護する**チェック ボックスをオンにし**OK**。  
  
8.  プロパティ ウィンドウでの**展開** タブで、**アプリケーション名**ボックスに「 **Microsoft.Practices.ESB**。  
  
9. [プロパティ] ウィンドウを閉じます。  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a>スキーマ プロジェクトにアイテムを追加するには  
  
1.  ソリューション エクスプ ローラーで右クリックして**Patterns.Schemas**、 をクリックし、**参照の追加**します。  
  
2.  **参照**のタブ、**参照の追加**ダイアログ ボックスで 参照 と C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB します。クリックして、DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll **OK**します。  
  
3.  ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、 をポイント**追加**、 をクリックし、**既存項目の**します。  
  
4.  **既存項目の追加**C:\HowTos\OrderDocEnvelope.xsd を選択しをクリックし、[参照] ダイアログ ボックスで、**追加**します。  
  
5.  すべてのソリューションの成果物を保存します。  
  
6.  ソリューション エクスプ ローラーで右クリックして**Patterns.Schemas**、 をクリックし、**デプロイ**します。  
  
    > [!NOTE]
    >  このトピックで作成されたものと同じビジネス ルール ポリシーとスケジュールを使用して、[方法。ビジネス ルール ポリシーを使用するスケジュールを選択します。](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)トピック。 そのセクションを既に完了しなかった場合は、次の手順を完了してください。 そのセクションを完了すると場合、は、「手順」セクションに直接進みます。  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>カスタム メッセージ プロパティを使用するスケジュールを選択するビジネス ルール エンジン (BRE) ポリシーを作成するには  
  
1.  クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**ビジネス ルール作成ツール**します。  
  
2.  ポリシー エクスプ ローラーで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。 ポリシーの名前**ResolveItineraryBasedOnCustomer**します。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>GlobalBank 西部の顧客の選択規則を追加するには  
  
1.  **ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリックします**新しいルールの追加**します。 ルールの名前として**SetGlobalBankWestItinerary**します。  
  
2.  ファクト エクスプ ローラーでクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、順にクリックします**参照**します。  
  
3.  **スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas が NAOrderDoc.xsd を選択し、クリックして**オープン**します。  
  
    > [!NOTE]
    >  テストに使用する西部と東部のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。  
  
4.  ファクト エクスプ ローラーで NAOrderDoc.xsd をクリックして、**ドキュメントの種類**プロパティのプロパティ ウィンドウと入力し、 **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**します。  
  
    > [!NOTE]
    >  これは、スキーマの完全修飾名です。  
  
5.  ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**、順に展開**OrderDoc**します。  
  
6.  ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、 をクリックし、**等しい**。  
  
7.  ファクト エクスプ ローラーからドラッグして、 **customerName**要素を **[引数 1]** ノードの下**条件**します。  
  
8.  をクリックして、 **[引数 2]** ノード、および入力**GlobalBankWest**します。  
  
9. ファクト エクスプ ローラーでクリックして、**ボキャブラリ**タブ。展開、 **ESB します。旅行プラン**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**旅行プラン名の設定**の定義を**アクション**します。  
  
10. クリックして**\<空の文字列\>** し入力**GlobalBankWestItinerary**します。  
  
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
  
8.  クリックして**\<空の文字列\>** し入力**GlobalBankEastItinerary します。**  
  
    > [!NOTE]
    >  このトピックの後半では、GlobalBank 東部からメッセージを処理するこの旅行プランが作成されます。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>発行して、ポリシーをデプロイするには  
  
1.  ポリシー エクスプ ローラーで 、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 (未保存)**、順にクリックします**発行**します。  
  
2.  ポリシー エクスプ ローラーで 、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 - 公開済み**、順にクリックします**デプロイ**します。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a>GlobalBank 西部メッセージの ESB 行程 DSL モデルを作成するには  
  
1.  **Visual Studio**C:\HowTos\Patterns\Patterns.sln を開きます。  
  
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
    >  この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージが受信したときに、このリポジトリからアタッチします。 後で BRI 競合回避モジュールを使用して、受信メッセージを評価し、このリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a>GlobalBank 西部旅行プランの構造を定義するには  
  
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
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a>GlobalBank 西部モデル行程データベースをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>GlobalBank 東部メッセージの ESB 行程 DSL モデルを作成するには  
  
1.  **Visual Studio**C:\HowTos\Patterns.sln を開きます。  
  
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
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a>GlobalBank 東部旅行プランの構造を定義するには  
  
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
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a>GlobalBank 東部モデル行程データベースをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成および ESB 入り口を構成するには  
  
1.  クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、順に展開**Microsoft.Practices.ESB**します。  
  
3.  右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OnRamp.Itinerary.HowTo**します。  
  
6.  **型**ドロップダウン リストでは、をクリックして**ファイル、** 順にクリックします**構成**します。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに「 **C:\HowTos\DropFolder**、順にクリックします**OK**します。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>旅行プラン セレクターのパイプライン コンポーネントを構成するには  
  
1.  **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**ItinerarySelectReceiveXml**で、**受信パイプライン**ドロップダウン ボックスの一覧し、省略記号ボタン (…) をクリックします。  
  
2.  使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**スケジュール セレクター**コンポーネントのプロパティ。  
  
    1.  をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。  
  
    2.  をクリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  クリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。  
  
        > [!NOTE]
        >  この受信場所が、XML インターチェンジを逆アセンブル、XML 逆アセンブラー コンポーネントの構成は必要ありません。  
  
3.  クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
4.  右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**します。  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>旅行プラン セレクターとビジネス ルールをテストするには  
  
1.  Windows エクスプ ローラーでは、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください) Batch.xml DropFolder フォルダーにします。  
  
3.  C:\HowTos\Out に移動します。1 つの West%MessageID%.xml メッセージと East%MessageID%.xml の 2 つのメッセージがディレクトリに書き込まれたことを確認します。  
  
    > [!NOTE]
    >  メッセージは customer 要素の値を除いて同一ですが、異なる日程表、日程セレクターのパイプライン コンポーネントの解像度に基づくを使用して処理されました。  
  
4.  BizTalk Server 管理コンソールで受信場所を右クリックして、OnRamp.Itinerary.HowTo と無効をクリックします。  
  
5.  後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。 **削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用するスケジュールを選択します。](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的解決サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)