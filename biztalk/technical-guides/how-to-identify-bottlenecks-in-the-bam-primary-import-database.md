---
title: "BAM プライマリ インポート データベースのボトルネックを特定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5780c8fcc893126997b37f687f010c5eb62e74c9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースのボトルネックを特定する方法
ビジネス アクティビティ監視 (BAM) データベースのボトルネックを特定するには、次の手順を実行します。  
  
1.  アクティブ インスタンス数が増えていないことを確認します。  
  
2.  SQL エージェント サービスが実行されていることを確認します。  
  
3.  OLAP 分析が構成されている場合ことを確認、bam_an _\<activityname\>ジョブが定期的に実行します。  
  
4.  確認する bam_dm _\<activityname\> (データ管理) ジョブを定期的に実行するようにスケジュールします。  
  
    > [!NOTE]  
    >  使用率が高いシナリオの BAM データベースのアクティビティ内の BizTalk Server の全体的なパフォーマンスが低下する可能性が他の BizTalk Server データベースのパフォーマンスに影響します。 ここでは、次の操作を実行を検討してください。  
    >   
    >  -   1 か月を以下に、既定値 (6 か月間) からのすべての BAM アクティビティの期間を短縮を検討します。 これにより、対象は、BAMPrimaryImport データベースに BAM データを保持アーカイブされる前に期間が低減されます。 BAM 管理ユーティリティを使用して`set-activitywindow`BAM アクティビティの期間を変更するコマンド。 詳細については、BAM 管理ユーティリティのアクティビティ管理コマンドを参照してください[アクティビティ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=210417)(http://go.microsoft.com/fwlink/?LinkId=210417)。  
    > -   すべての BizTalk メッセージ ボックス データベースをホストしていない SQL Server のインスタンスに、BAM アーカイブ データベースを移動します。 これらのデータベースのリソースの競合を防ぐ、全体的なパフォーマンスを向上させます。  
  
5.  専用のホストの追跡を使用し、負荷の下にあるときにホスト Queue Length パフォーマンス カウンターを測定します。  
  
6.  時間の経過と共に上昇傾向のスプール テーブル サイズのパフォーマンス カウンターを確認してください。  
  
7.  Archive/purge ジョブの実行時間の長い実行時間を確認してください。  
  
8.  BizTalk 追跡データベースをホストしているディスク上のディスク (ディスク (秒) パフォーマンス カウンターの読み取り/書き込みごと) の応答性を確認します。  
  
## <a name="see-also"></a>参照  
 [データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)