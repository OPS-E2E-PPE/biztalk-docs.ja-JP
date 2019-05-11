---
title: 監視するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8951b603fda6204ee8398d2dee9922a0f70a059
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399327"
---
# <a name="best-practices-for-monitoring"></a>監視するためのベスト プラクティス
このトピックでは、Microsoft BizTalk Server 環境とアプリケーションを監視するためのベスト プラクティスを提供します。  
  
 **作成して BizTalk アプリケーションとインフラストラクチャの監視の計画を実装し、**  
  
- このガイドに詳細な監視ソリューションの監視に関するトピックを読み取ります。 考慮すべき要素を以下に示します。  
  
  -   毎週、月単位、および必要な監視のタスクとして、毎日を実行するユーザーはでしょうか。  
  
  -   イベント、保留メッセージ、またはその他のシステムまたはアプリケーション エラーのだれかが通知されますか。  
  
  -   「予期される」例外がフィルター選択された、または特定の優先順位の低いは?  
  
  -   すべてのホスト インスタンスの監視が引き続き実行されていることを確認するか?  
  
  -   すべてのカスタム サービス、カスタムのイベント ログ、および監視のカスタム データベースか?  
  
  -   SQL Server コンピューターと BizTalk Server の SQL エージェント ジョブの監視対象ですか。  
  
  **など、監視アプリケーションのインストール可能であれば、 [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] BizTalk Server アプリケーションとインフラストラクチャの監視を自動化するには**  
  
- BizTalk Server 管理パックには、BizTalk Server の数百の組み込みの規則を提供するために、自動監視に対して推奨されるアプローチは、Microsoft System Center Operations Manager を使用します。  
  
   詳細については、次のリソースを参照してください。  
  
  -   [System Center Operations Manager 2007 用 Microsoft BizTalk Server 管理パック](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)します。  
  
  -   [Operations Manager 2007 で管理パックをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)  
  
  -   [カスタマイズした監視用に BizTalk Server データベースをマークする方法](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
  **BizTalk Server のベスト プラクティス アナライザーを実行します。**  
  
- BizTalk Server のベスト プラクティス アナライザーは、BizTalk Server の展開を調べ、問題に関連するベスト プラクティス基準の一覧が生成されます。 ツールは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集することにより構成レベルの検証を実行します。 データは、展開構成を評価するが使用されます。 ツールとレポートのみ、任意のシステム設定は変更されませんを読み取って自己調整ツールではありません。  
  
   BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)します。  
  
  **ログのパフォーマンス分析ツール (PAL) の実行します。**  
  
- PAL はから無償でダウンロードとして入手できます[ https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL)します。 インストールに関する重要なは、次を参照してください。[パフォーマンス分析のログ (PAL) ツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)します。  
  
  **Log Parser を実行します。**  
  
- Log Parser は強力な多目的ツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムの主要なデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータへの汎用クエリ アクセスを提供します。Directory® します。 このツールを使用して大量のログ情報を照会する可能性があります。 Log Parser ツールをダウンロードします。 [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)  
  
  **BizTalk MsgBoxViewer ツールを実行します。**  
  
  実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)から使用可能な[ http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930)します。 このツールは、BizTalk メッセージ ボックスとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む、HTML レポートが生成されます。 後で使用できるレポートを保存することもできます。 これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行う便利な可能性があります。  
  
  BizTalk MsgBoxViewer ツールでは、すべての問題を識別する場合は、実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)でご利用いただけます[ http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931)します。 このツールでは、簡単に BizTalk MsgBoxViewer ツールによって特定された問題を解決することができます。 BizTalk MsgBoxViewer ツールを使用して、終端記号のツールを統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk 終端記号のを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)します。  
  
> [!NOTE]  
>  、Microsoft では、これらのツールの使用はサポートされていないと、Microsoft がこれらのプログラムの適合性に関する保証をいたしません。 これらのプログラムは、ユーザー自身の責任で使用してください。  
  
 **優先度を監視します。**  
  
-   BizTalk Server アプリケーションとインフラストラクチャの一貫性のある監視、正常な環境を維持するために不可欠です。  
  
-   定期的に評価し、時間の経過と共に、BizTalk Server アプリケーションとインフラストラクチャの変更として、監視ツールを調整します。