---
title: BAM プライマリ インポート データベースのボトルネックを特定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 613bfa623110a4792894da71365c1a40d7856c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003627"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースのボトルネックを特定する方法
ビジネス アクティビティ監視 (BAM) データベースのボトルネックを識別するために、次の手順に従います。  
  
1. アクティブ インスタンス数が増えていないことを確認します。  
  
2. SQL エージェント サービスが実行されていることを確認します。  
  
3. OLAP 分析が構成されている場合ことを確認、bam_an _\<activityname\>ジョブが定期的に実行します。  
  
4. 確認する bam_dm _\<activityname\>定期的な間隔で実行する (データ管理) ジョブがスケジュールされています。  
  
   > [!NOTE]
   >  使用率が高いシナリオの BAM データベースのアクティビティは、BizTalk サーバー全体のパフォーマンスに影響を与える他の BizTalk Server データベースのパフォーマンスが影響します。 ここで、次の操作を検討してください。  
   > 
   > - 1 か月を以下に既定値 (6 か月) からのすべての BAM アクティビティの実行時間の短縮を検討します。 これにより、対象は、BAMPrimaryImport データベースに BAM データを保持アーカイブされる前に期間が低減されます。 BAM 管理ユーティリティを使用して`set-activitywindow`BAM アクティビティの期間を変更するコマンド。 コマンドを参照してください、BAM 管理ユーティリティの活動管理の詳細については[アクティビティ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=210417)(http://go.microsoft.com/fwlink/?LinkId=210417)します。  
   >   -   すべての BizTalk メッセージ ボックス データベースをホストしていない SQL Server のインスタンスには、BAM アーカイブ データベースを移動します。 これらのデータベースがリソースの競合を防ぐを全体的なパフォーマンスが向上します。  
  
5. 追跡専用のホストに使用し、負荷の下にある場合、Host Queue Length パフォーマンス カウンターを測定します。  
  
6. 時間の経過と共に、スプール テーブルのサイズのパフォーマンス カウンターを増加傾向を確認します。  
  
7. Archive/purge ジョブの実行時間の長い実行時間を確認します。  
  
8. BizTalk 追跡データベースをホストしているディスク上のディスク (ディスク秒数パフォーマンス カウンタの読み取り/書き込み) の応答性を確認します。  
  
## <a name="see-also"></a>参照  
 [データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)