---
title: ディザスター リカバリー サイトの準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b59adfbbb9ae8d995c3518eaa5c7491fa0179a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65252863"
---
# <a name="prepare-the-disaster-recovery-site"></a>ディザスター リカバリー サイトを準備します。
BizTalk Server ログ配布がサポートされている 2 つのシナリオ。 1 つは、ログのすべての実稼働インスタンス上のすべてのデータベースの配布[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の 1 つの災害復旧のインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 その他のシナリオは、配布の各実稼働インスタンス用のデータベースのログの保存場所[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の対応するインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ディザスター リカバリー サイトにします。 同じ番号にする完全にサポートされることに注意してください。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が運用環境で、より少ない物理サーバーでは、ディザスター リカバリー サイトのインスタンスをデータベース。 ここでは、これらの準備作業のガイダンスを示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ディザスター リカバリー SQL Server の準備](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [BAM 分析および Tracking Analysis Server データベースのバックアップ](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [ディザスター リカバリー BizTalk Server の準備](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [ディザスター リカバリーのためのアプリケーションの準備](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [マスター シークレット サーバーを復元する方法](../technical-guides/how-to-restore-the-master-secret-server.md)