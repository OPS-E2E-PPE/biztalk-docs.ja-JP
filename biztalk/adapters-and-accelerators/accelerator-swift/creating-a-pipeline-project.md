---
title: パイプライン プロジェクトを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b584e3ab-e824-4977-b4ed-4fc197a6cf7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eead267abbb990933e6fd3150d099d07b007526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209714"
---
# <a name="creating-a-pipeline-project"></a>パイプライン プロジェクトを作成します。
パイプライン プロジェクトを作成するには  
  
1.  Visual Studio で新しい BizTalk プロジェクトを作成します。  
  
2.  受信パイプライン項目とは、送信パイプラインの項目をプロジェクトに追加します。  
  
3.  ReceivePipeline.btp ファイルを開きます。  
  
4.  パイプライン デザイナーでは、ツールボックスを開きます。  
  
5.  右クリックし、**ツールボックス**画面、し、**アイテムの選択**です。  
  
6.  [ツールボックス アイテムの選択] ウィンドウ、**パイプライン コンポーネント**タブをクリックし、次のパイプライン コンポーネントを選択します。  
  
    -   SwiftMXDisassembler  
  
    -   SwiftMXAssembler  
  
    -   Swift MXRR エンコーダー コンポーネント  
  
    -   Swift MXRR デコーダー コンポーネント  
  
    -   Swift MXRR 相関関係者の競合回避コンポーネント  
  
7.  ドラッグ、 **SwiftMXDisassembler**コンポーネントを受信パイプラインの逆アセンブラーのプレース ホルダーです。  
  
8.  SwiftMXDisassembler コンポーネントのプロパティを設定、 **BRE 検証**プロパティを TRUE または FALSE を受信メッセージのビジネス ルールの検証を有効にするかどうかによって異なります。 設定、 **TransportHeaderRequired**プロパティを TRUE または FALSE をトランスポート メッセージ ヘッダーでグループを指定するかどうかによって異なります。  
  
9. デコーダーおよび受信パイプライン内のパーティの競合回避モジュールのプレース ホルダーに Swift MXRR デコーダーと Swift MXRR 相関パーティ競合回避モジュール コンポーネントをドラッグします。  
  
10. 選択、 **MXRR 相関パーティ リゾルバー**パイプラインでします。 パイプライン コンポーネントのプロパティ ウィンドウで次のように設定します。、 **BAM の調整のログ記録を有効にする**プロパティを TRUE または FALSE を迅速な応答の調整を有効にするかどうかによって異なります。  
  
11. 開く、 **SendPipeline.btp**ファイルをパイプライン デザイナーで開く、**ツールボックス**です。  
  
12. ツールボックスで、ドラッグ、 **SwiftMXAssembler**コンポーネント、送信パイプラインの内部アセンブラー プレース ホルダーをします。  
  
13. ドラッグ、 **Swift MXRR エンコーダー**コンポーネント、送信パイプラインのエンコーダーのプレース ホルダーをします。  
  
14. 選択、 **MXRR エンコーダー パーティ リゾルバー**パイプラインでし、パイプライン コンポーネントのプロパティ ウィンドウでは、次のプロパティを設定します。  
  
15. 有効にする**BAM の調整のログ記録**TRUE または FALSE の迅速な応答の調整を有効にするかどうかによって異なります。  
  
16. 設定、**必要 LAU** TRUE または SWIFT Alliance アクセス (SAA) でメッセージの署名を有効にする必要があるかどうかに応じて FALSE にします。  
  
17. LAU のために必要なプロパティがあった場合は TRUE、LAU キーの最初の部分と LAU キー 2 番目の部分 (値する必要があるものと同じで、SAA を構成するときに提供されている。) を入力に設定されています  
  
18. プロジェクトをビルドし、展開します。