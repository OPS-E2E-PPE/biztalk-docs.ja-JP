---
title: BAM ワークフロー |Microsoft ドキュメント
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
ms.openlocfilehash: 19356d6191963ec441f0b85c0e987c8515dcf1f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232042"
---
# <a name="bam-workflow"></a>BAM のワークフロー
ビジネス アクティビティ監視と連携する 4 つのユーザー ロールと、ロールで使用されるツールを次に示します。  
  
 ![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")  
BAM ロール  
  
 次の手順では、ビジネス アクティビティ監視を使用するためのワークフローの概要について説明します。  
  
## <a name="specifying-the-business-data-to-collect"></a>収集するビジネス データの指定  
 ビジネス データは次のように収集されます。  
  
-   ビジネス アナリストは、BAM アクティビティ ウィザードを使用して、すべてのビジネス ユーザー用に収集するデータを指定します。  
  
-   また、BAM ビュー ウィザードを使用して、ビジネス ユーザーのカテゴリごとにビューを定義します。  
  
-   定義が終了した後、BAM 定義ブックと呼ばれる Microsoft® Excel ブックに、アクティビティとビューを保存します。  
  
-   ビジネス アナリストは BAM 定義ブックを XML にエクスポートします。  
  
-   システム管理者と開発者は、この XML を使用してロールを実行します。  
  
-   BAM 定義ブックを使用するための手順にある[ビジネス アクティビティの定義および Excel でビュー](../core/defining-business-activities-and-views-in-excel.md)です。  
  
## <a name="managing-the-bam-infrastructure"></a>BAM インフラストラクチャの管理  
 ビジネス アナリストが必要な BAM ビューを定義した後、システム管理者は BAM 管理ユーティリティ (BM.EXE) というコマンド ライン ツールを使用して、BAM 定義ブック、またはブックからエクスポートした XML から BAM インフラストラクチャを展開します。  
  
 BAM 管理ユーティリティを使用すると、BAM ビューのサポートに必要なテーブル、トリガー、DTS パッケージ、および OLAP キューブが動的に作成されます。  
  
 ビジネス アナリストが別の BAM ビューを定義したり、既存の BAM ビューを変更するたびに、システム管理者は BAM 定義ブックを再展開する必要があります。  
  
## <a name="mapping-the-xml-to-an-orchestration"></a>オーケストレーションへの XML のマッピング  
 ビジネス アナリストが BAM 定義ブックを XML にエクスポートした後、開発者は XML ファイルを追跡プロファイル エディターにインポートします。 開発者は、XML をオーケストレーションにマップして、ビジネス アナリストに必要な情報を実装します。  
  
 XML をオーケストレーションにマップするには、追跡プロファイル エディター (TPE) を使用して次の手順を実行します。  
  
-   BizTalk 管理データベース (構成データベース) に格納されている展開済みのアセンブリを読み込みます。 展開済みのアセンブリには、上記の手順 1. でビジネス アナリストが指定した要件に対応する 1 つ以上のオーケストレーションが含まれています。  
  
-   オーケストレーションから抽出するデータを定義します。 これには、メッセージ スキーマやオーケストレーション図形から適切なビジネス マイルストーン (イベント) やデータ項目フォルダーに項目をドロップします。  
  
-   作業が終了した後、ファイルを BizTalk® Server 追跡 (.btt) ファイルとして Visual SourceSafe などの格納データベースに保存します。  
  
 開発者は .btt ファイルをテスト データベースに展開し、結合テストを行って結果を確認します。  
  
## <a name="deploying-the-tracking-profile"></a>追跡プロファイルの展開  
 システム管理者は、追跡プロファイル エディターを使用して、1 つ以上の BizTalk 管理データベースにプロファイルを展開します。  
  
 開発者がオーケストレーションを変更したり、ビジネス ユーザーの要件が変わって追跡するデータが増えるたびに、システム管理者は、コマンド ライン ユーティリティの bttdeploy.exe を使用して追跡プロファイルを再展開する必要があります。  
  
## <a name="viewing-the-business-data"></a>ビジネス データの表示  
 ビジネス ユーザーは、BM.exe ユーティリティによって生成される _LiveData ブックを使用します。 _LiveData ブックを開くたびに新しいライブ データが受信されます。このデータはビジネス プロセスの特定の側面を監視するために収集されたものです。  
  
-   リアルタイム集計として定義されているデータを表示するには、ビジネス ユーザーだけが必要 をクリックする**更新**データを表示するブックでします。  
  
-   集計データがリアルタイムでない場合は、スケジュール設定された DTS パッケージの実行時に取得されたビジネス データのスナップショットを参照できます。  
  
-   組織で共同作業が必要な場合、ビジネス ユーザーは BAS Web サイトからライブ データにアクセスできます。  
  
## <a name="see-also"></a>参照  
 [Excel でビジネス アクティビティとビューを定義します。](../core/defining-business-activities-and-views-in-excel.md)   
 [BAM によるビジネス アクティビティの監視](../core/monitoring-business-activities-with-bam.md)