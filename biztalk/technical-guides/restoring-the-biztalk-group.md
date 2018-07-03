---
title: BizTalk グループの復元 |Microsoft Docs
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
ms.openlocfilehash: b9bea20bacdd6b681d39e2bf3995d7626b9b1f63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021642"
---
# <a name="restoring-the-biztalk-group"></a>BizTalk グループの復元
BizTalk グループのセットによって表されます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース、SSIS パッケージ、および SQL エージェント ジョブ。 このセクションでは、BizTalk グループを復元するプロセスについて説明します。  
  
 送信先システム (ディザスター リカバリー サイト) への切り替えが必要なことは、次の手順を実行する必要があります。  
  
1. 復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と Analysis Services データベース。  
  
2. BizTalk Server ランタイム サーバーやアプリケーションを復元します。  
  
   障害復旧サイトで、次の手順を完了すると、BizTalk グループが確立された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーを構成することができ、アプリケーションは、BizTalk グループにデプロイできます。 このセクションのトピックでは、このプロセスの詳細について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ソース システムでのアプリケーション処理の停止](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [バックアップ BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [バックアップ BizTalk Server ジョブに含まれていないデータベースの復元](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)