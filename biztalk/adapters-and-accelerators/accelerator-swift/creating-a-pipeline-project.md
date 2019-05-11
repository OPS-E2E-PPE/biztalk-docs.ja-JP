---
title: パイプライン プロジェクトを作成する |Microsoft Docs
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
ms.openlocfilehash: 1f2e4ee625bd21dd16d58e5e75121de3a5c26308
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378451"
---
# <a name="creating-a-pipeline-project"></a>パイプライン プロジェクトを作成します。
パイプライン プロジェクトを作成するには  
  
1.  Visual Studio で新しい BizTalk プロジェクトを作成します。  
  
2.  受信パイプラインの項目と送信パイプラインの項目をプロジェクトに追加します。  
  
3.  ReceivePipeline.btp ファイルを開きます。  
  
4.  パイプライン デザイナーでは、ツールボックスを開きます。  
  
5.  右クリックし、**ツールボックス**画面選び**アイテムの選択**します。  
  
6.  [ツールボックス アイテムの選択] ウィンドウ、**パイプライン コンポーネント**タブをクリックし、次のパイプライン コンポーネントを選択します。  
  
    -   SwiftMXDisassembler  
  
    -   SwiftMXAssembler  
  
    -   Swift MXRR エンコーダー コンポーネント  
  
    -   Swift MXRR デコーダー コンポーネント  
  
    -   Swift MXRR 相関関係競合回避モジュールのパーティのコンポーネント  
  
7.  ドラッグ、 **SwiftMXDisassembler**コンポーネントを受信パイプラインの逆アセンブラーのプレース ホルダーです。  
  
8.  SwiftMXDisassembler コンポーネントのプロパティを設定、 **BRE 検証**受信メッセージでビジネス ルールの検証を有効にするかどうかに応じて TRUE または FALSE にプロパティ。 設定、 **TransportHeaderRequired**メッセージ トランスポート ヘッダーを指定するかどうかに応じて TRUE または FALSE にプロパティ。  
  
9. Swift MXRR デコーダーと Swift MXRR 相関パーティ競合回避モジュール コンポーネントは、デコーダーと受信パイプライン内のパーティの競合回避モジュールのプレース ホルダーにドラッグします。  
  
10. 選択、 **MXRR 相関パーティ リゾルバー**パイプライン。 パイプライン コンポーネントのプロパティ ウィンドウで、**調整用の BAM ログを有効にする**SWIFT の応答の調整を有効にするかどうかに応じて TRUE または FALSE のプロパティ。  
  
11. 開く、 **SendPipeline.btp**ファイルをパイプライン デザイナーで開く、**ツールボックス**します。  
  
12. ツールボックスで、ドラッグ、 **SwiftMXAssembler**コンポーネント、送信パイプラインの内部アセンブラーのプレース ホルダーにします。  
  
13. ドラッグ、 **Swift MXRR エンコーダー**コンポーネント、送信パイプラインのエンコーダーのプレース ホルダーにします。  
  
14. 選択、 **MXRR エンコーダー パーティ リゾルバー**パイプラインでは、し、パイプライン コンポーネントのプロパティ ウィンドウでは、次のプロパティを設定します。  
  
15. 有効にする**調整のログ記録を BAM** TRUE または FALSE、SWIFT 応答用の調整を有効にするかどうかによって異なります。  
  
16. 設定、 **LAU のために必要な**TRUE または FALSE SWIFT Alliance アクセス (SAA) でのメッセージの署名を有効にしているかによってにします。  
  
17. LAU に必要なプロパティがされている場合は、TRUE LAU キーの最初の部分と LAU キー 2 番目の部分 (値は、ものと同じ、SAA を構成するときに提供されていたにする必要)。 し、指定に設定されています  
  
18. ビルドし、プロジェクトを配置します。