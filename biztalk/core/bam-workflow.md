---
title: BAM のワークフロー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring business activities [BAM], collecting business data
- XML files
- orchestrations, XML files
- business activities, business data
- infrastructure, managing [BAM]
- business activities, monitoring
- monitoring business activities [BAM], monitoring flow
- managing [BAM], infrastructure
- monitoring business activities [BAM], viewing business data
- managing [orchestrations], mapping XML to orchestrations
ms.assetid: 8b4ae145-3e16-4bb8-bfba-09b9f666218d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82cfe7fe5f29994c72b9f9026c03321ba44e3575
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529163"
---
# <a name="bam-workflow"></a>BAM のワークフロー
次の図は、ビジネス アクティビティの監視、および使用するツールを使用する 4 つのユーザー ロールを示します。  
  
 ![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")  
BAM ロール  
  
 次の手順では、ビジネス アクティビティの監視を使用するため、ワークフローの概要を提供します。  
  
## <a name="specifying-the-business-data-to-collect"></a>ビジネス データの収集を指定します。  
 次のようにビジネス データが収集されます。  
  
-   ビジネス アナリストは BAM アクティビティ ウィザードを使用して、すべてのビジネス ユーザーを収集するデータを指定します。  
  
-   ビジネス アナリストは BAM ビュー ウィザードを使用して、ビジネス ユーザーの各カテゴリのビューを定義します。  
  
-   アクティビティが完了すると、保存し、Microsoft® Excel ブック内のビューには、BAM 定義ブックが呼び出されます。  
  
-   ビジネス アナリストは BAM 定義ブックを XML にエクスポートします。  
  
-   システム管理者および開発者は、その役割を実行するのに、XML を使用します。  
  
-   手順については、BAM 定義ブックを使用するためにある[ビジネス アクティビティの定義および Excel でのビュー](../core/defining-business-activities-and-views-in-excel.md)します。  
  
## <a name="managing-the-bam-infrastructure"></a>BAM インフラストラクチャの管理  
 システム管理者が、BAM 管理ユーティリティ (BM を使用して、ビジネス アナリストが希望している BAM ビューを定義した後。EXE) では、ブックからエクスポートされたコマンド ライン ツール、BAM 定義ブックまたは XML から BAM インフラストラクチャを展開します。  
  
 BAM 管理ユーティリティを動的に作成、テーブル、トリガー、DTS パッケージ、および OLAP キューブ、BAM ビューをサポートするために必要です。  
  
 たびに、ビジネス アナリストが別の BAM ビューを定義または既存の BAM ビューの変更、システム管理者は、BAM 定義ブックを再デプロイする必要があります。  
  
## <a name="mapping-the-xml-to-an-orchestration"></a>オーケストレーションに XML のマッピング  
 ビジネス アナリストが、BAM 定義ブックを XML にエクスポートした後、開発者は、追跡プロファイル エディターに XML ファイルをインポートします。 開発者は、オーケストレーションに XML のマッピング、ビジネス アナリストの情報の要件を実装します。  
  
 追跡プロファイル エディターを使用して、開発者は、XML をオーケストレーションにマップする、次の手順を実行します。  
  
- BizTalk 管理データベース (構成データベースとも呼ばれます) に格納されている展開済みのアセンブリを読み込みます。 展開済みのアセンブリには、ビジネス アナリストは、上記の手順 1. で指定されている要件に対応する 1 つまたは複数のオーケストレーションが含まれています。  
  
- オーケストレーションから抽出されるデータを定義します。 メッセージのスキーマから項目を削除することにより、これを行うし、オーケストレーション図形に、適切なビジネス マイルス トーン (イベント) とデータ項目フォルダー。  
  
- 彼が完了したら、彼プロファイルとして保存を BizTalk® Server 追跡 (.btt) ファイル、Visual SourceSafe などの格納データベースにします。  
  
  開発者は、テスト データベースに .btt ファイルを展開し、統合テストを行って結果を確認します。  
  
## <a name="deploying-the-tracking-profile"></a>追跡プロファイルの展開  
 追跡プロファイル エディターを使用して、システム管理者は、1 つまたは複数の BizTalk 管理データベースにプロファイルを展開します。  
  
 たびに、開発者は、オーケストレーション、またはビジネス ユーザーの変更の要件を変更しより多くのデータを追跡する、システム管理者は、bttdeploy.exe コマンド ライン ユーティリティを使用して追跡プロファイルを再展開する必要があります。  
  
## <a name="viewing-the-business-data"></a>ビジネス データの表示  
 ビジネス ユーザーは、BM.exe ユーティリティによって生成される _LiveData ブックを使用します。 ビジネス ユーザーが _LiveData ブックを開くたびに、ビジネス プロセスの特定の側面を監視するために収集されるデータの新しいライブ バージョンが表示されます。  
  
-   リアルタイム集計として定義されているデータを表示するビジネス ユーザーだけが必要 をクリックする**更新**データを表示するブックでします。  
  
-   集計データがリアルタイムでない場合、ビジネス ユーザーは、スケジュールされた DTS パッケージの実行時に実行されるビジネス データのスナップショットを表示します。  
  
-   お客様の組織は、コラボレーションの要件がある、ビジネス ユーザーは BAS Web サイトからライブ データをアクセスできます。  
  
## <a name="see-also"></a>参照  
 [Excel でビジネス アクティビティとビューの定義](../core/defining-business-activities-and-views-in-excel.md)   
 [BAM によるビジネス アクティビティの監視](../core/monitoring-business-activities-with-bam.md)