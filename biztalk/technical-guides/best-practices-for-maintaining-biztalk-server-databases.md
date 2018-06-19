---
title: BizTalk Server データベースを維持するためのベスト プラクティス |Microsoft ドキュメント
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
ms.openlocfilehash: b5f6cf1fadf5c039c53e6cca46792c4660353d0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300002"
---
# <a name="best-practices-for-maintaining-biztalk-server-databases"></a>BizTalk Server データベースを維持するためのベスト プラクティス
このトピックの一覧を維持するためのベスト プラクティス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
-   SQL Server で、SQL Server エージェントが実行されていることを確認してください。 SQL Server エージェントが停止したときに、データベースのメンテナンスを担当する組み込みの BizTalk SQL Server エージェント ジョブは実行できません。 この動作により、データベースの増大して、この成長のパフォーマンスの問題が発生する可能性があります。 SQL Server エージェント ジョブの監視については、次を参照してください。 [SQL Server エージェント ジョブの監視](../technical-guides/monitoring-sql-server-agent-jobs.md)です。  
  
-   SQL Server LDF と MDF ファイルが別々 のドライブに確認してください。 同じドライブ上、BizTalkMsgBoxDb と BizTalkDTADb データベースの LDF と MDF ファイルと、ディスクの競合する可能性があります。  
  
-   メッセージ本文が必要ない場合、追跡を有効にしません。 多くの場合、メッセージ本文の追跡を開発し、ソリューションをトラブルシューティングするときに有効にすることがあります。 その場合は、メッセージ本文の追跡が完了したら無効にすることを確認します。 メッセージ本文の追跡を保持する有効な場合、BizTalk Server データベースの拡大します。 メッセージ本文の追跡を有効にする必要があるビジネス ニーズがあれば、いることを確認、 **TrackedMessages_Copy_BizTalkMsgBoxDb**と**DTA Purge and Archive** SQL Server エージェント ジョブを実行しています。正常にします。  
  
-   通常、小規模なトランザクション ログには、パフォーマンス向上が発生することです。 トランザクション ログを小さく保ち、構成、 **BizTalk Server のバックアップ**より頻繁に実行する SQL Server エージェント ジョブ。 詳細については、次を参照してください。、 [BizTalk Server データベースの最適化のホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=153594) (http://go.microsoft.com/fwlink/?LinkId=153594)。  
  
-   使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既存を評価するベスト プラクティス アナライザー (BPA)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。 BPA は、多数のデータベースに関連するチェックを実行します。 BizTalk Server のベスト プラクティス アナライザー ツールをダウンロードする[BizTalk Server のベスト プラクティス アナライザー ツール](http://go.microsoft.com/fwlink/?LinkId=83317)(http://go.microsoft.com/fwlink/?LinkId=83317)。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: を維持し、BizTalk Server データベースのトラブルシューティング](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)   
 [BizTalk Server データベース テーブルの大規模な成長](../technical-guides/large-growing-biztalk-server-database-tables.md)