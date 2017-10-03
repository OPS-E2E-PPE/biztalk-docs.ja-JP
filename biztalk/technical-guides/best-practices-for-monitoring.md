---
title: "監視するためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d520026b9037f10f2ed20f52a366b1ff9d3183a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-monitoring"></a>監視のベスト プラクティス
このトピックでは、Microsoft を監視するためのベスト プラクティス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境とアプリケーション。  
  
 **作成し、BizTalk アプリケーションとインフラストラクチャの監視の計画を実装**  
  
-   詳細な監視ソリューションを確認するには、このガイドの監視のトピックを参照します。 考慮すべき要因を以下に示します。  
  
    -   毎週、月単位、および必要な監視タスクとして、毎日、誰が実行しますか。  
  
    -   イベント、中断されたメッセージ、またはその他のシステムまたはアプリケーション エラーの通知を受けるユーザーですか。  
  
    -   「予期される」例外フィルター選択されたまたは特定の優先順位が低いか。  
  
    -   すべてのホスト インスタンスの実行を継続するように監視されますか。  
  
    -   すべてのカスタム サービス、カスタム イベント ログ、および監視のカスタム データベースとは  
  
    -   SQL Server コンピューターであると、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL エージェント ジョブを監視しますか?  
  
 **など、監視のアプリケーションのインストール可能であれば、 [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] BizTalk Server アプリケーションとインフラストラクチャの監視を自動化するのには**  
  
-   BizTalk Server 管理パックが数百の組み込みの規則を提供するため、監視を自動推奨できるアプローチは、Microsoft System Center Operations Manager を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
     詳細については、次のリソースを参照してください。  
  
    -   [System Center Operations Manager 2007 用 Microsoft BizTalk Server 管理パック](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)。  
  
    -   [Operations Manager 2007 で管理パックをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)  
  
    -   [カスタマイズした監視の BizTalk Server データベースをマークする方法](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
 **BizTalk Server のベスト プラクティス アナライザーを実行します。**  
  
-   BizTalk Server のベスト プラクティス アナライザーを調べ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開し、ベスト プラクティスの標準に関連する問題の一覧を生成します。 このツールは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集することによって構成レベルの検証を実行します。 データは展開構成の評価に使用されます。 ツールを読み取りますをレポートのみ、そのシステム設定を変更しませんし、自己調整ツールではありません。  
  
     BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。  
  
 **ログのパフォーマンス分析ツール (PAL) の実行します。**  
  
-   PAL はから無償でダウンロードとして入手できます[http://go.microsoft.com/fwlink/LinkID=98098](http://go.microsoft.com/fwlink/?LinkID=98098)です。 インストールに関する重要な情報を参照してください。[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)です。  
  
 **ログ パーサーを実行します。**  
  
-   ログ パーサーは、強力な用途の広いツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムでキーのデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータにユニバーサル クエリ アクセスを提供します。Directory® です。 このツールを使用して大量のログ情報のクエリを実行する可能性があります。 Log Parser ツールをダウンロードする[http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)  
  
 **BizTalk MsgBoxViewer ツールを実行します。**  
  
 実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)から使用可能な[http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930)です。 このツールでは、BizTalk メッセージ ボックス データベースとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む HTML レポートを生成します。 後で使用できるレポートを保存することもできます。 これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行うときに役立ちます可能性があります。  
  
 BizTalk MsgBoxViewer ツールは、すべての問題を示している場合は、実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)いただけます[http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931)です。 このツールでは、簡単に BizTalk MsgBoxViewer ツールによって識別される問題を解決することができます。 ターミネータ ツールが、BizTalk MsgBoxViewer ツールと統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk のターミネータを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。  
  
> [!NOTE]  
>  Microsoft では、これらのツールの使用はサポートされていないと、Microsoft がこれらのプログラムの適合性に関して保証を行いません。 これらのプログラムは、ユーザー自身の責任で使用してください。  
  
 **優先度を監視します。**  
  
-   一貫した監視[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャが正常な環境を維持するために不可欠です。  
  
-   定期的に評価し、監視ツールを調整して時間の経過と共に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャを変更します。