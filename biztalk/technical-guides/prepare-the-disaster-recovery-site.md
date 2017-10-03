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
ms.openlocfilehash: 2119de8d5f8625943374d262b063491d2dafa6d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-the-disaster-recovery-site"></a>障害復旧サイトを準備します。
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布では、サポートされている 2 つのシナリオがあります。 1 つは、ログ配布のすべての実稼働インスタンス上のすべてのデータベースの保存場所[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の 1 つの災害復旧のインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 その他のシナリオは、ログ配布されてのデータベースの実稼働インスタンスごとに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の対応するインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]災害復旧サイトにします。 同じ番号にする完全にサポートされることに注意してください[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実稼働環境ではより少ない物理サーバーがあるため、障害復旧サイト内のインスタンスをデータベースします。 このセクションでは、これらの準備についてを説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [障害復旧 SQL サーバーを準備します。](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [BAM 分析をバックアップして、追跡分析サーバー データベース](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [災害復旧の BizTalk サーバーを準備します。](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [アプリケーションの災害復旧の準備](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [マスター シークレット サーバーを復元する方法](../technical-guides/how-to-restore-the-master-secret-server.md)