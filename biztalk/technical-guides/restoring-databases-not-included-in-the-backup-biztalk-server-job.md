---
title: バックアップ BizTalk Server のジョブに含まれていないデータベースの復元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7141980-d4a6-4409-be9b-c94a7f733376
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e4555b9a3f635d733d698109614c1ed673125f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291259"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a>バックアップ BizTalk Server のジョブに含まれていないデータベースの復元
このセクションでは、BizTalk Server のバックアップ ジョブによってバックアップされませんは全体的な BizTalk ソリューションの一部のデータベースを復元する方法について説明します。 BizTalk ソリューションの一部であるすべてのデータベースは、次を除く、BizTalk Server のバックアップ ジョブを使用してバックアップされます。  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services データベース  
  
- BAM が有効になっているが、BM.exe を使用して構成されている場合、BAM データベース  
  
  このセクションも上に挙げたデータベースの復元後のデータベース参照を更新する方法について説明し、不完全な BAM アクティビティ インスタンスの解決に関する情報が含まれます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Analysis Services とサポートするデータベースの復元](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [データベース参照の更新](../technical-guides/updating-database-references.md)  
  
-   [不完全な BAM アクティビティ インスタンスを解決する方法](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)