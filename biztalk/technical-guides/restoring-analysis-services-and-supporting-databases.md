---
title: "Analysis Services を復元して、サポートされるデータベース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da16bde7b69071b71b794c4c46407feab3ef4512
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-analysis-services-and-supporting-databases"></a>Analysis Services を復元して、データベースのサポート
2 つ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベースを障害復旧シナリオに復元する必要があります。  
  
-   BAM 分析 (BAMAnalysis)  
  
-   追跡 Analysis Server (BizTalkAnalysisdb)  
  
 BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースにバックアップされます、BizTalk Server のバックアップ ジョブの一環として BAM が有効になっているが、構成されていない場合。  
  
> [!NOTE]  
>  BAM プライマリ インポート データベースは、DTC トランザクションに含まれているためにも、常に、BizTalk Server のバックアップ ジョブの一部としてバックアップします。  
  
 BAM が有効になっているが、構成されていない場合は、次の BAM データベースを BizTalk Server のバックアップ ジョブの一部になります。  
  
-   BAMStarSchema  
  
-   BAMArchive  
  
 手順に従います[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)をこれらのデータベースを復元します。  
  
 **それ以外の場合**  
 **BAM が有効にし、BM.exe が装備されても、セットとして適切な BAM データベースのセットを一緒に復元する必要があります。** アーカイブ済みのデータの完全なセットを復元することを確認してください、BAM アーカイブ データベースがバックアップ パーティションを BAM アーカイブにコピーした後は、パーティションを BAM プライマリ インポート データベースから削除する前にします。 これは、最後の手順「アーカイブ終了」です前に、BAM アーカイブ データベースをバックアップするステップを挿入することで各アクティビティのデータ保守 SSIS パッケージを変更することで実行します。  
  
 BAM データベースの復元手順は、: BAM プライマリ インポート データベースは、x の前回のバックアップと復元は場合、は、データ保守 SSIS パッケージの時に最新の日付に対応する BAM アーカイブ、BAM スター スキーマ データベースのコピーを復元x の日の前に実行します。  
  
 適切な BAM データベースのセットを識別した後は、復元、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]で説明されているように、標準的な手順を使用して Analysis Services データベース、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]復元のオンライン ブック[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースおよび[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベースです。  
  
## <a name="see-also"></a>参照  
 [BAM 分析をバックアップして、追跡分析サーバー データベース](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)