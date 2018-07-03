---
title: SQL Server エージェント ジョブとデータベースの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2a0b770ded2bef9ccf28a763f63f053c0b3c89e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024312"
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a>SQL Server エージェント ジョブとデータベースの監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 複数含まれて[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]動作状況と状態、サーバーを保持する重要な機能を実行するエージェント ジョブ。 これらのジョブの状態を監視し、エラーが発生せずに動作していることを確認する必要があります。 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックには、SQL データベースなどの項目を監視するための規則が含まれています。 と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。 構成する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]すべての包括的な監視用管理パック[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックには、2 つの最も重要な BizTalk の正常性を監視するための 2 つの無効化されたルールが含まれています。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。  
  
- 重大なエラー: BizTalk SQL Server エージェント ジョブに失敗しました - BizTalk Server のバックアップ  
  
- 重大なエラー: BizTalk SQL Server エージェント ジョブに失敗しました: メッセージのコピーを追跡  
  
  すべての BizTalk Server を監視する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]内からのエージェント ジョブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、これらの規則を有効にし、次のプロセスを使用して監視する他のジョブの追加ルールを作成する必要があります。  
  
- Operations Manager 管理者コンソールで、2 つの前述の規則のいずれかのコピーを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コア ルール グループ化、およびルールを適切に名前を変更します。  
  
- ルールの [条件] セクションで適切にパラメーター 1 のワイルドカード比較を変更します。  
  
- 場合によっては、ジョブ名はデータベース名、ユーザーを作成するなど、メッセージ ボックス データベースの名前に依存します。  
  
- ルールのターゲットとなるジョブにいずれかに関連付けられている 1 つのメッセージ ボックス データベースまたはすべてのメッセージ ボックス。  
  
## <a name="see-also"></a>参照  
 [SQL Server エージェントを開始する方法](../technical-guides/how-to-start-the-sql-server-agent.md)