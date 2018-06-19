---
title: BAM プライマリ インポート データベースへの参照の更新 |Microsoft ドキュメント
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
ms.openlocfilehash: 0ba37a32c82967e84b61bb46c58c62af9bf23b1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301826"
---
# <a name="update-references-to-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースへの参照を更新します。
BAM プライマリ インポート データベースがバックアップされていると、システムまたはデータに障害が発生したときには、別のコンピュータにバックアップを復元でき、さらにその名前を変更することができます。  
  
 BAM イベント バス サービスでは、イベント データをメッセージ ボックス データベースから BAM プライマリ インポート データベースに移動します。 BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。 BAM イベント バス サービスの詳細については、トピックを参照してください。 [BAM イベント バス サービスを管理する](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)。  
  
 BAM プライマリ インポート データベースを復元する」の手順を実行[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)です。 さらに、新しいサーバー名とデータベース名と BAM SSIS パッケージを更新する必要があります。  
  
## <a name="how-to-update-references-to-bam-primary-import-database"></a>BAM プライマリ インポート データベースへの参照を更新する方法  
 BAM プライマリ インポート データベースへの参照を更新する方法の詳細について[新しい BAM プライマリ インポート データベースへの参照の更新](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)です。  
  
## <a name="see-also"></a>参照  
 [BAM 分析をバックアップして、追跡分析サーバー データベース](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)