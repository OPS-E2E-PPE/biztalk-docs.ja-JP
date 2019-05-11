---
title: BAM プライマリ インポート データベースへの参照の更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3da3b545-0d81-491b-bc37-0a980a7814b6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f01636801325980d3ac8ddd848c8a801e55327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400000"
---
# <a name="update-references-to-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースへの参照を更新します。
システムまたはデータに障害が発生した場合、BAM プライマリ インポート データベースをバックアップする場合は、別のコンピューターにそのバックアップを復元し、バックアップの名前を変更できます。  
  
 BAM イベント バス サービスでは、BAM プライマリ インポート データベースにメッセージ ボックス データベースからイベント データを移動します。 BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。 BAM イベント バス サービスの詳細については、トピックを参照してください。 [BAM イベント バス サービスの管理](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)します。  
  
 BAM プライマリ インポート データベースを復元する手順を実行[Backup BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)します。 さらに、新しいサーバー名とデータベース名を BAM SSIS パッケージを更新する必要があります。  
  
## <a name="how-to-update-references-to-bam-primary-import-database"></a>BAM プライマリ インポート データベースへの参照を更新する方法  
 手順については、BAM プライマリ インポート データベースへの参照を更新する方法の[新しい BAM プライマリ インポート データベースへの参照の更新](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)します。  
  
## <a name="see-also"></a>参照  
 [BAM 分析および Tracking Analysis Server データベースのバックアップ](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)