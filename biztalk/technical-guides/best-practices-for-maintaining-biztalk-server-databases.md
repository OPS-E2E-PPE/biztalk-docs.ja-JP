---
title: BizTalk Server データベースを維持するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93333f41-ee83-4b64-b381-66584a7d5551
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 259bc2d01401341e3cd8e7fb928fa373dfecfa3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242679"
---
# <a name="best-practices-for-maintaining-biztalk-server-databases"></a>BizTalk Server データベースを維持するためのベスト プラクティス
このトピックの一覧を維持するためのベスト プラクティス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
- SQL Server エージェントが SQL Server で実行されていることを確認します。 SQL Server エージェントを停止すると、データベースのメンテナンスを担当する組み込みの BizTalk SQL Server エージェント ジョブを実行できません。 この動作により、データベース サイズの増加と、この成長のパフォーマンスの問題が発生する可能性があります。 SQL Server エージェント ジョブの監視については、次を参照してください。 [SQL Server エージェント ジョブの監視](../technical-guides/monitoring-sql-server-agent-jobs.md)します。  
  
- SQL Server の LDF と MDF ファイルが別々 のドライブを確認します。 同じドライブ上、BizTalkMsgBoxDb および BizTalkDTADb データベースの LDF と MDF ファイルがある場合と、ディスクの競合する可能性があります。  
  
- メッセージ本文が必要ない場合、追跡を有効にしないでください。 多くの場合、メッセージ本文の追跡の開発や、ソリューションのトラブルシューティングを有効にすることがあります。 場合は、メッセージ本文の追跡が終わったら無効にすることを確認します。 メッセージ本文の追跡を維持する有効な場合、BizTalk Server のデータベースのサイズします。 メッセージ本文の追跡を有効にする必要があるビジネス ニーズがあれば、ことを確認します、 **TrackedMessages_Copy_BizTalkMsgBoxDb**と**DTA Purge and Archive** SQL Server エージェント ジョブを実行している。正常にします。  
  
- 通常、小規模なトランザクション ログが発生するパフォーマンスを向上させる。 トランザクション ログを比較的小さく保つには、構成、 **Backup BizTalk Server**より頻繁に実行する SQL Server エージェント ジョブ。 詳細については、次を参照してください。、 [BizTalk Server データベースの最適化に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=153594) (http://go.microsoft.com/fwlink/?LinkId=153594)します。  
  
- 使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既存を評価するベスト プラクティス アナライザー (BPA)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。 BPA は、多数のデータベースに関連したチェックを実行します。 BizTalk Server Best Practices Analyzer ツールをダウンロードする[BizTalk Server Best Practices Analyzer ツール](http://go.microsoft.com/fwlink/?LinkId=83317)(<http://go.microsoft.com/fwlink/?LinkId=83317>)。  
  
## <a name="see-also"></a>参照  
 [チェックリスト:メンテナンスと BizTalk Server データベースのトラブルシューティング](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)   
 [BizTalk Server データベース テーブルの大規模な成長](../technical-guides/large-growing-biztalk-server-database-tables.md)