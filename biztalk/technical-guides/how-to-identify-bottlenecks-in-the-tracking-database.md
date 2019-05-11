---
title: 追跡データベースのボトルネックを特定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c82a0b106cbb8fee680582aad7d1aa5ce331f02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400414"
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a>追跡データベースのボトルネックを特定する方法
BizTalk 追跡 (BizTalkDTADb) データベースのボトルネックを識別するために、次の手順に従います。  
  
1. SQL エージェント サービスが実行されていることを確認します。  
  
2. Archive/Purge ジョブが実行され、正常に完了することを確認します。  
  
3. TrackedMessages_Copy_BizTalkMsgBoxDB ジョブが実行され、正常に完了しないことを確認してください。  
  
4. DTADb アーカイブとデータベース サイズの増加に対応できるだけの十分な空きディスク領域があることを確認します。  
  
5. 追跡専用のホストに使用し、負荷の下にある場合、Host Queue Length パフォーマンス カウンターを測定します。  
  
6. 時間の経過と共に、スプール テーブルのサイズのパフォーマンス カウンターを増加傾向を確認します。  
  
7. Archive/purge ジョブの実行時間の長い実行時間を確認します。  
  
8. BizTalk 追跡データベースをホストしているディスク上のディスク (ディスク秒数パフォーマンス カウンタの読み取り/書き込み) の応答性を確認します。  
  
   Dtasp_BackupAndPurgeTrackingDatabase または dtasp_PurgeTrackingDatabase DTA Purge and Archive ジョブによって呼び出されるは、次のパラメーターの値をチューニングを強くお勧めします。  
  
- @nLiveHourstinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定では 0 時間です。  
  
- @nLiveDaystinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定の間隔は、1 日です。  
  
- @nHardDeleteDaystinyint — すべてのデータ (不完全な場合でも) これは、削除するよりも古いします。 HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。 データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。 この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。 既定値は、30 日間です。  
  
  お勧めパフォーマンス ラボ テストで値を使用する次のように対し、運用環境でのデータ保持ポリシーに基づいてこれらのパラメーターを設定する必要があります。  
  
  declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate()  
  exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup  
  
## <a name="see-also"></a>参照  
 [データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)