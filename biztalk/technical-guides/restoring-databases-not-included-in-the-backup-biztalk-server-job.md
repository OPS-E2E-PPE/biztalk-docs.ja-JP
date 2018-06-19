---
title: バックアップの BizTalk Server のジョブに含まれていないデータベースの復元 |Microsoft ドキュメント
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
ms.openlocfilehash: 3277886207e04a30fec8bb61f29b5fe8c5ec3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302122"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a>バックアップの BizTalk Server のジョブに含まれていないデータベースの復元
このセクションでは、全体的な BizTalk ソリューションの一部であるが、BizTalk Server のバックアップ ジョブでバックアップされていないデータベースを復元する方法について説明します。 BizTalk ソリューションの一部であるすべてのデータベースは、次を除く BizTalk Server のバックアップ ジョブを使用してバックアップされます。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース  
  
-   BAM が有効になり、BM.exe を使用して構成されているときに、BAM データベース  
  
 また、このセクションでは、上に示したデータベースを復元した後のデータベース参照を更新する方法について説明し、不完全な BAM アクティビティ インスタンスの解決に関する情報が含まれます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Analysis Services を復元して、データベースのサポート](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [データベース参照の更新](../technical-guides/updating-database-references.md)  
  
-   [不完全な BAM アクティビティ インスタンスを解決する方法](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)