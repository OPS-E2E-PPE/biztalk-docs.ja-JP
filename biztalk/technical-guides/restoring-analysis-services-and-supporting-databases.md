---
title: Analysis Services を復元して、データベースのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf50a7ef1903d3839aaa9b810e145432b62b552
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020463"
---
# <a name="restoring-analysis-services-and-supporting-databases"></a>Analysis Services を復元して、サポートするデータベース
2 つ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベースをディザスター リカバリーのシナリオで復元する必要があります。  
  
- BAM 分析 (BAMAnalysis)  
  
- 追跡 Analysis Server (BizTalkAnalysisdb)  
  
  BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースがバックアップ BizTalk Server のバックアップ ジョブの一環として BAM が有効になっているが、構成されていない場合。  
  
> [!NOTE]  
>  BAM プライマリ インポート データベースは、DTC トランザクションに含まれているためにも、常に、BizTalk Server のバックアップ ジョブの一部としてバックアップします。  
  
 BAM を有効になっているが、構成されていない場合は、次の BAM データベースを BizTalk Server のバックアップ ジョブの一部になります。  
  
- BAMStarSchema  
  
- BAMArchive  
  
  次の手順では、 [Backup BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)をこれらのデータベースを復元します。  
  
  **それ以外の場合、**  
  **BAM が有効にし、BM.exe を割り当てていることも、適切な BAM データベースのセットがセットとしてまとめて復元する必要があります。** アーカイブ済みのデータの完全なセットは、回復になっていることを確認するには、BAM アーカイブ データベースがバックアップに、BAM アーカイブ、パーティションをコピーした後が、パーティションを BAM プライマリ インポート データベースから削除する前にします。 これは、最後の手順「アーカイブ終了」です前に、BAM アーカイブ データベースをバックアップするステップを挿入することで各アクティビティのデータ保守 SSIS パッケージを変更することで実行します。  
  
  BAM データベースの復元手順は、: BAM プライマリ インポート データベースは x の前回のバックアップと復元された場合、に、データ保守 SSIS パッケージが最新の日付に対応する BAM アーカイブおよび BAM スター スキーマ データベースのコピーを復元x の日付より前に実行します。  
  
  適切な BAM データベースのセットを特定した後は、復元、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に記載されている標準的な手順を使用して Analysis Services データベース、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]復元のオンライン ブックの「[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース。  
  
## <a name="see-also"></a>参照  
 [BAM 分析および Tracking Analysis Server データベースのバックアップ](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)