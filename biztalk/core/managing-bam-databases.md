---
title: "BAM データベースの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], databases
- databases [BAM], managing
- databases, BAM
ms.assetid: ce3c472e-2da1-4d67-816a-befe4ded20d9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dbe8cdb2c7806ab62b67db80c4741d64560fba9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-databases"></a>BAM データベースの管理
管理者は、BAM 管理ユーティリティ (bm.exe) を使用して、BAM データベースを設定、管理、および更新できます。 このセクションでは、BAM 管理ユーティリティを使用して BAM データベースの一般的な管理者タスクを実行する方法について説明します。以下に示す表を参照してください。  
  
 バックアップして、BAM データベースの復元については、次を参照してください。[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)です。  
  
|データベース|既定のデータベース名|Description|  
|--------------|---------------------------|-----------------|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|BAM が未処理の追跡データを収集する場所。|  
|BAM Notification Services アプリケーション データベース|BAMAlertsApplication|BAM 通知に関する警告情報を格納します。 たとえば、BAM ポータルを使用して警告を作成すると、警告に関連する条件とイベントを指定するエントリに加え、警告に関するその他のサポート データ項目がデータベースに挿入されます。|  
|BAM Notification Services インスタンス データベース|BAMAlertsNSMain|BAM で監視しているシステムに Notification Services が接続する方法を指定するインスタンス情報を格納します。|  
|BAM スター スキーマ データベース|BAMStarSchema|段階テーブル、メジャー テーブル、およびディメンション テーブルを格納します。|  
|BAM 分析データベース|BAMAnalysis|オンライン分析用およびオフライン分析用の BAM OLAP キューブを格納します。|  
|BAM アーカイブ データベース|BAMArchive|古いビジネス アクティビティ データをアーカイブします。 BAM アーカイブ データベースを作成すると、BAM プライマリ インポート データベースにおけるビジネス アクティビティ データの蓄積を最小限に抑えることができます。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プライマリ インポート データベースのデータのアーカイブ](../core/archiving-primary-import-database-data.md)  
  
-   [アーカイブ データベースでパーティション分割されたビューを作成します。](../core/creating-a-partitioned-view-in-the-archiving-database.md)  
  
-   [スケジュール SQL Server Integration Services パッケージ](../core/scheduling-sql-server-integration-services-packages.md)  
  
-   [BAM 管理ユーティリティを使用して BAM データベースを設定する方法](../core/how-to-set-up-the-bam-databases-using-the-bam-management-utility.md)  
  
-   [BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法](../core/how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility.md)  
  
-   [BAM 管理ユーティリティを使用して BAM 構成を更新する方法](../core/how-to-update-the-bam-configuration-using-the-bam-management-utility.md)  
  
-   [追加の BAM プライマリ インポート データベースを参照する方法](../core/how-to-reference-additional-bam-primary-import-databases.md)  
  
-   [BAM プライマリ インポート データベース参照を無効にする方法](../core/how-to-disable-a-bam-primary-import-database-reference.md)  
  
-   [参照されるデータベースのすべての一覧を表示する方法](../core/how-to-list-all-referenced-databases.md)  
  
-   [不完全なアクティビティ インスタンスを削除する方法](../core/how-to-remove-incomplete-activity-instances.md)  
  
-   [バックアップと復元の後に BAM 管理ユーティリティ構成を更新する方法](../core/update-the-bam-management-utility-configuration-after-a-backup-and-restore.md)  
  
-   [BAM を SQL Server Reporting Services と統合する方法](../core/how-to-integrate-bam-with-sql-server-reporting-services.md)  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)