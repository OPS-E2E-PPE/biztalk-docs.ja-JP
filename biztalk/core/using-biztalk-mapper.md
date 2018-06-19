---
title: BizTalk マッパーを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.grid
ms.assetid: 07c69603-ee79-44b2-80b1-6ae4e4c8fb4e
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bf339069f4868aa7c7bff07ae8bdbbb029c5f81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288946"
---
# <a name="using-biztalk-mapper"></a>BizTalk マッパーの使用

## <a name="overview"></a>概要
BizTalk マッパーは [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルに格納されており、 BizTalk マッパーの機能の一部のユーザー インターフェイス要素に依存しています、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]シェルです。 たとえば、使用する、**ファイル**、**編集**、および**ビュー**と同様のメニューが他の開発では[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 この共通の機能に関する情報はから利用可能な**ヘルプ**メニュー。  
  
 既存のマップ (.btm ファイル) を開くときに、BizTalk プロジェクトに新しいマップを追加するとき、またはのメイン タブをクリックして、マップを再アクティブ化するとき、BizTalk マッパーがアクティブになった[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。  
  
> [!NOTE]
>  BizTalk マッパーでは、UTF-16 文字エンコードを使用してマップ ファイルを保存します。  
>
>  ビルド アクションは常に設定するときに、既存のアイテムを BizTalk プロジェクトに追加すると、 **BtsCompile**です。 既定値には、ビルド アクションが設定されている既存のアイテムの名前を変更する場合でも**BtsCompile**です。 したがって、既存のアイテムを追加または名前変更する場合は、その特定のアイテムをビルドするかどうかによって、ビルド アクションを適切に設定する必要があります。  

## <a name="parts-of-the-biztalk-mapper"></a>BizTalk マッパーの部分  
 次の図は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に含まれる BizTalk マッパーのさまざまな部分を示しています。  
  
 ![BizTalk マッパー](../core/media/mapper-views.gif "Mapper_Views")  
  
 各ビューの機能は次のとおりです。  
  
-   **Visual Studio マッパー ユーティリティ リボン** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]マッパーはマッパー関連コマンドを画面に表示するユーティリティ リボンを提供します。 リボンには送信元スキーマ情報、送信元スキーマと送信先スキーマの関連性ビューを切り替えるボタン、完全にスコープ外のリンクの表示と非表示を切り替えるボタン、自動スクロールのオンとオフを切り替えるトグル スイッチ、マッパー画面を左右に移動するボタン、ズームインとズームアウトのコントロール、検索テキスト ボックスが登録されています。 次の図は、グリッド ページの上部に表示されるユーティリティ リボンを示しています。  
  
     ![マッパー リボン](../core/media/mapper-ribbon.gif "Mapper_Ribbon")  
  
-   **送信元スキーマ ツリー ビューです。** : このビューは、送信先スキーマ ツリー ビューおよびグリッド ビューと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウを共有します。  
  
     名前が示すように、このビューには、マッピングの送信元であるインスタンス メッセージを記述するスキーマが表示されます。 マッピングを定義するリンクは、グリッド ビューと、最終的には、送信先スキーマ ツリー ビューに、送信元スキーマ ツリー ビューから潜在顧客です。  
  
     スキーマ ツリー ビューでの BizTalk スキーマの表記方法の詳細については、次を参照してください。[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)です。  
  
-   **送信先スキーマ ツリー ビューです。** : このビューは、送信元スキーマ ツリー ビューおよびグリッド ビューと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウを共有します。  
  
     名前が示すように、このビューには、マッピングの送信先であるインスタンス メッセージを記述するスキーマが表示されます。 マッピングを定義するリンクは、グリッド ビューから送信先スキーマ ツリー ビューに接続されており、送信元スキーマ ツリー ビューが始点となります。  
  
     スキーマ ツリー ビューでの BizTalk スキーマの表記方法の詳細については、次を参照してください。[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)です。  
  
-   **グリッドを表示します。** : 左側の送信元スキーマ ツリー ビューと右側の送信先スキーマ ツリー ビューの間にあるビューです。送信元スキーマ ツリー ビュー、送信先スキーマ ツリー ビュー、およびグリッド ビューは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウを共有します。  
  
     名前が示すように、このビューはマップの定義で重要な役割を果たし、リンクと Functoid が表示されます。リンクと Functoid は、送信元インスタンス メッセージのデータを送信先スキーマに準拠するインスタンス メッセージに変換する方法を制御します。  
  
     グリッド ビューは、グリッド ページと呼ばれる複数の層を持つ場合があります。この層によって、複雑なマップを細分して論理的なマッピングに構成できます。 通常は、グリッド ページは一度に表示できないため、グリッド ページのスクロールを行うための効率的な方法がいくつか用意されています。  
  
     マップを構築するには、このビューをアクティブ状態にして操作します。  
  
-   **Visual Studio ツールボックス ウィンドウ** : このビューには BizTalk マップで使用可能な Functoid が表示され、ここから Functoid をドラッグ アンド ドロップして、グリッド ページに配置できます。  
  
     ツールボックスに表示される Functoid は、カテゴリに応じて分けられています。 使用可能な functoid の詳細については、次を参照してください。[マップの Functoid](../core/functoids-in-maps.md)です。 また、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
-   **Visual Studio の [プロパティ] ウィンドウ。** : このビューおよび関連付けられたダイアログ ボックスを使用して、マップを定義するために作成したリンクおよび Functoid のプロパティの確認と設定を行います。  
  
     グリッド ビューでは、グリッド ページでリンクまたは functoid を選択すると、送信元または送信先スキーマ ツリー ビューでスキーマ ノードを選択またはでマップを選択、**ソリューション エクスプ ローラー** ; 期間は、そのリンク、functoid の対応するプロパティスキーマ ノード、またはマップに表示される、**プロパティ**Visual Studio の標準の規則を使用してウィンドウです。 たとえば、プロパティは、カテゴリごとにグループ化されていたり、カテゴリ順またはアルファベット順に従って表示されたりします。  
  
     リンク、functoid、スキーマ ノードまたはマップ自体に対して使用可能なプロパティの異なるセットの詳細については、次を参照してください、**マップ プロパティの参照**と**スキーマ プロパティのリファレンス**。[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
-   **Visual Studio タスク一覧ウィンドウと出力ウィンドウです。** : これらのビューは、BizTalk マップの検証、コンパイルおよびテストの結果を確認するために使用します。使用方法は、ソース コードのコンパイル時や、その他の種類のプロジェクトのビルド時にこれらのビューを使用する方法とほぼ同じです。  
  
 これらのビュー以外にも、いくつかのダイアログ ボックスを使用できます。 通常は、Functoid の入力パラメーターなど複雑なプロパティを編集する場合に、これらのダイアログ ボックスが開きます。  
  
 BizTalk マッパーと共に、[ソリューション エクスプローラー] ウィンドウを使用する場合があります。 たとえば、新しいマップを作成するで BizTalk プロジェクトを右クリックし、**ソリューション エクスプ ローラー**ウィンドウで、をクリックして**追加**、 をクリックして**新しい項目の追加**、しを使用して、 **新しい項目の追加** ダイアログ ボックスに名前を指定し、新しいマップを作成します。  
  
## <a name="next-steps"></a>次の手順
  
-   [BizTalk マッパー コマンドを使用します。](../core/using-biztalk-mapper-commands.md)  
  
-   [グリッド ページの操作](../core/working-with-grid-pages.md)  
  
-   [ビューを管理する方法](../core/how-to-manage-views.md)  
  
-   [色と BizTalk マッパーでフォントをカスタマイズする方法](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)  
  
-   [展開して、スキーマ ツリーを折りたたむ方法](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)  
  
-   [元に戻すまたはユーザーの操作を再実行する方法](../core/how-to-undo-or-redo-user-operations.md)  
  
-   [マップ項目を検索する方法](../core/how-to-search-for-map-items.md)  
  
-   [BizTalk マッパーの強化された機能を使用](../core/using-enhanced-features-in-biztalk-mapper.md)  
  
-   [ヒントを表示する方法](../core/how-to-view-infotip-and-tooltip.md)  
  
## <a name="see-also"></a>参照  
 [リンクの表示を最適化する方法](../core/how-to-optimize-the-display-of-links.md)