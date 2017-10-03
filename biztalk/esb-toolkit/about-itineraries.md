---
title: "行程に関する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d34632f-8652-49dd-97b7-2513aacc1bd7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9a759a6afdd55c3c1646d02c480aa193261aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-itineraries"></a>行程について
日程、ESB 仲介ポリシー処理に基づいて命令のシーケンスを実行するための表現である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]拡張可能な形式です。 日程が宣言型の itinerary サービスの構成で仲介コンポーネントに関連付けられているのシーケンスを記述する高度な仲介言語として見なすことができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンです。 メッセージの処理方法を説明する仲介フローをデザインすることができ、ビジュアルの描画として全体の流れを整理することができます。 実行時に、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンは、行程デザイナーによって生成される旅程を実行します。  
  
## <a name="the-itinerary-designer-surface"></a>Itinerary デザイナー画面  
 行程デザイナー画面の作成に使用される、ビジュアル デザイナーは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]旅程日程を実行時の形式にエクスポートするとします。 これは、図 1 に示すように、ツールボックスの項目をドラッグする先のキャンバスです。  
  
 ![Itinerary Designer](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5 ItineraryDesigner")  
  
 **図 1**  
  
 **Itinerary Designer 画面**  
  
 旅行計画の名前は、Microsoft Visual Studio タイトル バーと旅程デザイナーの上部のタブに表示されます。 デザイン画面は 1 つの領域で、旅行計画の実際のメッセージ フローを記述するモデル要素を含んでいます。 ItineraryDSL では、Visual Studio プロパティ ウィンドウを使用してモデル要素のプロパティを変更することができます。  
  
## <a name="itinerary-designer-toolbox"></a>Itinerary デザイナー ツールボックス  
 Visual Studio ツールボックスには、ツールのセットを表すのタブが含まれています。 ツールボックスには行程デザイナーを使用する Visual Studio プロジェクトを開いたときに 2 つのタブが含まれています。**全般** タブおよび**ItineraryDsl**タブです。 **ItineraryDsl**  タブには、次のツールが含まれています。  
  
-   **Itinerary サービス ツール**です。 このモデル要素は itinerary 仲介サービスに対応し、処理命令を表します。  
  
-   **コネクタ ツール**です。 このモデルの要素では、行程デザイナー サーフェイス上の個々 のモデル要素間のリレーションシップを定義します。  
  
-   **出口ツール**です。 このモデル要素は、出口メッセージを送信するに対応します。 行程デザイナーでは、複数オフ-ランプ モデルに 1 を実行します。  
  
-   **入り口ツール**です。 このモデル要素は、入り口メッセージを受信に対応します。 行程デザイナーは、1 つだけに着手モデルに 1 を使用します。  
  
-   **道順の Broker Service ツール**です。 このモデル要素は、複数の入力と複数の出力を使用した定義済みのメッセージ フローを可能にする itinerary 仲介サービスに対応します。  
  
-   **Itinerary Broker 出力ポート**です。 このモデル要素には、行程 Broker サービスの 1 つの出力ポートに対応しています。 行程ブローカー サービスのモデル要素は、複数の出力ポートを使用します。  
  
## <a name="steps-in-itinerary-development"></a>Itinerary 開発手順  
 ESB 仲介のフローを表し、日程を開発するのには、通常、次の操作を実行します。  
  
-   処理手順、日程のメッセージを表すモデル要素を追加します。 行程デザイナーには、さまざまな操作またはキーの抽象化を表すために使用する図形を含むツールボックスが用意されています。  
  
-   Itinerary モデルのプロパティは、Microsoft BizTalk Server 管理データベースとモデルのエクスポーター構成への接続文字列を含めるを指定します。  
  
-   物理 BizTalk へのバインド入り口と出口のモデル要素は、受信場所と、これらのモデル要素に対応するテクノロジのエクステンダーを関連付けることによってポートを送信します。  
  
-   Itinerary サービス モデル要素を関連付けるエクステンダーし、extender に必要なテクノロジに固有のプロパティを定義します。 これらのプロパティでは、特定の種類の extender; が異なる可能性があります。これらは、itinerary 仲介サービスのプロパティとその実行時コンポーネントとの成果物に関連付けられた BizTalk 固有のプロパティを表すことができます。  
  
-   Itinerary 仲介サービスとして参照することができますをカスタム コンポーネントを識別します。 たとえば、itinerary サービスとしてのオーケストレーションを開発する場合があります。  
  
-   に対して競合回避モジュール モデル要素の設定を確認する[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]デザイナー サーフェスからリゾルバー サービスを呼び出すことによって実行時構成します。  
  
-   検証し、エクスポーターを使用して、itinerary 実行時ポリシーをエクスポートします。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程デザイナーで 2 つのエクスポートを提供します。 ファイル エクスポーターとエクスポーターのデータベースです。 また、カスタム エクスポーターを実装することができます。  
  
-   テスト クライアント アプリケーションまたは BizUnit フレームワークを使用して、日程をテストします。  
  
## <a name="security-considerations-for-developing-itineraries"></a>日程を開発するためのセキュリティに関する考慮事項  
 日程を設計するときは、潜在的なセキュリティの問題を考慮してください。  
  
-   モデルのプロパティからの証明書を使用せずにユーザーの資格情報を指定しないでください。  
  
-   BizTalk を参照しない受信ポートと受信の匿名アクセスを許可する場所です。  
  
-   Itinerary メッセージには、機密データが含まれている場合は、メッセージまたはトランスポート チャネルを保護します。  
  
-   メッセージには、転送中に保護する必要がある機密データが含まれている場合は、パイプライン コンポーネントを含むメッセージ ボックス内のメッセージを保護します。