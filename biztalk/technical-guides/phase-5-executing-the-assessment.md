---
title: "フェーズ 5: 評価の実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fba6d49d8d69276af4282ad0a941ee1fc4d8068
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="phase-5-executing-the-assessment"></a>評価の実行フェーズ 5。
実行フェーズは、自動化されたロード テストでと、パフォーマンスのボトルネックが検出され、アドレス指定されるパフォーマンス データが生成される場所です。 このフェーズがパフォーマンスのボトルネックを削減または削除して、テストをそれにより、反復処理のパフォーマンスの評価、最適化、およびテストをもう一度です。  
  
 このトピックでは、BizTalk Server のパフォーマンス評価の実行フェーズ中に続き、通常の手順について説明します。  
  
## <a name="step-1-run-automated-tests"></a>手順 1: 自動テストを実行します。  
 自動テストを実行して、実行フェーズを開始します。 BizTalk Server のパフォーマンス評価は通常スループットや待機時間がテストの重点を置いていますが、ビルドの検証および機能テストに含めることができます。 自動テストの実行に関する包括的な情報は、次を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)です。  
  
## <a name="step-2-document-and-evaluate-test-results"></a>手順 2: を文書化し、テスト結果を評価  
 各テストの最後に、十分にテスト結果を文書化し、示されたパフォーマンス目標が満たされているかどうかを評価します。  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a>手順 3: テストの結果に基づいて、パフォーマンスをチューニングするには、BizTalk Server、サード パーティ製システム、またはソリューションの成果物の構成を変更します。  
 提示されたスループットや待機時間の目標を達成するのに環境を最適化するのに方法に関する意思決定を行うには、テスト結果を使用します。  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a>手順 4: が環境に加えられたすべての変更を記録します。  
 環境に加えられた変更が十分に記載されていることを確認します。 変更のレコードを簡単に実稼働環境の変更を適用することが、場合に、変更を元に戻してに対応する必要があります。  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a>手順 5: の目標を達成するまでこのサイクルを繰り返す  
 テスト、評価し結果を文書化、環境の最適化、目的のパフォーマンス目標に到達するまでに、環境に対する変更を文書化のサイクルを続行します。  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a>手順 6: 集計、毎日の最後のテスト結果  
 毎日の最後に進行状況、テスト結果の「概要」を完了します。 概要を含む電子メールをコンパイルし、パフォーマンスの評価対象のすべての関係者に送信して行われている進行状況の通知を受け取ります足並みをします。  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a>手順 7: 目標の達成タイムラインとプロジェクト計画を更新します。  
 計画フェーズで開発されたタイムラインは、パフォーマンスの評価の全体的な進行状況を適切な参照です。 進行状況をすべての利害関係者に通信するために必要に応じて、このタイムラインを更新します。  
  
## <a name="see-also"></a>参照  
 [パフォーマンス評価の段階](../technical-guides/phases-of-a-performance-assessment.md)