---
title: "BizTalk グループを復元する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12a1deff8fea6d769f138aa34bf6dab269a167f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-the-biztalk-group"></a>BizTalk グループを復元します。
BizTalk グループのセットによって表されます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース、SSIS パッケージ、および SQL エージェント ジョブ。 このセクションでは、BizTalk グループを復元するプロセスについて説明します。  
  
 送信先システム (災害復旧サイト) への切り替えが必要なことは、次の手順を実行する必要があります。  
  
1.  復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と Analysis Services データベースです。  
  
2.  復元[!INCLUDE[prague](../includes/prague-md.md)]ランタイム サーバーおよびアプリケーションです。  
  
 障害復旧サイトでこれらの手順の完了時に、BizTalk グループが確立されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をランタイムにサーバーを構成して、アプリケーションは、BizTalk グループに展開できます。 このセクションのトピックでは、このプロセスの詳細について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ソース システムで処理するアプリケーションを停止しています](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [バックアップの BizTalk Server のジョブ内のデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [バックアップの BizTalk Server のジョブに含まれていないデータベースの復元](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)