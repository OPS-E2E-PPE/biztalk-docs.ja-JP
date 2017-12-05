---
title: "障害復旧サイトを準備する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a60be6d04d0f73013f67c5fe8e5b0144357fd1f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="prepare-the-disaster-recovery-site"></a>障害復旧サイトを準備します。
BizTalk Server ログ配布がサポートされている 2 つのシナリオです。 1 つは、ログ配布のすべての実稼働インスタンス上のすべてのデータベースの保存場所[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の 1 つの災害復旧のインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 その他のシナリオは、ログ配布されてのデータベースの実稼働インスタンスごとに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の対応するインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]災害復旧サイトにします。 同じ番号にする完全にサポートされることに注意してください[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実稼働環境ではより少ない物理サーバーがあるため、障害復旧サイト内のインスタンスをデータベースします。 このセクションでは、これらの準備についてを説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ディザスター リカバリー SQL Server の準備](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [BAM 分析および Tracking Analysis Server データベースのバックアップ](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [ディザスター リカバリー BizTalk Server の準備](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [ディザスター リカバリーのためのアプリケーションの準備](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [マスター シークレット サーバーを復元する方法](../technical-guides/how-to-restore-the-master-secret-server.md)