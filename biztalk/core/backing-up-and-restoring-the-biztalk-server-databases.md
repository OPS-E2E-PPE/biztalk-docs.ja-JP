---
title: "バックアップと、BizTalk Server データベースを復元 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44bbb9316f1d036551acba5441424bcce65c2549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a>バックアップと、BizTalk Server データベースの復元
ここでは、BizTalk Server データベースをバックアップおよび復元する方法について説明します。 ハードウェア障害が発生したときに整合性のある BizTalk Server 環境を復元するためには、このセクションの手順に従う必要があります。 BizTalk Server では、いくつものデータベースに関わる分散トランザクションが実行されるため、すべてのデータベースのバックアップおよび復元が不可欠です。  
  
 BizTalk Server には、完全バックアップおよびログ バックアップをトランザクション ログ マーキングと共に使用する、カスタマイズされたバックアップ プロセスが必要です。 このプロセスについては、次を参照してください。[マークされたトランザクション、完全バックアップ、およびログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チェックリスト: をバックアップし、BizTalk Server データベースの復元](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [バックアップおよびデータベースを復元するためのベスト プラクティス](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)  
  
-   [データ損失の解決](../core/resolving-data-loss.md)  
  
-   [バックアップと復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)