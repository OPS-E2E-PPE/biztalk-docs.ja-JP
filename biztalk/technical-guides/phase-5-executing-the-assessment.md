---
title: フェーズ 5:評価の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 332073502c1b2cc358e09ce7f50338321eb42bdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393472"
---
# <a name="phase-5-executing-the-assessment"></a>フェーズ 5:評価の実行
実行フェーズは、自動化されたロード テストと、パフォーマンスのボトルネックが検出され、アドレス指定にパフォーマンス データを生成する場所です。 このフェーズがパフォーマンスのボトルネックを削減または削除して、テストをそれにより、反復的なプロセスのパフォーマンスの評価、最適化、そしてもう一度テストします。  
  
 このトピックでは、BizTalk Server のパフォーマンス評価の実行フェーズ中に従っている通常の手順について説明します。  
  
## <a name="step-1-run-automated-tests"></a>手順 1:自動テストを実行します。  
 実行フェーズを開始するには、自動テストを実行します。 BizTalk Server のパフォーマンス評価は通常スループットや待機時間のテストに重点を置いていますが、ビルドの検証および機能テストに含めることができます。 自動テストの実行に関する包括的な情報を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)します。  
  
## <a name="step-2-document-and-evaluate-test-results"></a>手順 2:文書化し、テスト結果を評価します。  
 各テストの最後には、十分にテスト結果を文書化し、規定されたパフォーマンスの目標を満たしているかどうかを評価します。  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a>手順 3:テスト結果に基づいてパフォーマンスをチューニングするには、BizTalk Server、サード パーティ システム、またはソリューションの成果物の構成を変更します。  
 環境を最適化するのに方法について説明したスループットや待機時間の目標に到達するのに決定を行うには、テスト結果を使用します。  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a>手順 4:環境に加えられたすべての変更を記録します。  
 環境に加えられた変更が十分に記載されていることを確認します。 変更のレコードは簡単に実稼働環境の変更を適用することし、場合、変更の取り消しを可能になる必要があります。  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a>手順 5:目標を達成するまでこのサイクルを繰り返します  
 テスト、評価、結果を文書化し、環境を最適化する、目的のパフォーマンス目標に達するまでは、環境への変更を文書化、サイクルを続行します。  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a>手順 6:1 日の最後にテスト結果を要約します。  
 1 日の最後に進行状況、テスト結果の「概要」を完了します。 概要を含む電子メールをコンパイルし、全員が行われているの進行状況の通知が常にパフォーマンスの評価ですべての利害関係者に送信します。  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a>手順 7:タイムラインの目標を満たしていると、プロジェクト計画を更新します。  
 計画フェーズで開発されたタイムラインは、パフォーマンス評価の全体的な進行状況の適切な参照です。 進行状況をすべての関係者に通信するために必要に応じて、このタイムラインを更新します。  
  
## <a name="see-also"></a>参照  
 [パフォーマンス評価のフェーズ](../technical-guides/phases-of-a-performance-assessment.md)