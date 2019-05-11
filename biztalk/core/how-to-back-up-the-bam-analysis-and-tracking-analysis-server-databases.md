---
title: BAM 分析および Tracking Analysis Server データベースをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2fdd707375404f26f9310c6c2d38a6f2dfcb4ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387115"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>BAM 分析データベースおよび Tracking Analysis Server データベースをバックアップする方法
ビジネス アクティビティ監視 (BAM) 分析データベースおよび Tracking Analysis Server データベースは、SQL Server Analysis Services キューブにコンテンツを保存します。 BizTalk Server のバックアップ ジョブでは、これらのデータベースをバックアップしません。 代わりに、これらのデータベースをバックアップするには、SQL Server 分析マネージャを使用する必要があります。  
  
 これらのデータベースをバックアップした後、OLAP キューブを削除したい場合があります。 OLAP キューブを削除するときに、次の手順も実行する必要があります。  
  
1. 削除する前に、BAMStarSchema データベースで、OLAP キューブを削除するキューブのファクト テーブルを切り捨てます。 テーブルの名前付け規則は"bam _*\<CubeName\>*_Facts"です。  
  
2. OLAP キューブを削除した後では、アクティブ、完了、および仮想キューブを完全に処理する必要があります。  
  
   分析データベースをバックアップする方法の詳細については、「アーカイブ Analysis Services データベースの」SQL Server オンライン ブックを参照してください。  
  
   **BAM データベースのバックアップのスケジュール設定**  
  
   BAM を使用している場合は、バックアップ パッケージの実行がスケジュールされるときにも、BAM キューブ プロセスやデータ メンテナンス データ変換サービス (DTS) パッケージが実行されていることを確認します。  
  
   すべての BAM データベース間で一貫したスキーマを確実にデプロイしたり、BAM アクティビティを展開解除するたびを BAM データベースおよび DTS パッケージをバックアップします。  
  
   展開または BAM ビューを展開解除するたびに、BAM 分析データベースおよび BAMStarSchema データベースをバックアップします。  
  
   次の順序で BAM データベースをバックアップします。  
  
3. BAMPrimaryImport データベースおよび他の BizTalk Server データベースをバックアップする BizTalk Server のバックアップ ジョブを実行します。  
  
4. すべてのアクティビティを BAM データ保守 DTS パッケージを実行します。  
  
    DTS パッケージでは、次の手順を組み込むし、定期的に実行するパッケージのスケジュール設定します。 データの整合性を確保するには、いないことを確認の他の BAM キューブまたはデータ保守 DTS パッケージがこのバックアップ パッケージの実行がスケジュールされるときに実行します。  
  
    BAMArchive データベースが失敗した場合、BAMArchive データベースをバックアップするパーティションを BAMArchive データベースにコピーした後、BAMPrimaryImport データベースからパーティションを削除する前に、アーカイブされたデータの完全なセットを回復できるようにします。 これを行うには、変更、DTS パッケージの最後のステップの前に、BAMArchive データベースをバックアップするステップを挿入するには、各アクティビティのデータ管理 DTS パッケージ「アーカイブ終了」です。  
  
5. BAMAnalysis データベースおよび BAMStarSchema データベースをバックアップします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)