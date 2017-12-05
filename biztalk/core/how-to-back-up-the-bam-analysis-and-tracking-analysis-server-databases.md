---
title: "バックアップ方法、BAM 分析および Tracking Analysis Server データベース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, DTS packages
- backing up [BAM], Tracking Analysis Server database
- backing up [BAM], OLAP cubes
- backing up [BAM], DTS packages
- purging, OLAP cubes
- Analysis database [BAM], backing up
- scheduling, BAM backups
- backing up [BAM], Analysis database
- OLAP cubes, purging
- backing up, BAM
- backing up [BAM], database order
- DTS packages, backing up
- backing up [BAM], Star Schema database
- backing up [BAM], scheduling
- Tracking Analysis Server database [BAM], backing up
- Star Schema database [BAM], backing up
ms.assetid: d39e3491-ab54-44f2-990a-7b8ee86f0501
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: effa2f5787f04493713ea6972562fe768081f4bc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>BAM 分析データベースおよび Tracking Analysis Server データベースをバックアップする方法
ビジネス アクティビティ監視 (BAM) 分析データベースおよび Tracking Analysis Server データベースには、SQL Server Analysis Services キューブの内容が格納されます。 BizTalk Server のバックアップ ジョブでは、これらのデータベースはバックアップされません。 これらのデータベースをバックアップするには、SQL Server 分析マネージャを使用する必要があります。  
  
 これらのデータベースをバックアップした後で、OLAP キューブを削除できます。 OLAP キューブを削除する場合には、次の手順も実行してください。  
  
1.  OLAP キューブを削除する前に、BAMStarSchema データベースで、削除するキューブのファクト テーブルを切り捨てます。 テーブルの名前付け規則は"bam _*\<CubeName\>*_Facts"です。  
  
2.  OLAP キューブを削除した後で、アクティブなキューブ、完了したキューブ、および仮想キューブを完全に処理する必要があります。  
  
 分析データベースをバックアップする方法については、SQL Server Books Online の「Analysis Services データベースのアーカイブ (Archiving an Analysis Services Database)」を参照してください。  
  
 **BAM データベースのバックアップのスケジュール設定**  
  
 BAM を使用している場合は、バックアップ パッケージの実行がスケジュールされているときに、並行して BAM キューブ プロセスやデータ管理のデータ変換サービス (DTS) パッケージが実行されないか、確認します。  
  
 すべての BAM データベースでスキーマの一貫性を確保するには、BAM アクティビティを展開または展開解除するたびに、BAM データベースおよび DTS パッケージをバックアップします。  
  
 BAM ビューを展開または展開解除するたびに、BAM 分析データベースおよび BAMStarSchema データベースをバックアップします。  
  
 次の順序で BAM データベースをバックアップします。  
  
1.  BizTalk Server のバックアップ ジョブを実行して、BAMPrimaryImport データベースおよび他の BizTalk Server データベースをバックアップします。  
  
2.  すべてのアクティビティに対して、BAM データ管理 DTS パッケージを実行します。  
  
     これらの手順を DTS パッケージに組み込み、パッケージが定期的に実行されるようにスケジュール設定します。 確実にデータの整合性を保つためには、このバックアップ パッケージの実行がスケジュールされているときに、並行して他の BAM キューブまたはデータ管理 DTS パッケージが実行されることのないようにします。  
  
     BAMArchive データベースでエラーが発生した場合に、アーカイブしたデータの完全なセットを確実に回復できるようにするには、BAMArchive データベースのバックアップは、パーティションを BAMArchive データベースにコピーした後、パーティションを BAMPrimaryImport データベースから削除する前に行います。 そのためには、各アクティビティのデータ管理 DTS パッケージを変更して、DTS パッケージの最後の手順 "アーカイブ終了" の前に、BAMArchive データベースをバックアップする手順を挿入します。  
  
3.  BAMAnalysis データベースおよび BAMStarSchema メッセージ スキーマをバックアップします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)