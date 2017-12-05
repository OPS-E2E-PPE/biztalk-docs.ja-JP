---
title: "方法: インターチェンジを分割し、個別の日程を使用して複数のファイルの場所に結果のメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 538432f548b1403fd9c0cd566b82eb8cb113f737
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a>方法: インターチェンジを分割し、結果として得られるメッセージをルーティング、個別の日程を使用して複数のファイルの場所
## <a name="goal"></a>[目標]  
 このセクションでは、ESB 入り口を使用するを作成する方法を示します、 **ItinerarySelectReceiveXml**の明細のパイプラインと受信インターチェンジを分割し、適切なルーティングを選択するパイプラインのコンポーネントを構成する方法各結果のメッセージ、メッセージ コンテキストに基づきます。 Itinerary 選択は、ビジネス ルール ポリシーを使用して解決して、顧客が存在する地域に基づいて、異なる方法でメッセージをルーティングします。  
  
 このトピックでは、次の手順を行います。  
  
-   ESB 入り口、XML インターチェンジを分割するを作成します。  
  
-   ビジネス ルール ポリシーを使用して、適切な旅程を選択、行程セレクター パイプライン コンポーネントを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
## <a name="before-you-begin"></a>はじめに  
 このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。  
  
-   必要なアイテムを作成します。  
  
-   Schemas プロジェクトをパターンのソリューションに追加します。  
  
-   成果物をスキーマ プロジェクトに追加します。  
  
-   カスタム メッセージ プロパティを使用して、日程を選択する BRE ポリシーを作成します。  
  
-   顧客 GlobalBank 西部の選択ルールを追加します。  
  
-   GlobalBank 東部の顧客の選択ルールを追加します。  
  
-   発行し、ポリシーを展開します。  
  
-   GlobalBank 西部メッセージの ESB itinerary ドメイン固有言語 (DSL) モデルを作成します。  
  
-   GlobalBank 西部旅行計画のプロパティを構成します。  
  
-   GlobalBank 西部行程の構造を定義します。  
  
-   行程データベース GlobalBank 西部モデルにエクスポートします。  
  
-   GlobalBank 東部メッセージの ESB itinerary DSL モデルを作成します。  
  
-   GlobalBank 東部旅行計画のプロパティを構成します。  
  
-   GlobalBank 東部行程の構造を定義します。  
  
-   行程データベース GlobalBank 東部モデルにエクスポートします。  
  
     次の手順では、これらの各を行う方法について説明します。  
  
#### <a name="to-create-the-required-artifacts"></a>必要なアイテムを作成するには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  OrderDocEnvelope.xsd をという名前の新しいテキスト ドキュメントを作成します。  
  
3.  OrderDocEnvelope.xsd スキーマをメモ帳で開きます。  
  
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
  
5.  Utf-8 として OrderDocEnvelope.xsd を保存し、メモ帳を閉じます。  
  
6.  C:\HowTos フォルダーでは、Batch.xml をという名前の新しいテキスト ドキュメントを作成します。  
  
7.  メモ帳で、Batch.xml を開きます。  
  
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
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a>Schemas プロジェクト ソリューションを追加する、パターン  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリック**ソリューション 'パターン'**、 をポイント**追加**、クリックして**新しいプロジェクト**です。  
  
3.  **新しいプロジェクトの追加**ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**BizTalk プロジェクト**、し、次の操作を行います。  
  
    1.  テンプレート ウィンドウで **空の BizTalk Server プロジェクト**です。  
  
    2.  **名前**ボックスに、入力**Patterns.Schemas**、順にクリック**OK**です。  
  
4.  ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、クリックして**プロパティ**です。  
  
5.  プロパティ ウィンドウでの**署名** タブで、**アセンブリに署名** チェック ボックスです。  
  
6.  **厳密な名前キー ファイルを選択して**ドロップダウン リストをクリックして**\<新規しています.\>**.  
  
7.  **厳密な名前キーの作成** ダイアログ ボックスで、次のプロパティを構成します。  
  
    1.  **キー ファイル名**ボックスに、入力**分割**です。  
  
    2.  クリア、**キーファイルをパスワードで保護する**チェック ボックスをクリックして**OK**です。  
  
8.  プロパティ ウィンドウで 、**展開** タブの 、**アプリケーション名**ボックスに、入力**Microsoft.Practices.ESB**です。  
  
9. [プロパティ] ウィンドウを閉じます。  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a>スキーマ プロジェクトにアイテムを追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、クリックして**参照の追加**です。  
  
2.  **参照**のタブ、**参照の追加** ダイアログ ボックスを参照して選択 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB です。クリックして、DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll **OK**です。  
  
3.  ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、 をポイント**追加**、クリックして**既存項目の**します。  
  
4.  **既存項目の追加**ダイアログ ボックスで、[参照] を C:\HowTos\OrderDocEnvelope.xsd を選択し、をクリックし、**追加**です。  
  
5.  すべてのソリューションの成果物を保存します。  
  
6.  ソリューション エクスプ ローラーで右クリック**Patterns.Schemas**、クリックして**展開**です。  
  
    > [!NOTE]
    >  この操作方法に関するトピックでは、同じビジネス ルール ポリシーと旅程で作成された、[する方法: ビジネス ルール ポリシーを使用して、日程を選択して](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)トピックです。 そのセクションを既に完了がいない場合は、次の手順を完了してください。 そのセクションを完了している場合は、「手順セクションに直接進みます。  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>カスタム メッセージ プロパティを使用して、日程を選択するビジネス ルール エンジン (BRE) ポリシーを作成するには  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**ビジネス ルール作成ツール**です。  
  
2.  ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。 ポリシーに名前**ResolveItineraryBasedOnCustomer**です。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>GlobalBank 西部の顧客の選択ルールを追加するには  
  
1.  **ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。 ルールの名前として**SetGlobalBankWestItinerary**です。  
  
2.  ファクト エクスプ ローラーで、をクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、クリックして**参照**です。  
  
3.  **スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas、NAOrderDoc.xsd を選択し、クリックして**開く**です。  
  
    > [!NOTE]
    >  これは、テストに使用する左右のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。  
  
4.  ファクト エクスプ ローラーで、NAOrderDoc.xsd をクリックし、**ドキュメントの種類**のプロパティ ウィンドウと 入力プロパティ**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**です。  
  
    > [!NOTE]
    >  これは、スキーマの完全修飾名です。  
  
5.  ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**の順に展開および**OrderDoc**です。  
  
6.  ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。  
  
7.  ファクト エクスプ ローラーからドラッグして、 **customerName**要素を**argument1**ノードの下**条件**です。  
  
8.  をクリックして、 **argument2**ノード、および入力**GlobalBankWest**です。  
  
9. ファクト エクスプ ローラーで、をクリックして、**ボキャブラリ**タブです。展開して、 **ESB です。行程**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**行程名の設定**定義**アクション**です。  
  
10. をクリックして**\<空の文字列\>**し入力**GlobalBankWestItinerary**です。  
  
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
  
8.  をクリックして**\<空の文字列\>**し入力**GlobalBankEastItinerary です。**  
  
    > [!NOTE]
    >  このトピックの後半 GlobalBank 東部からメッセージを処理するこの日程を作成します。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>発行して、ポリシーを展開するには  
  
1.  ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 (未保存)**、順にクリック**発行**です。  
  
2.  ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシー、をクリックして**バージョン 1.0 - 公開済み**、順にクリック**展開**です。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a>GlobalBank 西部メッセージの ESB itinerary DSL モデルを作成するには  
  
1.  **Visual Studio**C:\HowTos\Patterns\Patterns.sln を開きます。  
  
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
    >  この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージが受信したときに、このリポジトリからアタッチされます。 後で、BRI 競合回避モジュールを使用して受信メッセージを評価し、このリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a>GlobalBank 西部行程の構造を定義するには  
  
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
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a>行程データベースに GlobalBank 西部モデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>GlobalBank 東部メッセージの ESB itinerary DSL モデルを作成するには  
  
1.  **Visual Studio**C:\HowTos\Patterns.sln を開きます。  
  
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
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a>GlobalBank 東部行程の構造を定義するには  
  
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
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a>行程データベースに GlobalBank 東部モデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>作成し、ESB 入り口を構成します。  
  
1.  をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**Microsoft.Practices.ESB**です。  
  
3.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
4.  **受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、クリックして**[ok]**です。  
  
5.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**OnRamp.Itinerary.HowTo**です。  
  
6.  **型**ドロップダウン リストをクリックして**ファイル、**順にクリック**構成**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、入力**C:\HowTos\DropFolder**、クリックして**ok**です。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>行程セレクター パイプライン コンポーネントを構成するには  
  
1.  **受信場所のプロパティ**ダイアログ ボックスで、 をクリックして**ItinerarySelectReceiveXml**で、**受信パイプライン**ドロップダウン ボックスの一覧し、省略記号ボタン (...) をクリックします。  
  
2.  使用して、**パイプラインの構成**、次を構成するダイアログ ボックス**行程セレクター**コンポーネントのプロパティ。  
  
    1.  クリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**です。  
  
    2.  クリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true です。**  
  
    3.  をクリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。  
  
        > [!NOTE]
        >  この受信場所が、XML インターチェンジを逆アセンブル、XML 逆アセンブラー コンポーネントの構成は必要ありません。  
  
3.  をクリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
4.  BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**です。  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>行程セレクターとビジネス ルールをテストするには  
  
1.  Windows エクスプローラで、C:\HowTos を参照します。  
  
2.  コピー (移動しないでください) Batch.xml DropFolder フォルダーにします。  
  
3.  C:\HowTos\Out を参照します。1 つの West%MessageID%.xml メッセージと 2 つの East%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。  
  
    > [!NOTE]
    >  メッセージが顧客の要素の値を除いて同一、行程セレクター パイプライン コンポーネントの解像度に基づいて、別の日程を使用して処理されました。  
  
4.  BizTalk Server 管理コンソールで、受信場所を右クリック、OnRamp.Itinerary.HowTo と無効をクリックします。  
  
5.  後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、をクリックして**削除**です。 **受信場所のことを確認して削除**ダイアログ ボックスで、をクリックして**はい**です。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [方法: ビジネス ルール ポリシーを使用して、日程を選択](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的解決サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [メッセージ ルーティング パターン](../esb-toolkit/message-routing-patterns.md)