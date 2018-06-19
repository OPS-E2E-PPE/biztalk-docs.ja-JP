---
title: BAM 集計を定義する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- aggregations [BAM], creating
- Excel add-in [BAM], security
- Excel add-in [BAM], creating aggregations
- managing [BAM], creating aggregations
ms.assetid: a5ef3a15-b1de-4099-8e94-64af4b5ec746
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1b5b377611eb8e28088cb2d0c2f2ed6f829de8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249514"
---
# <a name="how-to-define-bam-aggregations"></a>BAM 集計を定義する方法
BAM では、次の 2 種類のデータ集計がサポートされます。  
  
-   オンライン分析処理 (OLAP) 集計  
  
-   リアルタイム集計 (RTA)  
  
 BAM では、OLAP 集計を実装するために Microsoft SQL Analysis Services が使用されます。  
  
 RTA を定義する BAM プライマリ インポート データベースでは、トリガーを構成する必要があります。  
  
### <a name="to-define-olap-aggregations"></a>OLAP 集計を定義するには  
  
1.  BAM Excel ブックで、ビューを作成し、PivotTable レポートにディメンションとメジャーを少なくとも 1 つずつ追加し、RTA ツール バー ボタンを非表示にしてブックを保存します。  
  
    -   BAM ブックを開く方法については、ビューを作成して、ディメンション、メジャーを追加するを参照してください[BAM ビューを定義する](../core/defining-a-bam-view.md)です。  
  
2.  ブックを展開します。  
  
    -   ブックを展開するの指示に従って、 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)です。  
  
3.  ソリューション開発者は、使用、 **DirectEventStream**クラス、BAM プライマリ インポート データベースにイベントをインポートします。  
  
    -   については、 **DirectEventStream**クラスを参照してください[DirectEventStream クラス](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)です。  
  
4.  キューブ更新データ変換サービス (DTS) パッケージを実行します。  
  
    -   キューブ更新 DTS パッケージの実行方法の詳細については、次を参照してください。[の BAM DTS パッケージ](../core/bam-dts-packages.md)です。  
  
5.  ブックのライブ データの最新コピーを開き、OLAP 集計を表示します。  
  
    > [!IMPORTANT]
    >  セキュリティ上の理由により、BAM ではブックの既存ライブ データのコピーが削除されません。 代わりに、ライブ データのコピーのファイル名がインクリメントされます。  
  
### <a name="to-define-the-rta"></a>RTA を定義するには  
  
1.  BAM Excel ブックで、ビューを作成し、PivotTable レポートに 1 つ以上のディメンションと 1 つのメジャーを追加し、RTA ツール バー ボタンを選択してブックを保存します。  
  
    > [!WARNING]
    >  同じ BAM アクティビティを使用する RTA を複数定義しないでください。 そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。  
  
    -   BAM ブックを開く方法については、ビューを作成して、ディメンション、メジャーを追加するを参照してください「ビジネス アクティビティ ビューの定義」および「集計の定義、*情報ワーカー ユーザー ガイド*です。  
  
2.  ブックを展開します。  
  
    -   ブックを展開するの指示に従って、 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)です。  
  
3.  ソリューション開発者は、使用、 **DirectEventStream**クラス、BAM プライマリ インポート データベースにイベントをインポートします。  

  
4.  ブックのライブ データの最新コピーを開き、RTA を表示します。  
  
    > [!IMPORTANT]
    >  セキュリティ上の理由により、BAM ではブックの既存ライブ データのコピーが削除されません。 代わりに、ライブ データのコピーのファイル名がインクリメントされます。  
  
## <a name="see-also"></a>参照  
 [BAM DTS パッケージ](../core/bam-dts-packages.md)   
 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)   
 [OLAP および RTA 接続文字列プロパティの更新](../core/updating-olap-and-rta-connection-string-properties.md)   
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)