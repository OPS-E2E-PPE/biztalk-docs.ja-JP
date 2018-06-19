---
title: BAM Analysis Server およびスター スキーマ データベース名への参照の更新 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 319caa26-1292-4453-a316-efca4fbffdb6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184ab156770b0a62208a8e24c7870afa43d3a128
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302234"
---
# <a name="update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a>BAM Analysis Server およびスター スキーマ データベース名への参照の更新
BAM 分析データベースがバックアップされていれば、システムまたはデータに障害が発生したときには、別のコンピュータにバックアップを復元でき、さらにその名前を変更することができます。  
  
 BAM 分析データベースおよびスター スキーマ データベースを復元する」の手順を実行[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)です。 さらに、BAM を更新する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Integration Services (SSIS) パッケージを新しいサーバー名およびデータベース名。  
  
## <a name="how-to-update-references-to-bam-analysis-server-and-star-schema-database-names"></a>BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法  
 BAM Analysis server データベースへの参照を更新する方法の手順については、次を参照してください。[新しい BAM 分析データベースへの参照の更新](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)です。 BAM スター スキーマ データベースへの参照を更新する方法の手順については、次を参照してください。[新しい BAM スター スキーマ データベースへの参照の更新](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)です。