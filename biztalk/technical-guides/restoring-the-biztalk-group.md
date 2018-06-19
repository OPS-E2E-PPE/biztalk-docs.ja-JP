---
title: BizTalk グループを復元する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e8d1741d89e8326cc68906644cf34e71bfcc8e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008115"
---
# <a name="restoring-the-biztalk-group"></a>BizTalk グループを復元します。
BizTalk グループのセットによって表されます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース、SSIS パッケージ、および SQL エージェント ジョブ。 このセクションでは、BizTalk グループを復元するプロセスについて説明します。  
  
 送信先システム (災害復旧サイト) への切り替えが必要なことは、次の手順を実行する必要があります。  
  
1.  復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と Analysis Services データベースです。  
  
2.  BizTalk Server ランタイム サーバーおよびアプリケーションを復元します。  
  
 障害復旧サイトでこれらの手順の完了時に、BizTalk グループが確立されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をランタイムにサーバーを構成して、アプリケーションは、BizTalk グループに展開できます。 このセクションのトピックでは、このプロセスの詳細について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ソース システムでのアプリケーション処理の停止](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [バックアップ BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [バックアップ BizTalk Server ジョブに含まれていないデータベースの復元](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)