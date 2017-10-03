---
title: "追跡データベースのボトルネックを特定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16cd05b6c399d250d8a411f41f56406f19afc9e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a>追跡データベースのボトルネックを特定する方法
BizTalk 追跡 (BizTalkDTADb) データベースのボトルネックを特定するには、次の手順を実行します。  
  
1.  SQL エージェント サービスが実行されていることを確認します。  
  
2.  Archive/Purge ジョブが実行され、正常に完了することを確認します。  
  
3.  TrackedMessages_Copy_BizTalkMsgBoxDB ジョブが実行されていて、正常に完了しないことを確認します。  
  
4.  DTADb アーカイブとデータベース サイズの増加に対応できるだけの十分な空きディスク領域があることを確認します。  
  
5.  専用のホストの追跡を使用し、負荷の下にあるときにホスト Queue Length パフォーマンス カウンターを測定します。  
  
6.  時間の経過と共に上昇傾向のスプール テーブル サイズのパフォーマンス カウンターを確認してください。  
  
7.  Archive/purge ジョブの実行時間の長い実行時間を確認してください。  
  
8.  BizTalk 追跡データベースをホストしているディスク上のディスク (ディスク (秒) パフォーマンス カウンターの読み取り/書き込みごと) の応答性を確認します。  
  
 Dtasp_BackupAndPurgeTrackingDatabase または dtasp_PurgeTrackingDatabase DTA Purge and Archive ジョブによって呼び出されるは、次のパラメーターの値をチューニングを強くお勧めします。  
  
-   @nLiveHourstinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定では 0 時間です。  
  
-   @nLiveDaystinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定の間隔は 1 日です。  
  
-   @nHardDeleteDaystinyint — すべてのデータ (不完全な場合でも) これは、削除するよりも古いします。 HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。 データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。 この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。 既定値は、30 日間です。  
  
 これらのパラメーターは、ことをお勧めパフォーマンス ラボ テストで値を使用する次のように対し、実稼働環境でのデータ保持ポリシーに従って設定する必要があります。  
  
 宣言@dtLastBackupdatetime セット@dtLastBackupGetUTCDate() を =  
 exec dtasp_PurgeTrackingDatabase 1, 0, 1,@dtLastBackup  
  
## <a name="see-also"></a>参照  
 [データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)